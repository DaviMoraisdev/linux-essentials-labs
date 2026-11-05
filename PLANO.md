# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** 1h10 a 1h25 por dia na operação prática; cerca de 2h por dia na Semana 10, que ainda tem as aulas
**Data da prova:** **30/11/2026, segunda-feira** (movida de 23/11 em 26/10; seção 11)
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> **Estratégia de 26/10 — conteúdo primeiro, depois prática todos os dias.** O modelo de "dívidas" saiu do plano: pagar pendências atrasadas não estava gerando aprendizado, e o rendimento caiu (simulado 02: 22 de 40, 17 firmes). O plano agora tem duas fases e nenhuma lista de pendências: **(1) conteúdo**: o Tópico 4 em três práticas de laboratório até 01/11, e o curso do Muller (aulas 41 a 72) e o 4.1 de 02 a 06/11, somados às sessões de prática; **(2) operação prática**, de 01/11 a 26/11: simulado, mini-simulado, lacunas e treino na VM todos os dias, com correção no mesmo dia. O que não cabe no dia some; um erro real volta no simulado seguinte.

---

## 1. Status atual

**Atualizado em 04/11.** Prova em **30/11**. Semana 9, fechada: `labs/semana-09.md`. De 05/11 em diante: `labs/operacao-pratica.md` (calendário refeito em 04/11, com carga maior e por igual em todos os dias).

### Concluído

| Item | Situação |
|---|---|
| **Semana 0 — Laboratório** | Concluída em 26/08 — VM, SSH, snapshot, repositório |
| **Semana 1 — Tópico 1 (peso 7)** | Concluída em 05/09 — comunidade, licenças, distros, FHS |
| **Semanas 2 e 3 — Tópico 2 (peso 9)** | Concluídas em 13/09 e 19/09 — os quatro objetivos |
| **Semana 4 — Objetivos 3.1 e 3.2** | Fechada em 29/09 — 24 correções (29 a 52) |
| **Semana 5 — Objetivo 3.3** | Laboratório 1 e exercício das frutas em 04/10; Correções 60 e 61 |
| **Semana 6 — abertura do Tópico 5** | Simulado 01 (05/10: 28 de 40, 23 firmes); Laboratório 2; curso até a aula 40 (09/10); Correções 62 a 74 |
| **Semana 7 — Tópico 5 em prática** | Autoavaliação da Semana 5 (9 de 10); Prática 1 (usuários e grupos); Correção 75 |
| **Semana 8 — Tópico 5 e simulado 02** | Prática 2 (permissões); Exercícios da LPI 5.1 a 5.4; simulado 02 (23/10: **22 de 40, 17 firmes**) |
| Autoavaliações | Semana 2: 14 de 15 · Semana 3: 20 de 20 · Semana 4: 14 de 20 · Semana 5: 9 de 10. Encerradas: daqui em diante, os simulados medem |
| Bandit | Níveis 0 a 9 |
| Cards de revisão (Notion) | Cards 60 a 70 em 22/10; daqui em diante, só para reincidências |

### O que falta estudar

O Tópico 4 está praticado: Práticas 3, 4 e 5 feitas até 02/11 e anotadas até 03/11. Falta o que está nos primeiros dias da operação prática:

| Item | Peso | Quando |
|---|---|---|
| **Curso, aulas 41 a 72** | — | À noite: 41 a 52 na qui 05/11, 53 a 62 na sex 06/11, 63 a 72 no sáb 07/11 (curso fechado) |
| **4.1 Sistemas operacionais** e here document | 1 | Sex 06/11, antes do R3 |
| **Exercícios da LPI de todas as 24 lições** (cerca de 205) | — | Um ou dois blocos por dia, de 05 a 20/11, e revisão das erradas de 21 a 25/11 (`labs/simulados-práticos.lpi/exercicios-lpi.md`) |

### Voucher e agendamento

