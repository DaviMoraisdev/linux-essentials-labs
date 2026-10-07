# Semana 6 — Tópico 5, usuários e permissões, e o fechamento das dívidas da Semana 5

Período: 05/10 a 11/10/2026 (segunda a domingo)
Objetivos da prova: 5.1, 5.2, 5.3 e 5.4 — Tópico 5, peso 7 de 40
Carga nominal: cerca de 11h00 (atualizada em 06/10), acima do teto de 7h; cerca de 8h30 com os cortes. A seção "Carga da semana e ordem de corte" explica o motivo e o que sai primeiro
Marco da semana: **Checkpoint A, domingo 11/10**, com decisão objetiva sobre manter ou remarcar a prova de 09/11

Observação sobre a natureza desta semana: ela carrega duas coisas ao mesmo tempo. De um lado, conteúdo novo e dependente de repetição, porque converter `rwxr-xr--` em `754` precisa virar reflexo. De outro, as dívidas que a Semana 5 não fechou: o simulado #1, o Laboratório 2, as aulas 31 a 43 e o voucher. Por isso o aquecimento diário desta semana é **obrigatório e dedicado a permissões**, e a ordem de corte está escrita de antemão. Decidir o que cortar com a semana já atrasada é como os dias se perderam na Semana 5.

---

## Objetivos oficiais cobertos

Fonte: LPI Learning Material, versão 1.6, Tópico 5.

| Objetivo | Peso | Áreas-chave | Arquivos, termos e utilitários |
|---|---|---|---|
| 5.1 Segurança básica e tipos de usuário | 2 | Root e usuários padrão; usuários do sistema | `/etc/passwd`, `/etc/shadow`, `/etc/group`; `id`, `last`, `who`, `w`; `sudo`, `su` |
| 5.2 Criação de usuários e grupos | 2 | Comandos de usuários e grupos; IDs de usuário | `/etc/passwd`, `/etc/shadow`, `/etc/group`, `/etc/skel/`; `useradd`, `groupadd`; `passwd` |
| 5.3 Permissões e donos de arquivos | 2 | Permissões de arquivos e diretórios e seus donos | `ls -l`, `ls -a`; `chmod`, `chown` |
| 5.4 Diretórios e arquivos especiais | 1 | Arquivos e diretórios temporários; links simbólicos | `/tmp/`, `/var/tmp/` e sticky bit; `ls -d`; `ln -s` |

Três pontos de atenção:

1. **O 5.4 já foi parcialmente praticado.** Links e `ls` foram tratados na Semana 3. Aqui entram só o que falta: o sticky bit e a diferença entre `/tmp`, `/var/tmp` e `/run`.
2. **SUID, SGID e sticky bit** aparecem no material oficial dentro das lições 5.3 e 5.4. A prova pode perguntar o que o `s` e o `t` significam em uma listagem de `ls -l`, e a diferença entre `s` minúsculo e `S` maiúsculo.
3. **`umask` não consta na lista parcial oficial do 5.3** (`ls -l`, `ls -a`, `chmod`, `chown`). Fica como opcional, só se sobrar tempo. O `chgrp` aparece no resumo da lição e entra.

---

## O que mudou em relação ao plano anterior

| Mudança | Detalhe |
|---|---|
| **Simulado geral todo domingo** | O simulado #2 é domingo 11/10. O calendário completo da série está no plano geral, seção 7 |
| **Checkpoint A** | Domingo 11/10, com critérios e resultado definidos antes. Detalhe no plano geral, seção 11 |
| **Regras de revisão e correção (06/10)** | Erros antigos de comandos já dominados passam para a **retaguarda** e saem do aquecimento. Nos simulados, só se **anotam as questões erradas**; a correção fica por conta do Notion. Ver a seção "Regras de revisão e correção" |
| **Mais prática de simulado (06/10)** | Questões da LPI no fim das Práticas 1 e 2 (20 minutos cada) e simulados mais difíceis. Ver a seção "Mais prática de simulado" |
| **Simulado #1 na segunda 05/10** | Não coube no domingo 04/10. É a primeira atividade da semana, antes do curso |
| **Laboratório 1 e frutas concluídos** | Feitos em 04/10. A Semana 5 fecha com as Correções 60 e 61 |
| **Laboratório 2 transferido da Semana 5** | Terça 06/10, três scripts obrigatórios. O `filtrar.sh` é opcional |
| **Curso 31 a 43 passa para quarta 07/10, a 2x** | O conteúdo já foi praticado no Laboratório 1, então o vídeo confirma e não ensina |
| **Correção e revisão** | Em 05/10 os erros do simulado #1 viraram as Correções 62 a 68. Em 06/10 a revisão prática foi cancelada e a correção de simulados passou para o Notion (ver "Regras de revisão e correção") |
| **Pré-checkpoint de quarta 07/10** | Decide se o voucher é para 09/11 ou direto para 16/11 |
| **Autoavaliação da Semana 5 reduzida** | 10 questões em vez de 20, sexta 09/10, três dias depois do Laboratório 2 |
| **Aquecimento dedicado a permissões** | Cinco conversões por dia, de memória. Os exercícios e o gabarito estão abaixo |

---

## Situação na abertura — 05/10

**Concluído em 04/10:** Laboratório 1 (blocos 3 a 6) e exercício das frutas. A Semana 5 fechou com as Correções 60 e 61. O que ficou aberto passa para esta semana:

| Item | Origem | Destino nesta semana |
|---|---|---|
| **Simulado #1** (40 questões) | Semana 3, adiado de novo | **Segunda 05/10**, primeira atividade do dia |
| Laboratório 2 — `backup.sh`, `contar.sh`, `usuario.sh` (`filtrar.sh` opcional) | Semana 5 | Terça 06/10 |
| Autoavaliação da Semana 5, 10 questões | Semana 5 | Sexta 09/10 |
| Curso, aulas 31 a 43 | Semana 5 | Quarta 07/10, a 2x |
| Voucher da prova e agendamento | Semana 5, adiado duas vezes | Quarta 07/10, com o pré-checkpoint |
| Revisão prática dos erros do simulado #1 (a apuração e as correções foram concluídas em 05/10) | Semana 6 | Cancelada em 06/10; vai para a retaguarda |
| Saídas do `teste.sh` e três saídas de cada editor (`vi` e `nano`) | Semana 5, Laboratório 1 | Terça 06/10, 5 minutos no aquecimento |
| Comparação de compressão com o `bzip2` | Semana 4 | Terça 06/10, no aquecimento |
| Reteste das correções do simulado #1 e da Semana 4 | Semana 5 | **Retaguarda** desde 06/10 (os simulados continuam medindo) | — |
| `.wslconfig` e teste de restauração do snapshot | Semana 0 | Sem prazo. Só com folga |

---

## Calendário da semana

| Dia | Atividade | Tempo |
|---|---|---|
| **Seg 05** | **Simulado #1** (60 min, antes de qualquer outra coisa) · apuração e correções (25 min) · aquecimento | cerca de 1h50 |
| **Ter 06** | Aquecimento · **Laboratório 2**: `backup.sh`, `contar.sh`, `usuario.sh` (**concluído**) · comparação de compressão e saídas do `vi` e `nano` (sem registro em 06/10) | cerca de 1h15 |
| **Qua 07** | **Voucher, agendamento e pré-checkpoint (10 min)** · aquecimento · **curso, aulas 31 a 43, a 2x** | cerca de 1h15 |
| **Qui 08** | Aquecimento · curso, aulas 44 a 50 · **Prática 1 — usuários e grupos**, com **20 min de questões da LPI** no fim · pedir o `simulado-02` | cerca de 2h15 |
| **Sex 09** | Aquecimento · **autoavaliação da Semana 5** (10 questões) e correção · curso, aulas 51 a 57 | cerca de 1h20 |
| **Sáb 10** | Aquecimento · **Prática 2 — permissões**, com **20 min de questões da LPI** no fim · limpeza dos usuários de teste | cerca de 1h30 |
| **Dom 11** | Aquecimento · **simulado #2** (60 min) · apuração · commits · **Checkpoint A** | cerca de 1h35 |

**Total nominal: cerca de 11h00** (10h35 antes de 06/10, menos 15 min da revisão cancelada, mais 40 min das questões da LPI).

### Carga da semana e ordem de corte

