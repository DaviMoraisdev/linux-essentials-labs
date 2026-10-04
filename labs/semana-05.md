## **Laboratório 1 — Sexta 02/10 — Fundamentos de shell script**

### **Blocos**

**1. Primeiro script, shebang e execução (10 min)**

```
cd ~/lab5 && mkdir -p scripts && cd scripts

echo 'echo "Hello World!"' > primeiro
./primeiro                       # Permission denied: leia a mensagem inteira
ls -l primeiro
chmod +x primeiro
./primeiro

which bash
cat > ola.sh << 'EOF'
#!/bin/bash
# Primeiro script com shebang e comentario.
echo "Hello World!"
EOF
chmod +x ola.sh
./ola.sh
bash ola.sh                      # roda mesmo sem o x: o bash le o arquivo
```

1. O que é shell script? → É um arquivo de texto que reúne comandos para o shell executar, os comandos são os mesmos que usamos no terminal como cd, ls, echo e etc 
2. Shell → O programa que interpreta os comandos digitados 
3. bash → Um tipo de shell, usado no linux 
4. shell script → Um arquivo contendo comandos para um shell executar 
5. Interpretador → O programa que lê e executa as instruções do script, no caso o bash 

---

1. echo 'echo "Hello World!"' > primeiro = 
    1. Existem dois echos, porém com funções em momentos diferentes
        1. O echo externo escreve um texto 
        2. O echo interno faz parte do texto que será salvo no arquivo 
        3.  As aspas simples delimitam o conteúdo 
    2. O operador “>” direciona esse texto para o arquivo primeiro, e esse arquivo passar a conter ( echo “hello world” )
    3. Ao tentar executar “./primeiro” → O . representa o diretorio atual, o ./ é usado porque o shell normalmente procura comandos nos diretorios da varíavel PATH, e a pasta atual não faz parte dessa lista, ou seja, o arquivo não tem permissão de execução (permission denied)
    4. ls -l primeiro = Aqui o comando de inspeção mostra as informações do arquivo:-rw-rw-r-- 1 davi davi 19 Oct  2 13:06 primeiro
    5. chmood +x primeiro → Acrescenta permissão de execução:
        1. chmod: altera permissões 
        2. +x: acresenta permissão de execução 
        3. Agora ./primeiro é executavel: Hello World 
- Obs: Esse primeiro arquivo não possui shebang, quando você executa a partir do bash, ele pode reconhecer a falha de execução direta e tentar interpretá-la como script, para indicar explicitamente ao interpretador é necessário shebang

---

1. which bash → descobrindo onde está o bash → /usr/bin/bash
2. Criando um script com shebang 
    1. cat > ola.sh << 'EOF'
    #!/bin/bash
    # Primeiro script com shebang e comentario.
    echo "Hello World!"
    EOF
    2. Cria um arquivo com 3 linhas:
        1. #!/bin/bash → É o shebang, ele informa qual interpretador deve executar o arquivo quando voê usa → ./ola.sh 
        2. O #! precisa estar no começo do arquivo: sem espaço, comentário ou linha vazia antes dele 
        3. A segunda linha é um comentario 
        4. A terceira linha e o comando que imprime a mensagem: echo “Hello World” 
    3. cat > arquivo << ‘EOF’
        1. cat: recebe o texto fornecido e o escreve na saída 
        2. > ola.sh: Direciona essa saída para o arquivo 
        3. << Inicia um here-document (EOF) que permite escrever um bloco de texto como entrada 
        4. Duas formas de executar:
            1. chmod +x ola.sh  → Exige permissão de execução e, havendo o shebang válido, usa o interpretador indicando nele 
            ./ola.sh 
            2. basg ola.sh → Você escolhe diretamente o Bash para ler o arquivo, não exige x, mas o arquivo precisa estar acesível para leitura 
            - chmod -x ola.sh
            ./ola.sh
            bash ola.sh
                - O -x remove a permissão de execução
                - ./ola.sh → permission denied
                - bash ola.sh → continua funcionando, se você puder ler o arquivo
                - A extensão .sh é uma convenção, ela ajuda uma pessoas reconhecer scripts

O que fixar: `#!` precisa ser os **dois primeiros caracteres** do arquivo; `./script` exige permissão `x` e usa o interpretador do shebang; `bash script` não exige `x`; a extensão `.sh` é convenção e não altera a execução.

---

**2. Variáveis e argumentos (10 min)**

```
cat > saudacao.sh << 'EOF'
#!/bin/bash
# Uso: ./saudacao.sh <nome>
nome=$1
echo "Ola, $nome!"
echo "Script: $0"
echo "Total de argumentos: $#"
echo "Todos: $@"
EOF
chmod +x saudacao.sh
./saudacao.sh Davi
./saudacao.sh Davi Morais
./saudacao.sh
```

1. Um argumento é uma informação passada ao executar um comando 
    1. Ex: ./saudacao.sh Davi Morais 
        1. $0 → ./saudacao.sh
        2. $1 → Davi 
        3.  $2 → Morais 
        4. $# → 2 
        5. $@ → A lista dos argumentos: Davi e Morais 
