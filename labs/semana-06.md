# Semana 6 — Tópico 5, usuários e permissões, simulado 01 e scripts do 3.3

Período: 05/10 a 11/10/2026 (segunda a domingo)
Objetivos da prova: 5.1, 5.2, 5.3 e 5.4 — Tópico 5, peso 7 de 40
Conteúdo do caderno: simulado 01 e Correções 62 a 68; Laboratório 2 (scripts do 3.3); aquecimento de conversões de permissão; curso, aulas 31 a 40, e Correções 69 a 74; roteiros das Práticas 1 e 2 e da autoavaliação da Semana 5

> As Práticas 1 e 2 e a autoavaliação da Semana 5 foram executadas na Semana 7. Os roteiros ficam aqui, junto do conteúdo do Tópico 5; o registro das sessões está em `labs/semana-07.md`.

Converter `rwxr-xr--` em `754` precisa virar reflexo. Por isso este caderno traz, além das práticas, um aquecimento diário de conversões, com gabarito no fim.

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

## Aquecimento diário — conversões de permissão

Dez minutos por dia, de memória, **sem consultar**. Responda no papel ou em voz alta, cronometrando. A meta é converter em **menos de 3 segundos por item**. Só depois confira no gabarito, no fim deste arquivo.

A regra de conversão é uma só: `r` vale 4, `w` vale 2, `x` vale 1, e cada dígito soma os valores do seu grupo (dono, grupo, outros).

| Série | Cinco exercícios |
|---|---|
| 1 | (a) `rwxr-xr-x` · (b) `644` · (c) `rwx------` · (d) `664` · (e) `r--r-----` |
| 2 | (a) `750` · (b) `rw-------` · (c) `777` · (d) `rw-r-----` · (e) `711` |
| 3 | Qual a permissão final, em octal, de um arquivo `644` depois de: (a) `chmod u+x` · (b) em um `755`, `chmod g-x,o-x` · (c) em um `640`, `chmod o+r` · (d) em um `600`, `chmod g+rw` · (e) em um `755`, `chmod a-x` |
| 4 | Bits especiais: (a) `4755` em símbolos · (b) `2755` em símbolos · (c) `1777` em símbolos · (d) `drwxrwsr-t` em octal · (e) `4644` em símbolos |
| 5 | (a) `rwxrwxr-x` · (b) `2770` em símbolos · (c) `rw-r--r--` depois de `chmod g+w` · (d) `555` · (e) `r--------` |
| 6 | Cronometrado, sem pausa: (a) `754` · (b) `rw-rw----` · (c) `4750` em símbolos · (d) `1770` em símbolos · (e) `chmod 2755` em um diretório, e como aparece no `ls -l` |

---

## Simulado #1 — Segunda 05/10

| Item | Valor |
|---|---|
| Arquivo | `labs/simulados-práticos.lpi/simulado-01.md` |
| Formato | 40 questões, 60 minutos, cronometrado, sem terminal, sem caderno, sem internet |
| Apuração | Cerca de 25 minutos, logo em seguida |
| Meta | Não há. É um diagnóstico. Esperado: de 24 a 30 acertos (60% a 75%) |
| Observação | Com o Laboratório 1 completo, o simulado mede o shell script **depois** da prática |

Protocolo aplicado em 05/10: **marcar cada chute**, abrir o gabarito só depois e apurar **por objetivo**. As questões 18, 20, 21, 22 e 24 retestavam correções já registradas, e as quatro marcadas com firmeza foram acertadas.

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

A prova corrigida, questão por questão, está em `labs/simulados-práticos.lpi/simulado-01.md`.

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
4. **Tempo: 20 min 31 s de 60**, cerca de 31 segundos por questão. O exame dá 90 segundos por questão. Parte dos erros com convicção (Q10, Q15 e Q16) cobre conteúdo que você já praticou, e isso sugere pressa e não lacuna.

