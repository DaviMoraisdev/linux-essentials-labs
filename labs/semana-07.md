# Semana 7 — Pagamento das dívidas, fechamento do curso e nova estratégia até a prova

Período: 12/10 a 18/10/2026 (segunda a domingo)
Objetivos da prova: Tópico 5 (5.1 a 5.4) em prática; curso do Matheus Muller até a aula 72
**Data da prova: segunda-feira, 23/11/2026** (definida em 13/10)
Carga prevista: cerca de 8h30, de terça 13/10 a domingo 18/10
Marco da semana: **Checkpoint A, domingo 18/10**, com as quatro dívidas pagas e o curso fechado

---

## 1. A nova estratégia (13/10)

A prova passou para **23/11**. O plano a partir de hoje tem três etapas, nesta ordem, e nada de fora delas entra na agenda.

| Etapa | Período | O que se faz | Termina quando |
|---|---|---|---|
| **1. Pagar as dívidas** | 13/10 a 18/10 | Prática 1, Prática 2, simulado 02, autoavaliações das Semanas 5 e 6 | As quatro dívidas estiverem registradas (Checkpoint A, 18/10) |
| **2. Conteúdo não estudado** | 15/10 a 25/10 | Curso do Muller até a aula 72 e os laboratórios do Tópico 4, no mesmo formato das práticas anteriores | Curso fechado e Tópico 4 praticado (Checkpoint B, 25/10) |
| **3. Simulados** | 23/10 a 19/11 | Um simulado completo a cada dois ou três dias, com revisão dirigida apenas nos erros | Gate de 08/11 e simulado final de 19/11 |

Regras que valem a partir de agora:

1. **Depois de pagas as dívidas, dívida antiga não volta.** O que não é conteúdo da prova ainda não estudado, nem simulado, sai do plano.
2. **O curso é feito junto com as dívidas, não depois.** As aulas 41 a 72 ocupam os dias de semana; as práticas e o simulado, os dias mais longos.
3. **Erro de simulado se anota e se corrige no Notion**, como desde 06/10. Erro de laboratório e de curso continua com correção numerada; a próxima é a **75**.

---

## 2. Conteúdos ainda não vistos na preparação

Levantamento feito em 13/10 a partir do plano, dos cadernos das Semanas 1 a 6 e do painel de resultados. Os pesos são os oficiais do exame 010-160, versão 1.6.

### 2.1 Curso do Matheus Muller

| Item | Situação |
|---|---|
| Último registro | Aula 40, em 09/10 (checkpoint na **aula 41**) |
| Restante | **Aulas 41 a 72**, 32 aulas |
| Plano | 41 a 57 de quinta 15/10 a sexta 16/10; 58 a 72 no fim de semana 17 e 18/10 |

Se você assistiu a alguma aula depois de 09/10 sem registrar, anote na tabela "Curso — Matheus Muller" (seção 5) e desconte da conta.

### 2.2 Tópico 5 — Segurança e permissões de arquivo (peso 7)

O aquecimento de 07/10 cobriu a conversão entre octal e simbólico e o `chmod` simbólico. Todo o resto do tópico ainda não foi praticado; é o que as Práticas 1 e 2 cobrem.

| Objetivo | Peso | O que falta |
|---|---|---|
| 5.1 Segurança básica e tipos de usuário | 2 | Root, usuários comuns e de sistema; campos de `/etc/passwd`, `/etc/shadow` e `/etc/group`; `id`, `who`, `w`, `last`; `su` contra `sudo` |
| 5.2 Criação de usuários e grupos | 2 | `useradd`, `groupadd`, `passwd`, `usermod -aG`, `userdel`, `groupdel`; `/etc/skel/`; faixas de UID |
| 5.3 Permissões e donos | 2 | Leitura do `ls -l`; `chown` e `chgrp`; SUID, SGID e sticky bit; o `x` em diretórios |
| 5.4 Diretórios e arquivos especiais | 1 | `/tmp` e `/var/tmp` com sticky bit; `ls -d`; `ln -s` com caminho relativo |

### 2.3 Tópico 4 — O sistema operacional Linux (peso 8)

Nunca estudado como tópico. Foi encostado na prática (LVM e partições na Semana 0, `/proc` e `/dev` na Semana 3, pacotes no curso), por isso a cobertura parte de cerca de 30%. O simulado 01 confirmou as lacunas: `top` (Q28) e o sinal padrão do `kill` (Q29) foram erros chutados.

| Objetivo | Peso | Conteúdo oficial | Onde será praticado |
|---|---|---|---|
| 4.1 Escolhendo um sistema operacional | 1 | Diferenças entre Windows, macOS e Linux; ciclo de vida das distribuições (LTS, estável, beta, rolling release); interface gráfica e linha de comando | Bloco de leitura de quinta 22/10 |
| 4.2 Entendendo o hardware | 2 | Placas-mãe, processadores, fontes, drives ópticos, periféricos; discos e partições, `/dev/sd*`; drivers | Prática 3 |
| 4.3 Onde os dados são armazenados | **3** | Programas e configuração, pacotes e banco de dados de pacotes; processos, memória, mensagens do sistema e logs; `ps`, `top`, `free`, `syslog`, `dmesg`; `/etc/`, `/var/log/`, `/boot/`, `/proc/`, `/dev/`, `/sys/` | Práticas 3 e 4 |
| 4.4 Seu computador na rede | 2 | Internet, rede, roteadores; cliente DNS; configuração de rede; `route`, `ip route show`, `ifconfig`, `ip addr show`, `netstat`, `ss`, `/etc/resolv.conf`, `/etc/hosts`, IPv4, IPv6, `ping`, `host` | Prática 5 |

