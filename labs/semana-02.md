# Semana 2 — Linha de comando e sistema de ajuda

Período: 07 a 13/09/2026 (segunda a domingo)
Objetivos da prova: 2.1 (Command Line Basics) e 2.2 (Using the Command Line to Get Help)
Tópico 2, peso 9 de 40 — o maior da prova, empatado com o Tópico 3
Carga prevista: 5 sessões de aproximadamente 1 hora, de segunda a sexta

Regra da semana: tudo digitado, nada copiado e colado. O objetivo não é ver o comando funcionar, é a mão aprender a escrevê-lo.

---

## Objetivos oficiais cobertos

**2.1 Command Line Basics** — conhecimentos exigidos:

- Shell básico
- Sintaxe da linha de comando
- Variáveis
- Globbing (curingas)
- Quoting (aspas e escape)
- Termos e utilitários: `echo`, `history`, variável `PATH`, `export`, `type`

**2.2 Using the Command Line to Get Help** — conhecimentos exigidos:

- Páginas de manual (man pages)
- Páginas info
- Termos e utilitários: `man`, `info`, `/usr/share/doc/`, `locate`

---

## Rotina de abertura e fechamento

Início de cada sessão:

```powershell
lab-up
ssh lab
```

```bash
cd ~/linux-essentials-labs
code .
```

Fim de cada sessão:

```bash
git add . && git commit -m "docs: semana 2 - sessao N" && git push
sudo poweroff
```

---

## Pendência herdada da Semana 1

**Bandit nível 5 para 6.** O desafio pede um arquivo com três características simultâneas: legível por humano, 1033 bytes, e não executável.

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
man find
```

Procure no manual por `-size`, `-type`, `-readable` e `-executable`. O `!` nega uma condição e tamanho em bytes leva o sufixo `c`. Monte o comando sem consultar solução pronta.

**Concluído em 13/09.**

O diretório `inhere` continha muitos arquivos espalhados por subdiretórios, inviabilizando a inspeção manual. A solução foi filtrar pelas três características simultâneas:

```bash
cd inhere
ls -l
find . -readable -size 1033c ! -executable
# encontrado: ./maybehere07/.file2
cat maybehere07/.file2
```

Anatomia do comando:

| Trecho | Significado |
|---|---|
| `find .` | Procura a partir do diretório atual, recursivamente |
| `-readable` | Apenas arquivos legíveis pelo usuário atual |
| `-size 1033c` | Exatamente 1033 bytes — o sufixo `c` significa *characters* (bytes) |
| `! -executable` | O `!` **nega** a condição: apenas os que **não** são executáveis |

Observação: o arquivo encontrado era `.file2`, com ponto no início — **oculto**. É a mesma lição do nível 3, agora resolvida sem precisar procurar por ela: o `find` percorre tudo, inclusive ocultos, por padrão.

---

## Sessão 1 — Quarta 09/09 — Anatomia de um comando e navegação — CONCLUÍDA

### Curso

Muller: seções de introdução ao shell e primeiros comandos.

### Laboratório

Onde estou e o que existe aqui:

```bash
whoami
hostname
pwd
ls
ls -l
ls -a
ls -la
ls -lah
ls -lt
ls --all
```

Compare `ls -a` com `ls --all`. São a mesma opção em duas formas: **curta** (uma letra, um hífen) e **longa** (palavra, dois hífens). Opções curtas se agrupam — `ls -lah` equivale a `ls -l -a -h`. Opções longas nunca se agrupam.

A estrutura de todo comando:

```
comando [opções] [argumentos]
   ls      -lh      /etc