**Para o simulado #2:** use **pelo menos 45 minutos** e reserve os últimos 15 para uma segunda passada nas questões marcadas e naquelas em que o enunciado traz uma pegadinha de comando.

**Questão 40 (`umask`).** Foi escrita para este simulado, mas o `umask` **não consta na lista oficial** do objetivo 5.3. No exame real ela pode não aparecer. Trate como baixa prioridade; a Q37 (conversão `rw-r--r--` para 644) é a que importa.

## Laboratório 2 — Terça 06/10 — Os scripts

As especificações dos três scripts e as soluções de referência estão no arquivo da Semana 5 (`labs/semana-05.md`, seção "Laboratório 2"). Este arquivo não as repete.

**Pré-requisito:** Laboratório 1, blocos 3 a 5 (`if`, `for`, código de saída), **concluídos em 04/10**.

| Script | Situação |
|---|---|
| `backup.sh` | Obrigatório |
| `contar.sh` | Obrigatório |
| `usuario.sh` | Obrigatório |

Regras de sempre: escreva **digitando**, um script por vez, rode `echo $?` depois de cada teste, e **quebre de propósito** pelo menos um (sem argumento, diretório inexistente, usuário que não existe).

**Situação: concluído em 06/10.** Os três scripts obrigatórios foram escritos, testados e registrados. O registro corrigido está em "Registro das sessões", mais abaixo.

---

## Prática 1 — Usuários e grupos

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

**Não apague os usuários agora.** A Prática 2 usa `alice`, `bob` e o grupo `dev`. A limpeza é no fim da Prática 2.

### Questões oficiais da LPI (20 min, ao fim da sessão)

Responda no **LPI Learning Material** (PDF do Projeto) os **Exercícios Guiados** e os **Exploratórios** das lições 5.1 e 5.2, **sem consultar o texto**. As páginas estão no sumário do PDF. Só depois abra "Respostas aos Exercícios". Anote apenas as questões erradas.

### Para o caderno

- O que muda entre `-g` e `-G`.
- O que o `/etc/skel` faz na criação de um usuário.
- A diferença entre `su` e `sudo`.

---

## Prática 2 — Permissões

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
sudo userdel teste_sem_nome          # o do experimento sem -m; não tem home, então sem o -r
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

## Autoavaliação da Semana 5

Dez questões sobre shell script (objetivo 3.3), respondidas **sem consultar**, alguns dias depois do Laboratório 2. **Faça-a no início da sessão, antes de estudar qualquer coisa nova.** Mede a retenção, como na regra da Semana 4. As questões foram escritas em 09/10 a partir do caderno da Semana 5 e da cola rápida de shell script. **Responda primeiro, confira só ao final.** Escreva as respostas à mão, como na prova, e use a segunda coluna do gabarito só depois.

1. O que é o *shebang*, como se escreve e em que posição do arquivo ele precisa estar?
2. Um script chamado `s.sh` pode ser executado de duas formas: `./s.sh` e `bash s.sh`. Qual delas exige a permissão de execução (`x`) e por quê?
3. Qual destas atribuições está correta, e o que há de errado nas outras? (a) `nome = Davi` (b) `nome=Davi` (c) `$nome=Davi`
4. O script é chamado com `./s.sh Davi Morais`. Quanto valem `$0`, `$1`, `$2` e `$#`?
5. Com `nome=Davi`, o que imprimem `echo "Ola, $nome"` e `echo 'Ola, $nome'`?
6. Escreva um `if` que imprima `erro` quando o número de argumentos for diferente de 2.
7. No teste `[ ... ]`, qual a diferença entre `-eq` e `=`? Escreva um exemplo de cada.
8. O que o `$?` guarda? O que significam `exit 0` e `exit 1`, e o que fazem `&&` e `||` entre dois comandos?
9. Escreva um `for` que imprima os números de 1 a 5, de duas formas.
10. No `vi`, qual sequência entra no modo de inserção, grava e sai? Como sair **sem** gravar? E no `nano`, como gravar e sair?