### 2.4 Resíduos dos tópicos já fechados

Dois pontos, apontados nas dicas recorrentes de 06/10, nunca foram estudados como conceito. Entram no bloco de quinta 22/10 e nos mini-simulados de reforço, sem sessão própria.

| Ponto | Objetivo | Situação |
|---|---|---|
| Here document (`<<` com delimitador) | 3.2 | Usado muitas vezes para criar arquivos, nunca estudado como conceito |
| Questões de preencher a lacuna | Formato do exame | Nunca treinadas; a Q11 do simulado 01 foi respondida com um sublinhado na frente de `PATH` |

### 2.5 Resumo

| Bloco | Tamanho | Peso no exame |
|---|---|---|
| Curso, aulas 41 a 72 | 32 aulas | — |
| Tópico 5 | 4 objetivos, 2 práticas | 7 de 40 |
| Tópico 4 | 4 objetivos, 3 práticas e 1 bloco de leitura | 8 de 40 |
| Here document e lacunas | 1 bloco curto e os reforços R1 e R2 | Transversal |

**Cobertura estimada em 13/10: cerca de 70% do conteúdo da prova** (Tópicos 1, 2 e 3 completos; 4 em 30%; 5 com a conversão de permissões).

---

## 3. Dívidas a pagar nesta semana

São as quatro dívidas que você escolheu pagar para entrar na nova estratégia. Os roteiros das práticas não mudam e continuam no arquivo da Semana 6; este arquivo só traz a agenda e o registro.

| # | Dívida | Roteiro | Quando |
|---|---|---|---|
| 1 | **Prática 1** — usuários e grupos, com 20 min de Exercícios da LPI (lições 5.1 e 5.2) | `labs/semana-06.md`, seção "Prática 1" | **Feita em 13 e 15/10**; faltam os Exercícios da LPI 5.1 e 5.2 (domingo 18/10) |
| 2 | **Prática 2** — permissões, com 20 min de Exercícios da LPI (lições 5.3 e 5.4) e limpeza dos usuários de teste | `labs/semana-06.md`, seção "Prática 2" | **Sexta 16/10** |
| 3 | **Simulado 02** — 40 questões, 60 minutos | `labs/simulados-práticos.lpi/simulado-02.md` | **Sábado 17/10** |
| 4 | **Autoavaliação da Semana 5** (10 questões, shell script) e **Autoavaliação da Semana 6** (10 questões, Tópico 5) | S5: `labs/semana-06.md`, seção "Autoavaliação da Semana 5" · S6: seção 6 deste arquivo | S5: **feita em 13 e 15/10 (9 de 10)** · S6: **segunda 19/10**, primeira atividade |

Dois ajustes nos roteiros, por causa da ordem nova:

- **As práticas vêm antes das aulas do Tópico 5.** Para não praticar às cegas, leia antes de cada prática a lição correspondente do PDF oficial (cerca de 15 minutos): lições 5.1 e 5.2 antes da Prática 1, e 5.3 e 5.4 antes da Prática 2. O vídeo, depois, confirma.
- **A autoavaliação da Semana 6 volta ao plano**, a seu pedido. Ela fica na segunda 19/10, três dias depois da Prática 2, para medir retenção e não memória de curto prazo (regra de 29/09). O simulado 02, no sábado, não a substitui: ele mede a prova inteira, e ela mede só o Tópico 5, com perguntas abertas.

---

## 4. Calendário da semana

**Replanejado em 15/10.** A quarta 14/10 ficou sem estudo, e a Prática 2 e as aulas 41 a 57 escorregaram. As linhas de 13 a 15/10 registram o que foi feito.

| Dia | Atividade | Tempo |
|---|---|---|
| Ter 13 | Autoavaliação da Semana 5, questões 1 a 7 · Prática 1, blocos 1 e 2 | **feito** |
| Qua 14 | Sem estudo | — |
| Qui 15 | Autoavaliação da Semana 5, questões 8 a 10 · Prática 1, bloco 3 e experimento sem `-m` | **feito** |
| **Sex 16** | Leitura das lições 5.3 e 5.4 do PDF (15 min) · **Prática 2 — permissões** (1h), com 20 min de Exercícios da LPI 5.3 e 5.4 e a limpeza · **curso, aulas 41 a 46** (2x) | cerca de 2h10 |
| **Sáb 17** | **Simulado 02** (60 min, primeira atividade) · apuração (25 min) · **curso, aulas 47 a 58** | cerca de 2h35 |
| **Dom 18** | Exercícios da LPI 5.1 e 5.2 (20 min, o que faltou da Prática 1) · **curso, aulas 59 a 72** (fechamento) · **Checkpoint A** (10 min) | cerca de 2h |
| Seg 19 | **Autoavaliação da Semana 6** (30 min, primeira atividade, três dias depois da Prática 2) · Prática 3 (Semana 8) | ver Semana 8 |

**Total de sexta a domingo: cerca de 6h45.** É o fim de semana mais pesado do plano, porque carrega o que a quarta deixou. Se faltar tempo, corte nesta ordem:

| Ordem | Corte | Para onde vai |
|---|---|---|
| 1 | Exploratórios da LPI (mantendo os Guiados) | Saem |
| 2 | Aulas de sexta (41 a 46) | Sábado, depois da apuração |
| 3 | Aulas que não couberem no domingo | Segunda 19/10 e terça 20/10, 30 minutos antes da prática do dia |

**Não se cortam:** a Prática 2 e o simulado 02.

