# Plano de Preparação — LPI Linux Essentials (010-160)

**Aluno:** Davi (@DaviMoraisdev) · **Ritmo:** 5–7h/semana
**Data da prova:** **09/11/2026, segunda-feira** (ou 16/11, se o pré-checkpoint de 07/10 mandar; seção 11)
**Repositório de labs:** https://github.com/DaviMoraisdev/linux-essentials-labs

> **Estratégia revisada em 26/09.** O cronograma tem **duas fases**: três semanas com o curso como atividade principal e duas práticas por semana, seguidas de três semanas de prática intensiva e simulados. Detalhamento na seção 7.
>
> **Atualização de 02/10, à noite.** Três mudanças: (1) **simulado geral de 40 questões todo domingo**, a partir de 04/10 (seção 7); (2) o fechamento da Semana 5 passa para o **domingo 04/10** (Laboratório 1 e simulado #1), e o Laboratório 2 e as aulas 31 a 43 passam para a Semana 6 (`labs/semana-06.md`); (3) nova **regra de adiamento da prova**, com checkpoints e datas alternativas (seção 11).
>
> **Atualização de 05/10.** O **simulado #1 foi feito: 28 de 40 (70%), 560 de 800**, acima do corte, mas com 5 acertos por chute (23 firmes). Tópico 3 em 9 de 9; seis dos sete erros com convicção caíram nos Tópicos 1 e 2. Correções 62 a 68 em `labs/semana-06.md`. Falta o Laboratório 2 (terça 06/10) para o pré-checkpoint de quarta.

> **Atualização de 04/10.** O Laboratório 1 e o exercício das frutas foram concluídos. O **simulado #1 passou para a segunda 05/10**, o Laboratório 2 para a terça 06/10 e as aulas 31 a 43 para a quarta 07/10. A Semana 6 foi reorganizada (`labs/semana-06.md`). Um novo **pré-checkpoint, na quarta 07/10**, decide se a prova é agendada para 09/11 ou direto para 16/11 (seção 11).
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
| **Semana 5 — Objetivo 3.3, parte prática** | **Laboratório 1 concluído em 04/10** (blocos 1 e 2 em 02/10; blocos 3 a 6 e exercício das frutas em 04/10); Correções 60 e 61. **Simulado #1 feito em 05/10 (28 de 40).** Falta o Laboratório 2 |
| **Tópico 1 (peso 7)** | Completo |
| **Tópico 2 (peso 9)** | Completo — os quatro objetivos |
| **Tópico 3 (peso 9)** | 3.1 e 3.2 feitos; 3.3 praticado no Laboratório 1 (04/10); simulado: 9 de 9 em 05/10; falta o Laboratório 2 |
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
| **Curso, aulas 31 a 43** (13 aulas; as aulas 26 a 30 foram concluídas em 30/09) | **quarta 07/10** (Semana 6), a 2x, porque o Laboratório 1 já praticou o 3.3 |
| Registrar as saídas do `teste.sh` e as três saídas de `vi` e `nano` (Laboratório 1) | terça 06/10, no aquecimento |
| **Laboratório 2** — `backup.sh`, `contar.sh`, `usuario.sh` (`filtrar.sh` opcional) | **terça 06/10** (Semana 6) |
| **Revisão prática** dos erros do simulado #1 (correções 62 a 68 já registradas em 05/10) | terça 06/10, 15 minutos, executada na VM; cards no Notion na segunda |
| **Autoavaliação da Semana 5** — 10 questões | sexta 09/10 |
| **Voucher da prova** e agendamento (09/11 ou 16/11, conforme o pré-checkpoint), com a janela de remarcação anotada | **quarta 07/10** (prazos anteriores: 29/09 e 30/09) |
| ~~**Simulado #1 (diagnóstico)**~~ | **Concluído em 05/10: 28 de 40 (70%), 560 de 800.** Prova corrigida em `praticas/simulado-01-diagnostico-resultado.md` |
| Reteste das 4 questões erradas da autoavaliação da Semana 4 | No aquecimento diário. As questões 18, 20, 21, 22 e 24 do simulado #1 também retestam |
| Refazer a comparação de compressão (`bzip2` já instalado) | terça 06/10, no aquecimento |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | segunda 05/10 |
| Registrar as observações sobre arquivos ocultos (Semana 3) | segunda 05/10 |
| **Checkpoint A** — decisão sobre manter 09/11 | domingo 11/10 (seção 11) |
| `.wslconfig` limitando o WSL2 a 3 GB | Quando houver folga |
| Teste de restauração do snapshot | Quando houver folga |

### Cobertura estimada por tópico

| Tópico | Peso | Cobertura |
|---|---|---|
| 1. Comunidade e open source | 7 | 100% |
| 2. Encontrando seu caminho | 9 | 100% |
| 3. Poder da linha de comando | 9 | 3.1 e 3.2 completos; 3.3 em prática (Laboratório 1 concluído) |
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
| **`praticas/` deste repositório** | — | Simulados próprios, com peso do exame e gabarito comentado. As questões atacam os erros já registrados nos cadernos. Série dominical: ver seção 7 |
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

**Da Semana 5 em diante, a autoavaliação de cada semana é respondida na semana seguinte**, em um dia de curso, como abertura da sessão. O intervalo mínimo é de três dias. Uma nota menor e honesta informa o plano; uma nota alta e cedo apenas o tranquiliza. A autoavaliação da Semana 5 é elaborada na quinta 08/10 e respondida na **sexta 09/10**, em versão reduzida de 10 questões, três dias depois do Laboratório 2, que foi transferido para a terça 06/10.

### As sessões de laboratório

Sem vídeo dentro delas — o vídeo agora tem espaço próprio. A sessão inteira é teclado:

1. **45 min de laboratório** — reproduzir tudo na VM, **digitando**, nunca copiando e colando
2. **10 min de registro** — anotar no caderno o comando, o que faz e o exemplo executado
3. **5 min** — commit no repositório

**Quebrar coisas de propósito** continua valendo. O snapshot `limpo` existe para isso.

### A fila de dívidas

Item adiado não some. Ele entra no início do próximo bloco de estudo e fica registrado na tabela de dívidas do arquivo da semana. Adiar tem custo visível: a Semana 5 subiu de 5h para cerca de 6h45 depois de dois dias de curso perdidos.

### O simulado dominical

**Regra criada em 02/10:** todo domingo, um simulado geral de 40 questões, 60 minutos, sem consulta, com a distribuição de pesos do exame. É o termômetro semanal e o treino da condição de prova. A série completa, com datas, fontes e metas, está na seção 7.

1. Cronometrado, sem terminal, sem caderno, sem internet.
2. **Marcar cada chute**, mesmo acertando.
3. Apuração **por objetivo**, não por questão, e correção com mecanismo para cada erro conceitual.
4. Cada simulado é um conjunto **novo**. As questões erradas voltam só pelo aquecimento, nunca refazendo o simulado inteiro.
5. O resultado entra na tabela da série e alimenta os checkpoints da seção 11.
6. Carga: cerca de 1h35 por domingo (60 min de prova, 20 a 25 de apuração, commits).
7. **Exceção:** domingo 08/11, véspera da prova, não tem simulado. O final é na quinta 05/11.

**Relação com a autoavaliação semanal.** Nas Semanas 6 e 7 a autoavaliação por tópico continua, reduzida a 10 questões, porque mede retenção do tópico da semana anterior. A partir da Semana 8, com os cinco tópicos estudados, o simulado a substitui.

---

## 7. Cronograma revisado

Semanas de **segunda a domingo**. A prova cai na segunda-feira seguinte ao fim da Semana 10.

### Visão geral

| Fase | Semanas | Período | Foco |
|---|---|---|---|
| **Fase 1 — Curso** | 5, 6, 7 | 28/09 a 18/10 | Fechar as 42 aulas restantes (31 a 72) · 2 práticas/semana · simulado todo domingo |
| **Fase 2 — Prática e simulados** | 8, 9, 10 | 19/10 a 08/11 | Simulados em condição de prova (inclusive os de domingo) · laboratório integrador |
| **Prova** | — | **09/11** | — |

### A conta

| Item | Número |
|---|---|
| Aulas restantes do curso | 42 (da 31 à 72), após o checkpoint de 30/09; nenhuma assistida até 02/10 |
| Semanas na Fase 1 | 3, mas a Semana 5 fecha sem as aulas 31 a 43 |
| Aulas por semana | Semana 6: 27 (31 a 43 transferidas e 44 a 57) · Semana 7: 15 (58 a 72) |
| Tempo de vídeo, em 1x a 1.5x | cerca de 3h na Semana 6 · cerca de 1h45 na Semana 7 |
| Laboratórios e práticas | 2 por semana, 1h cada |
| Aquecimento diário | 1h10 na semana |
| Simulado dominical | cerca de 1h35 por semana |
| **Total semanal** | **Semana 6: ~9h nominal**, acima do teto de 7h, com ordem de corte escrita · **Semana 7: ~7h** |

A Fase 1 ainda termina em **18/10**, com o curso fechado e os cinco tópicos estudados, **se** a Semana 6 cumprir o plano. A conta antiga, de 5h por semana, não vale mais: as dívidas da Semana 5 e o simulado dominical a derrubaram. É por isso que existem a ordem de corte da Semana 6 e os checkpoints da seção 11. Sobram três semanas para simulados, e elas são a margem que absorve um atraso pequeno.

### Datas do calendário que afetam o plano

| Data | Evento | Efeito |
|---|---|---|
| Seg 12/10 | Nossa Senhora Aparecida (feriado) | Primeiro dia da Semana 7. Dia extra disponível para curso ou para uma sessão de permissões, se a conversão não sair em 3 segundos |
| Qua 28/10 | Dia do Servidor Público | Sem efeito no plano |
| Seg 02/11 | Finados (feriado) | Primeiro dia da Semana 10, na revisão leve |
| Dom 08/11 | Véspera da prova | Sem simulado dominical. Descanso |
| Sex 20/11 | Consciência Negra (feriado) | Só importa se a prova for remarcada para 16/11 ou 23/11 |
| Seg 09/11 | Dia da prova | Não cai em feriado |

### Série de simulados dominicais

Um simulado geral de 40 questões todo domingo, mais os extras de Fase 2. Distribuição de pesos do exame. O #1, previsto para domingo 04/10, foi para a **segunda 05/10**. Meta em acertos: 24 = 60%, 28 = 70%, 30 = 75%, 34 = 85%.

| # | Data | Semana | Fonte | Meta |
|---|---|---|---|---|
| 1 | **Seg 05/10** (adiado do dom 04/10) | 5 | `simulado-01-diagnostico` | **Feito: 28 de 40 (70%), 23 firmes.** Esperado era 24 a 30 |
| 2 | Dom 11/10 | 6 | `simulado-02` | **24 ou mais** (Checkpoint A) |
| 3 | Dom 18/10 | 7 | `simulado-03` | **28 ou mais** (Checkpoint B) |
| 4 | Qui 22/10 | 8 | Exame final de prática do NDG | 28 ou mais |
| 5 | Dom 25/10 | 8 | `simulado-05` | **30 ou mais** |
| 6 | Ter 27/10 | 9 | `simulado-06` | Acompanhar |
| 7 | Qui 29/10 | 9 | `simulado-07` | 34 ou mais |
| 8 | Dom 01/11 | 9 | `simulado-08` | **34 ou mais** (Gate) |
| 9 | Qui 05/11 | 10 | `simulado-09` | 34 ou mais |

**Gate:** dois simulados consecutivos com 34 ou mais entre os de 27/10, 29/10 e 01/11.

**Produção.** Só o `simulado-01` existe. Os demais são escritos sob medida, com os erros já registrados virando questões, e precisam estar prontos **três dias antes** do uso. O próximo, `simulado-02`, deve ser pedido até **quinta 08/10**. O NDG é a fonte externa gratuita (`praticas/fontes-de-simulados.md`).

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
| Sáb 03 | **Opcional** — adiantar a Semana 6: Laboratório 1, blocos 3 a 5, e aulas de shell script | até 1h |
| **Dom 04** | Laboratório 1, blocos 3 a 6 e exercício das frutas — **realizado**. Simulado #1 não realizado: passou para a segunda 05/10 | — |

Total previsto em 29/09 a partir de quarta: 6h45. **Substituído pelo plano final abaixo.**

**Regra de transbordo.** Se a quarta ou a quinta não fecharem as 9 aulas: (1) as aulas de shell script têm prioridade e precisam estar vistas antes do Laboratório 1; (2) as demais podem transbordar para a segunda 05/10, antes das aulas de permissões; (3) o Laboratório 2 e o simulado não são cortados nem movidos.

**Atualização de 30/09.** A quarta fechou 5 das 9 aulas previstas. As 4 restantes passaram para a quinta, que fica com 13 aulas. No pior caso a semana vai a cerca de 7h10, 10 minutos acima do teto; a folga vem de usar **2x** nas aulas que só repetem conteúdo já praticado e da regra de transbordo. Detalhes em `labs/semana-05.md`.

**Atualização de 04/10 — fechamento.** O domingo rendeu o Laboratório 1 inteiro e o exercício das frutas; o simulado #1 não coube e foi para a segunda 05/10. A Semana 5 fecha com as Correções 60 e 61. Detalhes em `labs/semana-05.md`.

**Atualização de 02/10, à noite — plano (superado pela atualização de 04/10, acima).** A quinta não teve estudo e o Laboratório 1 de sexta foi feito em parte (blocos 1 e 2). O sábado deixa de ser obrigatório e o fechamento da semana passa para o **domingo 04/10**: simulado #1 **primeiro**, com a cabeça descansada, e depois o restante do Laboratório 1. O Laboratório 2 e as aulas 31 a 43 passam para a Semana 6. Se o tempo apertar no domingo, cortam-se, nesta ordem, o exercício das frutas e o bloco 6 (segunda 05/10); o simulado e os blocos 3 a 5 não se cortam.

**Curso:** aulas 26 a 30 concluídas em 30/09; **31 a 43 transferidas para a quarta 07/10**, a 2x. Como o Laboratório 1 já praticou o 3.3, o vídeo confirma e não ensina.

**Justificativa da divisão em duas práticas.** O objetivo 3.3 tem peso 4 e cobre shebang, variáveis, argumentos, condicionais, loops, códigos de saída e os editores `vi` e `nano`. Não cabe em uma sessão com os quatro scripts no fim. A sexta cobre os fundamentos; o sábado escreve o código.

**Prática 1 — Fundamentos de shell script (sexta 02/10)**

- Shebang `#!/bin/bash`, `chmod +x`, `./script.sh` versus `bash script.sh`
- Variáveis, `$1 $2 $@ $# $0`, aspas
- `if/elif/else`, `test` e `[ ]`, comparadores `-eq -ne -lt -gt -f -d -z`
- Loop `for` e `seq`
- Códigos de saída: `$?`, `exit 0`, encadeamento `&&` e `||`
- **`vi` e `nano`**: modos do `vi`, como gravar e sair de cada um
- Exercício do script das frutas, do material oficial do LPI, com erros de sintaxe para corrigir

**Prática 2 — Os scripts (terça 06/10, Semana 6)** — três obrigatórios; o `filtrar.sh` passa a opcional

Escrever em `scripts/`, um por vez, testando cada um antes de passar ao seguinte:

| Script | Exercita |
|---|---|
| Backup com a data no nome | Substituição de comando, `tar`, variáveis |
| Contar arquivos por extensão | `for`, `find`, `wc`, pipeline dentro de script |
| Verificar se um usuário existe | `if`, `grep -q`, `$?`, `exit` com código |
| Ler um arquivo linha a linha e filtrar | `while read`, redirecionamento de entrada |

> `while` e `read` não constam na lista oficial de termos do 3.3, mas o quarto script os exige. O que a prova cobra com certeza são `for`, argumentos, variáveis, `if` com operadores numéricos e o código de saída.

> Você já programa, então a sintaxe vem rápido; o que exige atenção é a diferença entre o modelo mental do shell e o de uma linguagem estruturada. Três pontos concretos: espaços dentro de `[ ]` são obrigatórios, `=` compara texto e `-eq` compara número, e uma variável sem aspas se parte em palavras.

**Simulado diagnóstico (segunda 05/10, adiado do domingo 04/10) — simulado #1 da série**

40 questões, 60 minutos, cronometrado, sem consultar nada. O simulado está em `praticas/simulado-01-diagnostico.md`, com a distribuição de pesos do exame e gabarito comentado. Fontes gratuitas complementares em `praticas/fontes-de-simulados.md` — a principal é o NDG Linux Essentials da Cisco Networking Academy, cujos quizzes e exame final de prática são gratuitos.

Esta é a pendência mais antiga do plano, com quatro semanas de atraso. Ela ocupa o lugar de uma prática porque **é** prática — e porque o resultado determina no que as práticas das Semanas 6 e 7 devem insistir. As questões 18, 20, 21, 22 e 24 retestam correções já registradas (29, 33/34/50, 36, 52 e a diferença entre regex e globbing).

**Expectativa:** entre 60% e 75%. Você cobriu ~65% do conteúdo e o Tópico 5 está zerado. Abaixo de 24 acertos, a Semana 7 ganha uma sessão de revisão e o gate da Semana 9 é revisitado.

**Resultado (05/10):** 28 de 40 (70%), 560 de 800, em 20 min 31 s. Dez questões marcadas como chute: cinco acertadas e cinco erradas. Sem os chutes acertados, 23 acertos firmes (57,5%).

| Tópico | Peso | Acertos | Erros | Chutes acertados |
|---|---|---|---|---|
| 1. Comunidade e open source | 7 | 5 | 2 | 0 |
| 2. Encontrando seu caminho | 9 | 5 | 4 | 0 |
| 3. Poder da linha de comando | 9 | 9 | 0 | 1 |
| 4. Sistema operacional | 8 | 6 | 2 | 1 |
| 5. Segurança e permissões | 7 | 3 | 4 | 3 |

**Como ler o resultado:**

- Erros concentrados em 4 e 5, ainda não estudados — o plano está funcionando.
- Erros em 1, 2 ou 3, que estão fechados — a base pede revisão, e as práticas das semanas seguintes precisam incluí-la.

**Leitura do resultado:** os dois cenários aconteceram. O Tópico 3 sustentou (9 de 9). Os cinco erros marcados como chute caíram nos Tópicos 4 e 5, ainda não estudados, e isso confirma o plano. Seis dos sete erros com convicção caíram nos Tópicos 1 e 2, fechados nas Semanas 1 a 3: a retenção desses tópicos pede reforço, e por isso a revisão prática de terça e o aquecimento carregam itens deles. As duas questões do Tópico 1 (Q3 e Q7) não se executam na VM e viram card no Notion; as do Tópico 2 entram na revisão executada de terça. O simulado #2 deve usar pelo menos 45 minutos: o #1 durou 20.

**Ação da semana: comprar o voucher e agendar a prova para 09/11.** Prazos anteriores: 29/09 e 30/09. **Novo prazo: quarta 07/10.** Antes da compra, o **pré-checkpoint de quarta 07/10** (seção 11) decide se a data é 09/11 ou 16/11. Na compra, confirmar e anotar a janela de remarcação sem custo e a validade do voucher.

Marcar antes de se sentir pronto é intencional. Prazo firme é o que impede o plano de escorregar para dezembro.

**Entregável:** `labs/semana-05.md` com o **Laboratório 1 completo**, o exercício das frutas e as Correções 60 e 61, entregue em 04/10. Simulado #1, scripts, autoavaliação e voucher passam para a Semana 6

---

### Semana 6 — 05 a 11/10 · Tópico 5, permissões (peso 7)

**Arquivo detalhado:** `labs/semana-06.md` (calendário dia a dia, exercícios, gabarito do aquecimento, ordem de corte, pré-checkpoint e Checkpoint A).

**Curso:** aulas **31 a 43** (transferidas da Semana 5) na quarta 07/10, a 2x, porque o Laboratório 1 já praticou o 3.3; aulas **44 a 50** na quinta 08 e **51 a 57** na sexta 09/10.

**Carga:** cerca de 10h35 nominais, acima do teto de 7h. Ordem de corte, se faltar tempo: `filtrar.sh`; revisão prática de terça; autoavaliação a 5 questões; aulas 51 a 57 e Prática 1 para a segunda 12/10 (feriado). Com os cortes, cerca de 8h25. Não se cortam: simulados #1 e #2, Laboratório 2 (três scripts), Prática 2, voucher e aquecimento.

| Dia | Atividade |
|---|---|
| Seg 05 | **Simulado #1** · apuração e correções · dívidas curtas (arquivos ocultos, `rm`) |
| Ter 06 | Revisão prática dos erros do simulado · Laboratório 2 — `backup.sh`, `contar.sh`, `usuario.sh` · comparação de compressão |
| Qua 07 | **Voucher, agendamento e pré-checkpoint** · aulas 31 a 43, a 2x |
| Qui 08 | Aulas 44 a 50 · Prática 1 — usuários e grupos · pedir o `simulado-02` |
| Sex 09 | Autoavaliação da Semana 5 (10 questões) · aulas 51 a 57 |
| Sáb 10 | Prática 2 — permissões |
| **Dom 11** | **Simulado #2** · apuração · **Checkpoint A** |

**Correção e revisão prática.** O simulado #1 gerou as **Correções 62 a 68** (sete erros com convicção; os cinco chutes errados definem a ênfase das Semanas 6 e 7). Para cada objetivo dos Tópicos 1 a 3 com erro, a terça traz uma revisão de 15 minutos **executada na VM**, sem reler o caderno. Os erros alimentam o aquecimento dos dias seguintes.

**Autoavaliação da Semana 5:** reduzida a 10 questões, respondida na sexta 09/10, três dias depois do Laboratório 2.

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

**Checkpoint A (domingo 11/10):** cinco critérios (curso até a aula 57, Laboratório 2, as duas práticas, simulado #2 com 24 ou mais acertos, voucher e agendamento). Resultado verde, amarelo ou vermelho decide se 09/11 se mantém (seção 11).

**Entregável:** `labs/semana-06.md` + `cheatsheets/permissoes.md` + os três scripts + resultados dos simulados #1 e #2

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

**Segunda 12/10 (feriado):** sessão extra de permissões, se a conversão ainda não sai em 3 segundos, ou as aulas 51 a 57 e a Prática 1 (usuários e grupos), se tiverem sido cortadas na Semana 6.

**Sexta 16/10:** autoavaliação da Semana 6 (Tópico 5), 10 questões.

**Domingo 18/10:** **simulado #3** (meta: 28 ou mais) e **Checkpoint B** (seção 11).

**Entregável:** `labs/semana-07.md`

**Marco:** ao fim desta semana, **o curso está fechado e os cinco tópicos foram estudados**.

---

### Semana 8 — 19 a 25/10 · Início da Fase 2

**Formato:** volta o ritmo diário. Cinco sessões.

- **2 simulados completos**, cronometrados, em dias diferentes: **quinta 22/10** (exame final de prática do NDG) e **domingo 25/10** (série dominical)
- Após cada um, listar os erros **por objetivo**, não por questão
- Revisão dirigida **apenas** nos objetivos com erro — não revisar o que já acerta
- Laboratório de reforço nos dois objetivos mais fracos

**Meta:** ≥ 75% (30 de 40) no simulado de domingo 25/10. A partir desta semana o simulado substitui a autoavaliação por tópico.

---

### Semana 9 — 26/10 a 01/11 · Simulados e laboratório integrador

- **3 simulados completos**: terça 27/10, quinta 29/10 e **domingo 01/11** (série dominical)
- Revisão dirigida após cada um

**Laboratório integrador** — 2h, do zero, sem consultar:

1. Criar dois usuários e um grupo compartilhado
2. Criar `/dados/projeto` com permissões de grupo corretas e SGID
3. Escrever um script de backup em `.tar.gz` com data no nome
4. Agendar o script com `cron`
5. Gerar um relatório com `find`, `grep` e `sort` dos arquivos maiores que 1 MB

**Meta: ≥ 85% (34 de 40) em dois simulados seguidos** entre os de 27/10, 29/10 e 01/11. Este é o gate. Se não atingir, a prova é remarcada para 16/11. O procedimento completo e as janelas de remarcação estão na seção 11. Reprovar custa mais caro que adiar.

---

### Semana 10 — 02 a 08/11 · Revisão final

- Segunda (feriado de Finados) a quarta: revisão **leve** — só a cola do GitHub e os cards do Notion, 40 min/dia. Sem conteúdo novo
- Quinta 05/11: simulado final (#9). Se ≥ 85%, está pronto
- Sexta, sábado e domingo: **descanso**. Não estudar na véspera. **A série dominical não tem simulado em 08/11**

**Prova: segunda-feira 09/11.** Chegar 30 minutos antes, levar dois documentos com foto.

Na prova: 40 questões em 60 minutos, 1,5 minuto por questão. Marcar as difíceis e voltar. Nas de preenchimento, escrever **só o comando**, sem caminho e sem flags, salvo se pedido.

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
| **Prova marcada sem margem** | 09/11 deixa três semanas de Fase 2, e qualquer atraso da Fase 1 consome essas semanas | Seção 11: checkpoints com critérios objetivos, datas alternativas (16/11, 23/11) e limite absoluto em 30/11 |
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
| `cd ..` e `cd -` trocados | **5** (a quarta em 30/09, Correção 53; a quinta em 05/10, Correção 64, agora com o `cd -` chamado de "pai") | `cd ..` é **pai** (espaço); `cd -` é **anterior** (tempo). Fixo no aquecimento até domingo |
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

## 11. Regra de adiamento da prova e checkpoints

**Criada em 02/10.** O objetivo é decidir sobre remarcar com critérios escritos antes, e não no meio de uma semana ruim. Remarcar cedo é simples. Reprovar custa uma nova taxa e o ritmo.

### Princípio

**09/11 continua sendo a meta.** A data só se mantém se os checkpoints forem cumpridos. Contam números (aulas assistidas, laboratórios feitos, acertos em simulado), não a sensação de estar pronto.

### Checkpoints

| Checkpoint | Data | Critérios | Resultado |
|---|---|---|---|
| **A** | Dom 11/10 | 1. Curso até a aula 57 (ou até a 50, com 51 a 57 marcadas para 12/10) · 2. Laboratório 2, três scripts · 3. Práticas 1 e 2 · 4. Simulado #2 com **24 ou mais** acertos · 5. Voucher comprado e prova agendada | **Verde:** todos cumpridos, mantém 09/11. **Amarelo:** um falhou, mantém, e o item vira obrigatório na segunda 12/10. **Vermelho:** dois ou mais falharam, ou simulado #2 abaixo de 20, **remarcar para 16/11** |
| **B** | Dom 18/10 | 1. Curso fechado (aula 72) · 2. Quatro práticas da Fase 1 feitas, com a sessão extra de permissões se a conversão passa de 3 s · 3. Simulado #3 com **28 ou mais** acertos | **Verde:** mantém. **Amarelo:** um falhou, mantém, mas o gate de 01/11 passa a não ter folga. **Vermelho:** dois ou mais falharam, ou curso não fechado, **remarcar para 16/11** |
| **Gate** | Dom 01/11 | Dois simulados consecutivos com **34 ou mais** entre os de 27/10, 29/10 e 01/11 · laboratório integrador feito | **Cumprido:** mantém 09/11. **Não cumprido:** remarcar para 16/11 |
| **Final** | Qui 05/11 | Simulado #9 | **34 ou mais:** vai. **30 a 33:** vai, com revisão leve dos erros. **Abaixo de 30:** remarcar, se a janela do agendamento ainda permitir |

O Checkpoint A só pesa de verdade se o voucher e o agendamento já existirem. Sem eles, a decisão de remarcar vira um problema novo, e é por isso que o voucher é o critério 5.

### Pré-checkpoint — quarta 07/10

**Criado em 04/10**, porque o simulado #1 e o Laboratório 2 escorregaram para o começo da Semana 6 e o voucher ainda não foi comprado. Uma pergunta só: **o simulado #1 (segunda) e o Laboratório 2 (terça) estão feitos?** Em 05/10, à noite, o simulado #1 está feito (28 de 40); falta o Laboratório 2.

| Resposta | Decisão |
|---|---|
| Os dois estão feitos | Comprar o voucher e agendar **09/11** |
| Qualquer um dos dois não está | Agendar direto para **16/11** |

Como o voucher ainda não existe, agendar para 16/11 não custa remarcação nem troca. Com 16/11 como data, os Checkpoints A, B e Gate mantêm as datas e os critérios, e o resultado "vermelho" passa a significar remarcar para **23/11**. A série de simulados dominicais continua igual, e a Fase 2 ganha uma semana.

### Datas alternativas

| Cenário | Data | O que muda |
|---|---|---|
| Manter | Seg 09/11 | Plano das Semanas 8 a 10 como está |
| Remarcar uma semana | **Seg 16/11** | A Semana 10 vira semana de prática, com dois simulados. A Semana 11 (09 a 15/11) é a revisão leve. Simulado dominical em 08/11 mantido. Simulado final na quinta 12/11, descanso de 13 a 15/11 |
| Remarcar duas semanas | Seg 23/11 | Mesma lógica, deslocada. Sexta 20/11 é feriado e pode servir de dia extra |
| **Limite absoluto** | **Seg 30/11** | Se a prova passar de 30/11 sem o gate cumprido, a causa deixa de ser calendário e passa a ser método. Reavaliar o plano antes de remarcar de novo |

O limite de 30/11 é uma **proposta**, para a Linux Essentials não empurrar o resto do roadmap de certificações para 2027. Ajuste-o se houver outro critério.

Nas semanas extras, a série dominical continua. A única exceção é sempre a véspera da prova.

### Voucher e agendamento

- Comprar o voucher e agendar a prova **até quarta 07/10**, para 09/11 ou, se o pré-checkpoint mandar, para 16/11. Marcar antes de se sentir pronto é intencional: prazo firme é o que impede o plano de escorregar.
- No ato da compra, **confirmar e anotar aqui**: (a) até quando é possível remarcar sem custo; (b) a validade do voucher; (c) se há vaga em 16/11 no centro escolhido. Não assumo valores: a regra vale a que estiver escrita na confirmação do agendamento.
- Registrar a janela de remarcação: ____________

### Registro das decisões

| Checkpoint | Data | Critérios cumpridos | Resultado | Decisão |
|---|---|---|---|---|
| A | 11/10 | | | |
| B | 18/10 | | | |
| Gate | 01/11 | | | |
| Final | 05/11 | | | |

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