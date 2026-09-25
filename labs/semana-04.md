# Semana 4 — Redirecionamento, filtros, busca e compactação

Período: 21 a 27/09/2026 (segunda a domingo)
Objetivos da prova: 3.1 (Archiving Files on the Command Line) e 3.2 (Searching and Extracting Data from Files)
Tópico 3, peso 9 de 40 — empatado com o Tópico 2 como o maior da prova
Esta semana cobre 5 dos 9 pontos; os 4 restantes ficam na Semana 5, com shell script
Carga prevista: 5 sessões de aproximadamente 1 hora

Observação sobre a natureza desta semana: até aqui os comandos foram usados isoladamente. A partir de agora eles se **combinam**. O valor não está em decorar o `sort` ou o `cut`, mas em enxergar que a saída de um vira a entrada do outro. É a ideia central do Unix, e é o que a prova cobra no objetivo 3.2.

---

## Objetivos oficiais cobertos

**3.1 Archiving Files on the Command Line** — conhecimentos exigidos:

- Arquivos e diretórios
- Arquivamento e compressão
- Termos e utilitários: `tar` com as opções `-c`, `-x`, `-v`, `-f`, `-z`, `-j`; `gzip`, `bzip2`, `zip`, `unzip`

**3.2 Searching and Extracting Data from Files** — conhecimentos exigidos:

- Pipes na linha de comando
- Redirecionamento de entrada e saída
- Expressões regulares básicas: `.`, `[ ]`, `*`, `?`
- Termos e utilitários: `grep`, `less`, `cat`, `head`, `tail`, `sort`, `cut`, `wc`

---

## Rotina de abertura e fechamento

```powershell
lab-up
ssh lab
```

```bash
cd ~/linux-essentials-labs
code .
```

Ao fim de cada sessão:

```bash
git add . && git commit -m "docs: semana 4 - sessao N" && git push
sudo poweroff
```

---

## Pendências herdadas da Semana 3

- [ ] Registrar as observações sobre **arquivos ocultos** (Sessão 3 da Semana 3)
- [ ] **Simulado diagnóstico completo** — 40 questões, cronometrado, sem consulta. Ver seção ao final
- [ ] Remover o arquivo acidental da home: `rm 'sudo apt upgrade -y'`

---

## Preparação do ambiente

Rode uma vez, no início da Sessão 1. Os arquivos servem à semana inteira.

```bash
cd ~ && mkdir -p lab4 && cd lab4

# Base de dados fictícia para os exercícios
cat > funcionarios.csv << 'EOF'
nome,setor,cargo,salario
Ana,TI,desenvolvedora,8500
Bruno,RH,analista,5200
Carla,TI,arquiteta,12000
Daniel,Vendas,gerente,9800
Eduarda,TI,desenvolvedora,8500
Felipe,RH,coordenador,7300
Gabriela,Vendas,vendedora,4500
Hugo,TI,devops,11000
Isabela,Financeiro,analista,6100
Joao,Vendas,vendedor,4500
EOF

# Arquivo de log fictício
cat > sistema.log << 'EOF'
2026-09-21 08:13:02 INFO servico iniciado
2026-09-21 08:14:47 WARN memoria acima de 70%
2026-09-21 09:02:11 ERROR falha ao conectar no banco
2026-09-21 09:02:15 INFO tentativa de reconexao
2026-09-21 09:02:19 ERROR falha ao conectar no banco
2026-09-21 10:30:00 INFO backup concluido
2026-09-21 11:45:33 ERROR timeout na requisicao
2026-09-21 12:00:00 INFO servico reiniciado
EOF

ls -l
```

---

## Sessão 1 — Segunda 21/09 — Visualização e redirecionamento — CONCLUÍDA

### Laboratório

**Ver o conteúdo de um arquivo**

```bash
cat funcionarios.csv
cat -n funcionarios.csv         # com numeração de linhas
less sistema.log                # q para sair
head funcionarios.csv           # 10 primeiras linhas, por padrão
head -3 funcionarios.csv
tail -3 funcionarios.csv
tail -n +2 funcionarios.csv     # da linha 2 em diante, descartando o cabeçalho
sudo tail -f /var/log/syslog    # acompanha em tempo real; Ctrl+C para sair
```

**Redirecionamento**

```bash
ls -l > listagem.txt            # cria ou SOBRESCREVE
ls -l >> listagem.txt           # ACRESCENTA ao final

ls /etc /naoexiste > saida.txt          # só o stdout
ls /etc /naoexiste 2> erros.txt         # só o stderr
ls /etc /naoexiste > saida.txt 2> erros.txt    # cada um no seu arquivo
ls /etc /naoexiste > tudo.txt 2>&1             # os dois no mesmo arquivo
ls /etc /naoexiste &> tudo2.txt                # forma abreviada

ls /naoexiste 2> /dev/null              # descarta o erro
ls /etc > /dev/null                     # descarta a saída
ls /etc &> /dev/null                    # descarta tudo

wc -l < funcionarios.csv                # redirecionamento de entrada

cat > exemplo.txt << 'EOF'              # heredoc
linha um
linha dois
EOF

ls -l | tee arquivo-visto.txt           # grava e exibe
ls -l | tee -a arquivo-visto.txt        # acrescenta
```