Velocidade do curso: **2x** onde o vídeo repete o que já foi praticado (shell script, Tópico 5 depois das práticas); **1.25x** no Tópico 4, que é conteúdo novo.

---

## 5. Curso — Matheus Muller

| Data | Aulas previstas | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|---|
| Qui 15/10 | 41 a 49 | | | |
| Sex 16/10 | 50 a 57 | | | |
| Sáb 17/10 | 58 a 64 | | | |
| Dom 18/10 | 65 a 72 | | | |

Regras de sempre: anote só o que o vídeo mostra e você ainda não sabia; em permissões, converta de cabeça antes de o professor mostrar; registre a aula em que parou ao fim de cada dia.

---

## 6. Autoavaliação da Semana 6 — Segunda 19/10

Dez questões sobre o Tópico 5 (objetivos 5.1 a 5.4), respondidas **sem consultar**, três dias depois da Prática 2. **Primeira atividade da segunda 19/10**, antes da Prática 3. Escreva as respostas à mão e só depois abra o gabarito.

1. Quais são os três tipos de conta em um sistema Linux? Como o UID ajuda a distingui-los, e onde se confere a partir de qual número começam os usuários comuns na sua VM?
2. Quantos campos tem cada linha do `/etc/passwd`, qual o separador, e o que guardam o **terceiro**, o **sexto** e o **sétimo** campos?
3. Por que o `/etc/passwd` pode ser lido por qualquer usuário e o `/etc/shadow` não? O que o `x` do segundo campo do `/etc/passwd` indica?
4. Explique a diferença entre `su - ana` e `sudo comando`. De quem é a senha pedida em cada caso? O que faz `sudo -i`?
5. Escreva o comando que cria o usuário `carla` com diretório pessoal, shell `/bin/bash` e o grupo secundário `dev`. Qual é o papel do `/etc/skel/` nessa criação?
6. A usuária `ana` está nos grupos secundários `dev` e `docker`. Escreva o comando que a acrescenta ao grupo `ops` sem retirá-la dos outros. O que acontece se o `-a` for esquecido?
7. Converta, nos dois sentidos: (a) `rw-r-----` para octal; (b) `751` para simbólico; (c) `rwsr-xr-x` para octal, com o bit especial.
8. Um arquivo tem permissão `640`. Qual a permissão final, em octal e em símbolos, depois de `chmod u+x,o+r arquivo`?
9. O que fazem o **SUID** em um executável (dê o exemplo do sistema), o **SGID** em um diretório e o **sticky bit** em um diretório? O que significa um `S` maiúsculo no lugar do `x` do dono?
10. O diretório `pasta` tem permissão `500` (`r-x------`) e pertence a você. Dentro dele há o arquivo `arq`, com permissão `644`. Você consegue (a) listar o diretório, (b) ler `arq`, (c) criar `pasta/novo`, (d) apagar `arq`? Justifique a resposta (d).

| Campo | Valor |
|---|---|
| Acertos | de 10 |
| Meta | 8 ou mais |
| Questões erradas | |
| Erros viram | lista das questões erradas aqui; a correção fica no Notion |

<details>
<summary>Gabarito (abra só depois de responder)</summary>

1. **Root** (superusuário, UID **0**), **usuários de sistema** (contas de serviço, como `www-data` e `sshd`, com UID abaixo do primeiro UID de usuário comum e normalmente com shell `nologin`) e **usuários comuns** (pessoas, a partir do `UID_MIN`). O valor está em `/etc/login.defs`: `grep UID_MIN /etc/login.defs`. No Ubuntu é **1000**.
2. **Sete** campos, separados por **dois-pontos**. Terceiro: **UID**. Sexto: **diretório pessoal**. Sétimo: **shell de login**. (A ordem completa: usuário, `x`, UID, GID, comentário, home, shell. O GID é o quarto, que foi o erro da Q35 do simulado 01.)
3. Vários programas comuns precisam traduzir UID em nome de usuário, por isso o `/etc/passwd` é legível por todos (`644`). A senha, por isso mesmo, **não** fica nele: o `x` indica que o hash da senha está no `/etc/shadow`, que só o root (e o grupo `shadow`) consegue ler.
4. `su - ana` troca para a usuária `ana`, com o ambiente de login dela, e pede a **senha da ana**. `sudo comando` executa só aquele comando como root (ou outro usuário), e pede a **sua própria senha**, se você estiver autorizado no `sudoers`. `sudo -i` abre um shell de login do root, com o ambiente do root, usando a sua senha.
5. `sudo useradd -m -s /bin/bash -G dev carla`. O `/etc/skel/` é o modelo: o conteúdo dele (por exemplo, `.bashrc`, `.profile`) é copiado para a nova home criada pelo `-m`.
6. `sudo usermod -aG ops ana`. Sem o `-a`, o `-G` **substitui** a lista de grupos secundários: ela ficaria só em `ops` e perderia `dev` e `docker`.
7. (a) `640`. (b) `rwxr-x--x`. (c) `4755`: o `s` no lugar do `x` do dono indica SUID ligado com `x` presente.
8. `744`, ou seja, `rwxr--r--`. O dono ganha `x` (6 para 7), o grupo fica em 4, os outros ganham `r` (0 para 4).
9. **SUID** em executável: o programa roda com os privilégios do **dono do arquivo**; exemplo, `/usr/bin/passwd`, que pertence ao root e precisa gravar no `/etc/shadow`. **SGID** em diretório: os arquivos criados dentro dele herdam o **grupo do diretório**. **Sticky bit** em diretório: só o **dono do arquivo** (ou o root) pode apagá-lo ou renomeá-lo, mesmo que outros tenham `w` no diretório; exemplo, `/tmp`. **`S` maiúsculo**: o bit especial está ligado, mas o `x` correspondente **não** está.
10. (a) **Sim**, há `r` e `x`. (b) **Sim**, há `x` no diretório e `r` no arquivo. (c) **Não**, falta `w` no diretório. (d) **Não**: apagar um arquivo é alterar a lista de entradas do **diretório**, e isso exige `w` (com `x`) no diretório. A permissão do próprio arquivo não decide.

