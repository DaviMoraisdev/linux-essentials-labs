# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** 5–7h/semana (~1h/dia útil)
**Início do conteúdo:** 01/09/2026 · **Data-alvo da prova:** **09 ou 10/11/2026**
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> Documento complementar: `claude/semana-00-setup-vm.md` — guia detalhado de instalação da VM, com troubleshooting.

---

## 1. Status atual

| Item | Situação |
|---|---|
| **Semana 0 — Laboratório** | ✅ **Concluída em 26/08/2026** |
| VM `lab-ubuntu` (Ubuntu Server 26.04.1 LTS) | ✅ instalada, atualizada, LVM estendido para 23 GB |
| Acesso SSH (`ssh lab`, porta 2222) | ✅ funcionando |
| Snapshot `limpo` | ✅ criado |
| Atalhos PowerShell (`lab-up`, `lab-down`, `lab-status`) | ✅ funcionando |
| Repositório `linux-essentials-labs` | ✅ público no GitHub, primeiro commit feito |
| `.wslconfig` limitando WSL2 a 3 GB | ⬜ pendente |
| Teste de restauração do snapshot | ⬜ pendente |
| Contas learning.lpi.org e OverTheWire | ⬜ pendente |
| Voucher da prova | ⬜ comprar na Semana 5 |

---

## 2. Quanto tempo é necessário

Partindo de uso básico de terminal, o Linux Essentials pede **45 a 60 horas de estudo efetivo**.
No ritmo de ~6h/semana, isso dá **9 a 10 semanas**.

| Cenário | Horas/semana | Semanas | Data da prova |
|---|---|---|---|
| Conservador (o adotado) | 6h | 10 | **09/11/2026** |
| Acelerado | 10h | 7 | ~20/10/2026 |
| Imersão | 15h+ | 5 | ~05/10/2026 |

**Há folga confortável para 2026.** Marcando para 09/11, sobram ~7 semanas no ano. A política da LPI exige apenas 7 dias de espera para refazer em caso de reprovação — ou seja, cabem duas tentativas dentro de 2026. Isso é o principal argumento para **não** comprimir o cronograma.

### Dados do exame

| Item | Valor |
|---|---|
| Código | 010-160, versão 1.6 |
| Questões / tempo | 40 questões em 60 minutos |
| Formato | Múltipla escolha e preenchimento (fill-in-the-blank) |
| Nota de corte | Referência comum: 500 de 800 (~65%) — confirmar no voucher |
| Idioma | **Português (Brasil) disponível**, em centro Pearson VUE e online (OnVUE) |
| Validade | **Vitalícia** |

> Recomendação: fazer em **centro Pearson VUE**, não OnVUE. O check-in remoto é rigoroso (mesa limpa, varredura de câmera, ninguém entrando na sala) e um problema técnico queima o voucher.

### Pesos dos tópicos

| Tópico | Peso | Semanas |
|---|---|---|
| 2. Finding Your Way on a Linux System | **9** | S1 + S2 |
| 3. The Power of the Command Line | **9** | S4 + S5 |
| 4. The Linux Operating System | **8** | S6 |
| 1. The Linux Community and a Career in Open Source | 7 | S7 |
| 5. Security and File Permissions | 7 | S3 |

Tópicos 2, 3 e 5 somam 25 dos 40 pontos e são **100% prática de terminal**. Tópico 1 é quase todo memorização.

---

## 3. O laboratório, como ficou montado

### Arquitetura

| Ambiente | Papel | Custo de RAM |
|---|---|---|
| **VM VirtualBox `lab-ubuntu`** — Ubuntu Server 26.04.1 LTS | Laboratório principal: boot real, systemd, LVM, `/dev`, `/proc`, rede, usuários, permissões, scripts | 2 GB (só ligada) |
| **Containers Docker** (no WSL2) | Comparar distros e gerenciadores de pacotes | ~30 MB cada |
| **WSL2 Ubuntu** | Caderno de labs, git e `gh` | limitar a 3 GB |

Uma VM só, e não duas — com 8 GB de RAM (i5-11300H), rodar Ubuntu + Debian simultaneamente não se paga. Para comparar distros, containers resolvem em segundos:

```bash
docker run -it --rm rockylinux/rockylinux:10 bash   # família RHEL: dnf, rpm
docker run -it --rm debian:13 bash                  # apt, dpkg
docker run -it --rm alpine sh                       # apk, sem bash
```

A segunda VM (**Rocky Linux** ou **AlmaLinux**) fica guardada para a preparação do RHCSA, onde ela realmente faz sentido — e será o laboratório gratuito no lugar dos cursos RH124/RH134.

### Especificação da VM

```
lab-ubuntu — Ubuntu Server 26.04.1 LTS "Resolute Raccoon"
2 vCPU · 2 GB RAM · disco 25 GB dinâmico
Rede: NAT + redirecionamento 2222 (host) → 22 (guest)
IP interno: 10.0.2.15 (interface enp0s3)
Usuário: davi · Hostname: lab-ubuntu
SSH: ativado por socket (ssh.socket)
Snapshot: limpo
Layout de disco: sda1 (1M BIOS boot) · sda2 (2G /boot) · sda3 → LVM ubuntu-vg/ubuntu-lv (23G, /)
```

---

## 4. Rotina de estudo — comandos para começar e terminar

### Abrir o laboratório

**Aba 1 — PowerShell (a VM):**

```powershell
lab-up          # liga a VM em modo headless, sem janela
                # espere ~25 segundos
lab-status      # confirma que está rodando
ssh lab         # entra na VM
```

**Aba 2 — WSL2 (o caderno):**

```bash
cd ~/linux-essentials-labs
git pull                        # se tiver editado de outra máquina
nano labs/semana-01.md          # ou: code .
```

### Fechar o laboratório

**Na aba do WSL2 — salvar o caderno:**

```bash
git add .
git commit -m "docs: semana 1 - navegação e ajuda"
git push
```

**Na aba da VM:**

```bash
sudo poweroff   # a conexão SSH cai sozinha, é esperado
```

Ou, do lado Windows: `lab-down` e depois `lab-status` para confirmar que nada ficou ligado.

### Comandos de emergência

```powershell
lab-status                                    # o que está ligado
VBoxManage list vms                           # todas as VMs
VBoxManage controlvm "lab-ubuntu" poweroff    # desligamento forçado (só se travar)
ssh -p 2222 davi@127.0.0.1                    # conectar sem depender do .ssh/config
```

Para snapshots, abrir o VirtualBox: selecionar `lab-ubuntu` → aba **Snapshots** → **Criar** / **Restaurar**.

### Configuração dos atalhos (referência, já aplicada)

`$PROFILE` do PowerShell:

```powershell
function lab-up     { VBoxManage startvm "lab-ubuntu" --type headless }
function lab-down   { VBoxManage controlvm "lab-ubuntu" acpipowerbutton }
function lab-status { VBoxManage list runningvms }
```

`%USERPROFILE%\.ssh\config`:

```
Host lab
    HostName 127.0.0.1
    Port 2222
    User davi
```

---

## 5. Cursos e recursos

### Trilha principal
**Matheus Muller — LPI Linux Essentials (Udemy, PT-BR)**, em 1.25x. É o fio condutor do conteúdo.

### Trilha de reforço
**Jason Dion — LPI Linux Essentials 010-160 (Udemy, EN)**. Não assistir do zero. Usar de duas formas:
1. Segunda passada nas **semanas 8–9**, em 1.5x, para revisão e terminologia em inglês.
2. **Os simulados dele**, guardados para as semanas 8–10.

> Fazer os dois cursos em série do início ao fim é o erro clássico: dobra o tempo sem dobrar o aprendizado.

### Recursos complementares

| Recurso | Para quê | Custo |
|---|---|---|
| **LPI Learning Materials** (learning.lpi.org) | Material oficial da LPI, escrito objetivo por objetivo, com tradução PT-BR | Grátis |
| **OverTheWire — Bandit** | Jogo de linha de comando via SSH. Níveis 0–20 treinam `find`, `grep`, `tar`, pipes e permissões — o coração dos tópicos 2, 3 e 5 | Grátis |
| **Anki** (deck próprio) | Retenção espaçada. Criar os cards é metade do estudo | Grátis |
| **explainshell.com** | Explica cada flag de um comando complexo | Grátis |
| **tldr / tealdeer** (`sudo apt install tealdeer`) | Exemplos práticos, complemento ao `man` | Grátis |
| **Livro "Certificação Linux Essentials"** (Uirá Endy Ribeiro) | Opcional, bom para o tópico 1 (licenças, distros, história) | ~R$40 |