```

```bash
ls -lh /etc
ls -lh /etc /var
ls /naoexiste
echo $?
```

O `echo $?` mostra o código de saída do último comando: `0` significa sucesso, qualquer outro número significa erro. Esse mecanismo reaparece na Semana 5, em shell script.

Navegação:

```bash
cd /etc
pwd
cd /var/log
pwd
cd
pwd
cd /tmp
cd -
pwd
cd ~
cd ..
pwd
```

O `cd` sozinho e o `cd ~` vão para a home. O `cd -` volta ao diretório anterior e funciona como alternador entre dois lugares.

### Comandos praticados

**Identificação e localização**

| Comando | Função |
|---|---|
| `whoami` | Mostra o nome do usuário atual |
| `hostname` | Mostra o nome da máquina |
| `pwd` | Mostra o caminho do diretório atual (ex.: `/home/davi/projetos`) |

**Navegação**

| Comando | Função |
|---|---|
| `cd` | Navega entre diretórios |
| `cd ..` | Vai para o diretório **pai** |
| `cd /` | Vai para a raiz do sistema |
| `cd ~` | Vai para a home do usuário |
| `cd -` | Volta ao **último diretório visitado** |

**Listagem**

| Comando | Função |
|---|---|
| `ls` | Lista o conteúdo do diretório atual |
| `ls -l` | Formato detalhado (long) |
| `ls -a` | Inclui arquivos ocultos (all) |
| `ls -h` | Tamanhos legíveis para humanos — só tem efeito junto com `-l` |
| `ls -lh` | Detalhado com tamanhos legíveis |
| `ls -la` | Detalhado com ocultos |
| `ls -lah` | Detalhado, com ocultos e tamanhos legíveis |
| `ls -lt` | Detalhado, ordenado por data de modificação (mais recente primeiro) |
| `ls --all` | Forma longa de `ls -a` |
| `echo` | Exibe texto na tela |

**Sequência de navegação executada**

```bash
cd /etc          # arquivos de configuração do sistema e dos programas instalados
pwd              # /etc
cd /var/log      # registros de eventos e erros do sistema e dos programas
pwd              # /var/log
cd /tmp          # arquivos temporários de curta duração
cd -             # volta ao diretório anterior
```

### O que aprendi

**Opção curta e opção longa.** `ls -a` e `ls --all` são a mesma opção em duas formas. A curta usa uma letra e um hífen; a longa usa uma palavra e dois hífens. Opções curtas podem ser agrupadas (`ls -lah` = `ls -l -a -h`); as longas nunca.

**Diferença entre `cd ..` e `cd -`.** `cd ..` sobe um nível na árvore, para o diretório **pai**. `cd -` volta para o **último diretório em que eu estive**, independentemente de onde ele fica na árvore. São coisas diferentes.

**Caminho com e sem a barra inicial.** `ls etc` procura uma pasta chamada `etc` **dentro do diretório atual** (caminho relativo). `ls /etc` parte da **raiz** do sistema (caminho absoluto).

**Código de saída.** Pendente — rodar `ls /naoexiste` seguido de `echo $?` e comparar com o retorno de um comando bem-sucedido.

### Correções desta sessão

**1. `cd ..` não é "voltar para a pasta anterior".** Ele vai para o **diretório pai**, ou seja, sobe um nível na árvore. Quem volta ao diretório anterior é o `cd -`. Verificação prática:

```bash
cd /var/log
cd /etc
cd ..     # resultado: /      (o pai de /etc)
cd -      # resultado: /etc   (o anterior)
```

**2. Erro no registro da sequência de navegação.** A anotação diz que o `cd -` do passo 6 retornou para a home. Ele retornou para **`/var/log`**, porque essa era a posição imediatamente anterior:

```
cd /etc      -> atual: /etc
cd /var/log  -> atual: /var/log · anterior: /etc
cd /tmp      -> atual: /tmp     · anterior: /var/log
cd -         -> atual: /var/log
```

O `cd -` guarda apenas **um** nível de histórico, na variável `$OLDPWD`. Rodando `cd -` duas vezes seguidas, você alterna entre os mesmos dois diretórios. Para confirmar:

```bash
echo $OLDPWD
```

**3. `ls` lista o conteúdo do diretório atual**, arquivos e pastas — não "o que cada diretório possui". Para ver o conteúdo dos subdiretórios é `ls -R` (recursivo).

**4. `ls -h` sozinho não muda nada.** O `-h` afeta apenas a **coluna de tamanho**, que só aparece com `-l`. Comprove:

```bash
ls -h /etc      # saída idêntica a "ls /etc"
ls -lh /etc     # aí sim: 4.0K em vez de 4096
```

**5. `echo` não é "para exibir valores de variáveis".** Ele exibe **qualquer texto**. A impressão de que serve para variáveis vem do fato de que o shell expande `$VAR` **antes** de o `echo` receber o argumento — quando ele executa, já recebeu o valor pronto, não a variável. Prove os dois usos:

```bash
echo "texto puro, sem variável nenhuma"
echo $HOME
type echo
```

O `type echo` revela algo útil: o `echo` é um **shell builtin**, embutido no Bash — e existe também um `/usr/bin/echo` no disco. Mesma distinção do `cd`, que aparece na Sessão 3.

### Dúvidas em aberto

-

### Pendências quitadas em 09/09

**Comando com dois argumentos — concluído**

```bash
ls -lh /etc
ls -lh /var /log
ls /
echo $?          # retornou 0
```

**Correção 6 — o `/log` não existe.** Não há um diretório `/log` na raiz do sistema. O diretório de logs é `/var/log`. Escrito com espaço, `ls -lh /var /log` passa **dois argumentos** ao `ls`: o `/var`, que existe, e o `/log`, que não. A saída correta traz a listagem de `/var` seguida de:

```
ls: cannot access '/log': No such file or directory
```

Para listar os logs, o comando é `ls -lh /var/log`, sem espaço.

**Correção 7 — o `echo $?` não testou o que deveria.** A variável `$?` guarda o código de saída do **último comando executado**, e apenas dele. Na sequência acima o `echo $?` veio depois do `ls /`, que funcionou — por isso o retorno `0`. O código de erro do `ls -lh /var /log` já havia sido sobrescrito.

Para observar o código de erro, o `echo $?` precisa vir **imediatamente** após o comando testado:

```bash
ls /naoexiste
echo $?          # 2 — erro
ls /
echo $?          # 0 — sucesso
ls -lh /var /log
echo $?          # 2 — falhou em um dos dois argumentos
```

Convenção dos códigos: `0` sempre significa sucesso; qualquer valor diferente de zero significa erro, e o número indica o tipo. O `ls` usa `1` para problemas menores e `2` para erro grave, como argumento inexistente.

Esse mecanismo é a base do `&&` e do `||`, que aparecem na Semana 5 — e é exatamente o que aconteceu no `apt update && apr upgrade` durante a montagem do laboratório: o `update` retornou `0`, então o shell executou o segundo comando, que não existia.

### Pendente desta sessão

- [x] Refazer a sequência acima com o `echo $?` imediatamente após cada comando
- [x] `echo $OLDPWD` — confirmar como o `cd -` funciona

---

## Sessão 2 — Quarta 09/09 — Caminhos absolutos e relativos — CONCLUÍDA

### Curso

Muller: estrutura de diretórios e caminhos.

### Laboratório

Construa uma árvore para praticar:

```bash
cd ~
mkdir -p treino/nivel1/nivel2/nivel3
cd treino/nivel1/nivel2/nivel3
pwd
```

Agora navegue somente com caminhos relativos. Proibido começar com `/` e proibido usar `cd ~`:

```bash
cd ..
pwd
cd ../..
pwd
cd nivel1/nivel2
pwd
cd ../../..
pwd
```

A diferença que a prova cobra:

```bash
cd ~
ls etc
ls /etc
```

O primeiro falha. Caminho **absoluto** começa em `/` e parte da raiz, funcionando de qualquer lugar. Caminho **relativo** parte de onde você está — `ls etc` procura uma pasta `etc` dentro da sua home, que não existe.

Símbolos de caminho:

| Símbolo | Significado |
|---|---|
| `/` | Raiz do sistema |
| `.` | Diretório atual |
| `..` | Diretório pai |
| `~` | Home do usuário atual |
| `-` | Diretório anterior (apenas com `cd`) |

```bash
cd /var/log
ls .
ls ..
ls ~
cp /etc/hostname .
ls -l hostname
rm hostname
```

A última linha deve falhar com `Permission denied`. Não é erro seu: `/var/log` pertence ao root. Anote a mensagem exata — ela é a ponte para a Semana 6.

Familiaridade com o sistema:

```bash
ls /
ls /etc | head -20
ls /var
ls /usr
ls /bin | wc -l
```

### Comandos praticados

Executada em 09/09, no mesmo dia da Sessão 1.

**Árvore de treino**

```bash
mkdir -p treino/nivel1/nivel2/nivel3
cd treino/nivel1/nivel2/nivel3
pwd                     # /home/davi/treino/nivel1/nivel2/nivel3
```

O `-p` cria toda a cadeia de diretórios-pai de uma vez. Sem ele, seria preciso criar um nível por comando.

**Exploração do sistema de arquivos**

```bash
ls /                    # conteúdo da raiz
ls /etc | head -20      # primeiras 20 linhas da listagem de /etc
ls /var                 # backups crash local log opt snap tmp cache lib lock mail run spool
ls /usr                 # bin include lib64 local share games lib libexec sbin src
ls /bin | wc -l         # 1114
```

### O que aprendi

**Caminho absoluto e relativo.** O caminho **absoluto** começa com `/` e parte da raiz do sistema — funciona de qualquer lugar. O **relativo** parte do diretório atual. Por isso `ls etc` procura uma pasta `etc` dentro de onde estou, enquanto `ls /etc` vai direto ao `/etc` do sistema.

| Símbolo | Significado |
|---|---|
| `/` | Raiz do sistema |
| `.` | Diretório atual |
| `..` | Diretório pai |
| `~` | Home do usuário atual |
| `-` | Diretório anterior (apenas com `cd`) |

**O pipe (`|`).** Pega a **saída** do comando da esquerda e a entrega como **entrada** ao comando da direita. Em `ls /etc | head -20`, a listagem completa é gerada e o `head -20` corta nas primeiras 20 linhas. Em `ls /bin | wc -l`, o `wc -l` conta as linhas em vez de exibi-las.

Isso é objetivo 3.2, conteúdo da Semana 4 — encontrado antes da hora, o que é bom.

**Observação sobre o resultado `1114`.** Em distribuições modernas, `/bin` é um **link simbólico** para `/usr/bin` (a chamada unificação `/usr merge`). Ou seja, esse número é o total de executáveis de `/usr/bin`. Confirmar com:

```bash
ls -l /bin
```

### Dúvidas em aberto

-

### Itens complementares

- [x] **Navegação usando apenas caminhos relativos**, sem `/` inicial e sem `cd ~`, partindo de `nivel3` — concluído em 09/09:
  ```bash
  cd ~/treino/nivel1/nivel2/nivel3
  cd ..
  cd ../..
  cd nivel1/nivel2
  cd ../../..
  ```
  Confirmando a posição com `pwd` a cada passo. É o exercício que transforma a definição de caminho relativo em intuição, e é onde o `cd ..` como "diretório pai" finalmente se separa do `cd -`.

- [x] **O experimento do `Permission denied`:**
  ```bash
  cd /var/log
  cp /etc/hostname .
  ls -l hostname
  rm hostname
  ```
  A última linha deve falhar. `/var/log` pertence ao root. Anotar a mensagem exata — ela é a ponte direta para o Tópico 5, na Semana 6.

### Limpeza

```bash
cd ~ && rm -rf treino
```

---

## Sessão 3 — Quinta 10/09 — Sistema de ajuda (objetivo 2.2) — CONCLUÍDA

Esta sessão corresponde a um objetivo inteiro da prova.

### Curso

Muller: páginas de manual e sistema de ajuda.

### Laboratório

As quatro formas de pedir ajuda:

```bash
man ls
ls --help
help cd
info ls
```

Dentro do `man`, navegue com Espaço, `b`, `g`, `G`, `/tamanho`, `n` e `q`. É o mesmo paginador `less` que você já encontrou.

As diferenças: `ls --help` é a ajuda curta embutida no próprio programa; `man ls` é o manual completo; `help cd` só funciona para comandos internos do Bash.

Seções do manual — conteúdo direto de prova:

```bash
man passwd
man 5 passwd
man 1 passwd
man -f passwd
whatis passwd
```

Existem duas coisas chamadas `passwd`: o comando (seção 1) e o arquivo de configuração `/etc/passwd` (seção 5). O `man passwd` sem número abre a de menor seção.

| Seção | Conteúdo |
|---|---|
| 1 | Comandos de usuário |
| 5 | Formatos de arquivo e configuração |
| 8 | Comandos de administração do sistema |

Quando não se sabe o nome do comando:

```bash
apropos copy
man -k copy
apropos "list directory"
whatis ls
```

`apropos` e `man -k` são o mesmo comando. Servem para buscar por descrição.

Onde o comando está:

```bash
which ls
which cd
type ls
type cd
type echo
whereis ls
```

O `which cd` não devolve nada, mas o `type cd` responde `cd is a shell builtin`. O `cd` não é um arquivo no disco, é uma função embutida no Bash. Já o `ls` é `/usr/bin/ls`, um programa real. Essa distinção cai na prova.

Documentação adicional e busca de arquivos:

```bash
ls /usr/share/doc | head -20
ls /usr/share/doc/tar/
sudo apt install -y plocate
sudo updatedb
locate hostname | head
```

O `/usr/share/doc/` guarda documentação dos pacotes instalados. O `locate` busca arquivos por nome usando um banco de dados pré-construído — por isso o `updatedb`. É muito mais rápido que o `find`, mas só enxerga o que existia na última indexação.

Comparação final:

```bash
tldr tar
man tar
```

O `man` é exaustivo; o `tldr` mostra os usos mais comuns. Os dois têm lugar.

### Comandos praticados

**As quatro formas de pedir ajuda**

| Comando | O que faz |
|---|---|
| `man ls` | Abre o manual completo do comando |
| `ls --help` | Ajuda rápida, embutida no próprio programa |
| `help cd` | Ajuda de comandos **internos do shell** (builtins) |
| `info ls` | Documentação mais extensa e organizada em nós navegáveis |

**Seções do manual**

`man passwd` abre o manual do comando *change user password*. Para escolher a seção: `man <número de 1 a 8> passwd`.

| Seção | Conteúdo |
|---|---|
| 1 | Comandos usados pelo usuário |
| 2 | Chamadas de sistema |
| 3 | Funções de bibliotecas |
| 4 | Dispositivos e arquivos especiais |
| 5 | Formatos de arquivos e arquivos de configuração |
| 6 | Jogos |
| 7 | Convenções, protocolos e tópicos diversos |
| 8 | Comandos administrativos |

Sem número, o `man` abre a **menor seção disponível**. Por isso `man passwd` mostra o comando (seção 1), e é preciso `man 5 passwd` para ver o formato do arquivo `/etc/passwd`.

As três que mais caem na prova são **1, 5 e 8**.

**Busca no manual**

| Comando | O que faz |
|---|---|
| `apropos copy` | Pesquisa a palavra nas **descrições** de todas as páginas — retorna `cp: copy files and directories` |
| `man -k copy` | Idêntico ao `apropos`; o `-k` vem de *keyword* |
| `apropos "list directory"` | As aspas fazem o shell enviar a frase como **um único argumento** |
| `whatis ls` | Procura pelo **nome exato** e mostra a descrição curta |
| `man -f ls` | Idêntico ao `whatis` |

**Localizar comandos e arquivos**

| Comando | Sentido |
|---|---|
| `which` | QUAL executável |
| `type` | QUE TIPO de comando |
| `whereis` | ONDE estão os arquivos relacionados (binário, fonte, manual) |

O `which ls` retorna `/usr/bin/ls`. Já `which cd` pode não retornar nada, porque o `cd` não é um programa externo e sim um comando **interno do shell**.

### O que aprendi

**Quando usar `apropos`.** Quando não se sabe o nome exato do comando. O `apropos` busca por descrição; o `whatis` exige o nome certo.

**O que existe em `/usr/share/doc/`.** Documentação de programas e pacotes instalados, fornecida pelos próprios pacotes — changelogs, exemplos de configuração e READMEs que não estão nas man pages.

**`locate` e `find`.** O `locate` procura num **banco de dados indexado**, o que o torna muito rápido. O `find` percorre o sistema de arquivos **em tempo real**, o que é mais lento porém sempre atual. Como o banco do `locate` é gerado pelo `updatedb`, ele não enxerga arquivos criados depois da última indexação.

### Correções desta sessão

**Correção 8 — a leitura do `type ls` está invertida.** A anotação diz que a saída `ls is aliased to 'ls --color=auto'` significa "que o `ls` é um programa externo encontrado naquele caminho". Ela significa o oposto: o `ls` que você digita é um **alias**, um apelido definido no `~/.bashrc` do Ubuntu, que chama o programa real acrescentando `--color=auto`.

O `type` pode devolver cinco respostas diferentes, e distingui-las é objetivo de prova:

| Resposta | Significado | Exemplo |
|---|---|---|
| `is aliased to` | Apelido criado pelo usuário ou pela distribuição | `ls` |
| `is a shell builtin` | Função embutida no Bash, não existe em disco | `cd`, `echo` |
| `is a function` | Função definida no shell | funções do `.bashrc` |
| `is /caminho/do/arquivo` | Programa externo, um arquivo real | `tar` |
| `is a shell keyword` | Palavra reservada da linguagem | `if`, `for`, `while` |

Para ver tudo que responde por um nome, use `-a`:

```bash
type ls
type -a ls        # mostra o alias E o /usr/bin/ls
type cd
type -a echo      # builtin E /usr/bin/echo
type if
alias
```

O `type -a ls` revela as duas camadas de uma vez: primeiro o alias, depois o executável que ele acaba chamando. É isso que explica por que sua listagem sai colorida sem você pedir.

**Correção 9 — caminho sem a barra inicial.** A anotação registra `which ls → usr/bin/ls`. O correto é **`/usr/bin/ls`**, com barra no início. Sem ela seria um caminho relativo, apontando para uma pasta `usr` dentro do diretório atual — que não existe. Justamente a distinção da Sessão 2.

**Correção 10 — erro de digitação no caminho da documentação.** É **`/usr/share/doc/`**, não `/usr/share/odc/`. O `doc` vem de *documentation*.

### Dúvidas em aberto

-

### Itens do roteiro ainda não registrados

- [x] Instalar e testar o `locate` na prática:
  ```bash
  sudo apt install -y plocate
  sudo updatedb
  locate hostname | head
  ```
- [x] Navegar em `/usr/share/doc/` e abrir a documentação de um pacote:
  ```bash
  ls /usr/share/doc | head -20
  ls /usr/share/doc/tar/
  ```
- [x] Comparar `tldr tar` com `man tar`

---

## Sessão 4 — Domingo 13/09 — Variáveis, aspas e globbing — CONCLUÍDA

### Curso

Muller: variáveis de ambiente e shell.

### Laboratório

Variáveis que a prova cobra:

```bash
echo $HOME
echo $USER
echo $PWD
echo $SHELL
echo $PATH
echo $?
env | head -20
env | wc -l
```

O `$PATH` é a lista de diretórios onde o shell procura programas, separados por dois-pontos. É o mesmo conceito do PATH do Windows que apareceu no `VBoxManage`.

```bash
echo $PATH | tr ':' '\n'
```

Criando variáveis:

```bash
minhavar="teste"
echo $minhavar
bash
echo $minhavar
exit

