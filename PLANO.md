# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** 5–7h/semana
**Data da prova:** **09/11/2026, segunda-feira**
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> **Estratégia revisada em 26/09.** O cronograma passa a ter **duas fases**: três semanas com o curso como atividade principal e duas práticas por semana, seguidas de três semanas de prática intensiva e simulados. Detalhamento na seção 7.

---

## 1. Status atual

### Concluído

| Item | Situação |
|---|---|
| **Semana 0 — Laboratório** | ✅ 26/08 — VM, SSH, snapshot, repositório |
| **Semana 1 — Tópico 1 (peso 7)** | ✅ 05/09 — comunidade, licenças, distros, FHS |
| **Semana 2 — Tópico 2 p1** | ✅ 13/09 — objetivos 2.1 e 2.2 |
| **Semana 3 — Tópico 2 p2** | ✅ 19/09 — objetivos 2.3 e 2.4 |
| **Semana 4 — Tópico 3 p1** | 🔄 fecha em 27/09 — objetivos 3.1 e 3.2 |
| **Tópico 1 (peso 7)** | ✅ completo |
| **Tópico 2 (peso 9)** | ✅ completo — os quatro objetivos |
| **Tópico 3 (peso 9)** | 🔄 3.1 e 3.2 feitos; falta 3.3 |
| Autoavaliação da Semana 2 | ✅ 14 de 15 |
| Autoavaliação da Semana 3 | ✅ 20 de 20 |
| Bandit | ✅ níveis 0 a 9 |
| Cards de revisão (Notion) | ✅ em uso desde a Semana 1 |
| Curso do Muller | 🔄 **aula 26 de 72** (23/09) — 46 restantes |

### Pendente

| Item | Prazo |
|---|---|
| **Simulado diagnóstico** — 40 questões, cronometrado | **Semana 5** — 4 semanas em atraso |
| Voucher da prova | Semana 5 |
| Sessão 5 da Semana 4 — `find` e desafio integrador | 27/09 |
| Instalar `bzip2` e refazer a comparação de compressão | Semana 5 |
| `.wslconfig` limitando WSL2 a 3 GB | quando houver folga |
| Teste de restauração do snapshot | quando houver folga |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | 27/09 |

### Cobertura estimada por tópico

| Tópico | Peso | Cobertura |
|---|---|---|
| 1. Comunidade e open source | 7 | 100% |
| 2. Encontrando seu caminho | 9 | 100% |
| 3. Poder da linha de comando | 9 | 55% — falta o 3.3 |
| 4. Sistema operacional | 8 | 30% |
| 5. Segurança e permissões | 7 | 0% |

**Progresso geral: aproximadamente 65% do conteúdo da prova.**

---

## 2. Dados do exame

| Item | Valor |
|---|---|
| Código | 010-160, versão 1.6 |
| Questões / tempo | 40 questões em 60 minutos |
| Formato | Múltipla escolha e preenchimento |
| Nota de corte | Referência comum: 500 de 800 (~65%) |
| Idioma | Português (Brasil) disponível |
| Validade | Vitalícia |
| Entrega | Centro Pearson VUE ou OnVUE |

> Recomendação: **centro Pearson VUE**, não OnVUE. O check-in remoto é rigoroso e um problema técnico queima o voucher.

### Pesos dos tópicos

| Tópico | Peso | Onde é tratado |
|---|---|---|
| 2. Finding Your Way on a Linux System | **9** | ✅ Semanas 2 e 3 |
| 3. The Power of the Command Line | **9** | Semana 4 (3.1, 3.2) + Semana 5 (3.3) |
| 4. The Linux Operating System | **8** | Semana 7 |
| 1. The Linux Community and a Career in Open Source | 7 | ✅ Semana 1 |
| 5. Security and File Permissions | 7 | Semana 6 |

---

## 3. O laboratório

| Ambiente | Papel |
|---|---|
| **VM VirtualBox `lab-ubuntu`** — Ubuntu Server 26.04.1 LTS | Laboratório principal |
| **Containers Docker** (no WSL2) | Comparar distros e gerenciadores de pacotes |
| **WSL2 Ubuntu** | Caderno de labs, git e `gh` |

```
lab-ubuntu — Ubuntu Server 26.04.1 LTS "Resolute Raccoon"
2 vCPU · 2 GB RAM · disco 25 GB dinâmico
Rede: NAT + redirecionamento 2222 (host) → 22 (guest)
IP interno: 10.0.2.15 (interface enp0s3)
Usuário: davi · Hostname: lab-ubuntu
SSH: ativado por socket (ssh.socket)
Snapshot: limpo
Disco: sda1 (1M BIOS boot) · sda2 (2G /boot) · sda3 → LVM ubuntu-vg/ubuntu-lv (23G, /)
```

