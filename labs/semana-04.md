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

## Sessão 1 — Segunda 21/09 — Visualização e redirecionamento

### Curso

Muller: seções sobre redirecionamento e visualização de arquivos.

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
```

O `tail -n +2` é útil o suficiente para valer a memorização: ele começa **a partir** da linha indicada, em vez de contar do fim.

**Acompanhar um arquivo em tempo real**

```bash
sudo tail -f /var/log/syslog
```

O `-f` de *follow* deixa o comando aberto, imprimindo cada linha nova conforme ela chega. Saia com `Ctrl+C`. É o comando mais usado do mundo em depuração de servidor.

**Os três fluxos padrão**

Todo comando no Linux nasce com três canais:

| Fluxo | Número | Nome | Função |
|---|---|---|---|
| `stdin` | 0 | Entrada padrão | De onde o comando lê |
| `stdout` | 1 | Saída padrão | Onde escreve o resultado |
| `stderr` | 2 | Saída de erro | Onde escreve mensagens de erro |

Por padrão, `stdout` e `stderr` vão ambos para a tela — e é por isso que parecem a mesma coisa. Não são.

**Redirecionamento de saída**

```bash
ls -l > listagem.txt            # cria ou SOBRESCREVE
cat listagem.txt

ls -l >> listagem.txt           # ACRESCENTA ao final
wc -l listagem.txt

echo "nova linha" > listagem.txt
cat listagem.txt                # o conteúdo anterior sumiu
```

A diferença entre `>` e `>>` é a mesma armadilha do `cp` da semana passada: o `>` sobrescreve em silêncio.

**Separando saída de erro**

```bash
ls /etc /naoexiste                      # os dois fluxos se misturam na tela

ls /etc /naoexiste > saida.txt          # só o stdout foi para o arquivo
cat saida.txt                           # o erro ficou na tela

ls /etc /naoexiste 2> erros.txt         # agora só o stderr foi
cat erros.txt

ls /etc /naoexiste > saida.txt 2> erros.txt    # cada um no seu arquivo
ls /etc /naoexiste > tudo.txt 2>&1             # os dois no mesmo arquivo
ls /etc /naoexiste &> tudo2.txt                # forma abreviada do anterior

ls /naoexiste 2> /dev/null              # descarta o erro
ls /etc > /dev/null                     # descarta a saída
ls /etc &> /dev/null                    # descarta tudo
```

A notação `2>&1` se lê como "mande o fluxo 2 para onde o fluxo 1 está indo". A ordem importa: `> arquivo 2>&1` funciona, mas `2>&1 > arquivo` não faz o que parece.

**Redirecionamento de entrada**

```bash
wc -l < funcionarios.csv
sort < funcionarios.csv
```

O `<` alimenta o comando a partir de um arquivo em vez do teclado. Repare na diferença sutil: `wc -l arquivo.txt` mostra o nome do arquivo na saída; `wc -l < arquivo.txt` não, porque o comando nunca soube de qual arquivo veio.

**O heredoc**

Você já usou sem saber o nome, ao criar o README:

```bash
cat > exemplo.txt << 'EOF'
linha um
linha dois
EOF

cat exemplo.txt
```

**O `tee` — gravar e exibir ao mesmo tempo**

```bash
ls -l | tee arquivo-visto.txt
cat arquivo-visto.txt

ls -l | tee -a arquivo-visto.txt    # -a acrescenta em vez de sobrescrever
```

O nome vem do encanamento: um "T" divide o fluxo em dois. É a solução para quando você quer ver o resultado e guardá-lo ao mesmo tempo.

### Registro da sessão

```bash