</details>

---

## 7. Checkpoint A — Domingo 18/10, à noite

Critérios revistos em 13/10 para a nova estratégia. Marque com base no que está registrado nos arquivos, não na sensação.

| # | Critério | Cumprido |
|---|---|---|
| 1 | Práticas 1 e 2 feitas e registradas | |
| 2 | Simulado 02 com **24 ou mais** acertos | |
| 3 | Autoavaliações das Semanas 5 e 6 feitas (meta: 8 de 10 em cada) | Semana 5: **sim, 9 de 10**. Semana 6: na segunda 19/10 |
| 4 | Curso até a aula 72 (ou até a 64, com 65 a 72 marcadas para a segunda 19/10) | |

| Resultado | Condição | Decisão |
|---|---|---|
| **Verde** | Os quatro cumpridos | Segue para a Etapa 2 na segunda 19/10 |
| **Amarelo** | Um critério falhou | Segue; o item vira a primeira atividade da segunda 19/10 |
| **Vermelho** | Dois ou mais falharam, ou simulado 02 abaixo de 20 | A semana de 19/10 abre com as dívidas restantes e o Checkpoint B (25/10) passa a decidir a data |

**Previsão de 15/10: amarelo.** O critério 3 falha no domingo por desenho, porque a autoavaliação da Semana 6 precisa de três dias depois da Prática 2. Pela regra, ela vira a primeira atividade da segunda 19/10, que é onde já está. Se mais um critério falhar (Prática 2 ou simulado 02), o resultado passa a vermelho.

Uma autoavaliação abaixo de 8 não reprova o checkpoint: as questões erradas viram o aquecimento da Etapa 2.

---

## 8. Etapa 2 — Laboratórios do Tópico 4 (Semana 8, 19 a 25/10)

Os roteiros ficam escritos aqui, para que a Semana 8 comece sem depender de preparação. O registro das sessões vai em `labs/semana-08.md`, que será aberto na segunda 19/10.

Formato igual ao das práticas anteriores: **45 minutos de teclado, 10 de registro, 5 de commit**, prevendo a saída **antes** de executar. No fim de cada prática, **20 minutos de Exercícios Guiados e Exploratórios** da lição correspondente do PDF da LPI, sem consultar o texto; anote só as questões erradas.

Antes da Prática 3, instale na VM o que pode faltar (o Ubuntu Server nem sempre traz):

```bash
sudo apt update && sudo apt install -y pciutils usbutils net-tools bind9-dnsutils
```

### Calendário da Semana 8

| Dia | Atividade | Tempo |
|---|---|---|
| Seg 19 | **Autoavaliação da Semana 6** (30 min, primeira atividade) · **Prática 3** — hardware, discos e o mapa dos diretórios (4.2 e 4.3), com Exercícios da LPI 4.2 | cerca de 1h50 |
| Ter 20 | **Prática 4** — processos, memória e logs (4.3), com Exercícios da LPI 4.3 | cerca de 1h20 |
| Qua 21 | **Prática 5** — rede (4.4), com Exercícios da LPI 4.4 | cerca de 1h20 |
| Qui 22 | **Bloco curto** — leitura do 4.1 e Exercícios da LPI 4.1 (30 min) · here document (15 min) · quizzes do NDG dos Tópicos 4 e 5 (30 min) | cerca de 1h15 |
| Sex 23 | **Mini-simulado R1** (20 questões, 25 min) e apuração (10 min) | 35 min |
| Sáb 24 | Reposição, se algo escorregou. Sem atividade nova | — |
| **Dom 25** | **Simulado 03** (60 min) · apuração · **Checkpoint B** | cerca de 1h40 |

### Prática 3 — Hardware, discos e o mapa dos diretórios

Objetivos 4.2 e 4.3 (primeira parte).

**Bloco 1 — Processador, memória e barramentos (10 min)**

```bash
lscpu | head -15
grep -m1 'model name' /proc/cpuinfo
grep -c processor /proc/cpuinfo
free -h
head -3 /proc/meminfo
lspci
lsusb
lsmod | head
```

Para o caderno: de onde o `lscpu` e o `free` tiram os números (os dois leem do `/proc`)? Quantos processadores a VM tem e por que bate com o que você configurou no VirtualBox? O que o `lsmod` lista? (Os **módulos do kernel** carregados, que é a forma como os **drivers** existem no Linux.)

**Bloco 2 — Discos e partições (10 min)**

```bash
lsblk
lsblk -f
ls -l /dev/sd*
df -h
df -h -t tmpfs
du -sh /var/log
```

Para o caderno:

- A convenção de nomes: `sd` + letra do disco + número da partição. `/dev/sda3` é a **terceira partição do primeiro disco**. Qual seria a segunda partição do terceiro disco? (`/dev/sdc2`.)
- No `ls -l /dev/sd*`, a primeira letra é `b`: **dispositivo de bloco**. Compare com `ls -l /dev/tty /dev/null`, que começam com `c`, **dispositivo de caractere**.
- Por que o `/boot` está em `sda2`, fora do LVM? (O carregador de inicialização precisa ler o kernel antes de o LVM existir.)
- `df` mostra o espaço por **sistema de arquivos montado**; `du` mostra o espaço ocupado por **diretórios e arquivos**.