| Item | Situação |
|---|---|
| Data da prova | **30/11/2026, segunda-feira** |
| Exame a escolher | **010-160** (versão 1.6), e não o 010-200 |
| Agendamento | Registrar aqui a confirmação: centro ____________ · horário ____________ · janela de remarcação sem custo ____________ |

Se a prova já estava agendada para 23/11, remarque para 30/11 respeitando a janela de remarcação sem custo da Pearson VUE. Se ainda não foi agendada, agende direto para 30/11.

### Cobertura estimada por tópico

| Tópico | Peso | Cobertura |
|---|---|---|
| 1. Comunidade e open source | 7 | 100% |
| 2. Encontrando seu caminho | 9 | 100% |
| 3. Poder da linha de comando | 9 | 100% (here document como conceito na qui 29/10) |
| 4. Sistema operacional | 8 | 30% → 100% até 30/10 |
| 5. Segurança e permissões | 7 | 100% (Práticas 1 e 2 e Exercícios da LPI) |

**Progresso geral: aproximadamente 85% do conteúdo da prova.** Falta o Tópico 4, nesta semana. Estudado não é fixado: o simulado 02 mostrou erros justamente nos Tópicos 2 e 5, já estudados. A fixação é o trabalho da operação prática.

---

## 2. Dados do exame

| Item | Valor |
|---|---|
| Código | **010-160, versão 1.6** (disponível até abril de 2027; a versão atual é a 2.0, exame 010-200) |
| Questões / tempo | 40 questões em 60 minutos |
| Formato | Múltipla escolha e preenchimento |
| Nota de corte | Referência comum: 500 de 800 (~65%), ou 26 acertos |
| Idioma | Português (Brasil) disponível |
| Validade | Vitalícia |
| Entrega | Centro Pearson VUE ou OnVUE |

> **Atenção ao agendar (conferido no site da LPI em 21/10):** a LPI lançou a versão 2.0 do Linux Essentials, exame **010-200**. Este plano cobre a **1.6, exame 010-160**, que continua disponível até abril de 2027. Na Pearson VUE, escolha o **010-160**.
>
> Recomendação: **centro Pearson VUE**, não OnVUE. O check-in remoto é rigoroso e um problema técnico queima o voucher.

### Pesos dos tópicos

| Tópico | Peso | Onde é tratado |
|---|---|---|
| 2. Finding Your Way on a Linux System | **9** | Concluído nas Semanas 2 e 3 |
| 3. The Power of the Command Line | **9** | Semanas 4 e 5 (concluído) |
| 4. The Linux Operating System | **8** | Semana 9 (Práticas 3, 4 e 5) |
| 1. The Linux Community and a Career in Open Source | 7 | Concluído na Semana 1 |
| 5. Security and File Permissions | 7 | Semanas 6 e 7 (Práticas 1 e 2) |

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
| **`labs/simulados-práticos.lpi/` deste repositório** | — | Simulados próprios, com peso do exame e gabarito comentado. As questões atacam os erros já registrados nos cadernos. Calendário na seção 7 e em `labs/operacao-pratica.md` |
| **NDG Linux Essentials** (Cisco Networking Academy) | Gratuito | Quizzes por módulo e exame final de prática. A melhor fonte externa gratuita |
| **LPI Learning Materials** (PDF no Projeto) | Gratuito | Exercícios Guiados e Exploratórios de cada lição, com respostas. É o único material de questões **escrito pela própria LPI** |
| **EDUSUM** | Gratuito | Amostra de questões no estilo LPI |

**Questões reais da LPI (decisão de 06/10).** Não encontrei simulado oficial gratuito da LPI para o 010-160; o material que a LPI divulga é o Learning Material. As questões "reais do exame" que circulam são vazadas. Por isso a prática com questões da LPI usa os **Exercícios Guiados e Exploratórios do PDF**, e a dificuldade do exame é aproximada pelos simulados escritos para o plano e pelo NDG.

Sites de dumps — ITExams, Marks4Sure, Pass4Success e semelhantes — estão fora do plano: violam o termo de confidencialidade assinado antes da prova, os gabaritos são reconstruídos de memória por terceiros e o método é o oposto do que vem funcionando aqui. Detalhes em `praticas/fontes-de-simulados.md`.

