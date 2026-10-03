# Semana 6 — Tópico 5, usuários e permissões, e o fechamento das dívidas da Semana 5

Período: 05/10 a 11/10/2026 (segunda a domingo)
Objetivos da prova: 5.1, 5.2, 5.3 e 5.4 — Tópico 5, peso 7 de 40
Carga nominal: cerca de 9h, acima do teto de 7h. A seção "Carga da semana e ordem de corte" explica o motivo e o que sai primeiro se o tempo faltar
Marco da semana: **Checkpoint A, domingo 11/10**, com decisão objetiva sobre manter ou remarcar a prova de 09/11

Observação sobre a natureza desta semana: ela carrega duas coisas ao mesmo tempo. De um lado, conteúdo novo e dependente de repetição, porque converter `rwxr-xr--` em `754` precisa virar reflexo. De outro, as dívidas que a Semana 5 não fechou: o Laboratório 2, as aulas 31 a 43 e o voucher. Por isso o aquecimento diário desta semana é **obrigatório e dedicado a permissões**, e a ordem de corte está escrita de antemão. Decidir o que cortar com a semana já atrasada é como os dias se perderam na Semana 5.

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
| **Laboratório 2 transferido da Semana 5** | Terça 06/10, três scripts obrigatórios. O `filtrar.sh` é opcional |
| **Autoavaliação da Semana 5 reduzida** | 10 questões em vez de 20, sexta 09/10, três dias depois do Laboratório 2 |
| **Aquecimento dedicado a permissões** | Cinco conversões por dia, de memória. Os exercícios e o gabarito estão abaixo |

---

## Situação na abertura — 05/10

Esta tabela assume que o domingo 04/10 correu como planejado. Ao abrir a semana, confira o checklist do domingo no arquivo da Semana 5 e marque aqui o que sobrou.

| Item | Origem | Destino nesta semana |
|---|---|---|
| Curso, aulas 31 a 43 | Semana 5 | Segunda 05/10 |
| Laboratório 2 — `backup.sh`, `contar.sh`, `usuario.sh` (`filtrar.sh` opcional) | Semana 5 | Terça 06/10 |
| Voucher da prova e agendamento para 09/11 | Semana 5, adiado duas vezes | Quarta 07/10, 10 minutos |
| Exercício das frutas e bloco 6 (`vi` e `nano`) | Semana 5, **só se cortados no domingo** | Segunda 05/10, 25 minutos |
| Registro das observações sobre arquivos ocultos | Semana 3 | Segunda 05/10, 10 minutos |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | Semana 3 | Segunda 05/10, 30 segundos |
| Comparação de compressão com o `bzip2` | Semana 4 | Terça 06/10, no aquecimento |
| Reteste das correções do simulado #1 | Semana 5 | Aquecimento diário, a partir de segunda |
| `.wslconfig` e teste de restauração do snapshot | Semana 0 | Sem prazo. Só com folga |

---

## Calendário da semana

| Dia | Atividade | Tempo |
|---|---|---|
| **Seg 05** | Abertura (5 min) · aquecimento · dívidas curtas (arquivos ocultos, `rm`, e frutas e bloco 6 se foram cortados) · **curso, aulas 31 a 43** | cerca de 1h30 |
| **Ter 06** | Aquecimento + comparação de compressão · **Laboratório 2**: `backup.sh`, `contar.sh`, `usuario.sh` | cerca de 1h15 |
| **Qua 07** | **Voucher e agendamento (10 min)** · aquecimento · curso, aulas 44 a 50 | cerca de 1h05 |
| **Qui 08** | Aquecimento · **Prática 1 — usuários e grupos** · pedir o simulado #2 até hoje | cerca de 1h10 |
| **Sex 09** | Aquecimento · **autoavaliação da Semana 5** (10 questões) e correção · curso, aulas 51 a 57 | cerca de 1h20 |
| **Sáb 10** | Aquecimento · **Prática 2 — permissões** · limpeza dos usuários de teste | cerca de 1h10 |
| **Dom 11** | Aquecimento · **simulado #2** (60 min) · apuração · commits · **Checkpoint A** | cerca de 1h35 |

**Total nominal: cerca de 9h05.**