A carga passa muito do teto de 7h por uma razão simples: a Semana 5 devolveu cerca de 3h30 de dívidas (simulado #1, Laboratório 2 e curso) e o simulado dominical acrescenta 1h35. Existem duas saídas honestas: estender a semana ou cortar com critério. O plano faz as duas, nesta ordem.

**O que não se corta**, em hipótese nenhuma:

1. Simulado #1 de segunda e simulado #2 de domingo.
2. O Laboratório 2, nos três scripts obrigatórios.
3. A Prática 2, de permissões.
4. O voucher e o pré-checkpoint de quarta.
5. O aquecimento de conversões, que leva 10 minutos.

**Se o tempo faltar, corte nesta ordem:**

| Ordem | Corte | Tempo liberado | Para onde vai |
|---|---|---|---|
| 1 | `filtrar.sh` (já é opcional; fora da conta nominal) | 15 min | Fica sem data |
| 2 | Comparação de compressão e saídas do `teste.sh`, `vi` e `nano` (dívidas antigas, sem registro em 06/10) | cerca de 15 min | Retaguarda |
| 3 | Autoavaliação da Semana 5 reduzida a 5 questões | 10 min | Mesmo dia, sexta 09/10 |
| 4 | Aulas 51 a 57 | 45 min | **Segunda 12/10** (feriado, dia extra da Semana 7) |
| 5 | Prática 1 — usuários e grupos, **inclusive os 20 min de questões da LPI** | 1h20 | **Segunda 12/10** |

Com os cortes 2 a 5 a semana cai de cerca de 11h00 para **cerca de 8h30**. Os tempos são estimativas. Se as aulas 51 a 57 forem cortadas, leia antes da Prática 2 as lições 5.3 e 5.4 do PDF oficial, em cerca de 20 minutos, no lugar do vídeo.

Se a quarta à noite chegar com **menos de 3h30 acumuladas** (o nominal de segunda a quarta é cerca de 4h35), o Checkpoint A de domingo já nasce amarelo. Isso não é falha: é informação antecipada.

---

## Curso — Matheus Muller

Posição na abertura da semana: **checkpoint na aula 31** (30/09). Sem registro de avanço desde então. Restam 42 aulas (31 a 72).

| Dia | Aulas | Velocidade | Tempo estimado |
|---|---|---|---|
| Qua 07 | 31 a 43 (13 aulas) | **2x**, porque o Laboratório 1 já praticou o 3.3. Reduza para 1x só em uma aula que traga algo que o laboratório não mostrou | cerca de 50 min a 1h |
| Qui 08 | 44 a 50 (7 aulas), início do Tópico 5 | 1.25x | cerca de 45 min |
| Sex 09 | 51 a 57 (7 aulas) | 1.25x | cerca de 45 min |

As faixas de 44 a 57 são aproximadas: o número exato das aulas de cada objetivo do Tópico 5 só aparece ao chegar nelas. Se a faixa de permissões (5.3) terminar antes ou depois da 57, ajuste a divisão entre quarta e sexta, mantendo a regra: **as aulas de usuários e grupos vêm antes da Prática 1 (quinta, no mesmo dia) e as de permissões e bits especiais vêm antes da Prática 2 (sábado).**

Regras do curso:

- Anote no caderno **só o que o vídeo mostra e você ainda não sabia**.
- Em permissões, pause o vídeo e **converta de cabeça antes de o professor mostrar a resposta**.
- Registre a aula em que parou ao fim de cada dia, na tabela abaixo.

### Registro do curso

| Data | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|
| Qua 07/10 | | | |
| Qui 08/10 | | | |
| Sex 09/10 | | | |

---

## Aquecimento diário — conversões de permissão

Dez minutos por dia, de memória, **sem consultar**. Responda no papel ou em voz alta, cronometrando. A meta é converter em **menos de 3 segundos por item**. Só depois confira no gabarito, no fim deste arquivo.

A regra de conversão é uma só: `r` vale 4, `w` vale 2, `x` vale 1, e cada dígito soma os valores do seu grupo (dono, grupo, outros).

| Dia | Cinco exercícios |
|---|---|
| Seg 05 | (a) `rwxr-xr-x` · (b) `644` · (c) `rwx------` · (d) `664` · (e) `r--r-----` |
| Ter 06 | (a) `750` · (b) `rw-------` · (c) `777` · (d) `rw-r-----` · (e) `711` |
| Qua 07 | Qual a permissão final, em octal, de um arquivo `644` depois de: (a) `chmod u+x` · (b) em um `755`, `chmod g-x,o-x` · (c) em um `640`, `chmod o+r` · (d) em um `600`, `chmod g+rw` · (e) em um `755`, `chmod a-x` |
| Qui 08 | Bits especiais: (a) `4755` em símbolos · (b) `2755` em símbolos · (c) `1777` em símbolos · (d) `drwxrwsr-t` em octal · (e) `4644` em símbolos |
| Sex 09 | (a) `rwxrwxr-x` · (b) `2770` em símbolos · (c) `rw-r--r--` depois de `chmod g+w` · (d) `555` · (e) `r--------` |
| Sáb 10 | Cronometrado, sem pausa: (a) `754` · (b) `rw-rw----` · (c) `4750` em símbolos · (d) `1770` em símbolos · (e) `chmod 2755` em um diretório, e como aparece no `ls -l` |
| Dom 11 | Os cinco comandos habituais, pautados pelos erros do simulado #1 |

**Atualização de 06/10:** os itens fixos tirados dos erros antigos do simulado #1 (`cd -`, `man cp`) **saíram do aquecimento** e foram para a retaguarda. Fica só o que é conteúdo desta semana: **`chown` contra `chmod`** (Q38), mais o que travar nas conversões e nos bits especiais. O que errar vira card no Notion na hora. Se ao fim da semana a conversão ainda não sair em 3 segundos, a Semana 7 abre com uma sessão extra de permissões, e o feriado de segunda 12/10 é o dia natural para ela.

**Atualização de 07/10 — o aquecimento veio antes do conteúdo.** Você registrou que as permissões nunca tinham sido estudadas, nem nos laboratórios nem no curso: o aquecimento pedia conversão "de memória" de algo que ainda não tinha sido ensinado. O erro foi do plano, não seu. A decisão: **a primeira vez que um assunto aparece no aquecimento conta como estudo**, e a leitura da seção correspondente da cola rápida (5 minutos, abaixo) vem **antes** das cinco questões. A quarta 07/10 foi assim, e seu estudo extra foi exatamente o certo. Daqui em diante: **quinta 08/10**, leia antes a linha SUID, SGID e sticky bit da cola rápida (os bits especiais só são ensinados nas aulas e na Prática 2); **sexta 09/10 abre com um reteste cego de 3 minutos** com dois itens do tipo de quarta (`chmod` simbólico sobre octal), sem consulta, para medir se ficou. A régua dos 3 segundos por item só vale para os itens já estudados.

---

## Simulado #1 — Segunda 05/10

| Item | Valor |
|---|---|
| Arquivo | `praticas/simulado-01-diagnostico.md` |
| Quando | **Primeira atividade do dia**, antes do curso e de qualquer outra coisa |
| Formato | 40 questões, 60 minutos, cronometrado, sem terminal, sem caderno, sem internet |
| Apuração | Cerca de 25 minutos, logo em seguida |
| Meta | Não há. É um diagnóstico. Esperado: de 24 a 30 acertos (60% a 75%) |
| Observação | Com o Laboratório 1 completo, o simulado mede o shell script **depois** da prática |

Protocolo aplicado em 05/10: **marcar cada chute**, abrir o gabarito só depois e apurar **por objetivo**. As questões 18, 20, 21, 22 e 24 retestavam correções já registradas, e as quatro marcadas com firmeza foram acertadas. Daqui em diante vale o protocolo da seção "Regras de revisão e correção", que é mais enxuto.

| Tópico | Peso | Questões | Acertos | Chutes acertados |
|---|---|---|---|---|
| 1. Comunidade e open source | 7 | 1 a 7 | 5 | 0 |
| 2. Encontrando seu caminho | 9 | 8 a 16 | 5 | 0 |
| 3. Poder da linha de comando | 9 | 17 a 25 | 9 | 1 |
| 4. Sistema operacional | 8 | 26 a 33 | 6 | 1 |
| 5. Segurança e permissões | 7 | 34 a 40 | 3 | 3 |
| **Total** | **40** | | **28** | **5** |

| Campo | Valor |
|---|---|
| Data | 05/10/2026 |
| Tempo gasto | 20 min 31 s (restaram 39:29 dos 60 minutos) |
| Acertos | **28** de 40 |
| Percentual | **70%** |
| Equivalente na escala LPI | 28 × 20 = **560 de 800**, acima do corte de 500 (26 acertos) |
| Questões marcadas como chute | **10**: 22, 28, 29, 33, 34, 35, 36, 37, 39 e 40. Cinco acertadas (22, 33, 34, 36, 39) e cinco erradas (28, 29, 35, 37, 40) |

A prova corrigida, questão por questão, está em `praticas/simulado-01-diagnostico-resultado.md`.

### Regras de revisão e correção

**Atualizadas em 06/10, a pedido.** A primeira versão desta seção, de 05/10, mandava corrigir cada erro com mecanismo e revisar os Tópicos 1 a 3 com execução na VM. Duas decisões mudaram isso.

**1. Erros antigos de comandos já dominados vão para a retaguarda.** Revisitar todo dia o que já foi estudado compete com o conteúdo novo da prova, e hoje o tempo é o recurso mais escasso. O que vale:

- Saem do aquecimento diário e da fila de pendências: o reteste das questões erradas da autoavaliação da Semana 4, o reteste das questões 18, 20, 21, 22 e 24 do simulado #1, os itens fixos `cd -` e `man cp`, e a **revisão prática de terça** (cancelada).
- Esses itens ficam numa **fila de retaguarda** (plano geral, seção 9). Voltam só em dois momentos: **nos próprios simulados**, que continuam medindo se o erro voltou a acontecer, e **na revisão leve da Semana 10**, pelos cards do Notion.
- O que **não** vai para a retaguarda é conteúdo **atual**: o que for do Tópico 5 (esta semana) e do Tópico 4 (próxima) continua no aquecimento e nas práticas. Por isso o par `chown` e `chmod`, que é do objetivo 5.3, permanece.

**2. Simulados: só se anotam as questões erradas.** O que fica registrado nos arquivos é a **apuração por tópico** (acertos e chutes acertados) e a **lista das questões erradas**, com tópico e objetivo. A **correção em si**, a explicação do mecanismo, fica por conta dos seus cards no Notion. Não se abre mais a série numerada de correções para erros de simulado. A numeração continua valendo para erros de laboratório e de curso, e a próxima é a **69**.

Em resumo, o fluxo de cada simulado passa a ser: **1.** responder cronometrado e marcar os chutes; **2.** abrir o gabarito e conferir; **3.** apurar por tópico; **4.** listar as questões erradas e as chutadas; **5.** corrigir no Notion, com as suas palavras.

As Correções 62 a 68, de 05/10, ficam como estão: já foram registradas e anotadas no Notion.

**Como ler o resultado:**

- **Erros concentrados nos Tópicos 4 e 5:** esperado. O plano está funcionando.
- **Erros nos Tópicos 1, 2 ou 3:** a base pede atenção, mas, pela decisão de 06/10, os erros antigos vão para a retaguarda e os simulados seguintes dizem se voltam a acontecer.
- **Abaixo de 24 acertos:** o Checkpoint A já nasce amarelo e o gate da Semana 9 é revisitado.

### Resultado de 05/10 e leitura

**28 de 40 (70%), 560 de 800.** Está acima do corte de 26 acertos e na parte alta da expectativa (de 24 a 30). Com a reserva de que **5 dos 28 acertos foram chutes**: sem eles são **23 acertos firmes (57,5%)**.

| Tópico | Acertos | % | Leitura |
|---|---|---|---|
| 1. Comunidade e open source | 5 de 7 | 71% | Dois erros com convicção (Q3, Q7) |
| 2. Encontrando seu caminho | 5 de 9 | 56% | **Quatro erros com convicção** (Q10, Q14, Q15, Q16) |
| 3. Poder da linha de comando | **9 de 9** | 100% | Shell script, redirecionamento e filtros sustentaram. Uma questão acertada por chute (Q22) |
| 4. Sistema operacional | 6 de 8 | 75% | Os dois erros foram chutes (Q28, Q29), em tópico ainda não estudado |
| 5. Segurança e permissões | 3 de 7 | 43% | **Os três acertos foram chutes.** Acertos firmes: zero. Três erros foram chutes e um foi com convicção (Q38) |

**O que o resultado diz:**

1. **O Tópico 3 se sustentou.** As questões 18, 20, 21 e 24 retestavam correções antigas e foram acertadas sem chute. A 22 (Correção 52, `-f` do `tar`) foi acertada **por chute** e continua sem confirmação.
2. **A fragilidade está nos Tópicos 1 e 2, os "fechados".** Seis dos sete erros com convicção caem neles, em 16 questões. Esses tópicos foram estudados nas Semanas 1 a 3 e só foram medidos por autoavaliações feitas no mesmo dia (14 de 15 e 20 de 20). É a regra de retenção da Semana 4, agora com um segundo dado.
3. **A calibração foi boa onde ainda não há estudo.** Todos os cinco erros marcados como chute estão nos Tópicos 4 e 5. Nos Tópicos 1 e 2 a confiança foi maior que o acerto.
4. **Tempo: 20 min 31 s de 60**, cerca de 31 segundos por questão. O exame dá 90 segundos por questão. Parte dos erros com convicção (Q10, Q15 e Q16) cobre conteúdo que você já praticou, e isso sugere pressa e não lacuna. Há um teste simples, no passo 1 da revisão de retaguarda abaixo.

**Para o simulado #2:** use **pelo menos 45 minutos** e reserve os últimos 15 para uma segunda passada nas questões marcadas e naquelas em que o enunciado traz uma pegadinha de comando.

**Questão 40 (`umask`).** Foi escrita para este simulado, mas o `umask` **não consta na lista oficial** do objetivo 5.3. No exame real ela pode não aparecer. Trate como baixa prioridade; a Q37 (conversão `rw-r--r--` para 644) é a que importa.

### Revisão prática de terça (cancelada em 06/10; fica como retaguarda)

Por decisão de 06/10 (seção "Regras de revisão e correção"), esta revisão **não é mais uma atividade da semana**. O conteúdo permanece aqui como material de retaguarda, para usar só se sobrar tempo ou na revisão leve da Semana 10.

1. **Refaça, devagar e sem consultar, as 7 questões com convicção:** 3, 7, 10, 14, 15, 16 e 38. Classifique cada uma: **acertou** significa que era pressa; **errou de novo** significa lacuna.
2. **Execute na VM** o que dá para executar (a Q38, de `chmod` e `chown`, é conteúdo desta semana e já entra na Prática 2, bloco 3):

```bash
cd /tmp ; cd /var ; cd - ; pwd ; echo $OLDPWD      # cd - volta ao anterior
cd .. ; pwd                                         # .. sobe um nível
ls /proc | head                                     # um diretório por PID
cat /proc/$$/status | head -3                       # $$ é o PID do seu shell
ls /dev | head
ls /usr ; ls /home                                  # o que mora em cada um
cp --manual a b ; echo $?                           # opção que não existe
cp --help | head -3                                 # resumo
man cp | head -5                                    # manual completo
touch t ; chmod davi:financeiro t ; echo $?         # leia a mensagem
uname -r                                            # na VM; repita dentro do container Rocky e compare
```

3. **As duas questões do Tópico 1 (Q3 e Q7) não se executam**, então viram card no Notion, sem reler o caderno.

---

## Laboratório 2 — Terça 06/10 — Os scripts

As especificações dos quatro scripts e as soluções de referência estão no arquivo da Semana 5 (`labs/semana-05.md`, seção "Laboratório 2"). Este arquivo não as repete.

**Pré-requisito:** Laboratório 1, blocos 3 a 5 (`if`, `for`, código de saída), **concluídos em 04/10**.

| Script | Situação |
|---|---|
| `backup.sh` | Obrigatório |
| `contar.sh` | Obrigatório |
| `usuario.sh` | Obrigatório |
| `filtrar.sh` (`while read`) | Opcional: `while` e `read` não constam na lista oficial |

Regras de sempre: escreva **digitando**, um script por vez, rode `echo $?` depois de cada teste, e **quebre de propósito** pelo menos um (sem argumento, diretório inexistente, usuário que não existe).

**Situação: concluído em 06/10.** Os três scripts obrigatórios foram escritos, testados e registrados. O `filtrar.sh`, opcional, não foi feito e fica sem data. O registro corrigido está em "Registro das sessões", mais abaixo.

Registro: caderno da Semana 6, seção "Registro das sessões". Se aparecer erro conceitual, abra uma nova correção na série global.

---

## Prática 1 — Usuários e grupos — Quinta 08/10

Objetivos 5.1 e 5.2. Pré-requisito: aulas de usuários e grupos já vistas. Quarenta e cinco minutos de teclado, 10 de registro, 5 de commit. Prediga o resultado **antes** de executar e anote.

### Bloco 1 — Quem sou eu e quem está logado (10 min)

```bash
whoami
id
id root
who
w
last | head
sudo whoami
```

Para responder no caderno, executando: qual o UID do root? O que o `w` mostra que o `who` não mostra? De qual arquivo o `last` lê? Qual a diferença entre `su - alice`, `sudo -i` e `sudo su`?

### Bloco 2 — Os arquivos de contas (10 min)

```bash
head -3 /etc/passwd
sudo head -3 /etc/shadow
head -3 /etc/group
ls -l /etc/passwd /etc/shadow /etc/group /etc/gshadow
grep UID_MIN /etc/login.defs
```

Conte os campos: `/etc/passwd` tem **7**, `/etc/group` tem **4** e `/etc/shadow` tem **9**, todos separados por dois-pontos. Anote o que cada campo do `passwd` significa, e responda: por que o `/etc/passwd` é legível por todos e mesmo assim não guarda a senha? (O `x` do segundo campo aponta para o `shadow`.) O `UID_MIN` que você leu é o primeiro UID de usuário comum nesta VM.

### Bloco 3 — Criar, alterar e quebrar (20 min)

```bash
sudo groupadd dev
sudo groupadd ops
sudo useradd -m -s /bin/bash alice
sudo useradd -m -s /bin/bash -G dev bob
sudo useradd -m -s /bin/bash -g ops -G dev carol
sudo passwd alice
id alice bob carol
grep -E 'alice|bob|carol' /etc/passwd
grep -E 'dev|ops' /etc/group
ls -a /etc/skel
ls -la /home/alice
```

Agora a quebra de propósito, que é o ponto mais cobrado:

```bash
sudo usermod -aG dev alice
id alice                          # alice está em dev
sudo usermod -G ops alice         # sem o -a
id alice                          # prediga: o que aconteceu com dev?
sudo usermod -aG dev alice        # restaura, desta vez com -a
id alice
```

Registre a regra com o **mecanismo**: sem `-a`, o `-G` **substitui** a lista de grupos secundários em vez de acrescentar.

Um experimento a mais: repita o `useradd` sem o `-m` em um usuário descartável e veja com `ls -ld /home/<nome>` se o diretório pessoal foi criado. O resultado depende da distribuição. Anote o que **a sua VM** fez.

**Não apague os usuários agora.** A Prática 2 usa `alice`, `bob` e o grupo `dev`. A limpeza é no sábado.

### Questões oficiais da LPI (20 min, ao fim da sessão)

Responda no **LPI Learning Material** (PDF do Projeto) os **Exercícios Guiados** e os **Exploratórios** das lições 5.1 e 5.2, **sem consultar o texto**. As páginas estão no sumário do PDF. Só depois abra "Respostas aos Exercícios". Anote apenas as questões erradas. Se não couber nos 20 minutos, faça os Guiados e deixe os Exploratórios para a segunda 12/10.

### Para o caderno

- O que muda entre `-g` e `-G`.
- O que o `/etc/skel` faz na criação de um usuário.
- A diferença entre `su` e `sudo`.

---

## Prática 2 — Permissões — Sábado 10/10

Objetivos 5.3 e 5.4. Pré-requisito: aulas de permissões e bits especiais já vistas. Quarenta e cinco minutos de teclado, 10 de registro, 5 de commit. Em todos os blocos: **prediga, execute, compare**.

### Bloco 1 — Ler as permissões (5 min)

```bash
ls -ld /tmp /etc/shadow /usr/bin/passwd /home
```

Para cada linha, separe os 10 caracteres: tipo, dono, grupo, outros. Identifique onde aparecem o `s` e o `t`.

### Bloco 2 — `chmod` em octal e simbólico (10 min)

```bash
mkdir -p ~/lab6 && cd ~/lab6
touch teste
stat -c '%a %A %n' teste
chmod 640 teste;     stat -c '%a %A %n' teste
chmod u+x teste;     stat -c '%a %A %n' teste
chmod g=rw,o= teste; stat -c '%a %A %n' teste
chmod a-x teste;     stat -c '%a %A %n' teste
chmod 4644 teste;    stat -c '%a %A %n' teste     # repare no S maiúsculo
chmod u+x teste;     stat -c '%a %A %n' teste     # e agora o s minúsculo
```

Registre a regra: **`s` minúsculo** significa bit especial ligado e `x` presente; **`S` maiúsculo** significa bit especial ligado e `x` ausente. O mesmo vale para `t` e `T` nos outros.

### Bloco 3 — `chown` e `chgrp` (5 min)

```bash
sudo chown bob:dev teste
sudo chown :ops teste
sudo chgrp dev teste
ls -l teste
```

Anote quem pode trocar o **dono** de um arquivo (apenas o root) e quem pode trocar o **grupo** (o dono, para um grupo do qual ele faz parte).

### Bloco 4 — Diretório: o `x` é de atravessar (10 min)

```bash
mkdir -p ~/lab6/pasta && echo oi > ~/lab6/pasta/arq
```

Para cada modo de `pasta` na tabela, **prediga** se cada operação funciona e depois teste com `chmod <modo> ~/lab6/pasta`. Volte para `700` entre os testes.

| Modo | `ls pasta` | `cat pasta/arq` | `touch pasta/novo` | `rm pasta/arq` |
|---|---|---|---|---|
| 700 | | | | |
| 600 | | | | |
| 500 | | | | |
| 300 | | | | |
| 100 | | | | |

O gabarito está no fim do arquivo. A regra a registrar: **para apagar um arquivo, a permissão que conta é a do diretório, não a do arquivo.**

### Bloco 5 — SGID e sticky bit (10 min)

O exercício do material oficial, adaptado para o grupo `dev` desta semana. O diretório fica em `/srv` porque o `/home` do seu usuário não é atravessável por `alice` e `bob`.

```bash
sudo mkdir /srv/Box
sudo chown :dev /srv/Box
sudo chmod g+wxs,o+t /srv/Box
ls -ld /srv/Box                      # espere drwxrwsr-t
sudo -u alice touch /srv/Box/a
ls -l /srv/Box                       # a qual grupo pertence o arquivo?
sudo -u bob rm /srv/Box/a            # prediga: funciona?
```

Registre os dois mecanismos: o **SGID** em diretório faz os arquivos novos herdarem o **grupo do diretório**, e o **sticky bit** impede que alguém apague arquivo que não é seu, mesmo tendo `w` no diretório.

### Bloco 6 — Temporários e links (5 min)

```bash
ls -ld /tmp /var/tmp /run
echo alvo > ~/lab6/alvo
cd ~/lab6 && ln -s alvo link && mkdir sub && mv link sub/ && cat sub/link
```

Responda: qual desses diretórios é esvaziado na inicialização? Por que o `cat sub/link` falha? (O destino foi gravado como caminho **relativo ao link**.) Refaça com `ln -s ~/lab6/alvo link` e compare.

### Limpeza (5 min, ao fim da sessão)

```bash
for u in alice bob carol; do sudo userdel -r "$u"; done
sudo groupdel dev
sudo groupdel ops
sudo rm -r /srv/Box
rm -r ~/lab6
```

Se qualquer coisa sair do controle, o snapshot `limpo` existe para isso.

### Questões oficiais da LPI (20 min, ao fim da sessão)

Exercícios Guiados e Exploratórios das lições 5.3 (páginas 416 a 423 do sumário do PDF) e 5.4 (páginas 434 a 440), **sem consultar o texto**. Depois, as respostas. Anote só as questões erradas e corrija-as no Notion.

### Para o caderno

- Tabela octal ↔ simbólico preenchida de memória.
- A regra do `x` em diretórios e a do `rw` para apagar.
- SUID, SGID e sticky: o que cada um faz e como aparece no `ls -l`.

Entregável: `cheatsheets/permissoes.md`, com a cola rápida desta semana reescrita **à mão**, sem copiar daqui.

---

## Autoavaliação da Semana 5 — Sexta 09/10

Dez questões sobre shell script (objetivo 3.3), respondidas **sem consultar**, três dias depois do Laboratório 2. Mede a retenção, como na regra da Semana 4. Elabore-as na quinta 08/10, depois da Prática 1, a partir do caderno da Semana 5: variáveis e aspas, argumentos (`$1`, `$#`, `$@`), `if` com `-eq` e `=`, `for`, `exit` e `$?`, `#!` e `chmod +x`, `vi` e `nano`.

| Campo | Valor |
|---|---|
| Acertos | de 10 |
| Meta | 8 ou mais |
| Erros viram | lista das questões erradas aqui; a correção fica no Notion |

---

## Simulado #2 — Domingo 11/10

| Item | Valor |
|---|---|
| Arquivo | `praticas/simulado-02-*.md`, a ser produzido. **Peça até quinta 08/10** |
| Formato | 40 questões, 60 minutos, distribuição de pesos do exame |
| Consulta | Nenhuma |
| Meta | **24 ou mais acertos (60%)** — é o critério de aprovação do Checkpoint A |
| Objetivo de longo prazo | 65% ou mais |

Expectativa: o Tópico 4 ainda não foi estudado, então as questões dele pesam contra. O que vale ler com cuidado são os Tópicos 1 a 3 (já fechados) e o Tópico 5 (estudado nesta semana).

Protocolo (atualizado em 06/10): cronometrar, **marcar cada chute**, abrir o gabarito só depois, apurar **por tópico** e **anotar apenas as questões erradas e as chutadas**, com o tópico de cada uma. A correção é feita por você no Notion; não se abrem correções numeradas.

**Dificuldade e fonte.** Peça o `simulado-02` com a instrução de ficar **mais próximo do exame**: enunciados com cenário, pegadinhas de comando, questões de escolher mais de uma resposta e de preencher, e distratores plausíveis. Ele é escrito sob medida, e não é composto de questões reais do exame. As questões da LPI são as das Práticas 1 e 2 e as do NDG (ver "Mais prática de simulado").

| Tópico | Peso | Acertos | Chutes acertados |
|---|---|---|---|
| 1. Comunidade e open source | 7 | | |
| 2. Encontrando seu caminho | 9 | | |
| 3. Poder da linha de comando | 9 | | |
| 4. Sistema operacional | 8 | | |
| 5. Segurança e permissões | 7 | | |
| **Total** | **40** | | |

Compare com o simulado #1 (28 de 40): o que errava e agora acerta, e o que continua errando. Esse é o dado mais útil da semana.

**Tempo.** No simulado #1 você usou 20 dos 60 minutos. No #2, use **pelo menos 45** e reserve os últimos 15 para uma segunda passada nas questões marcadas e nas que tenham pegadinha de comando.

---

## Mais prática de simulado — decisão de 06/10

Você pediu mais prática de simulado, com **questões reais da LPI** e **dificuldade próxima da prova**. O que existe de verdade, e o que foi decidido:

| Fonte | O que é | Uso |
|---|---|---|
| **LPI Learning Material** (PDF do Projeto) | Escrito pela própria LPI: Exercícios Guiados e Exploratórios por lição, com respostas | Vinte minutos no fim de cada prática, a partir de hoje |
| **NDG Linux Essentials** (Cisco Networking Academy) | Quizzes por capítulo e exame final de prática, gratuitos, no formato do exame | Quizzes dos Tópicos 4 e 5 na Semana 7; exame final na quinta 22/10 |
| **Simulados escritos aqui** | Questões modeladas sobre os objetivos oficiais, não questões reais | `simulado-02` e seguintes, **mais difíceis** que o #1 |
| **Questões "reais do exame"** | Não existe simulado oficial gratuito da LPI que eu tenha encontrado; as que circulam em sites de dumps são vazadas | **Fora do plano**, pelo termo de confidencialidade e porque os gabaritos não são confiáveis |

**Sobre a dificuldade.** No simulado #1 você usou 20 dos 60 minutos e fez 70%. Para o #2 em diante, o pedido é: enunciados com cenário, pegadinhas de comando, escolha de mais de uma resposta, preenchimento e distratores plausíveis; e a regra de **usar pelo menos 45 minutos**, com segunda passada.

**Dicas recorrentes (06/10).** Peça o `simulado-02` incluindo o mínimo de questões por tema (permissões 4, `tar` 2, redirecionamento 3 com `<<`, diretórios 3) e **5 questões de preencher a lacuna**, com uma tabela de temas no gabarito. A cola, as regras de lacuna e o mini-simulado R1 (terça 13/10) estão em `praticas-reforco-dicas-recorrentes.md`. Esta semana não ganha tempo novo: o reforço começa no simulado #2 de domingo.

**Carga.** São 40 minutos a mais nesta semana (20 na quinta e 20 no sábado), e a revisão de terça, de 15 minutos, saiu. Se a semana apertar, os 20 minutos da Prática 1 são os primeiros a ir para a segunda 12/10. Os simulados de domingo e os de Fase 2 (22/10, 27/10, 29/10 e 05/11) permanecem como estão no plano geral.

---

## Pré-checkpoint — Quarta 07/10 (decisão do voucher)

Uma pergunta só: **o simulado #1 (segunda) e o Laboratório 2 (terça) estão feitos?**

**Situação em 06/10, à noite:** o simulado #1 está feito (28 de 40) e o **Laboratório 2 está concluído** (três scripts). **As duas condições estão cumpridas.** Pela regra, na quarta 07/10 você **compra o voucher e agenda 09/11**.

| Resposta | Decisão |
|---|---|
| Os dois estão feitos | Compre o voucher e agende **09/11** |
| Qualquer um dos dois não está | Agende direto para **16/11** |

O voucher ainda não foi comprado, então agendar para 16/11 não custa remarcação nem troca. Com 16/11 como data, os Checkpoints A, B e Gate mantêm as datas e os critérios, e o resultado "vermelho" passa a significar remarcar para **23/11**. A série de simulados dominicais continua igual. O procedimento completo está no plano geral, seção 11.

Anote na hora do agendamento: data escolhida ____________ · janela de remarcação sem custo ____________ · validade do voucher ____________.

---

## Checkpoint A — Domingo 11/10, à noite

Marque os cinco critérios com base no que está registrado neste arquivo, não na sensação.

| # | Critério | Cumprido |
|---|---|---|
| 1 | Curso até a aula 57 (ou ao menos até a 50, com 51 a 57 marcadas para 12/10) | |
| 2 | Laboratório 2 com os três scripts obrigatórios | **Sim (06/10)** |
| 3 | Práticas 1 e 2 feitas | |
| 4 | Simulado #2 com **24 ou mais** acertos | |
| 5 | Voucher comprado e prova agendada | |

Resultado, pela regra do plano geral (seção 11):

- **Verde**, todos cumpridos: mantém 09/11.
- **Amarelo**, um critério falhou: mantém 09/11. O item vira pendência obrigatória na segunda 12/10 e o Checkpoint B de 18/10 passa a valer como decisão final.
- **Vermelho**, dois ou mais critérios falharam, ou simulado #2 abaixo de 20 acertos: **remarcar para 16/11** na própria segunda 12/10, enquanto a remarcação é mais simples.

---

## Pendências e fila de dívidas

| Item | Origem | Estado | Prazo |
|---|---|---|---|
| **Simulado #1** | Semana 3 | **Concluído em 05/10:** 28 de 40 (70%) | — |
| Correções 62 a 68 e cards no Notion | Semana 6 | **Concluído em 05/10**: correções registradas e cards anotados | — |
| ~~Revisão prática dos erros do simulado #1~~ | Semana 6 | **Cancelada em 06/10** (retaguarda) | — |
| Laboratório 2 (três scripts) | Semana 5 | **Concluído em 06/10** | — |
| Comparação de compressão com o `bzip2` | Semana 4 | Sem registro em 06/10; primeiro corte da fila | Retaguarda, se não houver folga |
| Saídas do `teste.sh` e três saídas de `vi` e `nano` | Semana 5 | Sem registro em 06/10; primeiro corte da fila | Retaguarda, se não houver folga |
| Voucher, agendamento e pré-checkpoint | Semana 5 | Em aberto, adiado duas vezes | **Qua 07/10** |
| Curso, aulas 31 a 43 (a 2x) | Semana 5 | Em aberto | Qua 07/10 |
| Curso, aulas 44 a 50 | Semana 6 | Previsto | Qui 08/10 |
| Prática 1 — usuários e grupos | Semana 6 | Previsto | Qui 08/10 |
| Pedir o `simulado-02` | Semana 6 | Previsto | Até qui 08/10 |
| Questões oficiais da LPI, 5.1 e 5.2 (20 min) | Semana 6 | Novo em 06/10 | Qui 08/10, fim da Prática 1 |
| Autoavaliação da Semana 5 (10 questões) | Semana 5 | Previsto | Sex 09/10 |
| Curso, aulas 51 a 57 | Semana 6 | Previsto | Sex 09/10 |
| Prática 2 — permissões, com questões oficiais da LPI 5.3 e 5.4 (20 min) | Semana 6 | Previsto | Sáb 10/10 |
| Simulado #2 | Semana 6 | Previsto | Dom 11/10 |
| `.wslconfig` e teste do snapshot | Semana 0 | Sem prazo | Com folga |

---

## Registro das sessões

### Simulado #1 — segunda 05/10

**28 de 40 (70%), 560 de 800, em 20 min 31 s.** Resultado, tabelas e leitura na seção "Simulado #1", acima. As correções abaixo são dos **sete erros com convicção** (os que não foram marcados como chute). Os cinco erros marcados como chute entram na tabela de lacunas conhecidas, mais abaixo.

#### Correção 62 — "mantida pela comunidade" não é o critério de *upstream* (Q3)

Marcou **Debian**; a resposta é **Fedora**. O enunciado traz duas pistas: "mantida pela comunidade" e "upstream do RHEL". A primeira não separa as opções, porque Debian, Fedora e openSUSE são comunitárias. A que decide é a segunda. **Upstream** é de onde o código vem **antes** de chegar à distribuição de baixo:

| Linhagem | Cadeia | Pacotes |
|---|---|---|
| Debian | Debian → Ubuntu → Mint | `dpkg` e `apt` |
| Red Hat | Fedora → CentOS Stream → RHEL → Rocky e AlmaLinux | `rpm` e `dnf` |

O Debian é upstream do Ubuntu, não do RHEL. Esta cadeia também é o começo do seu RHCSA.

#### Correção 63 — contêiner compartilha o kernel; máquina virtual tem o seu (Q7)

Marcou **contêineres**; a resposta é **virtualização por hipervisor**. A palavra-chave do enunciado é "cada um com seu **próprio kernel**".

| Tecnologia | Kernel |
|---|---|
| Virtualização por hipervisor | Cada máquina virtual roda **seu próprio** kernel e um sistema completo |
| Contêiner | Todos **compartilham o kernel do hospedeiro**. O que se isola são processos, rede e arquivos |

Para ver: `uname -r` na VM e dentro do container Rocky, se ele roda dentro da VM. O número é o mesmo.

#### Correção 64 — `..` sobe na árvore, `-` volta no histórico (Q10)

Marcou que `cd -` vai para o **diretório pai**; a resposta é "volta ao diretório em que estava antes". É a **quinta** ocorrência da família `cd ..` e `cd -`: nas quatro primeiras você chamou o `cd ..` de "anterior", e agora chamou o `cd -` de "pai". Os dois estão **trocados quando aparecem juntos**: na Q9 você acertou o `cd ..` isolado.

| Símbolo | Eixo | O que faz |
|---|---|---|
| `..` | **Espaço**: a árvore de diretórios | Um nível **acima**, o pai |
| `-` | **Tempo**: de onde você veio | Volta ao diretório **anterior**, guardado em `$OLDPWD` |

Mnemônico: **ponto-ponto sobe, traço volta**. Quatro correções escritas não resolveram. Reler não conserta isto; o que conserta é executar todo dia, e por isso o par está fixo no aquecimento até domingo.

#### Correção 65 — `/usr` não é *user* (Q14)

Marcou **User**; a resposta é **Unix System Resources**. O nome induz ao erro. Os arquivos pessoais ficam em `/home`; o `/usr` guarda programas e bibliotecas do sistema. Para ver: `ls /usr ; ls /home`.

#### Correção 66 — `/proc` é de *processos*, `/dev` é de *dispositivos* (Q15)

Marcou **/dev**; a resposta é **/proc**. A pista do enunciado é "informações sobre os processos": **proc** vem de *process*. O `/dev` guarda os arquivos de dispositivo (`sda`, `tty`, `null`). Para ver: `ls /proc | head` mostra um diretório numerado por PID, e `ls /dev | head` mostra dispositivos.

#### Correção 67 — a documentação completa é o `man`; o `--manual` não existe no `cp` (Q16)

Marcou **`cp --manual`**; a resposta é **`man cp`**. A opção tem um nome plausível, e é por isso que funciona bem como distrator.

| Forma | O que entrega |
|---|---|
| `man cp` | O manual **completo**, com todas as opções |
| `cp --help` | Um **resumo** de uso |
| `help cd` | Só funciona para comandos **internos** do shell |
| `cp --manual` | Não existe. O `cp` responde com erro de opção |

Quem entrega a documentação são **programas** (`man`, `info`), e não uma opção que valha para todo comando. Opção com nome plausível se testa executando.

#### Correção 68 — `chmod` muda permissões; `chown` muda dono (Q38)

Marcou **`chmod davi:financeiro`**; a resposta é **`chown davi:financeiro`**. Este erro **não** foi marcado como chute: foi convicção.

| Comando | Nome vem de | O que altera |
|---|---|---|
| `chmod` | *change **mod**e* | As **permissões** (`rwx`, `644`) |
| `chown` | *change **own**er* | O **dono** e, com `:`, o **grupo** |
| `chgrp` | *change **gr**ou**p*** | Só o **grupo** |

A sintaxe `dono:grupo` pertence ao `chown`. Para ver: `touch t ; chmod davi:financeiro t` responde com erro de modo inválido. A Prática 2, bloco 3, aplica `chown` e `chgrp`.

#### Lacunas conhecidas — os cinco erros marcados como chute

Você sabia que não sabia, e o simulado confirmou. Não geram correção agora; definem a ênfase.

| Q | Tema | Resposta | Onde será estudado |
|---|---|---|---|
| 28 | Processos em tempo real | `top` (o `free -h` mostra memória) | Semana 7, Prática 1 |
| 29 | Sinal padrão do `kill` | `SIGTERM` (15). O `SIGKILL` (9) só com `kill -9` | Semana 7, Prática 1 |
| 35 | Último campo do `/etc/passwd` | O **shell de login**, 7º campo. O GID é o 4º | Semana 6, Prática 1, bloco 2 |
| 37 | `rw-r--r--` em octal | **644**. O `664` é `rw-rw-r--`, que é o padrão da sua VM | Aquecimento de conversões |
| 40 | Quem retira permissões de arquivo novo | `umask` | Baixa prioridade: fora da lista oficial |

A Q37 merece atenção: você marcou **664**, e `rw-rw-r--` é justamente o que os arquivos novos recebem na sua VM. Pode ter sido o que você já vê no terminal, e não a conversão do enunciado.

#### Observações (sem número)

- **A Q11** foi respondida `PATH`, com um sublinhado na frente. No exame real, em campo de preenchimento, escreva **só a palavra**.
- **Erros com convicção são os mais caros.** Dos 12 erros, 7 foram com convicção e 5 com chute. Os 7 são os mais caros: erro sabido se estuda, erro confiante se defende.

### Laboratório 2 — terça 06/10 — CONCLUÍDO

Os três scripts obrigatórios foram escritos, testados e funcionaram com os códigos de saída pedidos (0, 1 e 2). O `filtrar.sh`, opcional, não foi feito e fica sem data.

**Avaliação.** As três soluções cumprem a especificação e **vão além da solução de referência**: validam se o diretório existe, mandam as mensagens de erro para o `stderr` (`>&2`), protegem o argumento com `--`, usam `if comando` para testar o código de saída, e o `usuario.sh` usa `grep -Fxq` em vez de `grep -q "^$1:"`, o que evita que um nome com `.` seja lido como expressão regular. Não há erro conceitual, por isso **nenhuma correção numerada** foi aberta. O que segue são ajustes de caderno e dois testes opcionais.

#### `backup.sh`

```bash
#!/bin/bash

if [ "$#" -ne 1 ]; then
    echo "Uso: $0 <diretorio>" >&2
    exit 1
fi

if [ ! -d "$1" ]; then
    echo "Erro: diretorio inexistente: $1" >&2
    exit 1
fi

data=$(date +%Y-%m-%d)
destino="backup-${data}.tar.gz"

if tar -czf "$destino" -- "$1"; then
    echo "Backup criado: $destino"
    exit 0
else
    echo "Erro: nao foi possivel concluir o backup." >&2
    exit 1
fi
```

O que cada parte faz:

| Trecho | Mecanismo |
|---|---|
| `[ "$#" -ne 1 ]` | `-ne` é "numericamente diferente". Compara **números**; para texto seria `!=` |
| `[ ! -d "$1" ]` | `-d` testa se é um diretório; o `!` inverte |
| `data=$(date +%Y-%m-%d)` | A substituição de comando guarda a **saída** do `date` na variável |
| `"backup-${data}.tar.gz"` | As chaves separam o nome da variável do texto vizinho |
| `if tar ...; then` | O `if` testa o **código de saída** do `tar`: 0 é sucesso |
| `--` | Encerra as opções: um diretório chamado `-x` não é lido como opção |
| `>&2` | Manda a mensagem para o `stderr`, o fluxo de erro |

Testes registrados: com `~/lab5` o código foi `0`, com a mensagem de confirmação e a listagem do `tar -tzf`; sem argumento, saiu `Uso: /home/davi/lab5/scripts/backup.sh <diretorio>` com código `1`.

Ajustes de caderno:

1. **A frase "criei um diretório para os backups" não descreve o script.** Ele não cria diretório; cria o arquivo `.tar.gz` no **diretório atual**. Reescreva: "Saída `0`: o backup foi criado e a mensagem de confirmação apareceu."
2. **O ponto mais valioso da sua anotação está certo:** o arquivo nasce no diretório onde se executa, e uma nova execução **no mesmo dia** usa o mesmo nome e **substitui** o anterior, em silêncio. O motivo é que o `tar -c` cria o arquivo de saída do zero, apagando o que tinha o mesmo nome. Para guardar duas cópias no mesmo dia, o nome precisaria de hora: `date +%Y-%m-%d_%H%M%S`.
3. **A listagem começa em `home/davi/...`, sem a barra inicial.** É o `tar` removendo a `/` do começo do caminho (ele avisa `Removing leading '/' from member names`), para que a extração não sobrescreva caminhos absolutos.
4. **A listagem traz dois itens que não deveriam estar num backup:** `scripts/backup-2026-10-06.tar.gz`, ou seja, um backup anterior **dentro** do novo, e `scripts/.ola.sh.swp`. O primeiro mostra que o destino estava dentro da origem; a regra prática é gerar o backup **fora** da árvore que está sendo copiada (por exemplo, executando a partir de `~`). O segundo é o arquivo temporário do `vi` ainda aberto ou interrompido em `ola.sh`; o `vi` o apaga ao sair normalmente (`:q`, `:wq` ou `ZZ`). Antes de apagar, confira que não há `vi` aberto (`jobs` e `pgrep -a vi`); depois, `rm ~/lab5/scripts/.ola.sh.swp`. Se ficar, o próximo `vi ola.sh` avisará que o arquivo de swap já existe.
5. No `nano`, `Ctrl+O` grava e `Enter` confirma o nome. Falta anotar o `Ctrl+X`, que **sai**.

#### `contar.sh`

```bash
#!/bin/bash

set -o pipefail

if [ "$#" -ne 1 ]; then
    echo "Uso: $0 <diretorio>" >&2
    exit 1
fi

if [ ! -d "$1" ]; then
    echo "Erro: diretorio inexistente: $1" >&2
    exit 1
fi

for ext in txt log conf; do
    if total=$(find "$1" -type f -name "*.$ext" | wc -l); then
        echo "$ext: $total"
    else
        echo "Erro: a contagem de $ext ficou incompleta." >&2
        exit 1
    fi
done

exit 0
```

| Trecho | Mecanismo |
|---|---|
| `for ext in txt log conf` | O laço roda três vezes; em cada uma, `$ext` vale uma extensão |
| `find "$1" -type f -name "*.$ext"` | Procura no diretório recebido e em todas as subpastas; `-type f` só arquivos regulares; `-name` filtra pelo nome |
| `"*.$ext"` entre aspas | O shell **não expande o `*`** antes de o `find` recebê-lo (a mesma lógica da Semana 4), mas expande o `$ext` |
| `\| wc -l` | O `find` imprime um caminho por linha; o `wc -l` conta as linhas |
| `if total=$(...)` | O `if` testa o **código de saída** da substituição de comando |
| `set -o pipefail` | Sem ele, o código de um pipeline é o do **último** comando (o `wc`, quase sempre 0). Com ele, vale o primeiro código diferente de zero, e uma falha do `find` deixa de ficar escondida |

Teste registrado: com `a.txt`, `b.txt`, `subpasta/c.txt`, `app.log` e `config.conf`, a saída foi `txt: 3`, `log: 1`, `conf: 1` e código `0`. Está correto: o `c.txt` na subpasta entra na contagem.

Ajustes de caderno:

1. No caderno, `type f` e `name "*.txt"` aparecem **sem o traço**. No terminal são `-type f` e `-name`. É provável que seja formatação do Notion; confira.
2. **Faltou explicar o `set -o pipefail` e o `if total=$(...)`**, que são as duas decisões menos comuns do script. A tabela acima traz o mecanismo. O `pipefail` não consta na lista oficial da prova; vale pelo entendimento de código de saída.
3. **Teste de aceitação não registrado:** a especificação pede `./contar.sh /etc`. **Previsão a confirmar:** como usuário comum, o `find` encontra diretórios que não pode ler e termina com código 1; com o `pipefail`, o `if` entra no `else`, o script imprime `Erro: a contagem de txt ficou incompleta.` e **sai sem contar** `log` e `conf`. A solução de referência descarta os erros com `2>/dev/null` e conta o que consegue ler. Não é erro seu: é uma escolha, mais rigorosa. Se quiser que `/etc` funcione, acrescente `2>/dev/null` ao `find`, ou aceite o comportamento e anote-o.

#### `usuario.sh`

```bash
#!/bin/bash

if [ "$#" -ne 1 ]; then
    echo "Uso: $0 <nome>" >&2
    exit 2
fi

if cut -d: -f1 /etc/passwd | grep -Fxq -- "$1"; then
    echo "O usuario $1 existe"
    exit 0
else
    echo "O usuario $1 nao existe"
    exit 1
fi
```

| Trecho | Mecanismo |
|---|---|
| `cut -d: -f1 /etc/passwd` | `-d:` usa `:` como separador; `-f1` fica com o primeiro campo, o nome |
| `grep -F` | Trata o nome como **texto literal**, não como expressão regular |
| `grep -x` | Exige que a **linha inteira** seja igual ao nome, então `davi` não casa com `davidson` |
| `grep -q` | Não imprime nada; o resultado vem só pelo código de saída |
| `--` | Encerra as opções, protegendo um nome que comece com `-` |
| `exit 2` | Falta de argumento. O 1 fica para "usuário não existe" |

Testes registrados: `./usuario.sh "$(id -un)"` saiu com `0`, `./usuario.sh fantasma` com `1` e `./usuario.sh` sem argumento com `2`. Os três códigos batem com a especificação.

Ajustes de caderno:

1. **`echo$?` está sem espaço.** No terminal, o shell trocaria `$?` pelo valor e procuraria um comando como `echo0`, que não existe. O correto é `echo $?`.
2. **As mensagens anotadas diferem das do script.** O script imprime `O usuario davi existe` e `O usuario fantasma nao existe`, e o anotado traz "já existe" e "não existe". Copie a saída real: o caderno vale como evidência do que rodou.
3. **O `grep -Fxq -- "$1"` aparece com travessão e aspas curvas** (`— “$1”`). São correções automáticas do editor; no terminal só funcionam `--` e aspas retas `"`.
4. **Este script não usa `pipefail`, e isso é uma boa decisão.** O `grep -q` termina no primeiro acerto e fecha o pipe; o `cut` pode então encerrar por **SIGPIPE** (código 141). Com `pipefail`, o `if` poderia ver esse 141 e dizer que o usuário **não existe**, mesmo ele existindo. No `contar.sh` o `pipefail` faz sentido; neste, atrapalharia.

#### Testes opcionais, 3 minutos

```bash
./contar.sh /etc ; echo $?                              # confirma a previsão do pipefail
mkdir "dir com espaco" ; ./backup.sh "dir com espaco"   # a armadilha das aspas
cd ~ ; ./lab5/scripts/backup.sh ~/lab5 ; tar -tzf backup-*.tar.gz | grep backup-   # o backup fora da origem não se inclui
```


### Aquecimento de permissões — quarta 07/10

Estudo prévio feito por conta própria, antes de responder (o conteúdo ainda não tinha sido ensinado; ver a atualização de 07/10 acima), seguido de prática no terminal em `lab6/permissoes`.

**Resultado das cinco questões: 5 de 5**, todas conferidas no terminal com `stat -c '%n: %a (%A)'`. Como foi estudo assistido, o resultado **não conta como medida de retenção**.

| Questão | Comando | Resultado | Conferência |
|---|---|---|---|
| (a) `644` | `chmod u+x` | `744` (`rwxr--r--`) | Correto |
| (b) `755` | `chmod g-x,o-x` | `744` | Correto |
| (c) `640` | `chmod o+r` | `644` | Correto |
| (d) `600` | `chmod g+rw` | `660` | Correto |
| (e) `755` | `chmod a-x` | `644` | Correto |

**Conteúdo coberto nas anotações:** leitura do octal por categoria (dono, grupo, outros), tabela de 0 a 7, `chmod` simbólico (`u`, `g`, `o`, `a`; `+`, `-`; vírgula para duas alterações), leitura do `ls -l`, `stat -c` com `%n`, `%a` e `%A`, e a diferença entre `chmod` e `chown` (com `id -un` e `id -gn` para descobrir os nomes).

**Ajustes de caderno (sem correção numerada, não há erro conceitual):**

1. Nas questões (c) e (d), "Outros: `--`" e "Grupo: `--`" têm **três** posições: `---`. Em `640`, os outros são `---`; em `600`, o grupo é `---`.
2. "Somente a posição dos outros usuários muda" (falta o `e` em "Somente").
3. `rw- r-- r—`: o último traço é um travessão; deve ser `r--`, com dois hífens.
4. Acrescentar ao quadro do `chown`: **só o root muda o dono** (por isso o `sudo`); o usuário comum só pode mudar o **grupo**, e só para um grupo de que faça parte (`chgrp`). `chown :grupo arquivo` muda só o grupo.
5. A data aparece como `Oct 7` e `out 7` nas listagens: o idioma do terminal variou entre as sessões. Não afeta nada, mas explica a diferença se aparecer na prova.

**Pontos fortes:** a conferência por `stat -c` ligou o octal ao símbolo nos dois sentidos, e a explicação de cada parte do `chmod u+x` está correta.

### Prática 1 — quinta 08/10

*A preencher.*

### Prática 2 — sábado 10/10

*A preencher.*

### Correções da semana

A numeração segue a série global. A última registrada na Semana 5 foi a **61** (o `2` do `2>` não é o `2` do `$?`). Em 05/10, o simulado #1 gerou as **Correções 62 a 68**. **A próxima é a 69.**

O painel de resultados, a lista de questões erradas e o índice das Correções 1 a 68 estão em `praticas-resultados-simulados-e-correcoes.md`.

| # | Tema | Origem |
|---|---|---|
| 62 | *Upstream* do RHEL é o Fedora, não o Debian | Q3 |
| 63 | Contêiner compartilha o kernel; VM tem o seu | Q7 |
| 64 | `..` sobe na árvore, `-` volta no histórico (5ª ocorrência) | Q10 |
| 65 | `/usr` não é *user* | Q14 |
| 66 | `/proc` é de processos, `/dev` de dispositivos | Q15 |
| 67 | `man` é o manual; `--manual` não existe no `cp` | Q16 |
| 68 | `chmod` muda permissões, `chown` muda dono | Q38 |

Os cards das Correções 62 a 68 foram anotados no Notion em 05/10. O Laboratório 2 de 06/10 **não gerou correção numerada**: não houve erro conceitual, só ajustes de caderno. A partir de 06/10, erros de simulado não geram correção numerada. **A próxima, para erros de laboratório e de curso, é a 69.**

*A preencher.*

---

## Checklist da semana

- [ ] Abertura: tabela de dívidas conferida
- [x] **Simulado #1** e apuração por objetivo (segunda): 28 de 40, 70%
- [x] Correções 62 a 68 registradas (segunda)
- [x] Cards das Correções 62 a 68 no Notion (05/10)
- [x] Arquivos ocultos: dívida encerrada em 05/10, a pedido (comandos já dominados)
- [ ] Aquecimento de conversões: segunda a domingo
- [x] ~~Revisão prática dos erros dos Tópicos 1 a 3 (terça)~~: cancelada em 06/10 (retaguarda)
- [x] Laboratório 2, três scripts (terça 06/10)
- [ ] Comparação de compressão refeita; saídas do `teste.sh`, do `vi` e do `nano` registradas: sem registro em 06/10, primeiro corte da fila
- [ ] **Voucher, agendamento e pré-checkpoint**, com a janela de remarcação anotada (quarta)
- [ ] Curso, aulas 31 a 43 (quarta)
- [ ] Curso, aulas 44 a 50 (quinta)
- [ ] Prática 1, usuários e grupos, e questões oficiais da LPI 5.1 e 5.2 (quinta)
- [ ] `simulado-02` pedido (até quinta)
- [ ] Autoavaliação da Semana 5 e correção (sexta)
- [ ] Curso, aulas 51 a 57 (sexta, ou segunda 12/10 se cortadas)
- [ ] Prática 2, permissões, questões oficiais da LPI 5.3 e 5.4 e limpeza dos usuários de teste (sábado)
- [ ] `cheatsheets/permissoes.md` escrito à mão
- [ ] Simulado #2 e apuração por objetivo (domingo)
- [ ] Checkpoint A preenchido
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-06.md` preenchido, `cheatsheets/permissoes.md`, os três scripts do Laboratório 2 em `scripts/`, voucher comprado com a prova agendada, resultados dos simulados #1 e #2 e o Checkpoint A preenchido.

---

## Cola rápida — permissões e contas

**Octal**

| Símbolo | Valor | Combinação | Octal |
|---|---|---|---|
| `r` | 4 | `rwx` | 7 |
| `w` | 2 | `r-x` | 5 |
| `x` | 1 | `r--` | 4 |
| `-` | 0 | `rw-` | 6 |

**Bits especiais**

| Bit | Octal (1º dígito) | Em arquivo | Em diretório | Aparece como |
|---|---|---|---|---|
| SUID | 4 | Executa com os privilégios do **dono** | Sem efeito prático nesta prova | `s` no lugar do `x` do dono |
| SGID | 2 | Executa com os privilégios do **grupo** | Arquivos novos herdam o **grupo do diretório** | `s` no lugar do `x` do grupo |
| Sticky | 1 | Ignorado pelo kernel | Só o dono do arquivo (ou o root) apaga ou renomeia | `t` no lugar do `x` de outros |

Maiúsculo (`S`, `T`) significa bit ligado **sem** o `x` correspondente.

**Diretórios**

- `r` lista os nomes. `x` permite **atravessar** e acessar o que está dentro. `w` (junto com `x`) permite criar, apagar e renomear entradas.
- Apagar um arquivo depende da permissão do **diretório**, não da do arquivo.

**Contas**

| Arquivo | Campos | O que guarda |
|---|---|---|
| `/etc/passwd` | 7 | Usuário, `x`, UID, GID, comentário, home, shell |
| `/etc/group` | 4 | Grupo, `x`, GID, membros |
| `/etc/shadow` | 9 | Senha criptografada e prazos |
| `/etc/skel/` | — | Modelo copiado para a home de usuário novo |

| Comando | Para quê |
|---|---|
| `useradd -m -s /bin/bash -G g1,g2 nome` | Criar usuário com home, shell e grupos secundários |
| `usermod -aG grupo nome` | **Acrescentar** a um grupo. Sem o `-a`, substitui |
| `passwd nome` | Definir ou trocar a senha |
| `userdel -r nome` | Remover o usuário e a home |
| `groupadd` / `groupdel` | Criar / remover grupo |
| `id`, `who`, `w`, `last` | Quem sou eu / quem está logado / histórico de logins |

---

## Gabarito do aquecimento e do Bloco 4

**Não abra antes de responder.**

| Dia | Respostas |
|---|---|
| Seg 05 | (a) 755 · (b) `rw-r--r--` · (c) 700 · (d) `rw-rw-r--` · (e) 440 |
| Ter 06 | (a) `rwxr-x---` · (b) 600 · (c) `rwxrwxrwx` · (d) 640 · (e) `rwx--x--x` |
| Qua 07 | (a) 744 · (b) 744 · (c) 644 · (d) 660 · (e) 644 |
| Qui 08 | (a) `rwsr-xr-x` · (b) `rwxr-sr-x` · (c) `rwxrwxrwt` · (d) 3775 · (e) `rwSr--r--` |
| Sex 09 | (a) 775 · (b) `rwxrws---` · (c) 664 · (d) `r-xr-xr-x` · (e) 400 |
| Sáb 10 | (a) `rwxr-xr--` · (b) 660 · (c) `rwsr-x---` · (d) `rwxrwx--T` · (e) `drwxr-sr-x` |

**Bloco 4 — diretório e operações** (assumindo que o arquivo `arq` tem permissão de leitura)

| Modo | `ls pasta` | `cat pasta/arq` | `touch pasta/novo` | `rm pasta/arq` |
|---|---|---|---|---|
| 700 | funciona | funciona | funciona | funciona |
| 600 | lista os nomes, mas com erro nos detalhes | **negado** (sem `x`) | negado | negado |
| 500 | funciona | funciona | **negado** (sem `w`) | **negado** (sem `w` no diretório) |
| 300 | **negado** (sem `r`) | funciona | funciona | funciona |
| 100 | negado | funciona | negado | negado |

No modo 600, o que o `ls` mostra exatamente varia conforme o alias de cor e a versão; anote o que apareceu na sua VM. Todo o resto da tabela decorre das três regras da cola rápida.