### Recursos complementares

| Recurso | Para quê |
|---|---|
| **LPI Learning Materials** (learning.lpi.org) | Material oficial, escrito objetivo por objetivo, com tradução PT-BR |
| **OverTheWire — Bandit** | Níveis 0 a 9 concluídos; 10 a 20 são bônus, não obrigatórios |
| **Notion** (cards próprios) | Cards das reincidências (regra de 26/10) |
| **explainshell.com** | Explica cada flag de um comando complexo |
| **tldr / tealdeer** | Exemplos práticos, complemento ao `man` |

---

## 6. Método de estudo

**Revisado em 26/10.** Duas fases, nenhuma pendência.

### Fase 1 — Conteúdo (26/10 a 06/11)

| Elemento | Como |
|---|---|
| Tópico 4 | Práticas 3, 4 e 5, **feitas até 02/11**: 45 min de teclado, 10 de registro, 5 de commit, **prevendo a saída antes de executar** |
| Aulas do curso | À noite: 41 a 52 na quinta 05/11, 53 a 62 na sexta 06/11, 63 a 72 no sábado 07/11. Anotações no caderno, repassadas aqui como sempre |
| 4.1 e here document | Sex 06/11, antes do R3 |
| Velocidade do curso | **2x** onde o vídeo repete o que já foi praticado, o que agora vale para quase todo o restante, inclusive o Tópico 4 |
| O que não fechar | Aula que não couber vai para o domingo 08/11. Nenhum outro item vira pendência |

### Fase 2 — Operação prática (05/11 a 26/11)

Detalhe completo em `labs/operacao-pratica.md`. O resumo:

| Elemento | Como |
|---|---|
| **Dia A** | Lacunas (5 min) · simulado completo (60 min) · correção (20 min) · treino na VM sobre os erros (25 min) · 1 bloco da LPI (25 min) · cerca de 2h15 |
| **Dia B** | Lacunas (5 min) · mini-simulado de 20 questões (25 min) · correção (10 min) · treino na VM (30 min) · 2 blocos da LPI (50 min) · cerca de 2h |
| **Exercícios da LPI** | As 24 lições do material oficial, um bloco por dia, respondidos sem consulta e conferidos no PDF (`labs/simulados-práticos.lpi/exercicios-lpi.md`) |
| **Descanso** | Domingos 08, 15 e 22/11, e de 27 a 29/11 |
| **Correção** | No mesmo dia, com tempo-limite. Erro de comando é **executado na VM**, não só lido |
| **Notion** | Card só para **reincidência**, um erro que já aconteceu antes |
| **Medida** | Acertos **firmes**, sem chutes e sem pesquisas |

### Por que mudou

Em outubro, o plano funcionava com "dívidas": o que não era feito no dia virava pendência para a semana seguinte. Na prática, as pendências se acumularam (o simulado 02 mudou de data quatro vezes), pagá-las virou tarefa burocrática e o rendimento caiu: de 23 para 17 acertos firmes entre os simulados 01 e 02. E escrever a correção não fixou: quatro das nove questões que retestavam correções antigas voltaram a errar.

A operação prática troca o acúmulo por repetição diária. Se um erro é real, ele reaparece no simulado seguinte e é corrigido ali, com o contexto fresco.

### O que continua valendo

1. **Digitar, nunca copiar.** Na VM, todo comando é digitado.
2. **Prever antes de executar.** A previsão errada é o que ensina.
3. **Quebrar coisas de propósito.** O snapshot `limpo` existe para isso.
4. **Correções numeradas** continuam só para erros de laboratório e de curso nesta semana; a próxima é a **76**. Erro de simulado não gera correção numerada.
5. **Formato das lacunas:** escrever só o comando, sem caminho, sem `sudo` e sem opções, salvo se pedido. Dois pontos se perderam por isso no simulado 02.

### Dicas recorrentes de prova (06/10)