### Carga da semana e ordem de corte

A carga passa do teto de 7h por uma razão simples: a Semana 5 devolveu cerca de 2h de dívidas (curso e Laboratório 2) e o simulado dominical acrescentou 1h35. Existem duas saídas honestas: estender a semana ou cortar com critério. O plano faz as duas, nesta ordem.

**O que não se corta**, em hipótese nenhuma:

1. Simulado #2 de domingo.
2. As aulas de shell script entre as 31 e 43, a 1x.
3. O Laboratório 2, nos três scripts obrigatórios.
4. A Prática 2, de permissões.
5. O aquecimento de conversões, que leva 10 minutos.

**Se o tempo faltar, corte nesta ordem:**

| Ordem | Corte | Tempo liberado | Para onde vai |
|---|---|---|---|
| 1 | `filtrar.sh` (já é opcional) | 15 min | Fica sem data |
| 2 | Aulas 51 a 57 | 45 min | **Segunda 12/10** (feriado, dia extra da Semana 7) |
| 3 | Autoavaliação da Semana 5 reduzida a 5 questões | 10 min | Mesmo dia, sexta 09/10 |
| 4 | Aulas 31 a 43 que **não** sejam de shell script, a 2x | 20 min | Mesma segunda 05/10 |

Se mesmo assim a quarta à noite chegar com **menos de 3h acumuladas** (o nominal de segunda a quarta é cerca de 3h50), o Checkpoint A de domingo já nasce amarelo. Isso não é falha: é informação antecipada.

---

## Curso — Matheus Muller

Posição na abertura da semana: **checkpoint na aula 31** (30/09). Sem registro de avanço desde então. Restam 42 aulas (31 a 72).

| Dia | Aulas | Velocidade | Tempo estimado |
|---|---|---|---|
| Seg 05 | 31 a 43 (13 aulas) | **1x** nas de shell script (3.3); 2x nas que só repetem o já praticado | cerca de 1h15 a 1h30 |
| Qua 07 | 44 a 50 (7 aulas), início do Tópico 5 | 1.25x | cerca de 45 min |
| Sex 09 | 51 a 57 (7 aulas) | 1.25x | cerca de 45 min |

As faixas de 44 a 57 são aproximadas: o número exato das aulas de cada objetivo do Tópico 5 só aparece ao chegar nelas. Se a faixa de permissões (5.3) terminar antes ou depois da 57, ajuste a divisão entre quarta e sexta, mantendo a regra: **as aulas de usuários e grupos vêm antes da Prática 1 (quinta) e as de permissões e bits especiais vêm antes da Prática 2 (sábado).**

Regras do curso:

- Anote no caderno **só o que o vídeo mostra e você ainda não sabia**.
- Em permissões, pause o vídeo e **converta de cabeça antes de o professor mostrar a resposta**.
- Registre a aula em que parou ao fim de cada dia, na tabela abaixo.

### Registro do curso

| Data | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|
| Seg 05/10 | | | |
| Qua 07/10 | | | |
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

O que errar vira card no Notion na hora. Se ao fim da semana a conversão ainda não sair em 3 segundos, a Semana 7 abre com uma sessão extra de permissões, e o feriado de segunda 12/10 é o dia natural para ela.

---

## Laboratório 2 — Terça 06/10 — Os scripts

As especificações dos quatro scripts e as soluções de referência estão no arquivo da Semana 5 (`labs/semana-05.md`, seção "Laboratório 2"). Este arquivo não as repete.

**Pré-requisito:** Laboratório 1, blocos 3 a 5, feitos no domingo 04/10.

| Script | Situação |
|---|---|
| `backup.sh` | Obrigatório |
| `contar.sh` | Obrigatório |
| `usuario.sh` | Obrigatório |
| `filtrar.sh` (`while read`) | Opcional: `while` e `read` não constam na lista oficial |

Regras de sempre: escreva **digitando**, um script por vez, rode `echo $?` depois de cada teste, e **quebre de propósito** pelo menos um (sem argumento, diretório inexistente, usuário que não existe).

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
| Erros viram | correção com mecanismo e card no Notion |

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

