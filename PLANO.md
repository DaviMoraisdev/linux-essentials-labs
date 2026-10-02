# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** 5–7h/semana
**Data da prova:** **09/11/2026, segunda-feira**
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> **Estratégia revisada em 26/09.** O cronograma tem **duas fases**: três semanas com o curso como atividade principal e duas práticas por semana, seguidas de três semanas de prática intensiva e simulados. Detalhamento na seção 7.
>
> **Calendário da Semana 5 revisado em 29/09.** O curso foi adiado na segunda e na terça. As 18 aulas restantes da semana passam a ser cumpridas em dois blocos, na quarta e na quinta, sem mover os laboratórios nem o simulado. Detalhamento na seção 7 e no arquivo `labs/semana-05.md`.

---

## 1. Status atual

### Concluído

| Item | Situação |
|---|---|
| **Semana 0 — Laboratório** | Concluída em 26/08 — VM, SSH, snapshot, repositório |
| **Semana 1 — Tópico 1 (peso 7)** | Concluída em 05/09 — comunidade, licenças, distros, FHS |
| **Semana 2 — Tópico 2, parte 1** | Concluída em 13/09 — objetivos 2.1 e 2.2 |
| **Semana 3 — Tópico 2, parte 2** | Concluída em 19/09 — objetivos 2.3 e 2.4 |
| **Semana 4 — Tópico 3, parte 1** | **Fechada em 29/09** — objetivos 3.1 e 3.2; 10 correções (43 a 52); simulado transferido para a Semana 5 |
| **Tópico 1 (peso 7)** | Completo |
| **Tópico 2 (peso 9)** | Completo — os quatro objetivos |
| **Tópico 3 (peso 9)** | 3.1 e 3.2 feitos; falta o 3.3, em curso na Semana 5 |
| Autoavaliação da Semana 2 | 14 de 15 — respondida no dia do estudo |
| Autoavaliação da Semana 3 | 20 de 20 — respondida no dia do estudo |
| Autoavaliação da Semana 4 | **14 de 20** (29/09) — respondida 4 dias depois; abaixo da meta de 16. **Correções 49 a 52 anotadas no caderno em 29/09** |
| Bandit | Níveis 0 a 9 |
| Cards de revisão (Notion) | Em uso desde a Semana 1 |
| Curso do Muller | **Checkpoint na aula 31 de 72** (30/09; aulas 26 a 30 assistidas) — 42 restantes. Adiado em 28 e 29/09 |

### Dívidas pagas (29 e 30/09)

| Dívida | Origem |
|---|---|
| Autoavaliação da Semana 4 realizada e corrigida | Semana 4 |
| Instalação do `bzip2` | Semana 4 |
| Commits da Semana 4 | Semana 4 |
| Correções 49 a 52 anotadas | Semana 4 |
| Curso, aulas 26 a 30 (30/09) | Semana 5 |

### Pendente

| Item | Prazo |
|---|---|
| **Curso, aulas 31 a 43** (13 aulas; as aulas 26 a 30 foram concluídas em 30/09) | sem estudo na quinta 01/10; replanejado para sex 02 e sáb 03/10, com o excedente que não for de shell script na segunda 05/10 |
| **Laboratório 1: blocos 3 a 6 e exercício das frutas** (blocos 1 e 2 concluídos em 02/10) | blocos 3 a 5 no sábado 03/10, **antes** do Laboratório 2; bloco 6 e exercício até segunda 05/10 |
| **Voucher da prova** e agendamento para 09/11 | quarta 30/09 (prazo original: 29/09) |
| **Simulado diagnóstico** — 40 questões, cronometrado | **domingo 04/10** — escrito, em `praticas/simulado-01-diagnostico.md` |
| Reteste das 4 questões erradas da autoavaliação da Semana 4 | No aquecimento diário, até domingo |
| Refazer a comparação de compressão (`bzip2` já instalado) | quarta 30/09, no aquecimento |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | quarta 30/09 |
| Registrar as observações sobre arquivos ocultos (Semana 3) | sexta 02/10 |
| `.wslconfig` limitando o WSL2 a 3 GB | Quando houver folga |
| Teste de restauração do snapshot | Quando houver folga |

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
| Nota de corte | Referência comum: 500 de 800 (~65%), ou 26 acertos |
| Idioma | Português (Brasil) disponível |
| Validade | Vitalícia |
| Entrega | Centro Pearson VUE ou OnVUE |