Dicas de candidatos, de fonte não oficial, conferidas contra o PDF da LPI: permissões (r = 4, w = 2, x = 1), `tar` e compressão, redirecionamento (`>`, `>>`, `2>`, `<<`), diretórios `/proc`, `/sys`, `/dev` e `/var`, e **atenção às questões de preencher a lacuna**. Todas constam do material oficial. Na operação prática elas entram de três formas: (1) **mínimo de questões por tema em todo simulado**: permissões 4, `tar` 2, redirecionamento 3, diretórios 3, **lacunas 5**; (2) os **mini-simulados R1 a R4**; (3) o **banco de lacunas** do aquecimento diário. Detalhe em `labs/simulados-práticos.lpi/praticas_simulados.md`.

---

## 7. Cronograma até a prova (revisado em 26/10)

Semanas de **segunda a domingo**. A prova é na **segunda-feira 30/11**. O histórico das Semanas 1 a 8 está em `labs/semana-01.md` a `labs/semana-08.md`.

### Visão geral

| Fase | Período | Arquivo | Foco |
|---|---|---|---|
| **1. Conteúdo** | 26/10 a 06/11 | `labs/semana-09.md` e `labs/operacao-pratica.md` | Tópico 4 em três práticas (feitas até 02/11) · aulas 41 a 72 em 03 e 04/11 · 4.1 em 06/11 |
| **2. Operação prática** | 05/11 a 26/11 | `labs/operacao-pratica.md` | Todos os dias: simulado ou mini-simulado, lacunas, treino na VM e correção no mesmo dia |
| **Descanso** | 27/11 a 29/11 | — | Sem estudo |
| **Prova** | **Seg 30/11** | — | — |

### A conta

| Item | Número |
|---|---|
| Aulas restantes do curso | 32 (41 a 72), à noite, de 05 a 07/11 |
| Práticas de laboratório restantes | Nenhuma: as três do Tópico 4 foram feitas até 02/11 |
| Dias de operação prática | 19, de 05 a 26/11, com os domingos de descanso |
| Simulados completos | 10 (03 a 12) |
| Mini-simulados | 10 (R1 a R4 e M1 a M6) |
| Exercícios da LPI | 24 lições, cerca de 205 exercícios, de 05 a 20/11, e revisão das erradas de 21 a 25/11 |
| Lacunas | 21 séries de cinco (105 questões) |

### Datas do calendário que afetam o plano

| Data | Evento | Efeito |
|---|---|---|
| Sex 20/11 | Consciência Negra (feriado) | Dia normal da operação (tipo B) |
| Seg 30/11 | **Prova** | Não cai em feriado |

### Semana 9 — 26/10 a 01/11 · Tópico 4

Refeita em 29/10 e fechada em 02/11.

| Dia | Atividade |
|---|---|
| Seg 26 a qui 29 | Prática 3, bloco 1 |
| Sex 30 | Prática 3, blocos 2 a 4 |
| Sáb 31 | Descanso |
| Dom 01 e seg 02/11 | Práticas 4 e 5 |

### Semanas 10 a 13 — 05/11 a 29/11 · Operação prática

Refeita em 04/11: carga de cerca de 2h a 2h15 em todos os dias (perto de 13h por semana), com treino na VM e Exercícios da LPI todos os dias.

| Semana | Dias A (simulados) | Dias B (mini-simulados) |
|---|---|---|
| 10 (05 a 08/11) | 03 (com o R4, o que ficou de 03 e 04/11), 05 | R3 (com o 4.1 e o here document) · aulas 41 a 72 à noite, de quinta a sábado |
| 11 (09 a 15/11) | 04, 06, 07 | R2, R1, M1 |
| 12 (16 a 22/11) | 08, 09, 10 (decisão) | M2, M3, M4 |
| 13 (23 a 29/11) | 11, 12 (final, 25/11) | M5 · M6 no dia leve, 26/11 · descanso de 27 a 29/11 |

Calendário dia a dia, metas e registro em `labs/operacao-pratica.md`; visão de mês em `labs/calendario.md`.