Containers para comparação entre famílias:

```bash
docker run -it --rm rockylinux/rockylinux:10 bash   # RHEL: dnf, rpm
docker run -it --rm debian:13 bash                  # apt, dpkg
docker run -it --rm alpine sh                       # apk, sem bash
```

---

## 4. Rotina de estudo

### Abrir o laboratório

```powershell
lab-up          # liga a VM em modo headless
                # espere ~25 segundos
lab-status      # confirma que está rodando
ssh lab         # entra na VM
```

```bash
cd ~/linux-essentials-labs
code .
```

### Fechar

```bash
git add . && git commit -m "docs: semana N - sessao X" && git push
sudo poweroff
```

### Comandos de emergência

```powershell
lab-status
VBoxManage list vms
VBoxManage controlvm "lab-ubuntu" poweroff    # só se travar
ssh -p 2222 davi@127.0.0.1                    # sem depender do .ssh/config
```

Snapshots são feitos pela interface do VirtualBox: selecionar `lab-ubuntu` → aba **Snapshots** → **Criar** / **Restaurar**.

### Configuração já aplicada

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
**Matheus Muller — LPI Linux Essentials (Udemy, PT-BR)**. Passa a ser a atividade principal na Fase 1.

**Velocidade recomendada por trecho:**

| Conteúdo | Velocidade | Motivo |
|---|---|---|
| Tópicos 1, 2, 3.1 e 3.2 | **1.5x** | Já praticados, com autoavaliação de 20/20. O vídeo confirma, não ensina |
| Objetivo **3.3 — shell script** | **1x** | Peso 4, o maior individual da prova. O vídeo entrega o modelo mental |
| Tópicos 4 e 5 | **1.25x** | Conteúdo novo, mas com laboratório logo em seguida |

### Trilha de reforço
**Jason Dion — LPI Linux Essentials 010-160 (Udemy, EN)**. Usar apenas na Fase 2:
1. Os **simulados**, que são o principal valor do curso.
2. Uma passada rápida em 1.5x para terminologia em inglês, se sobrar tempo.

### Recursos complementares

| Recurso | Para quê |
|---|---|
| **LPI Learning Materials** (learning.lpi.org) | Material oficial, escrito objetivo por objetivo, com tradução PT-BR |
| **OverTheWire — Bandit** | Níveis 0 a 9 concluídos; 10 a 20 são bônus, não obrigatórios |
| **Notion** (cards próprios) | Retenção espaçada |
| **explainshell.com** | Explica cada flag de um comando complexo |
| **tldr / tealdeer** | Exemplos práticos, complemento ao `man` |

**Evitar dumps** (marks4sure, validexamdumps e similares): violam o acordo da LPI, podem anular a certificação e dão falsa sensação de preparo.

---

## 6. Método de estudo — ajustado para a Fase 1

O ritmo anterior era de cinco sessões semanais de laboratório. A partir da Semana 5 passa a ser **duas sessões de laboratório e o curso como atividade principal**.

### O que muda

| | Antes (S1–S4) | Fase 1 (S5–S7) |
|---|---|---|
| Sessões de laboratório | 5 por semana | **2 por semana** |
| Curso | Complementar | **Atividade principal** |
| Aquecimento diário | Não existia | **10 min, todo dia** |

### O aquecimento diário — a peça que substitui a frequência perdida

Comando vira reflexo por **repetição espaçada**, não por tempo acumulado. Duas sessões de uma hora ensinam menos motricidade que cinco de vinte minutos, ainda que somem o mesmo.

Para não perder isso ao reduzir as sessões, entra um ritual curto de **10 minutos por dia**:

1. Abrir a VM
2. Refazer **cinco comandos de memória**, sem consultar nada
3. O que travar vira card no Notion na hora

Cinco comandos. Dez minutos. É o que mantém o espaçamento funcionando com duas sessões formais por semana.

### As sessões de laboratório

Sem vídeo dentro delas — o vídeo agora tem espaço próprio. A sessão inteira é teclado:

1. **45 min de laboratório** — reproduzir tudo na VM, **digitando**, nunca copiando e colando
2. **10 min de registro** — anotar no caderno o comando, o que faz e o exemplo executado
3. **5 min** — commit no repositório