> Recomendação: **centro Pearson VUE**, não OnVUE. O check-in remoto é rigoroso e um problema técnico queima o voucher.

### Pesos dos tópicos

| Tópico | Peso | Onde é tratado |
|---|---|---|
| 2. Finding Your Way on a Linux System | **9** | Concluído nas Semanas 2 e 3 |
| 3. The Power of the Command Line | **9** | Semana 4 (3.1, 3.2) + Semana 5 (3.3) |
| 4. The Linux Operating System | **8** | Semana 7 |
| 1. The Linux Community and a Career in Open Source | 7 | Concluído na Semana 1 |
| 5. Security and File Permissions | 7 | Semana 6 |

O objetivo 3.3 (shell script) tem **peso 4**, o maior individual do exame. A lista oficial de termos inclui `#!`, `/bin/bash`, variáveis, argumentos, `for`, `echo` e exit status, além do **reconhecimento dos editores `vi` e `nano`**.

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
**Matheus Muller — LPI Linux Essentials (Udemy, PT-BR)**. Atividade principal na Fase 1.

**Velocidade recomendada por trecho:**

| Conteúdo | Velocidade | Motivo |
|---|---|---|
| Tópicos 1, 2, 3.1 e 3.2 | **1.5x**, ou **2x** se a aula só repete o que o caderno já registra como praticado | Já praticados, com autoavaliação de 20/20 na S3 e 14/20 na S4. O vídeo confirma, não ensina |
| Objetivo **3.3 — shell script** | **1x** | Peso 4, o maior individual da prova. O vídeo entrega o modelo mental |
| Tópicos 4 e 5 | **1.25x** | Conteúdo novo, mas com laboratório logo em seguida |

### Trilha de reforço

**Jason Dion — LPI Linux Essentials 010-160 (Udemy, EN).** Fora do plano. Os simulados eram o principal valor do curso, e eles estão atrás da plataforma paga, sem acesso. Se o curso for adquirido em algum momento, o uso indicado é só o banco de simulados; caso contrário, nada se perde — o substituto gratuito é melhor para a Fase 2, porque os quizzes do NDG são por módulo e permitem medir tópico por tópico.

### Simulados e bancos de questões

| Fonte | Custo | Para quê |
|---|---|---|
| **`praticas/` deste repositório** | — | Simulados próprios, com peso do exame e gabarito comentado. As questões atacam os erros já registrados nos cadernos |
| **NDG Linux Essentials** (Cisco Networking Academy) | Gratuito | Quizzes por módulo e exame final de prática. A melhor fonte externa gratuita |
| **LPI Learning Materials** (PDF no Projeto) | Gratuito | Questões de revisão ao final de cada objetivo |
| **EDUSUM** | Gratuito | Amostra de questões no estilo LPI |

Sites de dumps — ITExams, Marks4Sure, Pass4Success e semelhantes — estão fora do plano: violam o termo de confidencialidade assinado antes da prova, os gabaritos são reconstruídos de memória por terceiros e o método é o oposto do que vem funcionando aqui. Detalhes em `praticas/fontes-de-simulados.md`.

### Recursos complementares

| Recurso | Para quê |
|---|---|
| **LPI Learning Materials** (learning.lpi.org) | Material oficial, escrito objetivo por objetivo, com tradução PT-BR |
| **OverTheWire — Bandit** | Níveis 0 a 9 concluídos; 10 a 20 são bônus, não obrigatórios |
| **Notion** (cards próprios) | Retenção espaçada |
| **explainshell.com** | Explica cada flag de um comando complexo |
| **tldr / tealdeer** | Exemplos práticos, complemento ao `man` |

---

## 6. Método de estudo

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

**O aquecimento não é livre: ele é pautado pelos erros da autoavaliação anterior.** Cinco comandos escolhidos ao acaso reforçam o que já está fixado. Cinco comandos escolhidos a partir das questões erradas atacam a lacuna medida.