### Registro da sessão

**Visualização**

| Comando | Função |
|---|---|
| `cat` | *Concatenate* — exibe o conteúdo e, na origem, serve para juntar arquivos |
| `cat -n` | Exibe com numeração de linhas |
| `less` | Visualizador interativo, adequado para arquivos com milhares de linhas |
| `head` / `head -3` | As 10 primeiras linhas, ou as 3 primeiras |
| `tail` / `tail -3` | As 10 últimas linhas, ou as 3 últimas |
| `tail -n +2` | Da linha 2 em diante — o `+` significa "a partir de" |
| `tail -f` | *Follow* — exibe cada linha nova assim que chega |

**Os três fluxos**

| Fluxo | Número | Função |
|---|---|---|
| `stdin` | 0 | Entrada de dados |
| `stdout` | 1 | Saída do resultado |
| `stderr` | 2 | Saída de erro |

Observação registrada corretamente: o `>` é abreviação de **`1>`**. Quando nenhum número é escrito, o shell assume o fluxo 1. É por isso que `2>` redireciona apenas o erro.

```
                ┌─ stdout (1) ──> saida.txt
ls ─────────────┤
                └─ stderr (2) ──> erros.txt
```

**Heredoc** — de *here document*. O `EOF` é convenção, não obrigação; as aspas simples em `'EOF'` impedem a expansão de variáveis.

**`tee`** — exibe no terminal e grava ao mesmo tempo. Sobrescreve por padrão; `-a` acrescenta.

### Correções desta sessão

**Correção 29 — o que o `2>&1` realmente faz.**

O `2>&1` **não menciona arquivo nenhum**. Ele diz: *"faça o fluxo 2 ir para onde o fluxo 1 está indo **neste momento**"*. Quem define o arquivo é o `> tudo.txt` anterior. E o shell processa os redirecionamentos da esquerda para a direita:

```bash
ls /etc /naoexiste > tudo.txt 2>&1
# 1. "> tudo.txt"  → o fluxo 1 passa a apontar para tudo.txt
# 2. "2>&1"        → o fluxo 2 aponta para onde o 1 está: tudo.txt

ls /etc /naoexiste 2>&1 > tudo.txt
# 1. "2>&1"        → o fluxo 2 aponta para onde o 1 está AGORA: o terminal
# 2. "> tudo.txt"  → o fluxo 1 muda; o 2 continua no terminal
```

O `&` antes do `1` importa: sem ele, `2>1` criaria um **arquivo chamado `1`**.

**Correção 30 — quem abre o arquivo no `<` é o shell, não o comando.**

| Forma | Quem abre o arquivo | O `wc` conhece o nome |
|---|---|---|
| `wc -l arquivo` | O `wc` | Sim — e por isso o imprime |
| `wc -l < arquivo` | O shell | Não — recebe só os dados |

É a mesma lógica da expansão do asterisco na Semana 2: o shell trabalha **antes** de o comando começar.

### O que aprendi

- **Os três fluxos padrão:** `stdin` (0), `stdout` (1) e `stderr` (2).
- **`>` e `>>`:** o `>` sobrescreve; o `>>` acrescenta.
- **`2>&1`:** faz o fluxo de erro seguir o destino que o fluxo de saída tem naquele ponto. Por isso a ordem importa.
- **`tee`:** exibe e grava simultaneamente.
- **`wc -l arquivo` e `wc -l < arquivo`:** no primeiro o `wc` abre o arquivo e conhece o nome; no segundo o shell abre e entrega só os dados.

---

## Sessão 2 — Terça 22/09 — Pipes e filtros — CONCLUÍDA

### Laboratório

```bash
cat funcionarios.csv | wc -l
ls /etc | head -5
history | grep ls

wc funcionarios.csv             # linhas, palavras, bytes
wc -l / -w / -c / -m

sort funcionarios.csv
sort -r funcionarios.csv
sort -t',' -k4 -n funcionarios.csv
sort -t',' -k4 -n -r funcionarios.csv

cut -d',' -f2 funcionarios.csv | sort | uniq
cut -d',' -f2 funcionarios.csv | sort | uniq -c | sort -rn

cut -d',' -f1,3 funcionarios.csv
cut -d',' -f2-4 funcionarios.csv
cut -c1-5 funcionarios.csv
cut -d':' -f1,7 /etc/passwd

echo $PATH | tr ':' '\n'
cat funcionarios.csv | tr 'a-z' 'A-Z'
cat funcionarios.csv | tr -d ','
```

### Registro da sessão — 22 e 23/09

**O pipe.** `cat funcionarios.csv | wc -l` devolveu **11** — as dez linhas de dados mais o cabeçalho.

**`wc`**