| Campo | Valor |
|---|---|
| Acertos | de 10 |
| Meta | 8 ou mais |
| Erros viram | lista das questões erradas aqui; a correção fica no Notion |

<details>
<summary>Gabarito (abra só depois de responder)</summary>

1. É a primeira linha do script, no formato `#!/bin/bash`: os **dois primeiros caracteres** são `#!`, sem espaço, comentário ou linha vazia antes. Diz qual interpretador executa o arquivo quando ele é chamado com `./`.
2. `./s.sh` exige o `x`, porque o sistema executa o arquivo diretamente. `bash s.sh` só precisa de permissão de **leitura**, porque o `bash` é quem executa e o arquivo é só dado de entrada.
3. A (b) `nome=Davi`. Em (a), os espaços ao redor do `=` fazem o shell tratar `nome` como um comando. Em (c), o `$` só se usa para **ler** a variável, não para atribuir.
4. `$0` vale `./s.sh`, `$1` vale `Davi`, `$2` vale `Morais` e `$#` vale `2`.
5. A primeira imprime `Ola, Davi` (aspas duplas expandem a variável). A segunda imprime `Ola, $nome` (aspas simples são literais).
6. `if [ $# -ne 2 ]; then echo "erro"; fi` (em várias linhas é equivalente). Os espaços dentro dos colchetes são obrigatórios.
7. `-eq` compara **números** (`[ $a -eq 5 ]`); `=` compara **texto** (`[ "$a" = "Davi" ]`). Para números também existem `-ne`, `-lt`, `-le`, `-gt` e `-ge`.
8. `$?` guarda o **código de saída** do último comando. `exit 0` indica sucesso e `exit 1` (ou outro valor diferente de 0) indica erro. `&&` executa o segundo comando só se o primeiro der 0; `||` executa o segundo só se o primeiro der diferente de 0.
9. `for i in 1 2 3 4 5; do echo $i; done` e `for i in $(seq 1 5); do echo $i; done`.
10. No `vi`: `i` (inserir), `Esc` (voltar ao modo de comando), `:wq` (gravar e sair). Sair sem gravar: `:q!`. No `nano`: `Ctrl+O` grava e `Ctrl+X` sai.

</details>

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

Mnemônico: **ponto-ponto sobe, traço volta**. Quatro correções escritas não resolveram. Reler não conserta isto; o que conserta é executar.

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
| 28 | Processos em tempo real | `top` (o `free -h` mostra memória) | Semana 8, Prática 4 |
| 29 | Sinal padrão do `kill` | `SIGTERM` (15). O `SIGKILL` (9) só com `kill -9` | Semana 8, Prática 4 |
| 35 | Último campo do `/etc/passwd` | O **shell de login**, 7º campo. O GID é o 4º | Prática 1, bloco 2 |
| 37 | `rw-r--r--` em octal | **644**. O `664` é `rw-rw-r--`, que é o padrão da sua VM | Aquecimento de conversões |
| 40 | Quem retira permissões de arquivo novo | `umask` | Baixa prioridade: fora da lista oficial |

A Q37 merece atenção: você marcou **664**, e `rw-rw-r--` é justamente o que os arquivos novos recebem na sua VM. Pode ter sido o que você já vê no terminal, e não a conversão do enunciado.

#### Observações (sem número)

- **A Q11** foi respondida `PATH`, com um sublinhado na frente. No exame real, em campo de preenchimento, escreva **só a palavra**.
- **Erros com convicção são os mais caros.** Dos 12 erros, 7 foram com convicção e 5 com chute. Os 7 são os mais caros: erro sabido se estuda, erro confiante se defende.

### Laboratório 2 — terça 06/10 — CONCLUÍDO

Os três scripts obrigatórios foram escritos, testados e funcionaram com os códigos de saída pedidos (0, 1 e 2).

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

### Aquecimento de permissões — quarta 07/10