export minhavar="teste"
bash
echo $minhavar
exit

set | grep minhavar
unset minhavar
echo $minhavar
```

O `bash` abre um shell filho. Sem `export`, a variável não é herdada. Essa é a diferença entre **variável de shell** e **variável de ambiente**, e é exatamente o que o `export` faz.

Aspas — três comportamentos distintos:

```bash
echo "Minha home é $HOME"
echo 'Minha home é $HOME'
echo Minha home é $HOME
echo "Custa \$100"
echo 'Custa $100'

arquivo="meu arquivo.txt"
touch $arquivo
ls
rm meu arquivo.txt
touch "$arquivo"
ls
rm "$arquivo"
```

| Forma | Comportamento |
|---|---|
| `"aspas duplas"` | Expande variáveis e protege espaços |
| `'aspas simples'` | Não expande nada, texto literal |
| `\` | Protege apenas o próximo caractere |

Globbing:

```bash
cd ~
mkdir -p globbing && cd globbing
touch arquivo{01..20}.txt
touch nota{a..e}.md
ls

ls *.txt
ls *.md
ls arquivo0?.txt
ls arquivo1[0-5].txt
ls nota[abc].md
ls arquivo*
```

| Curinga | Casa com |
|---|---|
| `*` | Qualquer quantidade de caracteres, inclusive nenhum |
| `?` | Exatamente um caractere |
| `[abc]` | Um caractere entre os listados |
| `[a-z]` | Um caractere no intervalo |

O experimento mais importante da semana:

```bash
echo *.txt
echo arquivo0?.txt
```

O `echo` mostra o que o `ls` receberia. **Quem expande o asterisco é o shell, não o comando.** O `ls` nunca vê um `*` — ele recebe a lista de nomes já pronta. Entender isso resolve boa parte da confusão com linha de comando.

Limpeza:

```bash
cd ~ && rm -rf globbing
```

### Variáveis de ambiente

O `$PATH` é a lista de diretórios onde o shell procura programas, separados por dois-pontos.

| Comando | O que mostra |
|---|---|
| `echo $HOME` | Diretório pessoal do usuário |
| `echo $USER` | Nome do usuário atual |
| `echo $PWD` | Diretório atual |
| `echo $SHELL` | Shell padrão configurado |
| `echo $PATH` | Diretórios onde o Linux procura comandos |
| `echo $?` | Código de saída do último comando executado |
| `env \| head -20` | Primeiras 20 variáveis de ambiente |
| `env \| wc -l` | Quantidade total de variáveis de ambiente |

O `echo $PATH | tr ':' '\n'` troca os dois-pontos por quebras de linha e mostra um diretório por linha:

```
/usr/local/sbin
/usr/local/bin
/usr/sbin
/usr/bin
/sbin
/bin
/usr/games
/usr/local/games
/snap/bin
```

### Criando e removendo variáveis

```bash
minhavar="teste"      # cria uma variável no shell atual
echo $minhavar        # teste
bash                  # inicia um processo Bash filho
echo $minhavar        # vazio — não foi herdada
exit                  # encerra o shell filho