```
wc funcionarios.csv    →    11  11  296  funcionarios.csv
```

As 11 palavras coincidem com as 11 linhas porque nenhuma linha do CSV tem espaço.

| Opção | Conta | Origem |
|---|---|---|
| `-l` | Linhas | *lines* |
| `-w` | Palavras | *words* |
| `-c` | Bytes | *chars*, no sentido antigo de byte |
| `-m` | Caracteres | *multibyte* |

Registro preciso na anotação: **`á` conta como um caractere mas ocupa dois bytes**.

**`sort`**

| Opção | Função |
|---|---|
| `-r` | Inverte a ordem |
| `-n` | Ordena por valor numérico |
| `-t','` | Define o separador de campos |
| `-k4` | Ordena pela quarta coluna |

**`cut`**

| Forma | Função |
|---|---|
| `-d','` | Define o delimitador |
| `-f1` | Extrai o campo 1 |
| `-f1,3` | Campos 1 **e** 3 |
| `-f2-4` | Do campo 2 **ao** 4 |
| `-c1-5` | Por posição de caractere |

Distinção registrada corretamente: **`-f` trabalha com campos separados por delimitador; `-c` trabalha com posições fixas na linha.**

**`tr`**

De *translate*. Lê exclusivamente do `stdin` — não abre arquivos.

**Detalhe que a prova explora: o `tr` opera caractere a caractere, não por palavra.**

```bash
echo "cab" | tr 'abc' 'xyz'      # zxy — mapeia a→x, b→y, c→z
```

Ele constrói uma tabela posição a posição. Para substituir palavras inteiras a ferramenta é o `sed`, fora do escopo do Essentials.

**Encadeamento**

```bash
cut -d':' -f7 /etc/passwd | sort | uniq -c | sort -rn
```

```
     29 /usr/sbin/nologin
      2 /bin/bash
      1 /bin/sync
      1 /bin/false
```

Total de 33, batendo com a contagem de usuários. As 29 contas com `/usr/sbin/nologin` são **contas de serviço** — Tópico 5, Semana 6.

### Correções desta sessão

**Correção 32 — o `sort` sem `-n` é crescente, não decrescente.**

As duas formas ordenam em ordem crescente. O que muda é o critério:

| Valor | Primeiro caractere | Posição |
|---|---|---|
| `100` | `1` | primeiro |
| `25` | `2` | segundo |
| `3` | `3` | terceiro |
| `9` | `9` | último |

Quem inverte é o `-r`, e só ele. `sort -r` inverte a ordem de texto; `sort -nr` inverte a numérica.

**Correção 33 e 34 — o `-k` escolhe a coluna, não "separa" e não é "setor".**

| Opção | Papel |
|---|---|
| `-t','` | **Separa** as colunas |
| `-k2` | **Escolhe** a coluna 2 para ordenar |

No `funcionarios.csv` a coluna 2 contém o setor — é coincidência do arquivo, não significado da opção. O `k` vem de *key*.

**Correção 35 — o pipeline próprio traz o cabeçalho e responde outra pergunta.**

```bash
# Por valor do salário, do maior para o menor (corrigido)
tail -n +2 funcionarios.csv | cut -d',' -f4 | sort -rn | uniq -c

# Por frequência, do mais repetido para o menos
tail -n +2 funcionarios.csv | cut -d',' -f4 | sort | uniq -c | sort -rn
```

A ordem dos `sort` muda a pergunta que o pipeline responde.

**Observação — a direção do pipe.**

```
cat funcionarios.csv          wc -l
        stdout      ──|──>     stdin
```

O `stderr` **não passa pelo pipe**:

```bash
ls /etc /naoexiste | wc -l      # o erro aparece na tela, fora da contagem
ls /etc /naoexiste 2>&1 | wc -l # agora o erro entra na contagem
```

### Bandit nível 8 para 9 — concluído em 23/09

```bash
sort data.txt | uniq -u
```

**Correção 36 — o `uniq -u` não "remove as duplicatas".**

| Comando | Com entrada `a a b c c c` | Resultado |
|---|---|---|
| `uniq` | | `a b c` — colapsa; cada valor aparece uma vez |
| `uniq -u` | | `b` — mostra **só** o que nunca se repetiu |
| `uniq -d` | | `a c` — mostra **só** o que se repete |

O `uniq` comum **mantém** os repetidos, reduzidos a uma ocorrência. O `-u` os **elimina por inteiro**.

### O que aprendi

- **Por que o `uniq` vem depois do `sort`:** ele só elimina duplicatas adjacentes.
- **`sort` e `sort -n`:** ambos crescentes; texto caractere a caractere versus valor numérico.
- **`-t` e `-k`:** separador de campos e coluna de ordenação.
- **Por que o `tr` não aceita nome de arquivo:** lê exclusivamente do `stdin`.
- **Meu pipeline:** `tail -n +2 funcionarios.csv | cut -d',' -f4 | sort -rn | uniq -c`

---

## Registro do curso — 23/09 — Objetivos 1.4 e 2.1