**Evitar dumps** (marks4sure, validexamdumps e similares): violam o acordo da LPI, podem anular a certificação e dão falsa sensação de preparo.

---

## 6. Método de estudo

**Regra 40% vídeo / 60% teclado.** Ciclo por sessão de 1h:

1. **20–25 min de vídeo** — uma seção do Muller, sem pausar para copiar comandos.
2. **25–30 min de laboratório** — reproduzir tudo na VM, **digitando**, nunca copiando e colando. Errar, ler a mensagem de erro, consertar.
3. **5–10 min de registro** — anotar no caderno: o comando, o que faz, e o exemplo real executado.

**Regra do dia seguinte:** antes de cada sessão nova, refazer de memória 3 comandos da sessão anterior, sem consultar. Travou? Consulta e o comando vira card no Anki. Isso é *active recall* e vale mais que reassistir a aula.

**Quebrar coisas de propósito.** O snapshot `limpo` existe para isso. Rodar `chmod 000 /etc`, apagar `/bin`, errar um `rm -rf` — ver o sistema quebrar e entender por que ensina mais rápido que qualquer aula.

**Sessões de 50 minutos em dias úteis batem 3h no domingo.** Repetição espaçada é o que faz comando virar reflexo.

### Fluxo do caderno de labs

Um arquivo por semana em `labs/`, commitado ao fim de cada sessão. Três benefícios: força a escrever (fixa), vira a cola de revisão nas semanas 9–10, e é portfólio de infraestrutura.

---

## 7. Cronograma semana a semana

### ✅ Semana 0 — 25 a 31/08 · Laboratório — **CONCLUÍDA**
- [x] VirtualBox instalado (sem Extension Pack)
- [x] VM `lab-ubuntu` criada: 2 GB RAM, 2 vCPU, disco 25 GB dinâmico
- [x] Ubuntu Server 26.04.1 LTS instalado com OpenSSH server
- [x] Redirecionamento de porta 2222 → 22
- [x] `apt update && full-upgrade` executados
- [x] LVM estendido de 12 GB para 23 GB (`lvextend` + `resize2fs`)
- [x] Snapshot `limpo` criado
- [x] SSH funcionando pelo Windows Terminal (`ssh lab`)
- [x] Atalhos `lab-up` / `lab-down` / `lab-status` no `$PROFILE`
- [x] Repositório `linux-essentials-labs` público no GitHub
- [ ] `.wslconfig` limitando WSL2 a 3 GB
- [ ] Teste de restauração do snapshot
- [ ] Contas em learning.lpi.org e OverTheWire

---

### Semana 1 — 01 a 07/09 · Tópico 2, parte 1 (peso 9)
**Objetivos:** 2.1 Command Line Basics · 2.2 Using the Command Line to Get Help