Estudo prévio feito por conta própria, antes de responder (o conteúdo ainda não tinha sido ensinado), seguido de prática no terminal em `lab6/permissoes`.

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

### Curso, aulas 31 a 35 — quinta 08/10

Retomada do curso (Udemy, Matheus Muller). Aulas 31 a 35 assistidas; **checkpoint na aula 36**. Anotações e prática no terminal.

**Conteúdo registrado**

| Tema | O que ficou anotado |
|---|---|
| Histórico do Bash | `history` lista os comandos; `~/.bash_history` guarda; `HISTFILE`, `HISTFILESIZE`, `HISTSIZE` e `HISTCONTROL`; `!NNN` reexecuta a linha NNN |
| Prática do histórico | `history`; `!331` (rodou `uname -a`); `export HISTSIZE=50` |
| Scripts de inicialização | `/etc/bash.bashrc`, `.bashrc`, `/etc/profile` e a ordem de busca `bash_profile`, `bash_login`, `profile` |
| Prática de inicialização | `cat .bash_history`; criar a variável `NOME` em todo terminal novo, pelo `.bashrc` |
| Variáveis | Locais contra globais; `set`, `env`, `export` |
| File globbing | `*`, `?`, `[ ]`; prática com `ls *.txt`, `touch file{1,2,3,4}.txt` e `ls [Tt]este` |
| Aspas | Duplas, simples e contra-barra |

**Ajustes de caderno (sem correção numerada)**

1. Os nomes das variáveis são **em maiúsculas**: `HISTFILE`, `HISTFILESIZE`, `HISTSIZE`, `HISTCONTROL` (o caderno tem `histifile`, `histfilesize` etc.). E em "history_file aramzena" falta o `m` de "armazena".
2. O comando da prática de inicialização está incompleto e com aspas curvas: `echo ‘export NOME=”TESTE” >> .bashrc`. O correto, com aspas **retas** e a aspa simples de fechamento, é `echo 'export NOME="TESTE"' >> ~/.bashrc`. A variável só aparece em um terminal **novo** ou depois de `source ~/.bashrc`; confira com `echo $NOME`.
3. O caminho do arquivo da pasta pessoal é `~/.bashrc`. O `/etc/bash.bashrc` é o nome em Debian e Ubuntu; em Red Hat e derivadas é `/etc/bashrc`.
4. "Dígito" aparece onde o termo é **caractere** (`?` casa um caractere, não um dígito).
5. Falta registrar o `!!`, que repete o último comando, e o `!NNN` com o **nome** `history expansion`.
6. A frase "Pode-se combinar difentes arquivos... arquivo s]" está truncada.

**Pontos fortes:** a prática de `history` com `!331` e a tabela de arquivos de inicialização; o reconhecimento de que o globbing já foi tratado nos laboratórios; e a escolha de `export HISTSIZE=50` na prática.

#### Correção 69 — o `~/.bashrc` é de shell interativo sem login, não de shell "não interativo"

O caderno diz: "`.bashrc` → arquivo local para shell não interativo". A palavra errada é **não**. A distinção que importa é *login* contra *sem login*:

| Tipo de shell | Quando acontece | Arquivos lidos |
|---|---|---|
| Shell de **login** | Entrada por `ssh`, console ou `bash -l` | `/etc/profile`, depois **o primeiro que existir** entre `~/.bash_profile`, `~/.bash_login` e `~/.profile` |
| Shell **interativo sem login** | Abrir um terminal na janela ou digitar `bash` | `/etc/bash.bashrc` (Debian e Ubuntu) e `~/.bashrc` |

O `/etc/profile` vem primeiro nos shells de login, e em muitas distribuições ele mesmo chama o `/etc/bash.bashrc`. Para ver: `shopt -q login_shell && echo login || echo sem-login` em um terminal da janela e depois em `bash -l`.

#### Correção 70 — `?` é um caractere qualquer, e as chaves `{}` não são globbing