Protocolo de sempre: cronometrar, **marcar cada chute**, abrir o gabarito só depois, apurar **por objetivo** e não por questão, e abrir correções com mecanismo para os erros conceituais.

| Tópico | Peso | Acertos | Chutes acertados |
|---|---|---|---|
| 1. Comunidade e open source | 7 | | |
| 2. Encontrando seu caminho | 9 | | |
| 3. Poder da linha de comando | 9 | | |
| 4. Sistema operacional | 8 | | |
| 5. Segurança e permissões | 7 | | |
| **Total** | **40** | | |

Compare com o simulado #1: o que errava e agora acerta, e o que continua errando. Esse é o dado mais útil da semana.

---

## Checkpoint A — Domingo 11/10, à noite

Marque os cinco critérios com base no que está registrado neste arquivo, não na sensação.

| # | Critério | Cumprido |
|---|---|---|
| 1 | Curso até a aula 57 (ou ao menos até a 50, com 51 a 57 marcadas para 12/10) | |
| 2 | Laboratório 2 com os três scripts obrigatórios | |
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
| Curso, aulas 31 a 43 | Semana 5 | Em aberto | Seg 05/10 |
| Laboratório 2 (três scripts) | Semana 5 | Em aberto | Ter 06/10 |
| Voucher da prova e agendamento | Semana 5 | Em aberto, adiado duas vezes | Qua 07/10 |
| Registro das observações sobre arquivos ocultos | Semana 3 | Em aberto | Seg 05/10 |
| Limpeza: `rm 'sudo apt upgrade -y'` | Semana 3 | Em aberto | Seg 05/10 |
| Comparação de compressão com o `bzip2` | Semana 4 | Em aberto | Ter 06/10 |
| Frutas e bloco 6, se cortados no domingo | Semana 5 | Condicional | Seg 05/10 |
| Curso, aulas 44 a 57 | Semana 6 | Previsto | Qua 07 e sex 09/10 |
| Prática 1 — usuários e grupos | Semana 6 | Previsto | Qui 08/10 |
| Prática 2 — permissões | Semana 6 | Previsto | Sáb 10/10 |
| Autoavaliação da Semana 5 (10 questões) | Semana 5 | Previsto | Sex 09/10 |
| Simulado #2 | Semana 6 | Previsto | Dom 11/10 |
| Pedir o `simulado-02` | Semana 6 | Previsto | Até qui 08/10 |
| `.wslconfig` e teste do snapshot | Semana 0 | Sem prazo | Com folga |

---

## Registro das sessões

### Laboratório 2 — terça 06/10

*A preencher.*

### Prática 1 — quinta 08/10

*A preencher.*

### Prática 2 — sábado 10/10

*A preencher.*

### Correções da semana

A numeração segue a série global. A última registrada até a Semana 5 foi a **60**, mais as que o simulado #1 gerar. A próxima é a seguinte a essa.

*A preencher.*

---

## Checklist da semana

- [ ] Abertura: checklist do domingo conferido e tabela de dívidas atualizada
- [ ] Aquecimento de conversões: segunda a domingo
- [ ] Curso, aulas 31 a 43 (segunda)
- [ ] Arquivos ocultos registrados, `rm` feito (segunda)
- [ ] Laboratório 2, três scripts (terça)
- [ ] Comparação de compressão refeita (terça)
- [ ] Voucher comprado e prova agendada, com a data-limite de remarcação anotada (quarta)
- [ ] Curso, aulas 44 a 50 (quarta)
- [ ] Prática 1, usuários e grupos (quinta)
- [ ] `simulado-02` pedido (até quinta)
- [ ] Autoavaliação da Semana 5 e correção (sexta)
- [ ] Curso, aulas 51 a 57 (sexta, ou segunda 12/10 se cortadas)
- [ ] Prática 2, permissões, e limpeza dos usuários de teste (sábado)
- [ ] `cheatsheets/permissoes.md` escrito à mão
- [ ] Simulado #2 e apuração por objetivo (domingo)
- [ ] Checkpoint A preenchido
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-06.md` preenchido, `cheatsheets/permissoes.md`, os três scripts do Laboratório 2 em `scripts/`, voucher comprado com a prova agendada, resultado do simulado #2 e o Checkpoint A preenchido.

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