**Bloco 3 — O mapa dos diretórios (15 min)**

```bash
ls /proc | head ; cat /proc/$$/status | head -5
cat /proc/version ; cat /proc/uptime
ls /sys ; ls /sys/class/net ; cat /sys/class/net/enp0s3/address
ls -l /dev/sda /dev/tty /dev/null /dev/zero
ls /boot
ls /etc | head ; cat /etc/os-release
ls /var/log
```

Preencha de memória e depois confira executando:

| Diretório | Real ou virtual | O que guarda | Um arquivo que você leu |
|---|---|---|---|
| `/proc` | | | |
| `/sys` | | | |
| `/dev` | | | |
| `/boot` | | | |
| `/etc` | | | |
| `/var/log` | | | |

Regra para fixar: **`/proc` é de processos** (e informações do kernel, como `cpuinfo` e `meminfo`); **`/sys` é de dispositivos e drivers, organizados pelo kernel**; **`/dev` são os arquivos de dispositivo** que os programas abrem. Os três são montados pelo kernel e não ocupam disco.

**Bloco 4 — Programas, configuração e banco de dados de pacotes (10 min)**

```bash
which ls ; dpkg -S /usr/bin/ls
dpkg -L coreutils | head
dpkg -l | wc -l
ls /var/lib/dpkg | head
ls /etc/ssh
```

No container Rocky, o equivalente:

```bash
docker run -it --rm rockylinux/rockylinux:10 bash
rpm -qf /usr/bin/ls ; rpm -ql coreutils | head ; rpm -qa | wc -l ; ls /var/lib/rpm
```

Para o caderno: o programa mora em `/usr/bin`, a configuração em `/etc`, e o **banco de dados de pacotes** em `/var/lib/dpkg` (Debian) ou `/var/lib/rpm` (Red Hat). `dpkg -S` e `rpm -qf` respondem "de qual pacote veio este arquivo?".

**Exercícios da LPI (20 min):** lição 4.2.

### Prática 4 — Processos, memória e logs

Objetivo 4.3 (segunda parte), o de maior peso do tópico.

**Bloco 1 — Listar processos (10 min)**

```bash
ps
ps aux | head
ps -ef | head
ps aux --sort=-%cpu | head -5
echo $$ ; ps -p $$
```

Para o caderno: o que significam as colunas `PID`, `USER`, `%CPU`, `%MEM` e `STAT` do `ps aux`? Qual é o processo de PID 1 e por quê? O `ps` é uma **foto**; o `top`, a seguir, é um **filme**.

**Bloco 2 — `top` e memória (10 min)**

```bash
top
```

Dentro do `top`: `P` ordena por CPU, `M` por memória, `k` pede um PID para encerrar, `q` sai. Depois:

```bash
free -h
uptime
cat /proc/loadavg
```

Para o caderno: o que é *load average* e o que são os três números (1, 5 e 15 minutos)? Por que a coluna `available` do `free` importa mais que a `free`?

**Bloco 3 — Primeiro e segundo plano, e sinais (15 min)**

```bash
sleep 300 &
jobs
sleep 400
# pressione Ctrl+Z
jobs
bg
jobs
fg %1
# pressione Ctrl+C
kill -l | head -3
sleep 500 & echo $!
kill $!            # prediga: qual sinal foi enviado?
sleep 600 &
kill -9 $!
jobs
```

Para o caderno, com o **mecanismo**:

| Sinal | Número | Efeito |
|---|---|---|
| `SIGTERM` | 15 | **Padrão do `kill`.** Pede para o processo encerrar; ele pode tratar o pedido e limpar o que precisa |
| `SIGKILL` | 9 | Encerra à força, pelo kernel; o processo não pode tratar nem ignorar |
| `SIGHUP` | 1 | Historicamente, "o terminal caiu"; muitos serviços o usam para reler a configuração |
| `SIGINT` | 2 | O que o `Ctrl+C` envia |

`&` inicia em segundo plano; `Ctrl+Z` suspende; `bg` continua em segundo plano; `fg` traz para o primeiro plano; `jobs` lista os trabalhos **deste shell**.

**Bloco 4 — Mensagens do sistema e logs (10 min)**

```bash
sudo dmesg | tail
sudo dmesg | grep -i enp0s3
ls -l /var/log
sudo tail -5 /var/log/syslog
logger "teste do lab de logs"
sudo grep "teste do lab" /var/log/syslog
journalctl -n 10 --no-pager
```

Para o caderno: o `dmesg` mostra o **buffer de mensagens do kernel** (inicialização, drivers, dispositivos conectados); o **syslog** (no Ubuntu, o serviço `rsyslog`) grava as mensagens do sistema e dos serviços em arquivos de `/var/log`; o `journalctl` lê o diário do `systemd`. Se o `/var/log/syslog` não existir na sua VM, anote isso: indica que só o journal está ativo.

**Exercícios da LPI (20 min):** lição 4.3 (lições 1 e 2).

### Prática 5 — Rede

Objetivo 4.4. Na VM, a rede é a do VirtualBox em modo NAT, que você já conhece da Semana 0.

**Bloco 1 — Interfaces e endereços (10 min)**

```bash
ip addr show
ip -4 addr show enp0s3
ip -6 addr show enp0s3
ifconfig
```

Para o caderno: identifique `lo` (`127.0.0.1` e `::1`, a própria máquina) e `enp0s3` (`10.0.2.15/24`). O endereço IPv6 que começa com `fe80::` é **link-local**: existe só no enlace. O `ifconfig` é o comando antigo (pacote `net-tools`); o `ip` é o atual. A prova cobra os dois nomes.