**Laboratório:**
- Navegação: `pwd`, `cd` (incluindo `cd -`, `cd ~`, `cd ..`), `ls` com `-l -a -h -R -t`
- Caminho absoluto vs relativo — criar uma árvore de 4 níveis e navegar só com caminhos relativos
- Ajuda: `man`, `man -k`, `apropos`, `whatis`, `--help`, `info`, `type`, `which`
- Variáveis: `echo $PATH`, `$HOME`, `$USER`, `env`, `export`
- Histórico e atalhos: `history`, `!!`, `!42`, Ctrl+R, Ctrl+A/E/U/K, Tab completion
- Aspas simples vs duplas vs `\` — testar `echo "$HOME"` vs `echo '$HOME'`
- Paginador `less`: `q`, Espaço, `g`/`G`, `/busca`, `n`

**Prática extra:** Bandit 0–5
**Entregável:** `labs/semana-01.md`

---

### Semana 2 — 08 a 14/09 · Tópico 2, parte 2 (peso 9)
**Objetivos:** 2.3 Using Directories and Listing Files · 2.4 Creating, Moving and Deleting Files

**Laboratório:**
- `mkdir -p`, `rmdir`, `touch`, `cp -r`, `mv`, `rm -r` (e por que `rm -rf /` é fatal — testar num snapshot!)
- Expansão de chaves: `touch arquivo{01..50}.txt`, `mkdir -p projeto/{src,docs,tests}`
- Wildcards/globbing: `*`, `?`, `[abc]`, `[a-z]` — selecionar subconjuntos dos 50 arquivos
- Arquivos ocultos, `.` e `..`
- Links: `ln` (hard) vs `ln -s` (simbólico) — criar os dois, apagar o original, observar a diferença
- FHS: percorrer `/etc`, `/var`, `/usr`, `/home`, `/tmp`, `/opt`, `/bin`, `/dev`, `/proc` e escrever uma linha sobre cada

**Prática extra:** Bandit 6–10
**Entregável:** `labs/semana-02.md` + primeira leva no Anki (~40 comandos)

---

### Semana 3 — 15 a 21/09 · Tópico 5 (peso 7)
**Objetivos:** 5.1 Basic Security and Identifying User Types · 5.2 Creating Users and Groups · 5.3 Managing File Permissions and Ownership · 5.4 Special Directories and Files

**Laboratório:**
- `whoami`, `id`, `who`, `w`, `last`, `su`, `sudo`, `sudo -i`
- Ler `/etc/passwd`, `/etc/shadow`, `/etc/group` campo por campo (o UID 1000 que aparece em `/run/user/1000` é você)
- `useradd`, `usermod`, `userdel`, `passwd`, `groupadd`, `gpasswd` — criar 3 usuários e 2 grupos
- Permissões: `chmod` em **notação octal e simbólica**, `chown`, `chgrp`, `umask`
- Especiais: SUID, SGID, sticky bit — inspecionar `/usr/bin/passwd` (SUID) e `/tmp` (sticky) e explicar por quê
- Por que diretórios precisam de `x` (é permissão de *atravessar*, não de executar)

> Semana com mais questões de preenchimento. Se `rwxr-xr--` ↔ `754` não sair em 3 segundos, não avance.

**Prática extra:** Bandit 11–15
**Entregável:** `labs/semana-03.md` + `cheatsheets/permissoes.md`

---

### Semana 4 — 22 a 28/09 · Tópico 3, parte 1 (peso 9)
**Objetivos:** 3.1 Archiving Files on the Command Line · 3.2 Searching and Extracting Data from Files

**Laboratório:**
- Compactação: `tar -cvf`, `-xvf`, `-czvf`, `-tzvf`, `gzip`/`gunzip`, `bzip2`, `xz`, `zip`/`unzip`
- Visualização: `cat`, `less`, `more`, `head -n`, `tail -n`, `tail -f`
- Redirecionamento: `>`, `>>`, `<`, `2>`, `&>`, `/dev/null`, pipes `|`, `tee`
- Heredoc: `cat > arquivo << 'EOF'`
- Filtros: `grep` (`-i -v -r -c -n -E`), `cut -d -f`, `sort -n -r -u`, `uniq -c`, `wc -l`, `tr`, `sed 's/a/b/g'`
- `find` com `-name`, `-type`, `-size`, `-mtime`, `-exec`
- **Desafio integrador:** a partir de `/etc/passwd`, listar os 5 shells mais usados em ordem de frequência, num único pipeline

**Prática extra:** Bandit 16–20 (SSH e permissões avançadas)
**Entregável:** `labs/semana-04.md`

---

### Semana 5 — 29/09 a 05/10 · Tópico 3, parte 2 (peso 9)
**Objetivo:** 3.3 Turning Commands into a Script — peso 4, o objetivo individual mais pesado da prova

**Laboratório:**
- Shebang `#!/bin/bash`, `chmod +x`, `./script.sh` vs `bash script.sh`
- Variáveis, `$1 $2 $@ $#`, `read`, aspas
- `if/elif/else`, `test` / `[ ]`, comparadores `-eq -ne -lt -gt -f -d -z`
- Loops `for`, `while`, `seq`
- Exit codes: `$?`, `exit 0`, encadeamento `&&` e `||`
- **4 scripts em `scripts/`:** (1) backup de uma pasta com data no nome; (2) contar arquivos por extensão num diretório; (3) verificar se um usuário existe; (4) ler um arquivo linha a linha e filtrar