Aquecimento da Semana 5 — `grep` e `sort`, pelos erros das questões 7, 11, 13 e 14:

```bash
grep -v '^#' /etc/ssh/sshd_config | grep -v '^$'
printf '100\n25\n3\n9\n' | sort ; printf '100\n25\n3\n9\n' | sort -n
grep -c ERROR sistema.log ; grep -o ERROR sistema.log | wc -l
grep '^[AB]' funcionarios.csv ; grep '[^0-9]' funcionarios.csv
grep -E 'ERROR|WARN' sistema.log
```

Na quinta e no sábado, o quinto item é trocado pelo teste do `-f` do `tar` (Correção 52). Os arquivos de apoio são recriados em `~/lab5`; o roteiro completo está em `labs/semana-05.md`.

### Quando responder a autoavaliação

**Regra alterada em 29/09.** As autoavaliações das Semanas 2 e 3 foram respondidas no mesmo dia do último laboratório e deram 14 de 15 e 20 de 20. A da Semana 4 foi respondida quatro dias depois e deu 14 de 20 — com todos os quatro conceitos errados já registrados corretamente no caderno, dias antes.

As duas primeiras notas mediam memória de curto prazo. A terceira mediu retenção, que é o que a prova mede.

**Da Semana 5 em diante, a autoavaliação de cada semana é respondida na semana seguinte**, em um dia de curso, como abertura da sessão. O intervalo mínimo é de três dias. Uma nota menor e honesta informa o plano; uma nota alta e cedo apenas o tranquiliza. A autoavaliação da Semana 5 é elaborada depois do Laboratório 2 e respondida na quarta 07/10.

### As sessões de laboratório

Sem vídeo dentro delas — o vídeo agora tem espaço próprio. A sessão inteira é teclado:

1. **45 min de laboratório** — reproduzir tudo na VM, **digitando**, nunca copiando e colando
2. **10 min de registro** — anotar no caderno o comando, o que faz e o exemplo executado
3. **5 min** — commit no repositório

**Quebrar coisas de propósito** continua valendo. O snapshot `limpo` existe para isso.

### A fila de dívidas

Item adiado não some. Ele entra no início do próximo bloco de estudo e fica registrado na tabela de dívidas do arquivo da semana. Adiar tem custo visível: a Semana 5 subiu de 5h para cerca de 6h45 depois de dois dias de curso perdidos.

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
| Aulas restantes do curso | 42 (da 31 à 72), após o checkpoint de 30/09 |
| Semanas na Fase 1 | 3 |
| Aulas por semana | ~15 |
| Tempo estimado de vídeo, em 1.25–1.5x | **1h30 a 2h por semana** |
| Duas sessões de laboratório | 2h |
| Aquecimento diário | 1h10 na semana |
| **Total semanal** | **~5h** — dentro do orçamento de 5 a 7h |

A Fase 1 termina em **18/10**, com o curso fechado e todos os cinco tópicos ao menos estudados. Sobram **três semanas inteiras** para simulados.

### Datas do calendário que afetam o plano

| Data | Evento | Efeito |
|---|---|---|
| Seg 12/10 | Nossa Senhora Aparecida (feriado) | Primeiro dia da Semana 7. Dia extra disponível para curso ou para uma sessão de permissões, se a conversão não sair em 3 segundos |
| Qua 28/10 | Dia do Servidor Público | Sem efeito no plano |
| Seg 02/11 | Finados (feriado) | Primeiro dia da Semana 10, na revisão leve |
| Seg 09/11 | Dia da prova | Não cai em feriado |

---

### Semana 5 — 28/09 a 04/10 · Objetivo 3.3, shell script

**Calendário revisado duas vezes.** Em 28/09 a segunda foi consumida pela Sessão 5 da Semana 4 e os laboratórios saíram de terça e sexta para sexta e sábado. Em 29/09 a terça foi consumida pela autoavaliação e pelas correções, e o curso perdeu os dois dias. As 18 aulas restantes (26 a 43) foram distribuídas em dois blocos de 9, na quarta e na quinta. Os laboratórios e o simulado **não mudam de dia**.