Quatro aulas assistidas. Posição: **aula 26 de 72**, no Tópico 2.1.

### Objetivo 1.4 — ICT Skills and Working in Linux

**Privacidade na navegação.**

> **Nuance que a prova explora:** o modo privado impede que o **seu computador** guarde histórico, cookies e dados de formulário. Ele **não torna você anônimo na internet.** Provedor, empregador e o próprio site continuam vendo o tráfego.

**TTY — terminais virtuais**

De *teletypewriter*. Consoles virtuais: sessões independentes, cada uma com seu login, sem interface gráfica. Alterna-se com `Ctrl+Alt+F1` a `Ctrl+Alt+F6`.

Uso prático: quando a interface gráfica congela, um TTY dá acesso ao sistema, que continua funcionando por baixo.

**Detalhe que você usa todo dia:** uma conexão SSH **não** é um TTY. É um **pseudo-terminal**, ou *pty*:

```bash
tty                  # numa sessão SSH: /dev/pts/0
who
```

Terminais virtuais reais aparecem como `/dev/tty1`; sessões remotas como `/dev/pts/N`.

**LAMP** — **L**inux + **A**pache + **M**ySQL/MariaDB + **P**HP, Perl ou Python. Com nginx vira **LEMP**, do inglês *engine-x*.

### Objetivo 2.1 — O shell

O shell é o interpretador de comandos. O padrão é o **Bash** — *Bourne Again Shell*.

| Shell | Característica |
|---|---|
| `bash` | Padrão na maioria das distribuições |
| `sh` / `dash` | Mínimo e rápido; scripts de sistema |
| `zsh` | Mais recursos interativos; padrão no macOS |
| `ksh` | Korn Shell |
| `csh` / `tcsh` | Sintaxe inspirada em C |
| `fish` | Foco em usabilidade |

```bash
sudo usermod -s /usr/bin/zsh davi      # como administrador
chsh -s /usr/bin/zsh                   # o próprio usuário
cat /etc/shells                        # shells autorizados
```

### Correções do curso

**Correção 37 — a troca de shell vale no próximo login, não após reiniciar.**

O `usermod -s` altera `/etc/passwd`, e esse campo é lido **no login**. Basta sair e entrar:

```bash
exit
ssh lab
```

**Correção 38 — o `$SHELL` mostra o shell configurado, não o que está rodando.**

```bash
echo $SHELL       # /bin/bash — o shell de login
sh                # abre um shell diferente
echo $SHELL       # continua /bin/bash
echo $0           # sh — este sim é o que está rodando
ps -p $$
exit
```

O `$0` guarda o nome do processo e o `$$` o PID. Conecta com a Semana 2: `$SHELL` é variável de ambiente herdada do login; `$0` é do processo.

---

## Sessão 3 — `grep` e expressões regulares — CONCLUÍDA em 24/09

### Laboratório

```bash
grep ERROR sistema.log
grep -i error sistema.log
grep -c ERROR sistema.log
grep -n ERROR sistema.log
grep -v ERROR sistema.log
grep -w TI funcionarios.csv
grep -r bash /etc 2>/dev/null
grep -l bash /etc/* 2>/dev/null

grep -v '^#' /etc/ssh/sshd_config | grep -v '^$'

printf "a\naa\naaa\nb\nabc\n" > regex.txt
grep 'a*' regex.txt
grep 'aa*' regex.txt
grep '^a' regex.txt
grep 'a$' regex.txt

grep '^2026' sistema.log
grep 'banco$' sistema.log
grep 'c.rla' funcionarios.csv
grep '^[AB]' funcionarios.csv
grep '[0-9][0-9][0-9][0-9]' funcionarios.csv
grep '[^0-9]' regex.txt

grep -E 'ERROR|WARN' sistema.log
grep -E 'a{2,3}' regex.txt
grep -E 'colou?r' regex.txt
```

### Registro da sessão

| Opção | Origem | Função |
|---|---|---|
| `-i` | *ignore case* | Ignora maiúsculas e minúsculas |
| `-c` | *count* | Conta **linhas** que casaram |
| `-n` | *number* | Mostra o número da linha |
| `-v` | *invert* | Mostra as linhas que **não** casam |
| `-w` | *word* | Casa apenas palavras inteiras |
| `-r` | *recursive* | Percorre diretórios |
| `-l` | *files with matches* | Só os **nomes** dos arquivos que casam |
| `-L` | *files without match* | Só os arquivos que **não** casam |

Observação precisa registrada: **o `-c` conta linhas, não ocorrências.**

```bash
printf "ERROR ERROR ERROR\nINFO\n" | grep -c ERROR             # 1
printf "ERROR ERROR ERROR\nINFO\n" | grep -o ERROR | wc -l      # 3
```

O `-o`, de *only matching*, imprime cada ocorrência em linha separada.

**Regex versus globbing**