```

### O que aprendi

- Os três fluxos padrão e seus números:
- Diferença entre `>` e `>>`:
- O que faz `2>&1`:
- Para que serve o `tee`:
- Diferença entre `wc -l arquivo` e `wc -l < arquivo`:

---

## Sessão 2 — Terça 22/09 — Pipes e filtros

### Curso

Muller: seções sobre pipes e processamento de texto.

### Laboratório

**O pipe**

O `|` conecta a saída de um comando à entrada do próximo. Nenhum arquivo intermediário é criado.

```bash
cat funcionarios.csv | wc -l
ls /usr/bin | wc -l
ls /etc | head -5
history | grep ls
```

**Contar — `wc`**

```bash
wc funcionarios.csv             # linhas, palavras, bytes
wc -l funcionarios.csv          # só linhas
wc -w funcionarios.csv          # só palavras
wc -c funcionarios.csv          # bytes
wc -m funcionarios.csv          # caracteres
```

Atenção à diferença entre `-c` e `-m`: em texto com acentos, um caractere pode ocupar mais de um byte.

**Ordenar — `sort`**

```bash
sort funcionarios.csv
sort -r funcionarios.csv                    # ordem inversa
sort -t',' -k4 funcionarios.csv             # pela 4ª coluna, separador vírgula
sort -t',' -k4 -n funcionarios.csv          # numericamente
sort -t',' -k4 -n -r funcionarios.csv       # do maior salário para o menor
sort -t',' -k2 funcionarios.csv             # por setor
```

A diferença entre ordem alfabética e numérica é fonte clássica de erro. Comprove:

```bash
printf "9\n100\n25\n3\n" > numeros.txt
sort numeros.txt         # 100 vem antes de 25 — ordem alfabética
sort -n numeros.txt      # agora sim: 3, 9, 25, 100
```

**Remover duplicatas — `uniq`**

```bash
cut -d',' -f2 funcionarios.csv | sort | uniq
cut -d',' -f2 funcionarios.csv | sort | uniq -c        # com contagem
cut -d',' -f2 funcionarios.csv | sort | uniq -c | sort -rn
```

**O `uniq` só remove duplicatas adjacentes.** Por isso ele quase sempre aparece depois de um `sort`. Verifique:

```bash
printf "a\nb\na\nb\n" | uniq        # não remove nada
printf "a\nb\na\nb\n" | sort | uniq # agora sim
```

**Extrair colunas — `cut`**

```bash
cut -d',' -f1 funcionarios.csv              # só os nomes
cut -d',' -f1,3 funcionarios.csv            # nome e cargo
cut -d',' -f2-4 funcionarios.csv            # da 2ª à 4ª coluna
cut -c1-5 funcionarios.csv                  # por posição de caractere
cut -d':' -f1 /etc/passwd                   # usuários do sistema
cut -d':' -f1,7 /etc/passwd                 # usuário e shell
```

**Substituir caracteres — `tr`**

```bash
echo $PATH | tr ':' '\n'
cat funcionarios.csv | tr ',' '\t'
cat funcionarios.csv | tr 'a-z' 'A-Z'
cat funcionarios.csv | tr -d ','            # remove
```

O `tr` é o único destes que **não aceita nome de arquivo** como argumento — ele só lê de `stdin`. Por isso aparece sempre depois de um pipe ou de um `<`.

**Encadeando de verdade**

```bash
# Quantos usuários existem no sistema
cut -d':' -f1 /etc/passwd | wc -l

# Quais shells estão em uso e quantas vezes
cut -d':' -f7 /etc/passwd | sort | uniq -c | sort -rn

# Os três maiores salários, com nome
tail -n +2 funcionarios.csv | sort -t',' -k4 -rn | head -3 | cut -d',' -f1,4
```

Leia o último da esquerda para a direita: descarta o cabeçalho, ordena pelo salário em ordem numérica decrescente, pega os três primeiros, extrai nome e salário. Cada etapa faz uma coisa só.

### Bandit nível 8 para 9

O desafio pede a única linha que aparece **uma só vez** num arquivo com muitas repetições. Os comandos são os desta sessão.

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
man uniq        # procure a opção -u
```

Lembre: o `uniq` precisa de entrada ordenada.

### Registro da sessão

```bash

```

### O que aprendi

- Por que o `uniq` quase sempre vem depois do `sort`:
- Diferença entre `sort` e `sort -n`:
- O que o `-t` e o `-k` fazem no `sort`:
- Por que o `tr` não aceita nome de arquivo:
- Meu próprio pipeline de três ou mais comandos:

---

## Sessão 3 — Quarta 23/09 — `grep` e expressões regulares

Esta é a sessão mais importante da semana. O `grep` é o comando mais cobrado do objetivo 3.2, e as expressões regulares básicas são conhecimento exigido explicitamente.

### Curso

Muller: seções sobre `grep` e busca em arquivos.

### Laboratório

**Busca simples**

```bash
grep ERROR sistema.log
grep -i error sistema.log           # ignora maiúsculas e minúsculas
grep -c ERROR sistema.log           # conta as ocorrências
grep -n ERROR sistema.log           # mostra o número da linha
grep -v ERROR sistema.log           # INVERTE: tudo que NÃO casa
grep -w TI funcionarios.csv         # palavra inteira
grep -r bash /etc 2>/dev/null       # recursivo em diretórios
grep -l bash /etc/* 2>/dev/null     # só os NOMES dos arquivos que casam
```