| Dia | Atividade | Tempo |
|---|---|---|
| Seg 28 | Sessão 5 da Semana 4 — `find` e desafio integrador | concluído |
| Ter 29 | Autoavaliação da Semana 4 · correções 49 a 52 · `bzip2` · commits | concluído |
| Qua 30 | Voucher (10 min) · curso, aulas 26 a 34 · aquecimento — **realizado: aulas 26 a 30** | 1h25 |
| Qui 01/10 | Curso, aulas 31 a 43 (13 aulas) · aquecimento | cerca de 1h50 |
| Sex 02 | Laboratório 1 — fundamentos de shell script, `vi` e `nano` · aquecimento | 1h10 |
| Sáb 03 | Laboratório 2 — os quatro scripts · aquecimento | 1h10 |
| Dom 04 | Simulado diagnóstico · apuração · commits | 1h35 |

Total a partir de quarta: **6h45**, dentro do teto de 7h, sem folga.

**Regra de transbordo.** Se a quarta ou a quinta não fecharem as 9 aulas: (1) as aulas de shell script têm prioridade e precisam estar vistas antes do Laboratório 1; (2) as demais podem transbordar para a segunda 05/10, antes das aulas de permissões; (3) o Laboratório 2 e o simulado não são cortados nem movidos.

**Atualização de 30/09.** A quarta fechou 5 das 9 aulas previstas. As 4 restantes passaram para a quinta, que fica com 13 aulas. No pior caso a semana vai a cerca de 7h10, 10 minutos acima do teto; a folga vem de usar **2x** nas aulas que só repetem conteúdo já praticado e da regra de transbordo. Detalhes em `labs/semana-05.md`.

**Curso:** aulas 26 a 43, com checkpoint na aula 31 em 30/09. Reduzir para **1x** ao chegar no shell script.

**Justificativa da divisão em duas práticas.** O objetivo 3.3 tem peso 4 e cobre shebang, variáveis, argumentos, condicionais, loops, códigos de saída e os editores `vi` e `nano`. Não cabe em uma sessão com os quatro scripts no fim. A sexta cobre os fundamentos; o sábado escreve o código.

**Prática 1 — Fundamentos de shell script (sexta 02/10)**

- Shebang `#!/bin/bash`, `chmod +x`, `./script.sh` versus `bash script.sh`
- Variáveis, `$1 $2 $@ $# $0`, aspas
- `if/elif/else`, `test` e `[ ]`, comparadores `-eq -ne -lt -gt -f -d -z`
- Loop `for` e `seq`
- Códigos de saída: `$?`, `exit 0`, encadeamento `&&` e `||`
- **`vi` e `nano`**: modos do `vi`, como gravar e sair de cada um
- Exercício do script das frutas, do material oficial do LPI, com erros de sintaxe para corrigir

**Prática 2 — Os quatro scripts (sábado 03/10)**

Escrever em `scripts/`, um por vez, testando cada um antes de passar ao seguinte:

| Script | Exercita |
|---|---|
| Backup com a data no nome | Substituição de comando, `tar`, variáveis |
| Contar arquivos por extensão | `for`, `find`, `wc`, pipeline dentro de script |
| Verificar se um usuário existe | `if`, `grep -q`, `$?`, `exit` com código |
| Ler um arquivo linha a linha e filtrar | `while read`, redirecionamento de entrada |

> `while` e `read` não constam na lista oficial de termos do 3.3, mas o quarto script os exige. O que a prova cobra com certeza são `for`, argumentos, variáveis, `if` com operadores numéricos e o código de saída.

> Você já programa, então a sintaxe vem rápido; o que exige atenção é a diferença entre o modelo mental do shell e o de uma linguagem estruturada. Três pontos concretos: espaços dentro de `[ ]` são obrigatórios, `=` compara texto e `-eq` compara número, e uma variável sem aspas se parte em palavras.

**Simulado diagnóstico (domingo 04/10)**