| Símbolo | No globbing | Na regex |
|---|---|---|
| `*` | Qualquer sequência de caracteres | Zero ou mais repetições **do elemento anterior** |
| `?` | Exatamente um caractere | Zero ou uma ocorrência do anterior (exige `-E`) |
| `.` | Ponto literal | Qualquer caractere, um só |
| `[abc]` | Um caractere entre os listados | Mesmo significado |

Raciocínio correto registrado sobre o `a*`: casa até a linha `b`, porque "zero ocorrências" satisfaz o padrão. Para exigir pelo menos um, `aa*`.

**Âncoras e conjuntos**

| Padrão | Significado |
|---|---|
| `^a` | Começa com `a` |
| `a$` | Termina com `a` |
| `^$` | Linha vazia |
| `c.rla` | `c`, qualquer caractere, `rla` — casa `Carla` |
| `^[AB]` | Começa com `A` ou `B` |
| `[^0-9]` | Qualquer caractere que **não** seja dígito |

**Regex estendida** — `-E` é necessário para `|`, `?`, `+`, `{}` e agrupamento. O `egrep` é a forma antiga, formalmente obsoleta.

### Correções desta sessão

**Correção 39 — o `grep ERROR` não falhou por causa de maiúsculas.**

O item 2 diz que não retornou saída, mas os itens 4 e 5 registram `grep -c ERROR` retornando 3 e `grep -n ERROR` mostrando a linha. O `sistema.log` contém `ERROR` **em maiúsculas**. Quem falharia é o inverso:

```bash
grep error sistema.log      # nada — o arquivo tem ERROR
grep ERROR sistema.log      # 3 linhas
grep -i error sistema.log   # 3 linhas
```

Causa provável: comando rodado fora do diretório `lab4`, o que produz `No such file or directory`, não saída vazia.

**Correção 40 — `-f1,4` são as colunas 1 e 4, não "de 1 a 4".**

| Forma | Significado |
|---|---|
| `-f1,4` | Colunas 1 **e** 4 |
| `-f1-4` | Colunas 1 **até** 4 |

A vírgula lista; o hífen define intervalo.

**Observação —** a anotação registra `c.arla`; o comando era `c.rla`.

### O que aprendi

- **Os dois significados do `^`:** dentro dos colchetes nega o conjunto; fora, ancora o início da linha.
- **O `-v`:** inverte o filtro.
- **Quando usar `-E`:** para `|`, `?`, `+`, `{}` e agrupamento.
- **Configuração limpa:** `grep -v '^#' arquivo | grep -v '^$'`
- **`-c` conta linhas, não ocorrências:** para ocorrências, `grep -o padrão | wc -l`.

---

## Sessão 4 — Compactação e arquivamento (objetivo 3.1) — CONCLUÍDA em 25/09

### Laboratório

**Arquivar não é comprimir.**

| Operação | O que faz | Ferramenta |
|---|---|---|
| **Arquivar** | Junta muitos arquivos em um só, preservando estrutura e permissões | `tar` |
| **Comprimir** | Reduz o tamanho de **um** arquivo | `gzip`, `bzip2`, `xz` |
| **Ambos** | Arquiva e comprime em um passo | `zip` |

```bash
cd ~/lab4
mkdir -p projeto/{src,docs,testes}
echo "codigo" > projeto/src/main.py
echo "documentacao" > projeto/docs/leiame.md
echo "testes" > projeto/testes/test_main.py
seq 1 5000 > projeto/docs/exemplo.log
du -sh projeto

tar -cvf projeto.tar projeto/
tar -czvf projeto.tar.gz projeto/
tar -cjvf projeto.tar.bz2 projeto/
tar -cJvf projeto.tar.xz projeto/
ls -lh projeto.tar*

tar -tvf projeto.tar.gz
mkdir destino && tar -xzvf projeto.tar.gz -C destino/

cp projeto/docs/exemplo.log teste.log
gzip teste.log
gunzip teste.log.gz
gzip -k teste.log
zcat teste.log.gz | head
zgrep 100 teste.log.gz

zip -r projeto.zip projeto/
unzip -l projeto.zip
unzip projeto.zip -d saida-zip/
```

### Registro da sessão

**Estrutura criada**

```
projeto/
├── src/
│   └── main.py
├── docs/
│   ├── leiame.md
│   └── exemplo.log
└── testes/
    └── test_main.py
```

O `du -sh projeto` mostra o espaço ocupado: `du` de *disk usage*, `-s` de *summarize* (só o total) e `-h` de *human readable*.

**Opções do `tar`**

| Opção | Origem | Função |
|---|---|---|
| `-c` | *create* | Cria o arquivo |
| `-x` | *extract* | Extrai |
| `-t` | *list* | Lista sem extrair |
| `-v` | *verbose* | Mostra os arquivos processados |
| `-f` | *file* | Indica o nome do arquivo — vem por último |
| `-z` | gzip | `.tar.gz` |
| `-j` | bzip2 | `.tar.bz2` |
| `-J` | xz | `.tar.xz` |
| `-C` | *change directory* | Muda de diretório antes de extrair |