**Bloco 2 — Roteamento (10 min)**

```bash
ip route show
route -n
ping -c 3 10.0.2.2
ping -c 3 1.1.1.1
```

Para o caderno: a linha `default via 10.0.2.2` é a **rota padrão**: tudo o que não é da rede local vai para esse roteador, que no NAT do VirtualBox é o próprio host. O `-c 3` faz o `ping` parar depois de três pacotes.

**Bloco 3 — DNS (15 min)**

```bash
cat /etc/resolv.conf
cat /etc/hosts
host lpi.org
dig lpi.org +short
ping -c 1 lpi.org
echo '127.0.0.1 labteste' | sudo tee -a /etc/hosts
ping -c 1 labteste
sudo sed -i '/labteste/d' /etc/hosts
```

Para o caderno: o `/etc/resolv.conf` diz **quais servidores DNS** consultar (no Ubuntu aparece `127.0.0.53`, o resolvedor local do `systemd-resolved`); o `/etc/hosts` é uma **tabela local**, consultada antes do DNS, e por isso o `labteste` funcionou sem servidor nenhum. O `host` dá uma resposta curta; o `dig`, a detalhada.

**Bloco 4 — Sockets e portas (10 min)**

```bash
ss -tuln
ss -tlnp | grep 22
sudo ss -tlnp
ss -s
netstat -tuln
```

Para o caderno: no `ss -tuln`, `t` é TCP, `u` UDP, `l` só as portas **escutando**, `n` mostra números em vez de nomes. Ache o `sshd` na porta **22**. O `netstat` é o equivalente antigo (`net-tools`).

**Teoria para o caderno (5 min, sem terminal):**

| Tema | O que fixar |
|---|---|
| Faixas IPv4 privadas | `10.0.0.0/8`, `172.16.0.0/12` (de `172.16` a `172.31`) e `192.168.0.0/16` |
| IPv4 e IPv6 | 32 bits em decimal (`192.168.0.1`) contra 128 bits em hexadecimal (`2001:db8::1`); `::` abrevia uma sequência de zeros, uma vez por endereço |
| Máscara | `/24` equivale a `255.255.255.0` |
| TCP e UDP | TCP com conexão e confirmação; UDP sem conexão, mais leve (DNS usa UDP 53) |
| Portas comuns | 22 SSH, 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS |
| DHCP | Entrega IP, máscara, rota padrão e DNS automaticamente; é o que deu o `10.0.2.15` à VM |

**Exercícios da LPI (20 min):** lição 4.4.

### Bloco curto de quinta 22/10 — 4.1, here document e NDG

**4.1, leitura e exercícios (30 min).** Leia a lição 4.1 do PDF e responda aos Exercícios. Para o caderno, uma tabela de três colunas (Windows, macOS, Linux) com: licença, kernel (o macOS usa o Darwin), interface padrão e como se instala software. E o ciclo de vida: versão **beta** (teste), **estável**, **LTS** (suporte estendido com atualizações de segurança por vários anos, como o Ubuntu 26.04 da sua VM) e **rolling release** (atualização contínua, sem versões fixas, como o Arch).

**Here document (15 min).** Na VM:

```bash
nome=Davi
cat << FIM
Ola, $nome
Hoje: $(date +%d/%m)
FIM
cat << 'FIM'
Ola, $nome
FIM
cat << FIM > lista.txt
um
dois
FIM
cat lista.txt ; wc -l lista.txt
```

Para o caderno: o `<<` alimenta a **entrada padrão** do comando com as linhas seguintes, até a linha que contém **só** o delimitador; o delimitador não entra no texto. Sem aspas no delimitador, variáveis e `$(...)` são expandidas; com aspas (`'FIM'`), o texto é literal. Não confundir com o `<`, que lê de um **arquivo**, nem com o `>>`, que acrescenta a um arquivo.

**NDG (30 min).** Quizzes dos capítulos de hardware, processos e rede e do capítulo de permissões, no NDG Linux Essentials. Anote só as questões erradas.

---

## 9. Registro das sessões

### Autoavaliação da Semana 5 — 13 e 15/10 — CONCLUÍDA

**Resultado: 9 de 10 acertos firmes. Meta: 8.** Questões 1 a 7 em 13/10 e 8 a 10 em 15/10, nove e onze dias depois do Laboratório 2.

| Q | Situação | Observação |
|---|---|---|
| 1 a 5 | Certas | — |
| 6 | **Respondida com consulta** | O `if` está correto, mas foi pesquisado: não conta como acerto firme |
| 7 | Certa no conceito | No exemplo de texto saiu `[ "$nome" - "Davi" ]`; o operador é `=` |
| 8 | Certa | Completa: `$?`, `exit 0`, `exit 1`, `&&` e `\|\|` |
| 9 | Certa | As duas formas valem: a lista `1 2 3 4 5` e a expansão de chaves `{1..5}`. O gabarito usava `$(seq 1 5)`; vale saber as três, porque a prova pode mostrar qualquer uma |
| 10 | Certa | `i`, `Esc`, `:wq` e `:q!` no `vi`; `Ctrl+O`, `Enter` e `Ctrl+X` no `nano` |

**Leitura.** Retenção boa: onze dias depois do laboratório, o shell script (peso 4, o maior objetivo da prova) segurou nove de dez sem consulta. A única lacuna é escrever o `if` de memória.

**Para o Notion:** questão 6, o `if [ $# -ne 2 ]; then echo "erro"; fi`, escrito de memória até sair sem pensar.