**Quebrar coisas de propósito** continua valendo. O snapshot `limpo` existe para isso.

---

## 7. Cronograma revisado

Semanas de **segunda a domingo**. A prova cai na segunda-feira seguinte ao fim da Semana 10.

### Visão geral

| Fase | Semanas | Período | Foco |
|---|---|---|---|
| **Fase 1 — Curso** | 5, 6, 7 | 28/09 a 18/10 | Fechar as 46 aulas restantes · 2 práticas/semana |
| **Fase 2 — Prática e simulados** | 8, 9, 10 | 19/10 a 08/11 | Simulados em condição de prova · laboratórios integradores |
| **Prova** | — | **09/11** | — |

### A conta

| Item | Número |
|---|---|
| Aulas restantes do curso | 46 (da 26 à 72) |
| Semanas na Fase 1 | 3 |
| Aulas por semana | ~15 |
| Tempo estimado de vídeo, em 1.25–1.5x | **1h30 a 2h por semana** |
| Duas sessões de laboratório | 2h |
| Aquecimento diário | 1h10 na semana |
| **Total semanal** | **~5h** — dentro do orçamento de 5 a 7h |

A Fase 1 termina em **18/10**, com o curso fechado e todos os cinco tópicos ao menos estudados. Sobram **três semanas inteiras** para simulados — uma a mais do que o plano original previa.

---

### Semana 5 — 28/09 a 04/10 · Objetivo 3.3, shell script

**Curso:** aulas 26 a 41, aproximadamente. Reduzir para **1x** ao chegar no shell script.

**Prática 1 — Shell script**

- Shebang `#!/bin/bash`, `chmod +x`, `./script.sh` versus `bash script.sh`
- Variáveis, `$1 $2 $@ $#`, `read`, aspas
- `if/elif/else`, `test` e `[ ]`, comparadores `-eq -ne -lt -gt -f -d -z`
- Loops `for` e `while`, `seq`
- Códigos de saída: `$?`, `exit 0`, encadeamento `&&` e `||`
- **Escrever 4 scripts em `scripts/`:** backup com data no nome; contar arquivos por extensão; verificar se um usuário existe; ler um arquivo linha a linha e filtrar

> Este é o objetivo de **peso 4** — o maior individual do exame. Você já programa, então a sintaxe vem rápido; o que exige atenção é a diferença entre o modelo mental do shell e o de uma linguagem estruturada.

**Prática 2 — Simulado diagnóstico**

40 questões, 60 minutos, cronometrado, sem consultar nada. Use os simulados do Jason Dion.

Esta é a pendência mais antiga do plano, com quatro semanas de atraso. Ela ocupa o lugar de uma prática porque **é** prática — e porque o resultado determina no que as práticas das Semanas 6 e 7 devem insistir.

**Expectativa:** entre 60% e 75%. Você cobriu ~65% do conteúdo e o Tópico 5 está zerado.

| Tópico | Peso | Acertos | Erros |
|---|---|---|---|
| 1. Comunidade e open source | 7 | | |
| 2. Encontrando seu caminho | 9 | | |
| 3. Poder da linha de comando | 9 | | |
| 4. Sistema operacional | 8 | | |
| 5. Segurança e permissões | 7 | | |

**Como ler o resultado:**

- Erros concentrados em 4 e 5, ainda não estudados — o plano está funcionando.
- Erros em 1, 2 ou 3, que estão fechados — a base pede revisão, e as práticas das semanas seguintes precisam incluí-la.

**🎯 Ação da semana: comprar o voucher e agendar a prova para 09/11.**

Marcar antes de se sentir pronto é intencional. Prazo firme é o que impede o plano de escorregar para dezembro.

**Entregável:** `labs/semana-05.md` + 4 scripts + voucher comprado + resultado do simulado

---

### Semana 6 — 05 a 11/10 · Tópico 5, permissões (peso 7)

**Curso:** aulas 42 a 57, aproximadamente.

**Prática 1 — Usuários e grupos**

- `whoami`, `id`, `who`, `w`, `last`, `su`, `sudo`, `sudo -i`
- Ler `/etc/passwd`, `/etc/shadow`, `/etc/group` campo por campo
- `useradd`, `usermod`, `userdel`, `passwd`, `groupadd`, `gpasswd`
- Criar três usuários e dois grupos, e colocar usuários em grupos

**Prática 2 — Permissões**

- `chmod` em **notação octal e simbólica**, `chown`, `chgrp`, `umask`
- SUID, SGID e sticky bit — inspecionar `/usr/bin/passwd` e `/tmp`
- Por que diretórios precisam de `x` (é permissão de **atravessar**, não de executar)