O caderno diz que o `?` casa "um dígito somente". O `?` casa **um caractere qualquer** (letra, número, símbolo). Os três curingas:

| Curinga | Casa | Exemplo |
|---|---|---|
| `*` | **Zero ou mais** caracteres | `ls *.txt` |
| `?` | **Exatamente um** caractere | `ls ?.txt` lista `a.txt` e `1.txt`, mas não `ab.txt` |
| `[ ]` | **Um** caractere do conjunto ou da faixa | `ls [Tt]este`, `ls [0-9].txt` |

O `touch file{1,2,3,4}.txt`, que apareceu na prática de globbing, é **expansão de chaves** (*brace expansion*), e não globbing: ela **cria** os nomes antes de o comando rodar, sem olhar o disco. O globbing só enxerga arquivos que **já existem**. Para ver: `echo f{1,2}.txt` imprime `f1.txt f2.txt` mesmo sem nenhum arquivo. É a **segunda ocorrência** do tema da Correção 11.

#### Correção 71 — variáveis exportadas são herdadas por processos filhos, não por "outras sessões"

O caderno diz que as variáveis globais são as que "outras sessões filhas também podem enxergar". O termo certo é **variável de ambiente** (exportada): quem a herda é o **processo filho** iniciado a partir do shell, e nada que esteja ao lado ou acima.

| Comando | O que mostra |
|---|---|
| `set` | **Todas** as variáveis do shell, locais **e** exportadas, mais as funções (não são só as locais) |
| `env` | **Somente** as exportadas, ou seja, o ambiente |
| `export VAR` | Marca a variável para ser herdada pelos filhos |

Teste, no terminal: `X=1 ; export Y=2 ; bash -c 'echo X=[$X] Y=[$Y]'` mostra `X=[] Y=[2]`. Lembre da Correção 12: a direção é do **pai para o filho**. É a **segunda ocorrência** desse tema.

#### Correção 72 — a contra-barra não produz `\n`, e as aspas duplas ainda expandem

O caderno diz que a contra-barra serve para "tratar o próximo dígito como normal e quebrar linha `\n`". A contra-barra **escapa o próximo caractere** (tira o significado especial dele) e, no fim de uma linha, **continua o comando na linha de baixo**. Ela não produz `\n`: `echo "a\nb"` imprime `a\nb`.

| Aspas | Efeito |
|---|---|
| Duplas `" "` | Agrupam palavras e preservam os espaços; ainda expandem `$VAR`, `$(...)` e a contra-barra; **impedem** o globbing |
| Simples `' '` | Tudo é literal, inclusive o `$` |
| `\` | Escapa **um** caractere; no fim da linha, continua o comando |

Para ver: `NOME=Davi ; echo "$NOME" '$NOME' \$NOME` imprime `Davi $NOME $NOME`.

### Curso, aulas 36 a 40 — sexta 09/10

Aulas 36 a 40 assistidas; **checkpoint na aula 41**.

**Conteúdo registrado**

| Tema | O que ficou anotado |
|---|---|
| Prompt e hostname | O prompt mostra o usuário e o nome da máquina; `/etc/hostname`; `sudo hostnamectl set-hostname davi18` |
| Usuário comum e root | `$` é usuário comum; `#` é root; `sudo su` troca para root |
| Encontrar arquivos | `locate` (índice em cache), `sudo updatedb`, `find`, `type`, `whereis` |
| Prática | `find / -iname "*.txt"`; `touch teste.txt`, `sudo updatedb`, `locate teste.txt` |
| Documentação | `man`, seções do manual, `man -k tty`, `apropos`, `man -f`, `whatis`, `man 5` |
| `info` | Páginas do GNU, nem todo comando tem; hiperlinks e navegação |

**Ajustes de caderno (sem correção numerada)**