2. nome=$1 → O script copia o primeiro argumento para variavel nome 
    1. Ao executar ./saudacao.sh Davi → Davi é o primeiro argumento 
    2. Saída:
        1. Olá, Davi!
        Script: ./saudacao.sh
        Total de argumentos: 1 
        Todos: Davi 
3. Executando dois argumentos:
    1. ./saudacao.sh Davi Morais 
    2. Saída:
        1. Ola, Davi!
        Script: ./saudacao.sh
        Total de argumentos: 2
        Todos: Davi Morais
    3. A saudação usa apenas $1, por isso que aparece Davi mesmo tendo sido Davi Morais 
    4. Para passar com o nome completo deve-se usar as aspas 
        1. ./saudacao.sh “Davi Morais”
        2. $1 = Davi Morais → 1 argumento 
4. Execuatando sem argumentos:
    1. Ola, !
    Script: ./saudacao.sh
    Total de argumentos: 0
    Todos:
5. Aspas simples e duplas:
    1. nome=Davi
    echo "Ola, $nome!"
    echo 'Ola, $nome!'
    2. O primeiro echo sai: Ola, Davi! / O segundo: Ola, $nome! → regra das aspas = duplas expandem variaveis e preservam espaços || simples = mantêm o texto literal 

Pontos de atenção: **sem espaço** ao redor do `=` na atribuição (`nome=Davi`, nunca `nome = Davi`); `$1` a `$9` são argumentos posicionais; `$#` é a quantidade; `$@` é a lista; `$0` é o nome do script. Aspas duplas expandem variáveis, aspas simples não.

---

**3. Decisões com `if` (10 min)**

```
cat > teste.sh << 'EOF'
#!/bin/bash
if [ $# -ne 2 ]
then
  echo "Uso: $0 <n1> <n2>"
  exit 1
fi

if [ $1 -gt $2 ]
then
  echo "$1 e maior que $2"
elif [ $1 -eq $2 ]
then
  echo "Iguais"
else
  echo "$1 e menor que $2"
fi
EOF
chmod +x teste.sh
./teste.sh 3 1 ; ./teste.sh 2 2 ; ./teste.sh 1 5 ; ./teste.sh 1
```

| **Operador** | **Compara** |
| --- | --- |
| `-eq` `-ne` | igual, diferente (números) |
| `-lt` `-le` | menor, menor ou igual (números) |
| `-gt` `-ge` | maior, maior ou igual (números) |
| `=` ou `==` | igualdade de **texto** |
| `-f` `-d` | arquivo comum existe, diretório existe |
| `-z` | texto vazio |
1. O if permite escolher o que executar conforme o resultado de um teste 
    1. if comando_ou_teste
    then
        # Executa quando o teste retorna sucesso 
    else 
        # Executa quando o teste não retorna sucesso 
    fi
2. if. inicia a decisão
then: inicia o bloco executado quando a condição é verdadeira
elif: testa outra condição, se a anterior foi falsa
else: trata os casos restantes 
fi: encerra a estrutura

| Operador | Significado | Exemplo verdadeiro |
| --- | --- | --- |
| `-eq` | Igual | `[ 3 -eq 3 ]` |
| `-ne` | Diferente | `[ 3 -ne 5 ]` |
| `-lt` | Menor que | `[ 3 -lt 5 ]` |
| `-le` | Menor ou igual | `[ 3 -le 3 ]` |
| `-gt` | Maior que | `[ 5 -gt 3 ]` |
| `-ge` | Maior ou igual | `[ 5 -ge 5 ]` |

O erro mais comum: `[ $1 -gt $2 ]` sem espaços internos, ou `[$1 -gt $2]`. Os espaços entre os colchetes e os operandos são **obrigatórios**, porque `[` é um comando, não uma sintaxe.

**4. Loops com `for` (5 min)**

```
for i in 1 2 3; do echo "volta $i"; done
for i in $(seq 1 5); do echo "n=$i"; done
for arq in /etc/*.conf; do echo "$arq"; done | head -3
```

1. Um loop repete um bloco de comandos, cada repetição é chamada de iteração 
2. for i in 1 2 3; do echo "volta $i"; done:
    1. for - inicia a repetição 
    2. i - Varíavel que recebe cada item 
    3. in 123 - Lista dos valores que serão percorridos 
    4. do - Inicia os comandos repetidos 
    5. done - Encerra o loop 
        1. i recebe 1 e o echo executa
        2. i recebe 2 e o echo executa novamente 
        3.  i recebe 3 e ocorre a última repetição  
3. for i in $(seq 1 5); do echo "n=$i"; done
    1. A expressão seq 1 5 gera 1, 2, 3, 4, 5 
    2. É uma substituição de comandos: o shell executa o comando interno e usa sua saída no comando externo 
    3. Nesse caso, o for recebe os números de 1 a 5 
        1. n=1
        n=2
        n=3
        n=4
        n=5