> **Esta é a semana de maior risco do novo formato.** Permissão é o conteúdo mais dependente de repetição do exame: converter `rwxr-xr--` em `754` precisa ser reflexo, e reflexo não se constrói em duas sessões.
>
> Por isso o **aquecimento diário desta semana é obrigatório** e sempre o mesmo: cinco conversões de permissão, de memória, sem consultar. Se ao fim da semana a conversão não sair em três segundos, a Semana 7 começa com mais uma sessão de permissões antes do Tópico 4.

**Entregável:** `labs/semana-06.md` + `cheatsheets/permissoes.md`

---

### Semana 7 — 12 a 18/10 · Tópico 4, sistema operacional (peso 8)

**Curso:** aulas 58 a 72 — **fechamento do curso**.

**Prática 1 — Hardware, armazenamento e processos**

- `lscpu`, `lsblk`, `lspci`, `lsusb`, `free -h`, `df -h`, `du -sh`, `dmesg`
- `/dev`, `/proc`, `/sys` — ler `/proc/cpuinfo` e `/proc/meminfo`
- Revisitar o `lsblk` da VM e explicar por que `/boot` fica fora do LVM
- `tmpfs`: por que `/run` e `/dev/shm` vivem em RAM
- Processos: `ps aux`, `ps -ef`, `top`, `htop`, `kill`, `killall`, `jobs`, `bg`, `fg`, `&`, `nice`

**Prática 2 — Rede e distribuições**

- `ip addr`, `ip route`, `ping`, `ss -tuln`, `traceroute`, `dig`/`host`
- `/etc/hosts`, `/etc/resolv.conf`
- Revisitar a rede da VM: por que o IP é `10.0.2.15`, o que o NAT faz, como o redirecionamento 2222→22 funciona
- IPv4 versus IPv6, DNS, DHCP, portas comuns, máscara de sub-rede
- Distros e ciclos de vida: LTS versus rolling release
- `apt`/`dpkg` na VM e `dnf`/`rpm` no container Rocky, lado a lado

> Boa parte deste tópico já foi encostada na prática: LVM e partições na Semana 0, `/proc` e `/dev` na Semana 3, portas e serviços na Semana 1, gerenciadores de pacotes no curso. A cobertura parte de ~30%, não de zero.

**Entregável:** `labs/semana-07.md`

**Marco:** ao fim desta semana, **o curso está fechado e os cinco tópicos foram estudados**.

---

### Semana 8 — 19 a 25/10 · Início da Fase 2

**Formato:** volta o ritmo diário. Cinco sessões.

- **2 simulados completos**, cronometrados, em dias diferentes
- Após cada um, listar os erros **por objetivo**, não por questão
- Revisão dirigida **apenas** nos objetivos com erro — não revisar o que já acerta
- Laboratório de reforço nos dois objetivos mais fracos

**Meta:** ≥ 75% no segundo simulado da semana.

---

### Semana 9 — 26/10 a 01/11 · Simulados e laboratório integrador

- **3 simulados completos**, um a cada dois dias
- Revisão dirigida após cada um

**Laboratório integrador** — 2h, do zero, sem consultar:

1. Criar dois usuários e um grupo compartilhado
2. Criar `/dados/projeto` com permissões de grupo corretas e SGID
3. Escrever um script de backup em `.tar.gz` com data no nome
4. Agendar o script com `cron`
5. Gerar um relatório com `find`, `grep` e `sort` dos arquivos maiores que 1 MB

**Meta: ≥ 85% consistente em dois simulados seguidos.** Este é o gate. Se não atingir, adiar a prova em uma semana — a política da LPI permite, e reprovar custa mais caro que adiar.

---

### Semana 10 — 02 a 08/11 · Revisão final

- Segunda a quarta: revisão **leve** — só a cola do GitHub e os cards do Notion, 40 min/dia. Sem conteúdo novo
- Quinta: um simulado final. Se ≥ 85%, está pronto
- Sexta e sábado: **descanso**. Não estudar na véspera

**Prova: segunda-feira 09/11.** Chegar 30 minutos antes, levar dois documentos com foto.

Na prova: 40 questões em 60 minutos, 1,5 minuto por questão. Marcar as difíceis e voltar. Nas de preenchimento, escrever **só o comando**, sem caminho e sem flags, salvo se pedido.

---

## 8. Riscos do novo formato e como são mitigados