**🎯 AÇÃO DA SEMANA: agendar a prova para 09 ou 10/11.**
Marcar antes de se sentir pronto é intencional — prazo firme é o que impede o plano de escorregar para dezembro. Nesta altura os dois tópicos de maior peso já foram cobertos.

**Entregável:** `labs/semana-05.md` + 4 scripts + **voucher comprado**

---

### Semana 6 — 06 a 12/10 · Tópico 4 (peso 8)
**Objetivos:** 4.1 Choosing an Operating System · 4.2 Understanding Computer Hardware · 4.3 Where Data is Stored · 4.4 Your Computer on the Network

**Laboratório:**
- Hardware: `lscpu`, `lsblk`, `lspci`, `lsusb`, `free -h`, `df -h`, `du -sh`, `dmesg`
- `/dev`, `/proc`, `/sys` — ler `/proc/cpuinfo` e `/proc/meminfo`
- Revisitar o `lsblk` da sua VM: `sda1` (BIOS boot), `sda2` (`/boot`), `sda3` → LVM. Explicar por que `/boot` fica fora do LVM
- `tmpfs`: por que `/run` e `/dev/shm` vivem em RAM e evaporam no boot
- Processos: `ps aux`, `ps -ef`, `top`, `htop`, `kill`, `killall`, `jobs`, `bg`, `fg`, `&`, `nice`
- Rede: `ip addr`, `ip route`, `ping`, `ss -tuln`, `traceroute`, `dig`/`host`, `/etc/hosts`, `/etc/resolv.conf`
- Revisitar a rede da VM: por que o IP é `10.0.2.15`, o que o NAT faz, como o redirecionamento 2222→22 funciona
- Conceitos: IPv4 vs IPv6, DNS, DHCP, portas comuns (22, 80, 443, 25, 53), máscara de sub-rede
- Distros e ciclos de vida: Debian/Ubuntu/RHEL/Fedora/SUSE/Arch — LTS vs rolling release
- Gerenciadores de pacotes: `apt`/`dpkg` na VM **e** `dnf`/`rpm` no container Rocky, lado a lado

**Entregável:** `labs/semana-06.md`

---

### Semana 7 — 13 a 19/10 · Tópico 1 (peso 7)
**Objetivos:** 1.1 Linux Evolution and Popular Operating Systems · 1.2 Major Open Source Applications · 1.3 Open Source Software and Licensing · 1.4 ICT Skills and Working in Linux

Semana conceitual — **é onde o Anki ganha a prova**, porque é memorização pura.

- História: Unix → GNU → kernel Linux (Torvalds, 1991) → distribuições
- Onde Linux roda: servidores, cloud, embarcados, Android, supercomputadores
- Aplicações por categoria: web (Apache, nginx), bancos (MySQL/MariaDB, PostgreSQL), compartilhamento (Samba, NFS), e-mail (Postfix, Dovecot), desktop (LibreOffice, GIMP, Firefox, Thunderbird)
- Shells e linguagens: Bash, Python, Perl, PHP, C, JavaScript, Shell script
- **Licenças (cai bastante):** GPL v2/v3 (copyleft), LGPL, BSD, MIT, Apache — permissiva vs copyleft; Creative Commons; FSF vs OSI; "free as in freedom, not free as in beer"
- Ambientes desktop: GNOME, KDE Plasma, Xfce; X11 vs Wayland
- Privacidade e boas práticas: senhas, criptografia, backup

**Meta:** ~60 cards no Anki, revisão de 10 min/dia até a prova.
**Entregável:** `labs/semana-07.md` + deck completo

---

### Semana 8 — 20 a 26/10 · Segunda passada + diagnóstico
- **Jason Dion completo em 1.5x** (~4h) — terminologia em inglês e caça a lacunas
- **Primeiro simulado completo**, 40 questões cronometradas, 60 min, sem consultar
- Registrar a nota e **listar todos os erros por objetivo** (ex.: "3 erros em 5.3")
- Revisitar na VM apenas os objetivos onde errou. Não revisar o que já acerta