40 questões, 60 minutos, cronometrado, sem consultar nada. O simulado está em `praticas/simulado-01-diagnostico.md`, com a distribuição de pesos do exame e gabarito comentado. Fontes gratuitas complementares em `praticas/fontes-de-simulados.md` — a principal é o NDG Linux Essentials da Cisco Networking Academy, cujos quizzes e exame final de prática são gratuitos.

Esta é a pendência mais antiga do plano, com quatro semanas de atraso. Ela ocupa o lugar de uma prática porque **é** prática — e porque o resultado determina no que as práticas das Semanas 6 e 7 devem insistir. As questões 18, 20, 21, 22 e 24 retestam correções já registradas (29, 33/34/50, 36, 52 e a diferença entre regex e globbing).

**Expectativa:** entre 60% e 75%. Você cobriu ~65% do conteúdo e o Tópico 5 está zerado. Abaixo de 24 acertos, a Semana 7 ganha uma sessão de revisão e o gate da Semana 9 é revisitado.

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

**Ação da semana: comprar o voucher e agendar a prova para 09/11**, até quarta 30/09.

Marcar antes de se sentir pronto é intencional. Prazo firme é o que impede o plano de escorregar para dezembro.

**Entregável:** `labs/semana-05.md` + 4 scripts + voucher comprado + resultado do simulado

---

### Semana 6 — 05 a 11/10 · Tópico 5, permissões (peso 7)

**Curso:** aulas **44 a 57**, aproximadamente. A faixa começa na 44 porque a Semana 5 fecha na 43. Aulas que tiverem transbordado da Semana 5 entram na segunda 05/10, antes de permissões.

**Abertura da semana:** autoavaliação da Semana 5 (shell script), respondida na quarta 07/10, com o intervalo mínimo de 3 dias em relação ao Laboratório 2.

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
> Por isso o **aquecimento diário desta semana é obrigatório** e sempre o mesmo: cinco conversões de permissão, de memória, sem consultar. Se ao fim da semana a conversão não sair em três segundos, a Semana 7 começa com mais uma sessão de permissões antes do Tópico 4. A segunda 12/10, feriado, é o dia natural para essa sessão.

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

- Segunda (feriado de Finados) a quarta: revisão **leve** — só a cola do GitHub e os cards do Notion, 40 min/dia. Sem conteúdo novo
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
| **Simulado adiado de novo** | Já atrasou 4 semanas | Ocupa formalmente o lugar de uma das duas práticas da Semana 5, em data fixa: domingo 04/10 |
| **Curso adiado repetidamente** | Segunda e terça da Semana 5 sem aulas; na quarta, 5 das 9 aulas previstas (26 a 30); 42 restantes (31 a 72) em 3 semanas | Quinta com as aulas 31 a 43 · 2x nas aulas que repetem conteúdo já praticado · regra de transbordo (shell script tem prioridade, o resto vai para segunda 05/10) · fila de dívidas registrada por semana |
| **Retenção menor que a percebida** | A autoavaliação da Semana 4, feita 4 dias depois, deu 14/20 contra 20/20 no mesmo dia | Autoavaliação sempre na semana seguinte · aquecimento pautado pelos erros · simulado com marcação de chutes |

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
| Arquivo comprimido de 0 bytes como sinal de falha | 3.1 | `tar -cjvf` sem o `bzip2` instalado |

### Erros que se repetiram e merecem atenção

| Erro | Vezes | Correção |
|---|---|---|
| `sort` sem `-n` descrito como "invertendo a ordem" | **4** (Correções 32, 33/34 e 50) | As duas formas são **crescentes**; só o `-r` inverte. `-k` é **coluna**, vem de *key*. Reler não resolveu: o que resolve é executar os quatro comandos lado a lado |
| `cd ..` descrito como "diretório anterior" | **4** (a quarta em 30/09, Correção 53) | `cd ..` é **pai**; `cd -` é anterior. "Anterior" só existe para o `cd -` |
| Confundir o efeito com o mecanismo (`2>&1`, hard link, `-f` do `tar`) | 3 | O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |
| `grep -v` entendido como *verbose* | 1 (Correção 49) | É *invert*. O `grep` é a exceção: em `tar`, `cp`, `rm` e `mv` o `-v` é verbose. Custou **duas** questões da autoavaliação, porque a 14 dependia dele |