**Ajustes de forma (sem número):**

1. **Aspas curvas** (`“ ”`) nas respostas 6, 7 e 9. No terminal, só as retas (`"`) funcionam; numa questão de preencher, aspa curva invalida a resposta.
2. **`Crtl` em vez de `Ctrl`** na questão 10. É a segunda vez (já aparecia no caderno da Semana 5).
3. Na questão 10, "o `Esc` volta ao modo em que você digita comandos": o `Esc` volta ao **modo normal** (o de navegação, que o material também chama de modo de comando). Os comandos com `:`, como `:wq`, são digitados no **modo de linha de comando**, que se abre com `:` a partir do normal. Na prova, os nomes que aparecem são **inserção** e **comando** (ou normal).

### Prática 1 — 13 e 15/10 — CONCLUÍDA (falta só a parte dos Exercícios da LPI)

**Blocos 1 e 2 anotados em 13/10; bloco 3, experimento sem `-m` e "Para o caderno" em 15/10.** Faltam os 20 minutos de Exercícios da LPI (lições 5.1 e 5.2), remarcados para o domingo 18/10.

**Vocabulário anotado:** UID, GID, grupo primário (registrado no `/etc/passwd`) e grupos secundários. Correto.

#### Bloco 1 — Quem sou eu e quem está logado

| Comando | Resultado registrado |
|---|---|
| `whoami` | `davi`: o usuário efetivo |
| `id` | `uid=1000(davi) gid=1000(davi)`, e os grupos `adm`, `cdrom`, `sudo`, `dip`, `plugdev`, `users` e `lxd` |
| `id root` | UID **0** |
| `who` e `w` | O `who` mostra as sessões (usuário e terminal); o `w` acrescenta o que cada sessão está fazendo: comando atual, tempo ocioso e uso de CPU |
| `last \| head` | Histórico de logins, do mais recente, nas 10 primeiras linhas |
| `sudo whoami` | `root`: o comando roda como root, e o shell volta a ser do `davi` |

Faltam duas respostas do roteiro:

1. **De qual arquivo o `last` lê?** Ainda sem resposta no caderno de 15/10. Do `/var/log/wtmp`, o registro binário de logins e logouts. (O `who` lê o `/var/run/utmp`, que guarda só as sessões abertas agora.)
2. **`su - alice`, `sudo -i` e `sudo su`:** a diferença entre `su` e `sudo` foi respondida em 15/10 ("Para o caderno", abaixo). O detalhe das três formas: o `su - alice` abre um shell de login como `alice` e pede a **senha da alice**; o `sudo -i` abre um shell de login do **root** e pede a **sua** senha; o `sudo su` também vira root com a sua senha, mas sem o ambiente de login do root (o `sudo su -` teria).

#### Bloco 2 — Os arquivos de contas

| Arquivo | Linha lida | O que mostra |
|---|---|---|
| `/etc/passwd` | `root:x:0:0:root:/root:/bin/bash` | 7 campos; as contas `daemon` e `bin` têm shell `/usr/sbin/nologin`, porque são de sistema |
| `/etc/shadow` | `root:*:20563:0:99999:7:::` | 9 campos; hash da senha e prazos |
| `/etc/group` | `root:x:0:` | 4 campos; definição dos grupos e membros |
| `/etc/gshadow` | — | Senha de grupo e administradores do grupo, protegido como o `shadow` |
| `/etc/login.defs` | `UID_MIN 1000` | O primeiro UID de usuário comum, que é o do `davi` |

Permissões registradas: `passwd` e `group` com `-rw-r--r--` (`root root`, legíveis por todos); `shadow` e `gshadow` com `-rw-r-----` (`root shadow`, só root e grupo `shadow` leem).

Ajustes de caderno:

1. **Ainda faltam os 7 campos do `/etc/passwd`, um por um** (o bloco 2 não mudou em 15/10), como o roteiro pede: usuário, `x`, UID, GID, comentário, diretório pessoal e shell de login. É o conteúdo da Q35 do simulado 01, errada por chute.
2. **Falta responder por que o `/etc/passwd` é legível por todos e não guarda a senha:** vários programas precisam traduzir UID em nome; por isso a senha foi para o `/etc/shadow`, e o `x` do segundo campo indica isso.
3. **O `*` no segundo campo do `shadow`** significa que a conta **não tem senha válida**: não dá para entrar com senha. É o caso das contas de sistema. O `20563` é a data da última troca de senha, contada em dias desde 01/01/1970; `0`, `99999` e `7` são o mínimo e o máximo de dias entre trocas e o aviso antes de expirar.
4. **No `/etc/group`, os 4 campos:** nome, `x`, GID e lista de membros. Em `root:x:0:` a lista está vazia.
5. Na listagem do `ls -l`, a primeira linha saiu `rw-r--r--`, sem o `-` do tipo de arquivo. É de cópia, mas na prova o primeiro caractere conta: `-` arquivo, `d` diretório, `l` link.
6. O `#SYS_UID_MIN 101` está comentado (começa com `#`), então vale o padrão do sistema. O `SUB_UID_MIN` é de outro assunto (contêineres sem root) e não cai na prova.

#### Bloco 3 — Criar, alterar e quebrar

| O que foi anotado | Revisão |
|---|---|
| `groupadd` cria o grupo, e os grupos precisam existir antes de aparecer nas opções do `useradd` | Correto. Sem o grupo, o `useradd -G dev` falha com `group 'dev' does not exist` |
| `-m` cria o diretório pessoal; `-s /bin/bash` define o shell de login; `-g ops` define o grupo primário; `-G dev` define os grupos secundários | Correto |
| `passwd` define a senha do usuário; `useradd` cria a conta; `/etc/skel` é o modelo do diretório pessoal | Correto |
| "`/home/alice` e `/home/bob` → grupo primário" | **Errado. Ver Correção 75** |