1. `find / -iname “*.txt”` está com aspas curvas; use aspas **retas**. Rodando em `/`, o `find` imprime muitas linhas de `Permission denied` (Correção 31). Use `find / -iname "*.txt" 2>/dev/null`. As aspas ao redor do `*.txt` existem para que o **shell não expanda** o curinga antes do `find` (Correção 72).
2. "Sessões" do manual é **seções**. As principais: 1 comandos de usuário, 2 chamadas de sistema, 3 bibliotecas, 4 arquivos especiais (`/dev`), 5 formatos de arquivo, 6 jogos, 7 diversos, 8 administração. Para abrir uma seção específica, informe o comando: `man 5 passwd` (formato do arquivo `/etc/passwd`) contra `man passwd` (o comando, seção 1). Só o número, como está no caderno, não basta.
3. `man -k` e `apropos` buscam a palavra no **nome e na descrição** (podem trazer muitos resultados); `man -f` e `whatis` mostram a descrição de **um nome exato**.
4. Sobre o `info`: sem argumento, `info` abre o **diretório** de todos os manuais disponíveis; `info ls` abre o manual do `ls`. A navegação por links usa `Enter` no link, `n` e `p` para o próximo e o anterior e `q` para sair. Nem todo comando tem página `info`; quando não tem, o `info` mostra a página do `man`.
5. O prompt mostra `usuário@hostname`. O hostname novo aparece em **terminais novos**; o `hostnamectl` não precisa de reinício.
6. `sudo su` funciona; as formas mais comuns são `sudo -i` e `su -`, que também carregam o ambiente do root. `exit` volta ao usuário comum.
7. Erros de digitação: "cimando", "omandos".

**Pontos fortes:** a prática de `touch`, `updatedb` e `locate` mostra a diferença entre os dois comandos de busca; o exemplo de `man -k tty` ligado à seção 4 do manual está correto.

#### Correção 73 — o `updatedb` refaz o índice inteiro, não "atualiza o arquivo adicionado"; o `locate` lê o índice e o `find` olha o disco

O caderno diz que `sudo updatedb` "atualiza o arquivo que foi adicionado no cache". O `updatedb` percorre o sistema de arquivos e **reconstrói o banco de dados inteiro** que o `locate` consulta. Por isso a diferença entre os dois comandos:

| Comando | Como procura | Arquivo criado há 1 minuto aparece? |
|---|---|---|
| `locate` | Consulta um **banco de dados** (índice) pronto; é muito rápido | **Não**, até rodar `sudo updatedb` |
| `find` | **Percorre os diretórios na hora**; é mais lento e aceita filtros (nome, tipo, tamanho, data) | **Sim**, imediatamente |

Para ver: `touch teste.txt ; locate teste.txt` (nada, ou só resultados antigos) ; `sudo updatedb ; locate teste.txt` (agora aparece) ; `find . -name teste.txt` (aparece sem o `updatedb`).

#### Correção 74 — o `type` mostra como o shell interpreta um nome, não "o tipo de binário"

O caderno diz que `type` "identifica o tipo de binário que estamos utilizando". O `type` é um comando **interno do shell** que responde "o que o shell faz com este nome?". As respostas possíveis:

| Resposta | Exemplo |
|---|---|
| Alias | `type ls` pode dar `ls is aliased to 'ls --color=auto'` (como na Correção 8) |
| Comando interno do shell (*builtin*) | `type cd` dá `cd is a shell builtin` |
| Palavra reservada | `type if` dá `if is a shell keyword` |
| Programa em arquivo | `type cp` dá `cp is /usr/bin/cp` |

Compare com os outros dois: `which` mostra só o caminho dentro do `PATH`; `whereis` mostra o **binário, o código-fonte e as páginas de manual**. `type -a` lista **todas** as ocorrências (por exemplo, `echo` é interno e também existe em `/usr/bin/echo`). Confirmado no terminal.

### Correções da semana

A numeração segue a série global. O simulado 01 gerou as **Correções 62 a 68**; o curso, as **69 a 74**. O Laboratório 2 não gerou correção numerada: não houve erro conceitual. O índice das Correções 1 a 74 está em `labs/simulados-práticos.lpi/resultados_simulados.md`.