### Série de simulados

| # | Data | Fonte | Meta de acertos firmes |
|---|---|---|---|
| 1 | Seg 05/10 | `simulado-01` | **Feito: 28 de 40, 23 firmes** |
| 2 | Sex 23/10 | `simulado-02` | **Feito: 22 de 40, 17 firmes** |
| 3 | **Qui 05/11** | `simulado-03` (pronto) | Linha de base |
| 5 | Sáb 07/11 | `simulado-05` (pronto) | 24 ou mais |
| 4 | Ter 10/11 | `simulado-04` (pronto; substitui o exame do NDG) | 24 ou mais |
| 6 | Qui 12/11 | `simulado-06` | 28 ou mais |
| 7 | Sáb 14/11 | `simulado-07` | 28 ou mais |
| 8 | Ter 17/11 | `simulado-08` | 28 ou mais |
| 9 | Qui 19/11 | `simulado-09` | 30 ou mais |
| 10 | **Sáb 21/11** | `simulado-10` | 30 ou mais · **decisão da data** |
| 11 | Seg 23/11 | `simulado-11` | 30 ou mais |
| 12 | **Qua 25/11** | `simulado-12` | **30 ou mais** (final) |

**Regras da série.** Cronometrado, sem consulta (questão **pesquisada** conta como errada), marcando cada chute; pelo menos 45 minutos de uso, com segunda passada; apuração por tópico e por tema; só se anotam as questões erradas e as chutadas. Cada simulado traz o mínimo por tema das dicas recorrentes. Os simulados escritos aqui ficam prontos **três dias antes** do uso.

---

## 8. Riscos e como são mitigados

| Risco | Por que existe | Mitigação |
|---|---|---|
| **A semana de conteúdo escorregar** | Aconteceu em todas as semanas desde 13/10 | Sexta 30/10 como reserva; o que não fechar não vira pendência, e a operação começa no sábado |
| **Assistir sem praticar** | O vídeo produz reconhecimento, não competência | Cada tema do Tópico 4 tem a sua prática logo depois das aulas |
| **Simular muito e corrigir pouco** | Um simulado mede; quem ensina é a correção | Dias A e B alternados; correção no mesmo dia, executando na VM; mini-simulados escritos sobre os erros |
| **Erros que voltam** | Quatro das nove correções antigas voltaram no simulado 02 | Lista de reincidências com treino na VM para cada uma; card no Notion só para elas |
| **Cansaço** | Todos os dias até a prova | Sessões de 1h10 a 1h25; domingo de descanso; três dias sem estudo antes da prova |
| **Erro de forma nas lacunas** | Duas questões perdidas no simulado 02 com a resposta certa escrita errado | Cinco lacunas por dia, com a regra de forma |

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

Atualizado em 23/10 com o simulado 02, em que **quatro das nove questões que retestavam correções antigas voltaram a errar**. Desde 26/10, esta lista é a **lista de reincidências** da operação prática (`labs/operacao-pratica.md`, seção 6): cada item tem um treino na VM, e a revisão leve de 25 e 26/11 passa por ela.