**A quebra de propósito.** Correto: sem o `-a`, o `usermod -G ops alice` **substituiu** a lista e tirou a `alice` do `dev`; o grupo primário não muda; o `usermod -aG dev alice` devolveu o `dev` mantendo o `ops`. Os GIDs anotados conferem: `dev` é 1001 e `ops` é 1002, porque foram os dois primeiros grupos criados depois do `davi` (1000).

**Os números da VM fecham.** Os usuários receberam UIDs em ordem (`alice` 1001, `bob` 1002, `carol` 1003, `teste_sem_nome` 1004). Os grupos: `dev` 1001, `ops` 1002, `alice` 1003, `bob` 1004 e `teste_sem_nome` 1005. A `carol` **não** ganhou grupo próprio, porque o `-g ops` já deu a ela um grupo primário. É por isso que o `teste_sem_nome` ficou com GID 1005, e não 1004.

**Experimento sem `-m` — registrado.** O `id` mostra a conta criada (`uid=1004`), o `ls -ld /home/teste_sem_nome` responde `No such file or directory`, e mesmo assim o `/etc/passwd` traz `/home/teste_sem_nome` no sexto campo. Conclusão certa, e vale escrever o mecanismo: **o `useradd` grava o caminho do diretório pessoal no `/etc/passwd`, mas só cria a pasta com `-m`**. No Ubuntu, o padrão é não criar (no Red Hat é o contrário). Uma conta assim abre a sessão em `/`, com aviso de que a home não existe. O `adduser`, interativo, cria a home sempre.

**Para o caderno — revisão.** As três respostas estão corretas: `-g` primário e `-G` secundários, com o `-G` sozinho substituindo e o `-aG` acrescentando; o `/etc/skel` como modelo do diretório pessoal; o `su` com a senha do usuário de destino e o `sudo` com a senha de quem o invoca, conforme a política do `sudoers`.

**Atenção para a Prática 2:** o `teste_sem_nome` não está na limpeza original. A limpeza da Prática 2 foi atualizada no caderno da Semana 6 para incluí-lo.

#### Correção 75 — o `/home/alice` é o diretório pessoal, não o grupo primário

A anotação diz "`/home/alice` e `/home/bob` → grupo primário". São coisas de campos diferentes do `/etc/passwd`:

| Campo do `/etc/passwd` | Exemplo da `alice` | O que é |
|---|---|---|
| 4º, GID | `1003` | O **grupo primário**: um grupo com o mesmo nome do usuário (`alice`), criado junto com a conta |
| 6º, diretório pessoal | `/home/alice` | A **pasta** do usuário, criada pelo `-m` com o conteúdo do `/etc/skel` |

Na sua VM: o grupo primário da `alice` é `alice`, o do `bob` é `bob` e o da `carol` é `ops` (por causa do `-g`). Para ver: `id -gn alice ; id -gn carol ; grep '^alice:' /etc/passwd | cut -d: -f4,6`.

### Prática 2 — sexta 16/10

*A preencher.*

### Simulado 02 — sábado 17/10

*A preencher.* Registre também em `labs/simulados-práticos.lpi/resultados_simulados.md`.

### Autoavaliação da Semana 6 — segunda 19/10

*A preencher.* Acertos: de 10. Questões erradas:

### Correções da semana

A numeração segue a série global. **A próxima é a 76.** Erros de simulado e de autoavaliação não geram correção numerada; vão para o Notion.

| # | Tema | Origem |
|---|---|---|
| 75 | `/home/alice` é o diretório pessoal (6º campo), não o grupo primário (4º campo) | Prática 1, bloco 3, 15/10 |

---

## 10. Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Ter 13 | 2h05 | | Autoavaliação S5 (1 a 7) e Prática 1, blocos 1 e 2 |
| Qua 14 | 2h20 | 0 | Sem estudo |
| Qui 15 | 1h | | Autoavaliação S5 (8 a 10) e Prática 1, bloco 3 |
| Sex 16 | 2h10 | | Prática 2 e aulas 41 a 46 |
| Sáb 17 | 2h35 | | Simulado 02 e aulas 47 a 58 |
| Dom 18 | 2h | | Exercícios da LPI 5.1 e 5.2, aulas 59 a 72 e Checkpoint A |

---

## 11. Checklist da semana

- [x] Autoavaliação da Semana 5 respondida e conferida (13 e 15/10): 9 de 10
- [x] Prática 1, blocos 1 a 3 e experimento (13 e 15/10)
- [ ] Exercícios da LPI 5.1 e 5.2 (domingo 18/10)
- [ ] Prática 2, com Exercícios da LPI 5.3 e 5.4 e limpeza dos usuários de teste (sexta 16/10)
- [ ] `cheatsheets/permissoes.md` escrito à mão, nos 10 minutos de registro da Prática 2
- [ ] Curso, aulas 41 a 46 (sexta)
- [ ] Simulado 02 e apuração por tópico e por tema (sábado 17/10)
- [ ] Curso, aulas 47 a 72 (sábado e domingo)
- [ ] Autoavaliação da Semana 6 respondida e conferida (segunda 19/10)
- [ ] Checkpoint A preenchido
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-07.md` preenchido, `cheatsheets/permissoes.md`, resultado do simulado 02 em `resultados_simulados.md`, as duas autoavaliações conferidas, o curso fechado e o Checkpoint A preenchido.