4. for arq in /etc/*.conf; do echo "$arq"; done | head -3
    1. /etc/*.conf: padrão que corresponde aos nomes terminados em .conf, diretamente dentro de /etc. 
    2. arq: recebe um caminho a cada repetição 
    3. echo “$arq”: mostra esse caminho 
    4. |→ envia a saída do loop para outro comando 
    5. head -3: mostra somente as três primeiras linhas recebidas 
        1. /etc/adduser.conf
        /etc/debconf.conf
        /etc/deluser.conf

**5. Código de saída (5 min)**

```
ls /etc > /dev/null ; echo $?        # 0
ls /naoexiste 2> /dev/null ; echo $? # diferente de 0
grep -q root /etc/passwd && echo "achou" || echo "nao achou"
```

1. Um comando pode produzir:
- Saída normal: resultados, textos e listagens 
- Saída de erro: mensagens sobre problemas
- Código de saída: um número indicando como terminou 
2. ls /etc > /dev/null ; echo $? 
    1. ls /etc: lista o conteúdo de /etc
    2. “>” redireciona a saída 
    3. /dev/null: descarta tudo que recebe 
    4. $?: contém o código de saída do comando anterior 
        1. Saída → 0
3. ls /naoexiste 2> /dev/null ; echo $? 
    1. O ls agora acessa um caminho inexistente
    2. 2> redireciona a saída de erro 
    3. A mensagem é descartada
    4. O código continua indicando falaha 
        1. Saída: 2 → erro stderr
4. grep -q root /etc/passwd && echo "achou" || echo "nao achou"
    1. grep - Busca um padrão em um texto 
    2. -q - Não mostra as linhas encontradas; permite consultar o resultado pelo código de saída 
    3. root - Texto procurado 
    4. /etc/passwd - arquivo pesquisado, que contém informações das contas locais 
    5. && echo “achou” - Executa se o grep retornar 0 
        1. Saída: achou 

O `$?` guarda o código do **último** comando: `0` é sucesso, qualquer outro valor é falha. O `exit N` define o código do próprio script. `&&` executa o segundo comando só se o primeiro der `0`; `||` só se der diferente de `0`. Regra 3 do plano: **saída na tela não é prova de sucesso**, então confira o `$?`.

**6. Editores `vi` e `nano` (10 min) — objetivo oficial**

```
nano ola.sh          # digite direto; Ctrl+O grava, Ctrl+X sai
vi ola.sh
```

1. Nano:
    1. Abre o arquivo nano:
        1. Crtl + O → Inicia a gravação, confirme o nome com Enter 
        2. Crtl + X → Sai do editor, se houver alterações não salvas, ele pergunta o que fazer 
2. Vi:
    1. Modo normal ou navegação: Mover o cursor e executar ações de edição 
    2. Inserção: Diigtar texto no arquivo 
    3. Linha de comando: Gravar, sair e executar comandos iniciados por :
    

No `vi`, memorize os três modos e as teclas de transição:

| **De** | **Para** | **Tecla** |
| --- | --- | --- |
| Navegação (padrão ao abrir) | Inserção | `i` |
| Inserção | Navegação | `Esc` |
| Navegação | Comando | `:` |

No modo de comando: `:w` grava, `:q` sai, `:wq` grava e sai, `:q!` sai sem gravar. No `nano` não há modos; os atalhos aparecem no rodapé, com `^` significando `Ctrl` (`^O` grava, `^X` sai). Saia dos dois editores três vezes cada, sem consultar.

### **Exercício de fixação — do material oficial**

O LPI Learning Material (objetivo 3.3, Exercícios Guiados, script `guided1.sh` das frutas) traz um script com **vários erros de sintaxe** para corrigir. Digite-o exatamente como está, rode, leia cada mensagem de erro inteira e corrija um por vez. Só depois compare com as respostas. O exercício cobre exatamente os três pontos do início do documento: espaços na atribuição, espaços dentro de `[ ]` e aspas simples que impedem a expansão.

#### Resolução do exercicio:

> O exercício das frutas propõe aprender a **ler o erro, localizar sua causa e corrigir um problema por vez**.
> 
1. criar arquivo com o nano e os erros: 
frutas.sh:

#!/bin/bash

fruta1 = Macas
fruta2=Laranjas

if [$1 -gt $2 ]
then
echo '$fruta1 venceram!'
elif [ "$1" -eq "$2" ]
then
echo "Empate!"
else
echo "$fruta2 venceram!"
done

1. Erros listados:

./frutas.sh: line 3: fruta1: command not found
./frutas.sh: line 14: syntax error near unexpected token `done' ./frutas.sh: line 14:` done'

1. Correção:
1º - fruta1 = Macas → fruta1=Macas - Espaços em variaveis 

2° - if [$1 -gt $2 ] → if [ $1 -gt $2 ] - colchete sem espaço 

3° - echo '$fruta1 venceram!’ - Aspas simples imprimem o texto literal é preciso corrigir para aspas duplas e atribuir o valor da variavel fruta1 corretamente 

4° - Encerramento incorreto - done trocar para fi 

Resultado:
- ./frutas.sh 2 5
Laranjas venceram!
- ./frutas.sh 5 2
Macas venceram!
- ./frutas.sh 3 3
Empate!