| Erro | Vezes | Correção |
|---|---|---|
| `sort` sem `-n` descrito como "invertendo a ordem" | **4** (Correções 32, 33/34 e 50) | As duas formas são **crescentes**; só o `-r` inverte. `-k` é **coluna**, vem de *key*. Reler não resolveu: o que resolve é executar os quatro comandos lado a lado |
| `cd ..` e `cd -` trocados | **5** (a quarta em 30/09, Correção 53; a quinta em 05/10, Correção 64, agora com o `cd -` chamado de "pai") | `cd ..` é **pai** (espaço); `cd -` é **anterior** (tempo). O simulado mede se voltou |
| Confundir o efeito com o mecanismo (`2>&1`, hard link, `-f` do `tar`) | 3 | O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |
| `grep -v` entendido como *verbose* ou como outra opção | **2** (Correção 49; Q22 do simulado 02, respondida com `-n`) | É *invert*. O `grep` é a exceção: em `tar`, `cp`, `rm` e `mv` o `-v` é verbose |
| Ordem do `2>&1` | **2** (Correção 29; Q19 do simulado 02) | Da esquerda para a direita: `> arq 2>&1`. O `2>&1` copia o destino **atual** da saída padrão |
| `/home` tratado como a pasta pessoal | **2** (Correção 54; Q9 do simulado 02) | `/home` contém as pastas pessoais; a pessoal é `~` |
| `$#` (quantidade de argumentos) | **2** (Q6 da autoavaliação da Semana 5; Q24 do simulado 02) | `$#` conta; `$1`, `$2` são os valores; `$0` é o nome do script e não conta |
| O `x` do segundo campo do `/etc/passwd` | **2** (Q35 do simulado 01, sobre o mesmo arquivo; Q34 do simulado 02) | Só indica que o hash está no `/etc/shadow`. Administrador é o UID 0 |
| Direção da herança de variáveis (pai para filho) e `{}` tratado como globbing | **2 cada** (Correções 12 e 71; Correções 11 e 70) | Variável exportada vai para o **processo filho**, nunca para o que está ao lado ou acima; `{1,2}` expande antes e sem olhar o disco, o globbing só vê o que já existe |

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
| 1 | **LPI Linux Essentials** (010-160) | Em preparação — prova em 30/11/2026 |
| 2 | **GitHub Foundations** | Na sequência, em dezembro |
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

## 11. A data da prova

**Revisada em 26/10.** A prova passou de 23/11 para **30/11**. Os checkpoints A, B, Gate e Final saíram do plano: eram critérios demais para acompanhar, e a semana extra é de prática, não de conteúdo.

### Por que 30/11

| Medida | Situação em 26/10 |
|---|---|
| Acertos firmes | 23 no simulado 01 e 17 no simulado 02. O corte do exame é 26 |
| Conteúdo | O Tópico 4 (8 das 40 questões) só fecha em 29/10 |
| Prática com 23/11 | Cerca de 20 dias, sem margem se a semana de conteúdo atrasar |
| Prática com 30/11 | 19 dias de operação, de 05 a 26/11, mais três de descanso |
| Validade do exame 010-160 | Até abril de 2027: a semana a mais não tem custo de versão |

### A única decisão que resta

**Sábado 21/11, depois do simulado 10**, com a média de acertos firmes dos simulados 08, 09 e 10:

| Média | Decisão |
|---|---|
| **26 ou mais** | Vai em 30/11 |
| **Abaixo de 26** | Remarcar. Antes de escolher a nova data, revemos o método com os números na mão |

### Voucher e agendamento

- Exame **010-160**, em **centro Pearson VUE**, não OnVUE: o check-in remoto é rigoroso, e um problema técnico queima o voucher.
- Confira no site da Pearson VUE a janela de remarcação sem custo e registre-a na seção 1. Eu não conheço esse valor.

### Histórico das decisões

Em 08/10 a compra do voucher foi adiada; em 10/10 a data principal passou a 16/11; em 13/10 a prova foi fixada em 23/11; em 19/10 o Checkpoint A deu vermelho; em 23/10, com o simulado 02 em 22 de 40, o Tópico 4 foi para a Semana 9; **em 26/10 a estratégia mudou para conteúdo seguido de operação prática diária, as dívidas e os checkpoints saíram do plano, e a prova passou para 30/11.** Em 29/10, as Práticas 4 e 5 e o simulado 03 foram para o domingo 01/11, o sábado 31/10 virou descanso e as aulas 41 a 72 foram para a Semana 10. Em 02/11, com as Práticas 4 e 5 feitas, o simulado 03 passou para a terça 03/11, a operação andou dois dias, o simulado 13 saiu e a decisão da data passou para o sábado 21/11. Em 04/11, o que não saiu em 03 e 04/11 foi para o dia 05, a carga diária subiu para cerca de 2h a 2h15 em todos os dias e a decisão passou a usar os simulados 08, 09 e 10.

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