### Regras de bolso

1. **Leia a mensagem de erro inteira antes de reescrever o comando.**
2. **Quando um arquivo de configuração não pega, leia o arquivo de volta** antes de procurar causas complicadas.
3. **Saída na tela não é prova de sucesso.** Quando um comando produz arquivo, confira o `$?` ou o tamanho do resultado.
4. **Um comando por vez, verificando a saída**, sempre que estiver aprendendo algo novo.
5. **Antes de improvisar com o comando que você já sabe, pergunte se existe um comando feito para aquilo.** `apropos` responde em segundos.
6. **Conceito que resiste a três leituras cede a uma execução.** Quando o mesmo erro reaparece, não releia: rode.
7. **Uma lacuna conceitual não custa uma questão, custa todas as que dependem dela.** Priorize a base (o `-v`) sobre o padrão (o `'^#'`).

---

## 10. Depois da aprovação

### Roadmap completo — atualizado em 29/09

Ordem de estudo confirmada:

| # | Certificação | Situação |
|---|---|---|
| 1 | **LPI Linux Essentials** (010-160) | Em preparação — prova em 09/11/2026 |
| 2 | **GitHub Foundations** | Na sequência, em novembro/dezembro |
| 3 | **Red Hat RHCSA** (EX200) | Próxima grande certificação |
| 4 | **LPIC-1** (101-500 e 102-500) | Duas provas; o certificado só sai com as duas aprovadas |
| 5 | **Red Hat RHCE** (EX294) | Depois do LPIC-1; construída sobre o RHCSA |
| 6 | **AWS Cloud Practitioner** | |
| 7 | **AWS AI Practitioner** | |
| 8 | **AWS Developer Associate** | |
| Opcional | **LFCS** — Linux Foundation Certified System Administrator | Sem data definida |
| Opcional | **Docker Certified Associate** | Sem data definida |

### Horizonte futuro — certificações que exigem proficiência e experiência

Estas três ficam **fora da sequência de estudo atual**. Elas cobram experiência prática comprovada além do conteúdo de prova, então entram no roadmap como metas de longo prazo, sem data, a serem retomadas depois que as etapas 1 a 8 estiverem concluídas e houver vivência real com as tecnologias.

| Certificação | Apoio no roadmap atual |
|---|---|
| **AWS Certified Machine Learning Engineer — Associate** | AWS Cloud Practitioner, AWS AI Practitioner e AWS Developer Associate (etapas 6 a 8) |
| **HashiCorp Terraform Associate** | Trilha AWS (etapas 6 a 8) e a prática de infraestrutura construída no RHCSA, no LPIC-1 e na RHCE |
| **CKA — Certified Kubernetes Administrator** | Linux sólido (RHCSA e LPIC-1) e o uso diário de Docker no projeto de e-commerce |

A coluna da direita é apenas o caminho natural dentro do roadmap atual, não um pré-requisito oficial de nenhuma das provas.

**Como este plano alimenta as próximas etapas**

- **GitHub Foundations logo na sequência.** É bem mais leve, você já usa Git e `gh` no dia a dia, e fecha 2026 com duas certificações.
- **O Linux Essentials é a base do RHCSA.** Manter a VM e o repositório de labs. Para o EX200, criar a segunda VM (Rocky Linux ou AlmaLinux) e considerar a trilha do RHEL Developer Subscription como alternativa gratuita ao RH124/RH134. O RHCSA é prático, feito no terminal, e o hábito construído aqui — laboratório diário, quebrar coisas de propósito, conferir o `$?` — é exatamente o que ele cobra.
- **O LPIC-1 vem logo depois** e reaproveita boa parte do RHCSA no lado de administração. Ele exige dois exames, o 101-500 e o 102-500, e pedirá material complementar vendor-neutral com foco em Debian.
- **A RHCE vem depois do LPIC-1.** É a certificação de nível engenheiro da Red Hat, construída sobre o RHCSA e centrada em automação com Ansible (exame EX294). O ambiente de laboratório montado para o RHCSA continua sendo a base.

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