O `-v` é o mais esquecido e um dos mais úteis: filtrar por exclusão.

```bash
grep -v '^#' /etc/ssh/sshd_config | grep -v '^$'
```

Esse comando mostra um arquivo de configuração **sem comentários e sem linhas em branco** — o jeito mais rápido de ver o que de fato está configurado num servidor.

**Expressões regulares básicas**

Aqui mora a confusão mais comum de quem acabou de aprender globbing.

| Símbolo | No **globbing** (nomes de arquivo) | Na **regex** (conteúdo de texto) |
|---|---|---|
| `*` | Qualquer sequência de caracteres | **Zero ou mais repetições do caractere anterior** |
| `?` | Exatamente um caractere | Zero ou uma repetição do anterior (exige `grep -E`) |
| `.` | Um ponto literal | **Qualquer caractere, um só** |
| `[abc]` | Um caractere entre os listados | Um caractere entre os listados (igual) |

**O `*` significa coisas diferentes nos dois contextos.** No globbing, `a*` casa `abc`, `arquivo`, `azul`. Na regex, `a*` casa "zero ou mais letras a" — ou seja, casa até com uma string vazia. Comprove:

```bash
printf "a\naa\naaa\nb\nabc\n" > regex.txt

grep 'a*' regex.txt        # casa TUDO, inclusive "b" — zero ocorrências de "a" conta
grep 'aa*' regex.txt       # pelo menos um "a"
grep '^a' regex.txt        # começa com a
grep 'a$' regex.txt        # termina com a
```

**Âncoras e curingas**

```bash
grep '^2026' sistema.log            # linhas que COMEÇAM com 2026
grep 'banco$' sistema.log           # linhas que TERMINAM com banco
grep '^$' sistema.log               # linhas vazias
grep 'c.rla' funcionarios.csv       # o ponto casa qualquer caractere
grep '^[AB]' funcionarios.csv       # começa com A ou B
grep '[0-9][0-9][0-9][0-9]' funcionarios.csv    # quatro dígitos seguidos
grep '[^0-9]' regex.txt             # dentro de [], o ^ NEGA
```

Atenção: o `^` tem dois significados. Fora dos colchetes, ancora o início da linha; **dentro** dos colchetes, nega o conjunto.

**Regex básica e estendida**

```bash
grep -E 'ERROR|WARN' sistema.log       # o | alternativo exige -E
grep -E 'a{2,3}' regex.txt             # entre 2 e 3 repetições
grep -E 'colou?r' regex.txt            # o ? exige -E
egrep 'ERROR|WARN' sistema.log         # forma antiga, equivale a grep -E
```

Na regex **básica** funcionam `.`, `[]`, `*`, `^` e `$`. Para `|`, `?`, `+`, `{}` e parênteses de agrupamento é preciso o `-E`, de *extended* — ou escapá-los com barra invertida, o que fica ilegível.

**Uso combinado**

```bash
grep ERROR sistema.log | wc -l
grep ERROR sistema.log | cut -d' ' -f2
grep -i ti funcionarios.csv | cut -d',' -f1,4 | sort -t',' -k2 -rn
cut -d':' -f7 /etc/passwd | sort -u | grep -v nologin
```

### Bandit nível 7 para 8

O desafio pede a senha que está ao lado de uma palavra específica, dentro de um arquivo com milhares de linhas. É `grep` puro.

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

### Registro da sessão

```bash

```

### O que aprendi

| Símbolo | No globbing | Na regex |
|---|---|---|
| `*` | | |
| `?` | | |
| `.` | | |
| `[abc]` | | |

- Os dois significados do `^`:
- O que o `-v` do `grep` faz:
- Quando é preciso usar `grep -E`:
- O comando que mostra um arquivo de configuração sem comentários nem linhas vazias:

---

## Sessão 4 — Quinta 24/09 — Compactação e arquivamento (objetivo 3.1)

### Curso

Muller: seções sobre compactação e arquivos.

### Laboratório

**Arquivar não é comprimir.** Esta é a ideia central do objetivo 3.1, e foi registrada como correção na Semana 2:

| Operação | O que faz | Ferramenta |
|---|---|---|
| **Arquivar** | Junta muitos arquivos em um só, preservando estrutura e permissões | `tar` |
| **Comprimir** | Reduz o tamanho de **um** arquivo | `gzip`, `bzip2`, `xz` |

O `tar` sozinho gera um `.tar`, que não é menor que a soma das partes. A compressão vem de um segundo programa, acionado por flag.

**Preparando material**

```bash
cd ~/lab4
mkdir -p projeto/{src,docs,testes}
echo "codigo" > projeto/src/main.py
echo "documentacao" > projeto/docs/leiame.md
echo "testes" > projeto/testes/test_main.py
cp /var/log/dmesg projeto/docs/exemplo.log 2>/dev/null || \
  seq 1 5000 > projeto/docs/exemplo.log
du -sh projeto
```

**As opções do `tar` que a prova cobra**

| Opção | Significa | Função |
|---|---|---|
| `-c` | *create* | Cria o arquivo |
| `-x` | *extract* | Extrai |
| `-t` | *list* | Lista o conteúdo sem extrair |
| `-v` | *verbose* | Mostra os arquivos processados |
| `-f` | *file* | Indica o nome do arquivo — **sempre vem por último** |
| `-z` | gzip | Comprime com gzip, gera `.tar.gz` |
| `-j` | bzip2 | Comprime com bzip2, gera `.tar.bz2` |
| `-J` | xz | Comprime com xz, gera `.tar.xz` |

O `-f` precisa ser a última letra do grupo porque o nome do arquivo vem logo depois dele. `tar -cfv nome.tar pasta` falha; `tar -cvf nome.tar pasta` funciona.

**Criar, listar e extrair**

```bash
tar -cvf projeto.tar projeto/           # só arquiva
ls -lh projeto.tar

tar -czvf projeto.tar.gz projeto/       # arquiva e comprime com gzip
tar -cjvf projeto.tar.bz2 projeto/      # com bzip2
tar -cJvf projeto.tar.xz projeto/       # com xz

ls -lh projeto.tar*                     # compare os tamanhos
```

Observe a diferença de tamanho e, em arquivos grandes, também de tempo. A regra geral: `gzip` é o mais rápido, `xz` comprime mais, `bzip2` fica no meio.

```bash
tar -tvf projeto.tar.gz                 # LISTA sem extrair

mkdir restaurado && cd restaurado
tar -xzvf ../projeto.tar.gz
ls -R
cd ..
```

Hábito de segurança: **sempre liste antes de extrair.** Um `.tar` pode conter caminhos absolutos ou espalhar dezenas de arquivos no diretório atual.

**Extrair para um destino específico**

```bash
mkdir destino
tar -xzvf projeto.tar.gz -C destino/
ls destino
```

**Comprimir arquivos isolados**

```bash
cp projeto/docs/exemplo.log teste.log
ls -lh teste.log

gzip teste.log                  # o original é SUBSTITUÍDO por teste.log.gz
ls -lh teste.log.gz
gunzip teste.log.gz             # volta ao original
ls -lh teste.log

gzip -k teste.log               # -k mantém o original
ls -lh teste.log*
```

Comportamento que surpreende: por padrão, `gzip` e `bzip2` **substituem** o arquivo original. O `-k` de *keep* preserva.

**Ler comprimido sem descomprimir**

```bash
gzip -k teste.log
zcat teste.log.gz | head
zless teste.log.gz
zgrep 100 teste.log.gz
```

Você já esbarrou nesses comandos na Semana 3, em `/usr/share/doc/tar/changelog.Debian.gz`.

**O formato `zip`**

```bash
zip -r projeto.zip projeto/
unzip -l projeto.zip            # lista
unzip projeto.zip -d saida-zip/ # extrai em um diretório
```

O `zip` arquiva **e** comprime num passo só, ao contrário do `tar`. É o formato de interoperabilidade com Windows; no mundo Unix, `tar.gz` é o padrão.

### Registro da sessão

```bash

```

### O que aprendi

- Diferença entre arquivar e comprimir:
- Por que o `-f` vem por último:
- Comando para listar sem extrair:
- O que acontece com o original ao rodar `gzip arquivo`:
- Diferença entre `tar` e `zip`:

---

## Sessão 5 — Sexta 25/09 — `find`, desafio integrador e autoavaliação

### Laboratório — `find`

O `find` percorre o sistema de arquivos em tempo real, ao contrário do `locate`.