Justificativa correta registrada para a posição do `-f`: **ele exige um argumento**, que vem imediatamente depois. Se não for a última letra do grupo, o nome do arquivo acaba consumido por outra opção.

**Resultados medidos**

```
projeto.tar       60K
projeto.tar.gz    17K
projeto.tar.bz2    0     <- comando falhou, ver correção 41
projeto.tar.xz    15K
```

**Comprimir arquivos isolados.** O `gzip` e o `bzip2` **substituem** o original por padrão; o `-k`, de *keep*, preserva. O `gunzip` reverte.

**Ler comprimido sem descomprimir.** `zcat`, `zless` e `zgrep` são as versões do `cat`, `less` e `grep` para arquivos `.gz`.

**O formato `zip`**

| Comando | Função |
|---|---|
| `zip -r arquivo.zip pasta/` | Arquiva e comprime; `-r` por haver subdiretórios |
| `unzip -l arquivo.zip` | Lista o conteúdo |
| `unzip arquivo.zip -d destino/` | Extrai para um diretório específico |

### Correções desta sessão

**Correção 41 — o `.tar.bz2` com 0 bytes indica que o comando falhou.**

```
-rw-rw-r-- 1 davi davi   0 Sep 25 13:59 projeto.tar.bz2
```

Um arquivo comprimido de **zero bytes é impossível** — mesmo comprimindo um diretório vazio, o formato tem cabeçalho. O que aconteceu: o `tar` criou o arquivo de saída, tentou acionar o `bzip2`, não encontrou o programa, e abortou deixando o arquivo vazio.

Causa mais provável: o `bzip2` não está instalado. A instalação mínima do Ubuntu Server não o inclui, ao contrário do `gzip` e do `xz`.

```bash
which bzip2                                   # sem saída = não instalado
sudo apt install -y bzip2
rm projeto.tar.bz2
tar -cjvf projeto.tar.bz2 projeto/
echo $?                                       # deve ser 0
ls -lh projeto.tar*
```

**O aprendizado maior está em como isso passou despercebido.** O `tar -cjvf` é *verbose*: ele lista os arquivos na tela **antes** de tentar comprimir. A saída parecia normal, e a falha só apareceu no tamanho do resultado.

É o cenário do código de saída, visto na Sessão 1:

```bash
tar -cjvf teste.tar.bz2 projeto/
echo $?        # diferente de zero denuncia a falha na hora
```

Regra para o caderno: **saída na tela não é prova de sucesso.** Quando um comando produz arquivo, confira o `$?` ou o tamanho do resultado.

**Correção 42 — a ordem de compressão está invertida.**

A anotação registra o `bzip2` comprimindo melhor que o `xz`. É o contrário — e os próprios números provam: o `xz` gerou **15K** contra **17K** do `gzip`, e o `bzip2` nem chegou a rodar.

| Formato | Velocidade | Taxa de compressão | Resultado medido |
|---|---|---|---|
| `gzip` | Mais rápido | Menor | 17K |
| `bzip2` | Intermediário | Intermediária | *(não executou)* |
| `xz` | Mais lento | **Maior** | **15K** |

Regra a fixar: **quanto mais lento, mais comprime.** O tempo extra é gasto procurando padrões que os algoritmos rápidos ignoram. Por isso o `gzip` domina em transferência de rede, onde velocidade importa, e o `xz` domina em distribuição de pacotes, comprimidos uma vez e baixados milhões de vezes.

Depois de instalar o `bzip2`, refaça os três e compare os tamanhos reais.

### O que aprendi

- **Arquivar e comprimir:** arquivar agrupa vários arquivos em um só sem reduzir o tamanho; comprimir reduz. O `tar` arquiva, `gzip`/`bzip2`/`xz` comprimem, o `zip` faz as duas coisas.
- **Por que o `-f` vem por último:** ele exige um argumento, o nome do arquivo, que vem logo em seguida.
- **Listar sem extrair:** `tar -tvf arquivo.tar.gz`.
- **O que acontece com o original ao rodar `gzip arquivo`:** ele é **substituído** pelo `arquivo.gz` e deixa de existir. O `-k`, de *keep*, preserva.
- **`tar` e `zip`:** o `tar` foi criado só para arquivar, precisando de flag para acionar um compressor; o `zip` arquiva e comprime em um passo.

---

## Sessão 5 — Sexta 25/09 — `find`, desafio integrador e autoavaliação

### Laboratório — `find`

```bash
cd ~/lab4

find . -name "*.log"
find . -iname "*.LOG"                   # -i ignora maiúsculas

find . -type f                          # só arquivos
find . -type d                          # só diretórios
find . -type l                          # só links simbólicos

find . -size +1k                        # maiores que 1 KB
find . -size -1k                        # menores que 1 KB
find . -size 1033c                      # exatamente 1033 bytes

find . -mtime -1                        # modificados nas últimas 24h
find . -mmin -30                        # modificados nos últimos 30 min

find /etc -name "*.conf" 2>/dev/null | head
find / -name "hostname" 2>/dev/null
```