export minhavar="teste"   # cria e marca para ser enviada aos filhos
set | grep minhavar       # confirma que existe
unset minhavar            # remove do shell atual
echo $minhavar            # vazio
```

```
Bash pai
│
│ minhavar="teste" [EXPORTADA]
│
└── processos filhos
    recebem minhavar
```

O `set` sozinho mostra variáveis do shell, variáveis exportadas, funções e outras configurações.

| Tipo | Escopo |
|---|---|
| **Variável de shell** | Existe apenas no shell atual; **não é herdada** pelos processos filhos |
| **Variável de ambiente** | Existe no shell atual e **é herdada** por todos os processos filhos |

### Aspas

| Forma | Comportamento | Exemplo |
|---|---|---|
| `"duplas"` | O Bash **expande** variáveis | `echo "Minha home é $HOME"` → `Minha home é /home/davi` |
| `'simples'` | Tudo é tratado como **texto literal** | `echo 'Minha home é $HOME'` → `$HOME` não é interpretado |
| sem aspas | A variável **é expandida**, mas o Bash pode **separar o conteúdo em vários argumentos** | ver exemplo abaixo |
| `\` | Protege o próximo caractere | `echo "Custa \$100"` → `Custa $100` |

Sem aspas, o `echo` recebe quatro argumentos separados:

```
echo
├── Minha
├── home
├── é
└── /home/davi
```

**O experimento do espaço no nome:**

```bash
arquivo="meu arquivo.txt"
touch $arquivo        # cria DOIS arquivos: "meu" e "arquivo.txt"
ls
rm meu arquivo.txt    # o rm também recebe dois argumentos e remove os dois
touch "$arquivo"      # o espaço é preservado — UM argumento, UM arquivo
```

### Globbing

Mecanismo do shell usado para encontrar nomes de arquivos que combinam com padrões.

| Padrão | Significado |
|---|---|
| `*` | Zero ou mais caracteres |
| `?` | Exatamente um caractere |
| `[abc]` | Um caractere dentre os listados |
| `[a-z]` | Um caractere dentro de um intervalo |

```bash
touch arquivo{01..20}.txt   # brace expansion: cria arquivo01.txt até arquivo20.txt
touch nota{a..e}.md         # cria notaa.md até notae.md