```bash
cd ~/lab4

find . -name "*.log"
find . -name "*.LOG"                    # não encontra: é case sensitive
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

O `2>/dev/null` deixa de ser curiosidade aqui: buscando a partir de `/`, você recebe centenas de `Permission denied` que poluem o resultado. Descartá-los é prática padrão.

**Combinando condições**

```bash
find . -type f -name "*.log" -size +1k
find . -type f ! -name "*.log"          # o ! nega
find . -type f -name "*.py" -o -name "*.md"     # -o é OU
```

**Executando ações sobre o que foi encontrado**

```bash
find . -name "*.log" -exec ls -lh {} \;
find . -name "*.log" -exec wc -l {} \;
```

O `{}` é substituído pelo caminho de cada resultado, e o `\;` encerra o comando. A barra invertida existe para impedir que o shell consuma o ponto e vírgula antes de o `find` recebê-lo.

**`find` e `locate` lado a lado**

| | `find` | `locate` |
|---|---|---|
| Como busca | Percorre o disco em tempo real | Consulta um banco indexado |
| Velocidade | Lenta | Muito rápida |
| Atualidade | Sempre atual | Só o que existia no último `updatedb` |
| Filtros | Tamanho, data, tipo, permissão, dono | Apenas o nome |

### Bandit nível 6 para 7

O desafio pede um arquivo em algum lugar do servidor, com dono, grupo e tamanho específicos. É `find` a partir de `/`, com três filtros combinados e o descarte dos erros de permissão.

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
man find        # procure -user e -group
```

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
7. Sem `-n`, o `sort` compara caractere por caractere, em ordem alfabética — e `100` vem antes de `25`. Com `-n`, compara valor numérico.
8. `-t` define o separador e `-k` define a coluna.
9. `cut -d':' -f1 /etc/passwd | wc -l`, ou simplesmente `wc -l < /etc/passwd`.
10. Porque ele lê exclusivamente da entrada padrão. Precisa de um pipe ou de `<`.
11. Inverte a busca: mostra as linhas que **não** casam com o padrão.
12. No globbing, qualquer sequência de caracteres. Na regex, zero ou mais repetições **do caractere anterior**.
13. Fora dos colchetes, ancora o início da linha. Dentro dos colchetes, nega o conjunto.
14. `grep -v '^#' arquivo | grep -v '^$'`
15. Para `|`, `?`, `+`, `{}` e agrupamento com parênteses — os metacaracteres da regex estendida.
16. Arquivar junta vários arquivos em um só, sem reduzir tamanho. Comprimir reduz o tamanho de um arquivo. O `tar` arquiva; `gzip`, `bzip2` e `xz` comprimem.
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

Encaixe no sábado ou domingo. Uma hora, sem interrupção.

**Formato:** 40 questões, 60 minutos, cronometrado, sem consultar nada. Use os simulados do Jason Dion.

**Expectativa:** algo entre 55% e 70%. Você cobriu cerca de 60% do conteúdo até aqui e ainda não estudou o Tópico 5, que vale 7 pontos. Uma nota nessa faixa é o resultado esperado, não um problema.

**O que importa não é a nota, é onde os erros se concentram.** Registre por tópico:

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

- [ ] Preparação do ambiente (`lab4`, `funcionarios.csv`, `sistema.log`)
- [ ] Sessão 1 — visualização e redirecionamento
- [ ] Sessão 2 — pipes e filtros
- [ ] Sessão 3 — `grep` e expressões regulares
- [ ] Sessão 4 — compactação e arquivamento
- [ ] Sessão 5 — `find`, desafio integrador e autoavaliação
- [ ] Bandit níveis 6, 7 e 8
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
Duplicatas     uniq  uniq -c  uniq -u        (exige entrada ordenada)
Colunas        cut -d',' -f1,3   cut -c1-5
Substituir     tr ':' '\n'   tr 'a-z' 'A-Z'   tr -d ','
Buscar texto   grep  -i  -c  -n  -v  -w  -r  -l  -E
Regex          .  [abc]  [a-z]  [^abc]  *  ^inicio  fim$     (-E para | ? + {})
Arquivar       tar -cvf  -xvf  -tvf  -czvf  -cjvf  -cJvf  -C destino
Comprimir      gzip  gunzip  gzip -k  bzip2  xz  zcat  zless  zgrep
Zip            zip -r  unzip  unzip -l  unzip -d
Buscar arquivo find . -name -iname -type -size -mtime -user ! -o -exec {} \;
```