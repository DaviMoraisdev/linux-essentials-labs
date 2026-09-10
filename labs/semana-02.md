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

Sugestão de encaixe: sábado, ou ao final da Sessão 2.

Registro:

```bash

```

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

- [ ] Refazer a sequência acima com o `echo $?` imediatamente após cada comando
- [ ] `echo $OLDPWD` — confirmar como o `cd -` funciona

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

- [ ] **O experimento do `Permission denied`:**
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

## Sessão 3 — Quinta 10/09 — Sistema de ajuda (objetivo 2.2)

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

```bash

```

### Seções do manual

| Seção | Conteúdo |
|---|---|
| 1 | |
| 5 | |
| 8 | |

### O que aprendi

- `which` e `type`, e o caso do `cd`:
- Quando usar `apropos`:
- O que existe em `/usr/share/doc/`:
- `locate` e `find`, diferença:

### Dúvidas em aberto

-

---

## Sessão 4 — Sexta 11/09 — Variáveis, aspas e globbing

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

### Comandos praticados

```bash

```

### Aspas

| Forma | Comportamento | Meu exemplo |
|---|---|---|
| `"duplas"` | | |
| `'simples'` | | |
| `\` | | |

### Globbing

| Curinga | Casa com | Meu exemplo |
|---|---|---|
| `*` | | |
| `?` | | |
| `[abc]` | | |
| `[a-z]` | | |

### O que aprendi

- Por que `touch $arquivo` criou dois arquivos:
- Variável de shell e variável de ambiente:
- Quem expande o asterisco:

### Dúvidas em aberto

-

---

## Sessão 5 — Sábado 12/09 — Histórico, atalhos e autoavaliação

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

### Atalhos treinados

| Atalho | Ação | Já é reflexo |
|---|---|---|
| `Ctrl+A` | | |
| `Ctrl+E` | | |
| `Ctrl+U` | | |
| `Ctrl+K` | | |
| `Ctrl+W` | | |
| `Ctrl+L` | | |
| `Ctrl+R` | | |
| `Tab` | | |

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
- [ ] Sessão 3 — sistema de ajuda (10/09)
- [ ] Sessão 4 — variáveis, aspas e globbing (11/09)
- [ ] Sessão 5 — histórico, atalhos e autoavaliação (12/09)
- [ ] Bandit nível 5 para 6 (pendência da Semana 1)
- [ ] Cards do Notion atualizados
- [ ] Autoavaliação com 12 acertos ou mais
- [ ] Commits diários no repositório

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