**Combinando condições**

```bash
find . -type f -name "*.log" -size +1k
find . -type f ! -name "*.log"          # o ! nega
find . -type f -name "*.py" -o -name "*.md"     # -o é OU
```

**Executando ações**

```bash
find . -name "*.log" -exec ls -lh {} \;
find . -name "*.log" -exec wc -l {} \;
```

O `{}` é substituído pelo caminho de cada resultado, e o `\;` encerra o comando. A barra invertida impede que o shell consuma o ponto e vírgula.

**`find` e `locate` lado a lado**

| | `find` | `locate` |
|---|---|---|
| Como busca | Percorre o disco em tempo real | Consulta um banco indexado |
| Velocidade | Lenta | Muito rápida |
| Atualidade | Sempre atual | Só o que existia no último `updatedb` |
| Filtros | Tamanho, data, tipo, permissão, dono | Apenas o nome |

### Bandit nível 6 para 7 — concluído em 21/09

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

**Correção 31 — as linhas de `Permission denied` não eram arquivos encontrados.** O `find` encontrou **um único arquivo**. As centenas de outras linhas eram mensagens de erro sobre diretórios sem permissão de entrada — saíram pelo `stderr`. Com `2>/dev/null` a saída fica limpa.

### Desafio integrador

Resolva sem consultar solução pronta. Cada um é um único pipeline.

1. Liste os cinco shells mais usados em `/etc/passwd`, em ordem de frequência.
2. Conte quantas linhas de `ERROR` existem em `sistema.log`.
3. Mostre apenas os horários das linhas de `ERROR` do `sistema.log`.
4. Liste os setores da empresa sem repetição, em ordem alfabética.
5. Mostre o nome e o salário dos funcionários de TI, do maior salário para o menor.
6. Conte quantos arquivos `.conf` existem em `/etc`, incluindo subdiretórios.
7. Mostre as dez maiores entradas de `/usr/bin` por tamanho, só nome e tamanho.

<details>
<summary>Soluções de referência — só depois de tentar</summary>

```bash
# 1
cut -d':' -f7 /etc/passwd | sort | uniq -c | sort -rn | head -5

# 2
grep -c ERROR sistema.log

# 3
grep ERROR sistema.log | cut -d' ' -f2

# 4
tail -n +2 funcionarios.csv | cut -d',' -f2 | sort -u

# 5
grep ',TI,' funcionarios.csv | sort -t',' -k4 -rn | cut -d',' -f1,4

# 6
find /etc -name "*.conf" 2>/dev/null | wc -l

# 7
ls -lS /usr/bin | head -11 | tail -10 | tr -s ' ' | cut -d' ' -f5,9
```

Há mais de uma resposta certa para quase todos. Se a sua chegou ao mesmo resultado por outro caminho, está correta.

</details>

### Autoavaliação da Semana 4

Responda sem consultar. Confira só ao final.

**Redirecionamento**

1. Quais são os três fluxos padrão e seus números?
2. Qual a diferença entre `>` e `>>`?
3. Como enviar apenas as mensagens de erro de um comando para um arquivo?
4. O que faz `comando > arquivo 2>&1`?
5. Qual comando grava a saída em um arquivo **e** a mostra na tela ao mesmo tempo?

**Filtros e pipes**

6. Por que o `uniq` quase sempre é precedido por `sort`?
7. `sort` e `sort -n` dão resultados diferentes para números. Por quê?
8. Que opções do `sort` definem o separador e a coluna de ordenação?
9. Escreva um pipeline que conte quantos usuários existem em `/etc/passwd`.
10. Por que o `tr` não aceita nome de arquivo como argumento?

**`grep` e expressões regulares**

11. O que `grep -v` faz?
12. O que significa `*` no globbing e o que significa na regex?
13. Quais os dois significados do `^` em uma expressão regular?
14. Qual comando mostra um arquivo de configuração sem comentários nem linhas em branco?
15. Quando é necessário usar `grep -E`?

**Compactação**

16. Qual a diferença entre arquivar e comprimir?
17. O que fazem as opções `-c`, `-x`, `-t`, `-v` e `-f` do `tar`?
18. Por que o `-f` deve ser a última letra do grupo de opções?
19. O que acontece com o arquivo original ao rodar `gzip arquivo.txt`, e qual opção evita isso?
20. Qual comando lista o conteúdo de um `.tar.gz` sem extrair?

<details>
<summary>Gabarito</summary>