| # | Tema | Origem |
|---|---|---|
| 62 | *Upstream* do RHEL é o Fedora, não o Debian | Q3 |
| 63 | Contêiner compartilha o kernel; VM tem o seu | Q7 |
| 64 | `..` sobe na árvore, `-` volta no histórico (5ª ocorrência) | Q10 |
| 65 | `/usr` não é *user* | Q14 |
| 66 | `/proc` é de processos, `/dev` de dispositivos | Q15 |
| 67 | `man` é o manual; `--manual` não existe no `cp` | Q16 |
| 68 | `chmod` muda permissões, `chown` muda dono | Q38 |
| 69 | `~/.bashrc` é de shell interativo sem login; a diferença é login ou não | Curso, 08/10 |
| 70 | `?` casa um caractere qualquer; as chaves `{}` não são globbing (2ª ocorrência da Correção 11) | Curso, 08/10 |
| 71 | Variáveis exportadas são herdadas por processos filhos; `set` mostra tudo, `env` só as exportadas (2ª ocorrência da Correção 12) | Curso, 08/10 |
| 72 | `\` escapa um caractere e não produz `\n`; aspas duplas ainda expandem | Curso, 08/10 |
| 73 | `updatedb` refaz o índice inteiro; `locate` lê o índice e `find` olha o disco | Curso, 09/10 |
| 74 | `type` mostra como o shell interpreta um nome, não "o tipo de binário" | Curso, 09/10 |

---

## Checklist da semana

- [x] Simulado 01 e apuração por tópico (05/10): 28 de 40, 70%
- [x] Correções 62 a 68 registradas e anotadas no Notion (05/10)
- [x] Laboratório 2, três scripts (06/10)
- [x] Aquecimento de conversões de permissão (07/10)
- [x] Curso, aulas 31 a 40, e Correções 69 a 74 (08 e 09/10)

---

## Entregável

`labs/semana-06.md` com o simulado 01, o Laboratório 2, o aquecimento de conversões, o curso até a aula 40 e os roteiros do Tópico 5.

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

| Série | Respostas |
|---|---|
| 1 | (a) 755 · (b) `rw-r--r--` · (c) 700 · (d) `rw-rw-r--` · (e) 440 |
| 2 | (a) `rwxr-x---` · (b) 600 · (c) `rwxrwxrwx` · (d) 640 · (e) `rwx--x--x` |
| 3 | (a) 744 · (b) 744 · (c) 644 · (d) 660 · (e) 644 |
| 4 | (a) `rwsr-xr-x` · (b) `rwxr-sr-x` · (c) `rwxrwxrwt` · (d) 3775 · (e) `rwSr--r--` |
| 5 | (a) 775 · (b) `rwxrws---` · (c) 664 · (d) `r-xr-xr-x` · (e) 400 |
| 6 | (a) `rwxr-xr--` · (b) 660 · (c) `rwsr-x---` · (d) `rwxrwx--T` · (e) `drwxr-sr-x` |

**Bloco 4 — diretório e operações** (assumindo que o arquivo `arq` tem permissão de leitura)

| Modo | `ls pasta` | `cat pasta/arq` | `touch pasta/novo` | `rm pasta/arq` |
|---|---|---|---|---|
| 700 | funciona | funciona | funciona | funciona |
| 600 | lista os nomes, mas com erro nos detalhes | **negado** (sem `x`) | negado | negado |
| 500 | funciona | funciona | **negado** (sem `w`) | **negado** (sem `w` no diretório) |
| 300 | **negado** (sem `r`) | funciona | funciona | funciona |
| 100 | negado | funciona | negado | negado |

No modo 600, o que o `ls` mostra exatamente varia conforme o alias de cor e a versão; anote o que apareceu na sua VM. Todo o resto da tabela decorre das três regras da cola rápida.