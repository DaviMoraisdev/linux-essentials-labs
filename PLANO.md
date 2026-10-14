# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** cerca de 9h/semana até a prova
**Data da prova:** **23/11/2026, segunda-feira** (definida em 13/10; seção 11)
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> **Atualização de 13/10 — nova estratégia até 23/11.** A prova passou para **segunda 23/11**. O plano tem agora três etapas: (1) **pagar as dívidas** escolhidas (Práticas 1 e 2, simulado 02, autoavaliações das Semanas 5 e 6) até o domingo 18/10; (2) **estudar o conteúdo que falta**, com o curso fechado até 18/10 e o Tópico 4 em três práticas de laboratório na Semana 8; (3) **simulados** de 23/10 a 19/11. As dívidas antigas sem motivo para serem feitas agora saíram do plano. Detalhe na seção 1, no cronograma (seção 7) e em `labs/semana-07.md`.
>
> **Estratégia revisada em 26/09.** O cronograma tem **duas fases**: três semanas com o curso como atividade principal e duas práticas por semana, seguidas de três semanas de prática intensiva e simulados. Detalhamento na seção 7.
>
> **Atualização de 02/10, à noite.** Três mudanças: (1) **simulado geral de 40 questões todo domingo**, a partir de 04/10 (seção 7); (2) o fechamento da Semana 5 passa para o **domingo 04/10** (Laboratório 1 e simulado #1), e o Laboratório 2 e as aulas 31 a 43 passam para a Semana 6 (`labs/semana-06.md`); (3) nova **regra de adiamento da prova**, com checkpoints e datas alternativas (seção 11).
>
> **Atualização de 06/10.** O **Laboratório 2 foi concluído** (três scripts, sem erro conceitual). Com ele, as duas condições do pré-checkpoint estão cumpridas: na quarta 07/10, comprar o voucher e agendar **09/11**. Três decisões novas: (1) **erros antigos de comandos já dominados vão para a retaguarda** e saem do aquecimento (seções 6 e 9); (2) nos simulados, **só se anotam as questões erradas** e a correção fica no Notion; (3) **mais prática de simulado**, com questões da LPI no fim das Práticas 1 e 2 e simulados mais difíceis (seções 5 e 7).
>
> **Atualização de 05/10.** O **simulado #1 foi feito: 28 de 40 (70%), 560 de 800**, acima do corte, mas com 5 acertos por chute (23 firmes). Tópico 3 em 9 de 9; seis dos sete erros com convicção caíram nos Tópicos 1 e 2. Correções 62 a 68 em `labs/semana-06.md`. Falta o Laboratório 2 (terça 06/10) para o pré-checkpoint de quarta.

> **Atualização de 04/10.** O Laboratório 1 e o exercício das frutas foram concluídos. O **simulado #1 passou para a segunda 05/10**, o Laboratório 2 para a terça 06/10 e as aulas 31 a 43 para a quarta 07/10. A Semana 6 foi reorganizada (`labs/semana-06.md`). Um novo **pré-checkpoint, na quarta 07/10**, decide se a prova é agendada para 09/11 ou direto para 16/11 (seção 11).
>
> **Calendário da Semana 5 revisado em 29/09.** O curso foi adiado na segunda e na terça. As 18 aulas restantes da semana passam a ser cumpridas em dois blocos, na quarta e na quinta, sem mover os laboratórios nem o simulado. Detalhamento na seção 7 e no arquivo `labs/semana-05.md`.

---

## 1. Status atual

**Atualizado em 13/10.** Prova em **23/11**. Detalhe da semana em `labs/semana-07.md`.

### Concluído

| Item | Situação |
|---|---|
| **Semana 0 — Laboratório** | Concluída em 26/08 — VM, SSH, snapshot, repositório |
| **Semana 1 — Tópico 1 (peso 7)** | Concluída em 05/09 — comunidade, licenças, distros, FHS |
| **Semanas 2 e 3 — Tópico 2 (peso 9)** | Concluídas em 13/09 e 19/09 — os quatro objetivos |
| **Semana 4 — Objetivos 3.1 e 3.2** | Fechada em 29/09 — 24 correções (29 a 52) |
| **Semana 5 — Objetivo 3.3** | Laboratório 1 e exercício das frutas em 04/10; Correções 60 e 61 |
| **Semana 6 — abertura do Tópico 5** | Simulado 01 (05/10: 28 de 40); Laboratório 2 (06/10: três scripts); aquecimento de conversões (07/10: 5 de 5, com estudo prévio); curso até a aula 40 (09/10); Correções 62 a 74 |
| Autoavaliações | Semana 2: 14 de 15 · Semana 3: 20 de 20 · Semana 4: 14 de 20 |
| Bandit | Níveis 0 a 9 |
| Cards de revisão (Notion) | Em uso desde a Semana 1 |

### Dívidas a pagar — Etapa 1, de 13/10 a 18/10

As únicas dívidas que continuam no plano. Depois delas, o plano só tem conteúdo não estudado e simulados.

| Dívida | Roteiro | Data |
|---|---|---|
| Autoavaliação da Semana 5 (10 questões, shell script) | `labs/semana-06.md` | Ter 13/10, primeira atividade |
| Prática 1 — usuários e grupos, com Exercícios da LPI 5.1 e 5.2 | `labs/semana-06.md` | Ter 13/10 |
| Prática 2 — permissões, com Exercícios da LPI 5.3 e 5.4 | `labs/semana-06.md` | Qua 14/10 |
| Simulado 02 (40 questões) | `labs/simulados-práticos.lpi/simulado-02.md` | Sáb 17/10 |
| Autoavaliação da Semana 6 (10 questões, Tópico 5) | `labs/semana-07.md`, seção 7 | Dom 18/10, primeira atividade |

### Conteúdo ainda não estudado — Etapa 2, de 15/10 a 25/10

| Item | Quando |
|---|---|
| **Curso, aulas 41 a 72** (32 aulas; último registro na 40) | 41 a 57 em 15 e 16/10; 58 a 72 em 17 e 18/10 |
| **Tópico 4** — Práticas 3 (hardware, discos, diretórios), 4 (processos, memória, logs) e 5 (rede) | 19, 20 e 21/10 |
| 4.1, here document (`<<`) e quizzes do NDG | 22/10 |

A lista completa, objetivo por objetivo, está em `labs/semana-07.md`, seção 2.

### Retirado do plano em 13/10

Comparação de compressão com o `bzip2`; registro das saídas do `teste.sh`, do `vi` e do `nano`; `filtrar.sh`; retestes da autoavaliação da Semana 4 e das questões 18, 20, 21, 22 e 24 do simulado 01; revisão prática dos erros do simulado 01; `.wslconfig`; teste de restauração do snapshot; laboratório integrador da Semana 9; cards das Correções 69 a 74 como pendência do plano. Motivo e detalhe em `labs/semana-07.md`, seção 4. O que esses itens mediam continua sendo medido pelos simulados.

### Voucher e agendamento

| Item | Situação |
|---|---|
| Data da prova | **23/11/2026, segunda-feira** |
| Agendamento | Registrar aqui a confirmação: centro ____________ · horário ____________ · janela de remarcação sem custo ____________ |

### Cobertura estimada por tópico

| Tópico | Peso | Cobertura |
|---|---|---|
| 1. Comunidade e open source | 7 | 100% |
| 2. Encontrando seu caminho | 9 | 100% |
| 3. Poder da linha de comando | 9 | 100% (falta o here document como conceito, 22/10) |
| 4. Sistema operacional | 8 | 30% |
| 5. Segurança e permissões | 7 | 20% (conversões praticadas; Práticas 1 e 2 em 13 e 14/10) |

**Progresso geral: aproximadamente 70% do conteúdo da prova.**

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
| 3. The Power of the Command Line | **9** | Semanas 4 e 5 (concluído) |
| 4. The Linux Operating System | **8** | Semana 8 (Práticas 3, 4 e 5) |
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
| **`praticas/` deste repositório** | — | Simulados próprios, com peso do exame e gabarito comentado. As questões atacam os erros já registrados nos cadernos. Série dominical: ver seção 7 |
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

**Desde 06/10, o aquecimento só carrega conteúdo atual.** Erros antigos de comandos já dominados vão para a retaguarda (seção 9) e saem daqui, porque competiam com o conteúdo novo da prova. Abaixo, o texto original de 28/09, que vale para o conteúdo da semana.

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

**Regra de 07/10 — aquecimento depois do conteúdo.** O aquecimento de permissões da Semana 6 pedia conversão de memória antes de o assunto ser ensinado (as aulas e a Prática 2 vêm depois). Você estudou por conta própria na quarta 07/10, e o resultado de 5 de 5 conta como **estudo**, não como retenção. A regra passa a ser: a primeira aparição de um assunto no aquecimento é leitura de 5 minutos mais cinco questões, e o reteste cego vem no dia seguinte. A régua de 3 segundos só vale para o que já foi estudado. Vale para todo tópico novo, inclusive os da Semana 7.

### Quando responder a autoavaliação

**Regra alterada em 29/09.** As autoavaliações das Semanas 2 e 3 foram respondidas no mesmo dia do último laboratório e deram 14 de 15 e 20 de 20. A da Semana 4 foi respondida quatro dias depois e deu 14 de 20 — com todos os quatro conceitos errados já registrados corretamente no caderno, dias antes.

As duas primeiras notas mediam memória de curto prazo. A terceira mediu retenção, que é o que a prova mede.

**Da Semana 5 em diante, a autoavaliação de cada semana é respondida na semana seguinte**, em um dia de curso, como abertura da sessão. O intervalo mínimo é de três dias. Uma nota menor e honesta informa o plano; uma nota alta e cedo apenas o tranquiliza. A autoavaliação da Semana 5 é elaborada na quinta 08/10 e respondida na **sexta 09/10**, em versão reduzida de 10 questões, três dias depois do Laboratório 2, que foi transferido para a terça 06/10.

### As sessões de laboratório

Sem vídeo dentro delas — o vídeo agora tem espaço próprio. A sessão inteira é teclado:

1. **45 min de laboratório** — reproduzir tudo na VM, **digitando**, nunca copiando e colando
2. **10 min de registro** — anotar no caderno o comando, o que faz e o exemplo executado
3. **5 min** — commit no repositório

**Quebrar coisas de propósito** continua valendo. O snapshot `limpo` existe para isso.

### A fila de dívidas

**Regra de 13/10:** depois de pagas as dívidas da Etapa 1, a fila só recebe conteúdo da prova ainda não estudado e simulados. O texto abaixo é o original.

Item adiado não some. Ele entra no início do próximo bloco de estudo e fica registrado na tabela de dívidas do arquivo da semana. Adiar tem custo visível: a Semana 5 subiu de 5h para cerca de 6h45 depois de dois dias de curso perdidos.

### A retaguarda de erros antigos

**Atualização de 13/10:** os itens de ambiente e de registro retroativo que estavam na retaguarda saíram do plano (seção 1). Ficam só os erros de conteúdo, medidos pelos simulados. Abaixo, o texto de 06/10.

**Regra de 06/10.** Erros de comandos passados e já dominados deixam de ocupar o aquecimento, as pendências e a rotina diária. Ficam numa fila de retaguarda (seção 9) e voltam em dois momentos: **nos simulados**, que continuam testando esses pontos de forma natural, e na **revisão leve da Semana 10**, pelos cards do Notion. O que não vai para a retaguarda é o conteúdo **atual**: Tópico 5 agora, Tópico 4 em seguida.

### Dicas recorrentes de prova (06/10)

Dicas de candidatos, de fonte não oficial, conferidas contra o PDF da LPI: permissões (r = 4, w = 2, x = 1), `tar` e compressão, redirecionamento (`>`, `>>`, `2>`, `<<`), diretórios `/proc`, `/sys`, `/dev` e `/var`, e **atenção às questões de preencher a lacuna**. Todas constam do material oficial. O plano já cobria permissões, `tar` e `/proc` e `/dev`; as lacunas reais eram o `<<` como conceito, o `/sys` e o **formato de lacuna**, nunca treinado (a Q11 do simulado #1 foi respondida com um sublinhado na frente de `PATH`).

Como entram, sem aumentar a carga: (1) **mínimo de questões por tema em todo simulado a partir do #2**: permissões 4, `tar` 2, redirecionamento 3 (com `<<`), diretórios 3, **lacunas 5**; (2) **mini-simulados de reforço de 20 questões e 25 minutos**: R1 na sexta 23/10 e R2 na terça 27/10 (datas de 13/10); (3) a partir de 26/10, o aquecimento diário gira pelas cinco frentes (segunda permissões, terça `tar`, quarta redirecionamento, quinta diretórios, sexta lacunas). O detalhe, a cola e o R1 com gabarito estão em `praticas-reforco-dicas-recorrentes.md`; o desempenho por tema é registrado em `praticas-resultados-simulados-e-correcoes.md`.

### O simulado dominical

**Atualização de 13/10:** a série deixou de ser só dominical. Da Semana 9 em diante há dois ou três simulados por semana; as datas estão na seção 7.

**Regra criada em 02/10:** todo domingo, um simulado geral de 40 questões, 60 minutos, sem consulta, com a distribuição de pesos do exame. É o termômetro semanal e o treino da condição de prova. A série completa, com datas, fontes e metas, está na seção 7.

1. Cronometrado, sem terminal, sem caderno, sem internet.
2. **Marcar cada chute**, mesmo acertando.
3. Apuração **por tópico** e **lista das questões erradas e das chutadas**, com o tópico de cada uma. **Desde 06/10 não se abre correção numerada para erro de simulado:** a correção fica por conta dos seus cards no Notion.
4. Cada simulado é um conjunto **novo**. As questões erradas voltam só pelo aquecimento, nunca refazendo o simulado inteiro.
5. O resultado entra na tabela da série e alimenta os checkpoints da seção 11.
6. Carga: cerca de 1h35 por domingo (60 min de prova, 20 a 25 de apuração, commits).
7. **Exceção:** a véspera da prova (domingo 22/11) não tem simulado. O final é na quinta 19/11.
8. **Dificuldade (06/10):** do #2 em diante os simulados escritos aqui ficam mais próximos do exame: enunciados com cenário, pegadinhas de comando, escolha de mais de uma resposta, preenchimento e distratores plausíveis. Use pelo menos 45 minutos e reserve os últimos 15 para uma segunda passada nas marcadas.

**Relação com a autoavaliação semanal (13/10).** As autoavaliações das Semanas 5 e 6 são dívidas da Etapa 1: a da Semana 5 na terça 13/10 e a da Semana 6, **devolvida ao plano em 13/10**, no domingo 18/10. A partir da Semana 8, com os cinco tópicos estudados, o simulado substitui a autoavaliação.

---

## 7. Cronograma até a prova (revisado em 13/10)

Semanas de **segunda a domingo**. A prova é na **segunda-feira 23/11**, depois do fim da Semana 12. O histórico das Semanas 1 a 6 está nos arquivos `labs/semana-01.md` a `labs/semana-06.md`; esta seção só trata do que vem pela frente.

### Visão geral

| Etapa | Semanas | Período | Foco |
|---|---|---|---|
| **1. Dívidas** | 7 | 13/10 a 18/10 | Práticas 1 e 2, simulado 02, autoavaliações das Semanas 5 e 6 · curso até a aula 72 em paralelo |
| **2. Conteúdo não estudado** | 7 e 8 | 15/10 a 25/10 | Curso fechado · Tópico 4 em três práticas de laboratório · 4.1 e here document |
| **3. Simulados** | 8 a 12 | 23/10 a 19/11 | Um simulado completo a cada dois ou três dias · revisão dirigida só nos erros · revisão leve na última semana |
| **Prova** | — | **Seg 23/11** | — |

### A conta

| Item | Número |
|---|---|
| Semanas até a prova | 6 (de 13/10 a 22/11) |
| Aulas restantes do curso | 32 (41 a 72), todas na Semana 7 |
| Práticas de laboratório restantes | 5 (Práticas 1 e 2 do Tópico 5; Práticas 3, 4 e 5 do Tópico 4) |
| Simulados completos | 10 (02 a 11), mais os reforços R1 e R2 |
| Semanas só de simulados | 4 (9 a 12) |
| Meta semanal | cerca de 9h, com 1h por dia útil e blocos maiores no fim de semana |

### Datas do calendário que afetam o plano

| Data | Evento | Efeito |
|---|---|---|
| Qua 28/10 | Dia do Servidor Público | Sem efeito |
| Seg 02/11 | Finados (feriado) | Dia livre na Semana 10; nada é agendado nele |
| Sex 20/11 | Consciência Negra (feriado) | Primeiro dia do descanso antes da prova |
| Seg 23/11 | **Prova** | Não cai em feriado |

### Série de simulados

Meta em acertos: 24 = 60%, 28 = 70%, 30 = 75%, 34 = 85%.

| # | Data | Semana | Fonte | Meta |
|---|---|---|---|---|
| 1 | Seg 05/10 | 6 | `simulado-01` | **Feito: 28 de 40 (70%), 23 firmes** |
| 2 | **Sáb 17/10** | 7 | `simulado-02` (pronto) | **24 ou mais** (Checkpoint A) |
| R1 | Sex 23/10 | 8 | Reforço, 20 questões (`praticas_simulados.md`) | 15 de 20 |
| 3 | **Dom 25/10** | 8 | `simulado-03` | **28 ou mais** (Checkpoint B) |
| R2 | Ter 27/10 | 9 | Reforço, 20 questões (a escrever até 24/10) | 15 de 20 |
| 4 | Qui 29/10 | 9 | Exame final de prática do NDG | 28 ou mais |
| 5 | Dom 01/11 | 9 | `simulado-05` | **30 ou mais** |
| 6 | Ter 03/11 | 10 | `simulado-06` | Acompanhar |
| 7 | Qui 05/11 | 10 | `simulado-07` | 34 ou mais |
| 8 | **Dom 08/11** | 10 | `simulado-08` | **34 ou mais** (Gate) |
| 9 | Ter 10/11 | 11 | `simulado-09` | 34 ou mais |
| 10 | Dom 15/11 | 11 | `simulado-10` | 34 ou mais |
| 11 | **Qui 19/11** | 12 | `simulado-11` | **34 ou mais** (final) |

**Gate:** dois simulados consecutivos com 34 ou mais entre o 06, o 07 e o 08.

**Regras da série.** Cronometrado, sem consulta, marcando cada chute; pelo menos 45 minutos de uso, com segunda passada; apuração por tópico e por tema; só se anotam as questões erradas e as chutadas, e a correção fica no Notion. Cada simulado traz o mínimo por tema das dicas recorrentes (permissões 4, `tar` 2, redirecionamento 3, diretórios 3, lacunas 5). Os simulados escritos aqui ficam prontos **três dias antes** do uso.

**Revisão dirigida.** Depois de cada simulado, no máximo 30 minutos, **só nos objetivos com erro**, de preferência executando na VM. Não se revisa o que já se acerta.

---

### Semana 7 — 12 a 18/10 · Etapa 1, dívidas, e fechamento do curso

**Arquivo detalhado:** `labs/semana-07.md`.

| Dia | Atividade |
|---|---|
| Ter 13 | Autoavaliação da Semana 5 · Prática 1 |
| Qua 14 | Prática 2 |
| Qui 15 | Curso, aulas 41 a 49 |
| Sex 16 | Curso, aulas 50 a 57 |
| Sáb 17 | **Simulado 02** · curso, aulas 58 a 64 |
| Dom 18 | Autoavaliação da Semana 6 · curso, aulas 65 a 72 · **Checkpoint A** |

### Semana 8 — 19 a 25/10 · Etapa 2, Tópico 4

**Roteiros:** `labs/semana-07.md`, seção 9. **Registro:** `labs/semana-08.md`.

| Dia | Atividade |
|---|---|
| Seg 19 | Prática 3 — hardware, discos e o mapa dos diretórios (4.2 e 4.3) |
| Ter 20 | Prática 4 — processos, memória e logs (4.3) |
| Qua 21 | Prática 5 — rede (4.4) |
| Qui 22 | Leitura do 4.1 · here document · quizzes do NDG dos Tópicos 4 e 5 |
| Sex 23 | **R1** |
| Sáb 24 | Reposição |
| Dom 25 | **Simulado 03** · **Checkpoint B** |

**Marco:** ao fim desta semana, o curso está fechado e os cinco tópicos foram estudados.

### Semana 9 — 26/10 a 01/11 · Etapa 3, simulados

| Dia | Atividade |
|---|---|
| Ter 27 | **R2** |
| Qui 29 | **Simulado 04** (exame final de prática do NDG) |
| Dom 01/11 | **Simulado 05** |
| Demais dias | Revisão dirigida dos erros (30 min) e aquecimento rotativo pelas cinco frentes |

### Semana 10 — 02 a 08/11 · Simulados e Gate

| Dia | Atividade |
|---|---|
| Seg 02 (feriado) | Livre |
| Ter 03 | **Simulado 06** |
| Qui 05 | **Simulado 07** |
| Dom 08 | **Simulado 08** · **Gate** |

### Semana 11 — 09 a 15/11 · Simulados

| Dia | Atividade |
|---|---|
| Ter 10 | **Simulado 09** |
| Dom 15 | **Simulado 10** |
| Demais dias | Revisão dirigida dos erros que se repetiram em dois simulados ou mais |

### Semana 12 — 16 a 22/11 · Revisão leve e descanso

- Segunda a quarta: revisão **leve**, 40 minutos por dia, só nas colas (`cheatsheets/`) e nos cards do Notion. Sem conteúdo novo.
- **Quinta 19/11: simulado final (11).**
- Sexta (feriado), sábado e domingo: **descanso**. Não estudar na véspera.

**Prova: segunda-feira 23/11.** Chegar 30 minutos antes, com dois documentos com foto. Na prova: 40 questões em 60 minutos, 1,5 minuto por questão; marcar as difíceis e voltar; nas de preenchimento, escrever **só o comando**, sem caminho e sem flags, salvo se pedido.

---

## 8. Riscos do novo formato e como são mitigados

| Risco | Por que existe | Mitigação |
|---|---|---|
| **Perda de motricidade** | Comando vira reflexo por repetição espaçada; 2 sessões/semana espaçam menos que 5 | Aquecimento diário de 10 minutos, cinco comandos de memória |
| **Permissões sem repetição suficiente** | É o conteúdo mais dependente de reflexo, e cai na semana de menor frequência | Aquecimento da Semana 6 dedicado só a conversão de permissões · sessão extra na Semana 7 se a conversão não sair em 3 segundos |
| **Curso sem prática imediata** | Assistir sem digitar produz reconhecimento, não competência | As 2 práticas da semana cobrem sempre o objetivo de maior peso daquele bloco |
| **Simulado adiado de novo** | Já atrasou 4 semanas | Ocupa formalmente o lugar de uma das duas práticas da Semana 5, em data fixa: domingo 04/10. **Não coube no domingo**; passou para a segunda 05/10, como **primeira** atividade do dia, antes do curso e de qualquer outra coisa |
| **Curso adiado repetidamente** | Segunda e terça da Semana 5 sem aulas; na quarta, 5 das 9 aulas previstas (26 a 30); 42 restantes (31 a 72) em 3 semanas | Quinta com as aulas 31 a 43 · 2x nas aulas que repetem conteúdo já praticado · regra de transbordo (shell script tem prioridade, o resto vai para segunda 05/10) · fila de dívidas registrada por semana |
| **Carga acima do teto nas Semanas 6 e 7** | As dívidas da Semana 5 (cerca de 3h30: simulado #1, Laboratório 2 e curso) e o simulado dominical (cerca de 1h35) somam-se a um orçamento de 5 a 7h. A Semana 6 sai com cerca de 10h35 nominais | Ordem de corte escrita de antemão no arquivo da Semana 6 (cerca de 8h25 com os cortes) · feriado de 12/10 como dia extra · pré-checkpoint de 07/10 · Checkpoints A e B |
| **Dívidas acumuladas sobre o conteúdo novo** | Em 13/10, quatro dívidas e 32 aulas disputavam a mesma semana | Etapas em ordem fixa (dívidas, conteúdo, simulados) · dívidas antigas retiradas do plano em 13/10 · ordem de corte escrita em `labs/semana-07.md` |
| **Prova marcada sem margem (atualizado em 13/10)** | Com 23/11, sobram quatro semanas de simulados depois do conteúdo | Checkpoints A, B, Gate e Final na seção 11 · limite absoluto em 30/11 |
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

**Desde 06/10, esta tabela é a fila de retaguarda.** Os erros abaixo são de comandos já estudados e saíram do aquecimento diário; os simulados continuam medindo se voltam, e a revisão leve da Semana 12 passa por eles nos cards do Notion. Entram na retaguarda, além destes, as Correções 62 a 67 (Tópicos 1 e 2). Os demais itens que estavam aqui (reteste da autoavaliação da Semana 4, comparação de compressão, saídas do `teste.sh`, do `vi` e do `nano`, `.wslconfig` e teste do snapshot) **saíram do plano em 13/10**. A Correção 68 (`chmod` e `chown`) é do Tópico 5 e continua ativa até a Prática 2.

| Erro | Vezes | Correção |
|---|---|---|
| `sort` sem `-n` descrito como "invertendo a ordem" | **4** (Correções 32, 33/34 e 50) | As duas formas são **crescentes**; só o `-r` inverte. `-k` é **coluna**, vem de *key*. Reler não resolveu: o que resolve é executar os quatro comandos lado a lado |
| `cd ..` e `cd -` trocados | **5** (a quarta em 30/09, Correção 53; a quinta em 05/10, Correção 64, agora com o `cd -` chamado de "pai") | `cd ..` é **pai** (espaço); `cd -` é **anterior** (tempo). Era fixo no aquecimento; passou para a retaguarda em 06/10. O simulado mede se voltou |
| Confundir o efeito com o mecanismo (`2>&1`, hard link, `-f` do `tar`) | 3 | O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |
| `grep -v` entendido como *verbose* | 1 (Correção 49) | É *invert*. O `grep` é a exceção: em `tar`, `cp`, `rm` e `mv` o `-v` é verbose. Custou **duas** questões da autoavaliação, porque a 14 dependia dele |
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
| 1 | **LPI Linux Essentials** (010-160) | Em preparação — prova em 23/11/2026 |
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

## 11. Checkpoints e regra de adiamento da prova

**Revisada em 13/10**, com a prova em **23/11**. O princípio de 02/10 continua: a decisão sobre manter ou mover a data é tomada por critérios escritos antes, com números (práticas feitas, aulas assistidas, acertos em simulado), e não pela sensação de estar pronto.

### Checkpoints

| Checkpoint | Data | Critérios | Resultado |
|---|---|---|---|
| **A** | Dom 18/10 | 1. Práticas 1 e 2 · 2. Simulado 02 com **24 ou mais** · 3. Autoavaliações das Semanas 5 e 6 feitas · 4. Curso até a aula 72 (ou 64, com 65 a 72 na segunda 19/10) | **Verde:** segue. **Amarelo:** um falhou; o item abre a segunda 19/10. **Vermelho:** dois ou mais falharam, ou simulado 02 abaixo de 20; a Semana 8 abre com as dívidas restantes e o Checkpoint B decide a data |
| **B** | Dom 25/10 | 1. Curso fechado (aula 72) · 2. Práticas 3, 4 e 5 feitas · 3. Simulado 03 com **28 ou mais** | **Verde:** mantém 23/11. **Amarelo:** um falhou; mantém, mas o Gate fica sem folga. **Vermelho:** dois ou mais falharam; mover a prova para **30/11** |
| **Gate** | Dom 08/11 | Dois simulados consecutivos com **34 ou mais** entre o 06 (03/11), o 07 (05/11) e o 08 (08/11) | **Cumprido:** mantém 23/11. **Não cumprido:** se a média dos três ficou em 30 ou mais, mantém e o Final decide; abaixo disso, mover para **30/11** |
| **Final** | Qui 19/11 | Simulado 11 | **34 ou mais:** vai. **30 a 33:** vai, com revisão leve dos erros no fim de semana. **Abaixo de 30:** remarcar para 30/11, se a janela de remarcação ainda permitir |

### Datas alternativas

| Cenário | Data | O que muda |
|---|---|---|
| Manter | **Seg 23/11** | Plano como está |
| Remarcar uma semana | Seg 30/11 | A Semana 12 vira semana de simulados (dois); a revisão leve e o simulado final passam para 23 a 26/11 |
| **Limite absoluto** | **Seg 30/11** | Passar de 30/11 sem o Gate cumprido indica problema de método, não de calendário. Reavaliar o plano antes de remarcar de novo |

### Voucher e agendamento

- **Decisão de 13/10:** a prova é em **23/11**.
- Se o voucher **já foi comprado e a prova agendada**, registre na seção 1 o centro, o horário e a janela de remarcação sem custo, e desconsidere o item seguinte.
- Se **ainda não foi comprado**, o gatilho de 08/10 (média dos três últimos simulados com 30 ou mais) continua sendo o critério de compra, avaliado no **domingo 01/11**, com os simulados 03, 04 e 05. Antes disso, sem custo, consulte no site da Pearson VUE a disponibilidade de 23/11 e a antecedência mínima de agendamento. Eu não conheço esses valores, e a data depende deles.
- Recomendação mantida: **centro Pearson VUE**, não OnVUE.

### Registro das decisões

| Checkpoint | Data | Critérios cumpridos | Resultado | Decisão |
|---|---|---|---|---|
| A | 18/10 | | | |
| B | 25/10 | | | |
| Gate | 08/11 | | | |
| Final | 19/11 | | | |

Histórico: o Checkpoint A original (11/10) e o pré-checkpoint de 07/10 estão registrados em `labs/semana-06.md`. A decisão de 08/10 adiou a compra do voucher; a de 10/10 fez de 16/11 a data principal; a de 13/10 fixou **23/11**.

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