1. `stdin` (0), `stdout` (1) e `stderr` (2).
2. O `>` sobrescreve o destino; o `>>` acrescenta ao final.
3. `comando 2> arquivo`.
4. Envia a saída padrão para o arquivo e, em seguida, redireciona o erro para o mesmo destino da saída padrão. Resultado: os dois fluxos no mesmo arquivo.
5. `tee`.
6. Porque o `uniq` só elimina duplicatas **adjacentes**. Sem ordenar antes, repetições separadas passam.
7. Sem `-n`, o `sort` compara caractere por caractere — e `100` vem antes de `25`. Com `-n`, compara valor numérico. Ambos em ordem crescente.
8. `-t` define o separador e `-k` define a coluna.
9. `cut -d':' -f1 /etc/passwd | wc -l`, ou simplesmente `wc -l < /etc/passwd`.
10. Porque ele lê exclusivamente da entrada padrão. Precisa de um pipe ou de `<`.
11. Inverte a busca: mostra as linhas que **não** casam com o padrão.
12. No globbing, qualquer sequência de caracteres. Na regex, zero ou mais repetições **do caractere anterior**.
13. Fora dos colchetes, ancora o início da linha. Dentro dos colchetes, nega o conjunto.
14. `grep -v '^#' arquivo | grep -v '^$'`
15. Para `|`, `?`, `+`, `{}` e agrupamento com parênteses.
16. Arquivar junta vários arquivos em um só, sem reduzir tamanho. Comprimir reduz o tamanho de um arquivo.
17. `-c` cria, `-x` extrai, `-t` lista, `-v` mostra os arquivos processados, `-f` indica o nome do arquivo.
18. Porque o nome do arquivo é o argumento que vem imediatamente após o `-f`.
19. O original é substituído pelo `.gz`. A opção `-k`, de *keep*, preserva o original.
20. `tar -tvf arquivo.tar.gz`, ou `tar -tzvf`.

</details>

Nota: ___ de 20

Meta: 16 de 20.

### Limpeza

```bash
cd ~ && rm -rf lab4
```

---

## Simulado diagnóstico — pendência da Semana 3

Uma hora, sem interrupção. 40 questões, cronometrado, sem consultar nada. Use os simulados do Jason Dion.

**Expectativa:** entre 55% e 70%. Você cobriu cerca de 60% do conteúdo e ainda não estudou o Tópico 5, que vale 7 pontos.

**O que importa não é a nota, é onde os erros se concentram.**

| Tópico | Peso | Acertos | Erros |
|---|---|---|---|
| 1. Comunidade e open source | 7 | | |
| 2. Encontrando seu caminho | 9 | | |
| 3. Poder da linha de comando | 9 | | |
| 4. Sistema operacional | 8 | | |
| 5. Segurança e permissões | 7 | | |

**Como ler o resultado:**

- Erros concentrados em 3, 4 e 5 — conteúdo ainda não estudado. O plano está funcionando, e há espaço para conversar sobre antecipar a prova.
- Erros em 1 e 2, que estão fechados — a base não está tão sólida quanto as autoavaliações sugerem, e o prazo permanece como está.

---

## Checklist da semana

- [x] Preparação do ambiente (`lab4`, `funcionarios.csv`, `sistema.log`)
- [x] Sessão 1 — visualização e redirecionamento (21/09)
- [x] Sessão 2 — pipes e filtros (22 e 23/09)
- [x] Sessão 3 — `grep` e expressões regulares (24/09)
- [x] Sessão 4 — compactação e arquivamento (25/09)
- [ ] Sessão 5 — `find`, desafio integrador e autoavaliação
- [x] Bandit níveis 6, 7 e 8 — todos concluídos (21 e 23/09)
- [x] Curso do Muller — retomado em 23/09, aula 26 de 72
- [ ] Instalar o `bzip2` e refazer a comparação de compressão
- [ ] Desafio integrador — sete pipelines
- [ ] Autoavaliação com 16 acertos ou mais
- [ ] Simulado diagnóstico de 40 questões
- [ ] Pendências da Semana 3: arquivos ocultos e limpeza da home
- [ ] Commits ao fim de cada sessão

---

## Cola rápida

```
Ver            cat  cat -n  less  head -n  tail -n  tail -n +2  tail -f
Fluxos         stdin 0   stdout 1   stderr 2
Redirecionar   >  >>  <  2>  &>  2>&1  /dev/null  tee  tee -a
Heredoc        cat > arq << 'EOF' ... EOF
Contar         wc  wc -l  wc -w  wc -c  wc -m
Ordenar        sort  -r  -n  -u  -t','  -k4
Duplicatas     uniq  uniq -c  uniq -u  uniq -d     (exige entrada ordenada)
Colunas        cut -d',' -f1,3   cut -d',' -f1-3   cut -c1-5
Substituir     tr ':' '\n'   tr 'a-z' 'A-Z'   tr -d ','
Buscar texto   grep  -i  -c  -n  -v  -w  -r  -l  -L  -o  -E
Regex          .  [abc]  [a-z]  [^abc]  *  ^inicio  fim$     (-E para | ? + {})
Arquivar       tar -cvf  -xvf  -tvf  -czvf  -cjvf  -cJvf  -C destino
Comprimir      gzip  gunzip  gzip -k  bzip2  xz  zcat  zless  zgrep
Zip            zip -r  unzip  unzip -l  unzip -d
Buscar arquivo find . -name -iname -type -size -mtime -user ! -o -exec {} \;
```