ls *.txt                    # todos os .txt; não pega os .md
ls arquivo0?.txt            # arquivo01 a arquivo09 — um caractere após o 0
ls arquivo1[0-5].txt        # arquivo10 a arquivo15
ls nota[abc].md             # notaa.md, notab.md, notac.md
ls arquivo*                 # qualquer nome que comece com "arquivo"

cd ~ && rm -rf globbing
```

### Correções desta sessão

**Correção 11 — brace expansion não é globbing.** A anotação colocou `{01..20}` sob o título de globbing. São mecanismos diferentes, e a prova distingue os dois:

| Mecanismo | O que faz | Depende de arquivos existirem |
|---|---|---|
| **Brace expansion** `{01..20}` `{a,b,c}` | Gera uma **lista literal de texto** | Não |
| **Globbing** `*` `?` `[abc]` | **Casa com nomes de arquivos que já existem** | Sim |

Comprove a diferença:

```bash
cd /tmp && mkdir teste-expansao && cd teste-expansao
echo {1..5}.txt     # imprime: 1.txt 2.txt 3.txt 4.txt 5.txt — mesmo sem nenhum arquivo
echo *.txt          # imprime: *.txt — não casou com nada, o shell devolve o padrão cru
touch {1..5}.txt
echo *.txt          # agora sim: 1.txt 2.txt 3.txt 4.txt 5.txt
cd ~ && rm -rf /tmp/teste-expansao
```

É por isso que o brace expansion serve para **criar** arquivos e o globbing para **selecionar** os que já existem.

**Correção 12 — direção da herança.** A anotação diz que a variável de shell "não recebe processos filhos". A direção é a inversa: os **processos filhos é que não recebem** a variável. Quem herda é o filho, não a variável.

**Correção 13 — o que o `grep` está filtrando.** A anotação diz que `set | grep HOME` "procura texto em HOME". Ele procura a palavra `HOME` **na saída do comando `set`**. O `grep` sempre filtra o que chega pela entrada; o argumento é o que ele procura, não onde procura.

**Correção 14 — `emv` não existe.** Erro de digitação na tabela: o comando é `env | wc -l`.

**Correção 15 — o `tar` sozinho não comprime.** A anotação registra que o `tar` empacota vários arquivos em um `.tar`, o que está certo. Vale completar: empacotar e comprimir são **operações separadas**. O `.tar` é só o pacote; a compressão vem de um segundo programa acionado por flag — `-z` (gzip, gera `.tar.gz`), `-j` (bzip2, `.tar.bz2`), `-J` (xz, `.tar.xz`). Isso é objetivo 3.1, na Semana 4.

**Correção 16 — o `history` não é só da sessão atual.** Ele lê o arquivo `~/.bash_history`, que persiste entre sessões. Por isso comandos de dias anteriores aparecem na lista.

### Pendente desta sessão

- [x] O experimento que fecha o conceito da semana — rodar e comparar:
  ```bash
  echo *.txt
  ls *.txt
  ```
  O `echo` mostra **exatamente o que o `ls` recebe**. Quem expande o asterisco é o shell, antes de o comando existir; o `ls` nunca vê um `*`.

### Dúvidas em aberto

-

---

## Sessão 5 — Domingo 13/09 — Histórico, atalhos e autoavaliação — CONCLUÍDA (exceto autoavaliação)

### Laboratório

Histórico:

```bash
history
history | tail -20
history | grep chmod
!!
sudo !!
!42
!ls
```

O `sudo !!` repete o comando anterior com `sudo` na frente. É o atalho mais usado do mundo Linux, para quando se esquece do privilégio.

O `Ctrl+R` faz busca reversa no histórico: aperte, digite parte de um comando antigo, `Ctrl+R` de novo para ir à ocorrência anterior, Enter para executar ou seta para editar.

Atalhos de edição — treine cada um, não apenas leia:

| Atalho | Ação |
|---|---|
| `Ctrl+A` | Início da linha |
| `Ctrl+E` | Fim da linha |
| `Ctrl+U` | Apaga do cursor até o início |
| `Ctrl+K` | Apaga do cursor até o fim |
| `Ctrl+W` | Apaga a palavra anterior |
| `Ctrl+L` | Limpa a tela |
| `Ctrl+C` | Cancela o comando atual |
| `Ctrl+D` | Encerra a entrada ou sai do shell |
| `Tab` | Completa comando ou nome de arquivo |
| `Tab Tab` | Lista as opções possíveis |

Tab completion:

```bash
cd /et<Tab>
ls /usr/sh<Tab>
ls /etc/pas<Tab>
gr<Tab><Tab>
```

Aliases:

```bash
alias
alias ll='ls -lah'
ll
alias ..='cd ..'
..
unalias ll
```

Aliases criados assim desaparecem ao fechar o terminal. Para torná-los permanentes vão no `~/.bashrc`, que será tratado na Semana 5.

### Histórico

| Comando | O que faz |
|---|---|
| `history` | Mostra o histórico de comandos, com um número associado a cada um |
| `history \| tail -20` | As últimas 20 linhas do histórico |
| `history \| grep chmod` | Filtra o histórico procurando por `chmod` |
| `!!` | Executa novamente o comando imediatamente anterior |
| `sudo !!` | Executa o último comando com `sudo` na frente |
| `!42` | Executa o comando número 42 do histórico |
| `!ls` | Executa o comando mais recente que começou com `ls` |

O `history` lê o arquivo `~/.bash_history`, que **persiste entre sessões** — por isso comandos de dias anteriores continuam na lista.

### Atalhos treinados

| Atalho | Ação |
|---|---|
| `Ctrl+A` | Início da linha |
| `Ctrl+E` | Fim da linha |
| `Ctrl+U` | Apaga do cursor até o início |
| `Ctrl+K` | Apaga do cursor até o fim |
| `Ctrl+W` | Apaga a palavra anterior |
| `Ctrl+L` | Limpa a tela |
| `Ctrl+C` | Cancela o comando atual |
| `Ctrl+D` | Encerra a entrada ou sai do shell |
| `Tab` | Completa comando ou nome de arquivo |
| `Tab Tab` | Lista as opções possíveis |

### Aliases

Apelidos para comandos no shell, usados para encurtar comandos longos ou criar atalhos personalizados.

```bash
alias                    # lista os aliases existentes
alias ll='ls -lah'       # cria o apelido ll
alias ..='cd ..'         # cria o apelido ..
unalias ll               # remove o apelido
```

Aliases criados assim desaparecem ao fechar o terminal. Para torná-los permanentes vão no `~/.bashrc`, que será tratado na Semana 5.

---

## Autoavaliação

Responda sem consultar nada. Confira só depois de responder todas.

1. Qual a diferença entre `ls -a` e `ls --all`?
2. O que `cd -` faz?
3. Escreva um caminho absoluto e um relativo para o mesmo arquivo.
4. Em que seção do manual está o formato do arquivo `/etc/passwd`? Qual comando abre exatamente essa seção?
5. Você quer descobrir qual comando compacta arquivos, mas não lembra o nome. Que comando usa?
6. Qual a diferença entre `which cd` e `type cd`, e por quê?
7. O que `echo $?` retorna depois de um comando bem-sucedido?
8. Qual a diferença entre `echo "$HOME"` e `echo '$HOME'`?
9. O que o `export` faz que a atribuição simples não faz?
10. Quantos arquivos `ls arquivo?.txt` casa, se existem `arquivo1.txt` até `arquivo20.txt`?
11. Quem expande o asterisco, o shell ou o comando?
12. Como repetir o comando anterior com `sudo`?
13. Que atalho leva o cursor ao início da linha?
14. Qual comando mostra onde o executável `ls` está no disco?
15. O que a variável `PATH` armazena?

<details>
<summary>Gabarito</summary>

1. Nenhuma. São a mesma opção, nas formas curta e longa.
2. Volta ao diretório anterior.
3. Exemplo: `/home/davi/notas.txt` (absoluto) e `notas.txt` estando na home (relativo).
4. Seção 5. `man 5 passwd`.
5. `apropos compress` ou `man -k compress`.
6. O `which` procura executáveis no `PATH` e não encontra o `cd`, porque `cd` é builtin do Bash. O `type` reconhece builtins.
7. Zero.
8. Aspas duplas expandem a variável e mostram o caminho. Aspas simples não expandem e mostram o texto `$HOME`.
9. Torna a variável disponível para processos filhos, ou seja, variável de ambiente.
10. Nove: de `arquivo1.txt` a `arquivo9.txt`. O `?` casa exatamente um caractere.
11. O shell. O comando recebe a lista já expandida.
12. `sudo !!`
13. `Ctrl+A`
14. `which ls`, ou `type ls`, ou `whereis ls`.
15. A lista de diretórios onde o shell procura executáveis, separados por dois-pontos.

</details>

**Não realizada na Semana 2.** Transferida como dívida para a Semana 3, onde será a primeira atividade.

Nota obtida: ___ de 15

Meta: 12 de 15. Cada erro vira card no Notion no mesmo dia.

Erros e o que revisar:

1.
2.
3.

---

## Checklist da semana

- [x] Sessão 1 — anatomia do comando e navegação (09/09)
- [x] Sessão 2 — caminhos absolutos e relativos (09/09)
- [x] Sessão 3 — sistema de ajuda (10/09)
- [x] Sessão 4 — variáveis, aspas e globbing (13/09)
- [x] Sessão 5 — histórico, atalhos e aliases (13/09)
- [x] Bandit nível 5 para 6 (pendência da Semana 1)
- [ ] Autoavaliação — transferida para a Semana 3
- [ ] Curso do Muller — nenhum avanço nesta semana
- [ ] Cards do Notion atualizados

## Fechamento da Semana 2

**Concluída em 13/09, no último dia do prazo.** As cinco sessões foram cumpridas, mas com duas sessões comprimidas no domingo, o que gerou dívidas.

**Objetivos cobertos:** 2.1 (Command Line Basics) e 2.2 (Using the Command Line to Get Help) — 5 dos 9 pontos do Tópico 2.

**Realizado:**

- Estrutura de comandos, opções curtas e longas, códigos de saída
- Caminhos absolutos e relativos, símbolos `/ . .. ~ -`
- Sistema de ajuda completo: `man` e suas 8 seções, `apropos`, `whatis`, `--help`, `help`, `info`
- Localização de comandos: `which`, `type`, `whereis`
- Variáveis de shell e de ambiente, `export`, `set`, `unset`
- Aspas simples, duplas e escape
- Globbing e brace expansion
- Histórico, atalhos de edição e aliases
- Bandit nível 5 para 6, com `find` e filtros combinados

**Ponto de atenção:** o conteúdo foi absorvido **apenas pela prática**, sem avanço no curso. Funcionou bem nesta semana, porque os objetivos 2.1 e 2.2 são inteiramente operacionais. Não deve funcionar igual nos Tópicos 3 e 4, que trazem conceitos que o laboratório sozinho não ensina.

**Qualidade das anotações:** 16 correções registradas ao longo da semana, nenhuma delas grave. A maioria foi imprecisão de redação, não erro de compreensão. As duas conceituais reais foram a leitura invertida do `type ls` (Sessão 3) e a confusão entre brace expansion e globbing (Sessão 4).

---

## Fechamento da semana

O que ficou sólido:

-

O que preciso revisar:

-

Comandos que viraram card no Notion:

-

---

## Cola rápida

```
Navegação      pwd  cd  cd ~  cd -  cd ..  ls -lah  ls -lt
Estrutura      comando [opções] [argumentos]   -a curta   --all longa
Caminhos       /   .   ..   ~   -
Ajuda          man  man 5  man -k  apropos  whatis  --help  help  info
Localizar      which  type  whereis  locate  updatedb
Documentação   /usr/share/doc/
Variáveis      echo $HOME $USER $PATH $SHELL $?   env  set  export  unset
Aspas          "expande"   'literal'   \escapa
Globbing       *   ?   [abc]   [a-z]   {01..20}
Histórico      history  !!  sudo !!  !42  Ctrl+R
Edição         Ctrl+A  Ctrl+E  Ctrl+U  Ctrl+K  Ctrl+W  Ctrl+L
Outros         alias  unalias  file  clear  exit
```