| Risco | Por que existe | Mitigação |
|---|---|---|
| **Perda de motricidade** | Comando vira reflexo por repetição espaçada; 2 sessões/semana espaçam menos que 5 | Aquecimento diário de 10 minutos, cinco comandos de memória |
| **Permissões sem repetição suficiente** | É o conteúdo mais dependente de reflexo, e cai na semana de menor frequência | Aquecimento da Semana 6 dedicado só a conversão de permissões · sessão extra na Semana 7 se a conversão não sair em 3 segundos |
| **Curso sem prática imediata** | Assistir sem digitar produz reconhecimento, não competência | As 2 práticas da semana cobrem sempre o objetivo de maior peso daquele bloco |
| **Simulado adiado de novo** | Já atrasou 4 semanas | Ocupa formalmente o lugar de uma das duas práticas da Semana 5 |

---

## 9. Aprendizados acumulados

### Conceitos que valeram como estudo antes da hora

| Conceito | Objetivo | Onde apareceu |
|---|---|---|
| `$PATH` e caminhos relativos | 2.1 | `VBoxManage` fora da pasta do VirtualBox |
| Paginador `less` e a tecla `q` | 3.2 | `apt list --upgradable` parando no `(END)` |
| Redirecionamento `>` e heredoc | 3.2 / 3.3 | Criação do README |
| `&&` e códigos de saída | 3.3 | `apt update && apr upgrade` |
| Partições, LVM e `/boot` fora do LVM | 4.3 | `lsblk` da própria VM |
| `tmpfs` — arquivos que vivem em RAM | 4.3 | `df -h` mostrando `/run` e `/dev/shm` |
| NAT, portas, DHCP e IP privado | 4.4 | Redirecionamento 2222 → 22 |
| Fingerprint de host SSH e `known_hosts` | 5.1 | Primeira conexão `ssh lab` |
| Contas de serviço e `nologin` | 5.1 | 29 das 33 contas do `/etc/passwd` |
| Repositórios e gerenciamento de pacotes | 1.2 | `resolute`, `-security`, `-updates`, `-backports` |
| Pseudo-terminais (`pts`) versus TTY | 1.4 | A própria sessão SSH |

### Erros que se repetiram e merecem atenção

| Erro | Vezes | Correção |
|---|---|---|
| `-k` do `sort` chamado de "setor" | 2 | `-k` é **coluna**, sempre. Vem de *key* |
| `cd ..` descrito como "diretório anterior" | 3 | `cd ..` é **pai**; `cd -` é anterior |
| Confundir o efeito com o mecanismo (`2>&1`, hard link) | 2 | O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |

### Regras de bolso

1. **Leia a mensagem de erro inteira antes de reescrever o comando.**
2. **Quando um arquivo de configuração não pega, leia o arquivo de volta** antes de procurar causas complicadas.
3. **Saída na tela não é prova de sucesso.** Quando um comando produz arquivo, confira o `$?` ou o tamanho do resultado.
4. **Um comando por vez, verificando a saída**, sempre que estiver aprendendo algo novo.
5. **Antes de improvisar com o comando que você já sabe, pergunte se existe um comando feito para aquilo.** `apropos` responde em segundos.

---

## 10. Depois da aprovação

- **GitHub Foundations logo na sequência** (novembro/dezembro). É bem mais leve, você já usa Git e `gh` no dia a dia, e fecha 2026 com duas certificações.
- **O Linux Essentials é a base do RHCSA.** Manter a VM e o repositório de labs. Para o EX200, criar a segunda VM (Rocky Linux ou AlmaLinux) e considerar a trilha do RHEL Developer Subscription como alternativa gratuita ao RH124/RH134.

---

## Fontes

- [LPI — Linux Essentials Overview](https://www.lpi.org/our-certifications/linux-essentials-overview/)
- [LPI — Objetivos do exame 010](https://www.lpi.org/our-certifications/exam-010-objectives/)
- [LPI Learning Materials](https://learning.lpi.org/)
- [OverTheWire — Bandit](https://overthewire.org/wargames/bandit/)
- [Pearson VUE — LPI](https://home.pearsonvue.com/Clients/LPI.aspx)
- [Udemy — Matheus Muller, LPI Linux Essentials](https://www.udemy.com/course/lpi-linux-essentials/)
- [Dion Training — Linux Essentials 010-160](https://www.diontraining.com/products/lpi-linux-essentials-c-usd)
- [Repositório de labs — DaviMoraisdev/linux-essentials-labs](https://github.com/DaviMoraisdev/linux-essentials-labs)