**Meta:** ≥ 70% no primeiro simulado (normal e esperado)

---

### Semana 9 — 27/10 a 02/11 · Simulados e fechamento de lacunas
- **3 simulados completos**, um a cada 2 dias, sempre cronometrados
- Após cada um: revisão dirigida só nos objetivos com erro
- **Lab integrador final** (2h, do zero, sem consultar):
  1. Criar dois usuários e um grupo compartilhado
  2. Criar `/dados/projeto` com permissões de grupo corretas e SGID
  3. Escrever um script de backup em `.tar.gz` com data no nome
  4. Agendar o script com `cron` (bônus além do exame)
  5. Gerar um relatório com `find` + `grep` + `sort` dos arquivos maiores que 1 MB
- Revisar o LPI Learning Materials nos objetivos mais fracos

**Meta: ≥ 85% consistente em dois simulados seguidos.** Este é o gate. Se não atingir, adiar a prova em 1 semana — há folga.

---

### Semana 10 — 03 a 09/11 · Revisão final e prova
- Seg–Qua: revisão **leve** — só a cola do GitHub + Anki, 40 min/dia. Sem conteúdo novo
- Qui: 1 simulado final. Se ≥ 85%, está pronto
- Sex/Sáb: **descanso**. Não estudar na véspera
- **Prova: 09 ou 10/11.** Chegar 30 min antes, levar dois documentos com foto
- Na prova: 40 questões / 60 min = 1,5 min por questão. Marcar as difíceis e voltar. Nas de preenchimento, escrever **só o comando**, sem caminho e sem flags, salvo se pedido

---

## 8. Aprendizados da Semana 0

Registro do que foi descoberto na prática, para não repetir.

### Conceitos que já valeram como estudo

| Conceito | Objetivo da prova | Onde apareceu |
|---|---|---|
| `$PATH` e por que `.\programa` só funciona na pasta certa | 2.1 | `VBoxManage` não reconhecido fora da pasta do VirtualBox |
| Paginador `less` e a tecla `q` | 3.2 | `apt list --upgradable` "travando" no `(END)` |
| Redirecionamento `>` e heredoc `<< 'EOF'` | 3.2 / 3.3 | Criação do README |
| `&&` — o segundo comando só roda se o primeiro der certo | 3.3 | `apt update && apr upgrade` (o typo revelou o mecanismo) |
| Partições, LVM e `/boot` fora do LVM | 4.3 | `lsblk` da própria VM |
| `tmpfs` — arquivos que vivem em RAM | 4.3 | `df -h` mostrando `/run` e `/dev/shm` |
| NAT, portas, DHCP e IP privado | 4.4 | Redirecionamento 2222 → 22 |
| Fingerprint de host SSH e `known_hosts` | 5.1 | Primeira conexão `ssh lab` |
| `mv` também renomeia | 2.4 | Correção de `cheatseets` → `cheatsheets` |
| Repositórios e gerenciamento de pacotes | 1.2 | `resolute`, `-security`, `-updates`, `-backports` |

### Armadilhas encontradas (e como resolver)

| Problema | Causa | Solução |
|---|---|---|
| `invalid option -- '1'` | `-1` (número) digitado no lugar de `-l` (letra L) | Fontes de terminal confundem `l`/`1` e `O`/`0`. Preferir a forma longa: `--extents`, `--lines` |
| `Command 'apr' not found` | Typo em `apt` | Ler a mensagem de erro antes de reescrever o comando |
| `Package 'tldr' has no installation candidate` | Pacote descontinuado no Ubuntu 26.04 | Usar `tealdeer`. Um pacote inexistente aborta o `apt install` inteiro |
| `systemctl is-active ssh` → `inactive`, mas SSH funciona | Ativação por socket (Ubuntu 24.04+) | Consultar `ssh.socket`, não `ssh.service`. Confirmar com `ss -tlnp \| grep :22` |
| 4 pacotes eternamente "upgradable" | *Phased updates* da Canonical | Normal. Entram sozinhos em alguns dias |
| `Invalid operation cache` | `apt cache` (espaço) em vez de `apt-cache` (hífen) | São programas diferentes |
| `lab-up` não reconhecido | `$PROFILE` existia mas estava vazio (Bloco de Notas não salvou) | Escrever com `Set-Content` pelo próprio PowerShell. **Sempre ler o arquivo de volta para conferir** |
| `Could not resolve hostname lab` | `.ssh/config` não criado | Mesma causa e mesma solução. Usar `-Encoding ascii` (o padrão insere BOM que o OpenSSH não entende) |
| `nothing to commit` | A pasta só tinha diretórios vazios | **O git rastreia arquivos, não pastas.** Pasta vazia é invisível para ele |
| Ícone de tartaruga verde na VM | VirtualBox rodando sobre o Hyper-V por causa do WSL2 | Normal e esperado. Não atrapalha labs de terminal |
| `tree` não encontrado no WSL2 | VM e WSL2 são dois Linux **separados** | Instalar em cada um. Sem instalar, `ls -R` é o plano B |

### Regras de bolso que saíram daqui

1. **Leia a mensagem de erro inteira antes de reescrever o comando.** O Linux quase sempre diz o que ele entendeu.
2. **Quando um arquivo de configuração "não pega", leia o arquivo de volta** (`cat` / `Get-Content`) antes de procurar causas complicadas. Metade dos casos é o arquivo estar vazio ou no lugar errado.
3. **Um comando por vez, verificando a saída**, sempre que estiver aprendendo algo novo. Rodar cinco de uma vez esconde onde quebrou.
4. **Prefira a forma longa das opções** em anotações e scripts. `--extents` é autoexplicativo; `-l` não.

---

## 9. Como acelerar sem perder a confiança

Para antecipar a prova para meados de outubro, em ordem de impacto:

1. **Corte o que já sabe.** Fazer um simulado diagnóstico na **semana 1**, não na 8. Se já acerta 60% do Tópico 1, essa semana vira 2h de Anki.
2. **Não assistir o Dion do zero.** Economiza ~5h sozinho.
3. **Subir para 10h/semana só nas semanas 4–5** (Tópico 3, peso 9 e o objetivo mais pesado). Investir onde o peso é maior comprime mais que aumentar tudo uniformemente.
4. **Bandit todo dia, 20 min.** Única atividade que substitui vídeo por competência real. Chegar ao nível 20 vale mais que 10h de aula.
5. **Vídeo em 1.5x com legenda.** ~30% do tempo de vídeo, sem perda de compreensão, se estiver reproduzindo tudo na VM.

**O que NÃO fazer:** pular os labs, usar dumps, ou marcar a prova para setembro. Há tempo de sobra em 2026 — a única forma de perder o ano é reprovar por pressa e desanimar.

---

## 10. Depois da aprovação

- **GitHub Foundations logo na sequência** (novembro/dezembro). É bem mais leve, você já usa Git e `gh` no dia a dia, e fecha 2026 com duas certificações.
- **O Linux Essentials é a base do RHCSA.** Manter a VM e o repositório de labs. Para o EX200, criar a segunda VM (Rocky Linux ou AlmaLinux) e considerar a trilha do RHEL Developer Subscription + laboratórios próprios como alternativa gratuita ao RH124/RH134.

---

## Fontes

- [LPI — Linux Essentials Overview](https://www.lpi.org/our-certifications/linux-essentials-overview/)
- [LPI — Objetivos do exame 010](https://www.lpi.org/our-certifications/exam-010-objectives/)
- [LPI Learning Materials](https://learning.lpi.org/)
- [OverTheWire — Bandit](https://overthewire.org/wargames/bandit/)
- [Pearson VUE — LPI](https://home.pearsonvue.com/Clients/LPI.aspx)
- [Ubuntu — Download Server](https://ubuntu.com/download/server)
- [Canonical — Ubuntu 26.04 LTS "Resolute Raccoon"](https://canonical.com/blog/canonical-releases-ubuntu-26-04-lts-resolute-raccoon)
- [Udemy — Matheus Muller, LPI Linux Essentials](https://www.udemy.com/course/lpi-linux-essentials/)
- [Dion Training — Linux Essentials 010-160](https://www.diontraining.com/products/lpi-linux-essentials-c-usd)
- [Repositório de labs — DaviMoraisdev/linux-essentials-labs](https://github.com/DaviMoraisdev/linux-essentials-labs)