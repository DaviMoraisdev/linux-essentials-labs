# Semana 5 — Shell script, simulado diagnóstico e reorganização do curso

Período: 28/09 a 04/10/2026 (segunda a domingo)
Objetivo da prova: 3.3 (Turning Commands into a Script), peso 4 de 40 — o maior peso individual do exame
Tópico 3, peso 9: com o 3.3 esta semana fecha os 4 pontos restantes (3.1 e 3.2 foram fechados na Semana 4)
Plano final (02/10, à noite): o fechamento da semana é o **domingo 04/10**, com o simulado #1 e o Laboratório 1. O Laboratório 2 e as aulas 31 a 43 passam para a Semana 6

Observação sobre a natureza desta semana: até aqui cada comando foi aprendido isoladamente, e na Semana 4 eles passaram a se combinar em pipelines. O shell script é o passo seguinte: o pipeline vira um arquivo reutilizável, com variáveis, decisões e código de saída. Você já programa, então a sintaxe vem rápido. O que exige atenção é o modelo mental do shell, que difere de uma linguagem estruturada em três pontos concretos: espaços dentro de `[ ]` são obrigatórios, `=` compara texto e `-eq` compara número, e uma variável sem aspas se parte em palavras.

---

## Objetivo oficial coberto

Fonte: LPI Learning Material, versão 1.6, objetivo 3.3.

**Áreas-chave de conhecimento**

- Shell scripting básico
- Reconhecimento de editores de texto comuns (**vi e nano**)

**Termos e utilitários citados oficialmente**

- `#!` (shebang) e `/bin/bash`
- Variáveis
- Argumentos
- `for` loops
- `echo`
- Exit status

Dois pontos de atenção que o plano anterior não destacava:

1. **Os editores `vi` e `nano` fazem parte do objetivo.** A prova pode perguntar como se entra no modo de inserção do `vi` ou como se sai do `nano`. Isso entra no Laboratório 1, em 10 minutos.
2. **`while` e `read` não constam na lista oficial.** São úteis e entram no Laboratório 2 porque o quarto script os exige, mas o que a prova cobra com certeza são `for`, argumentos, variáveis, `if` com operadores numéricos e o código de saída.

---

## A estratégia em vigor

Esta é a estratégia consolidada nas Semanas 4 e 5. Ela vale até a prova.

| Elemento | Como funciona |
|---|---|
| **Duas fases** | Fase 1 (Semanas 5 a 7, até 18/10): fechar o curso, com 2 laboratórios por semana. Fase 2 (Semanas 8 a 10, até 08/11): simulados em condição de prova e laboratório integrador |
| **Curso como atividade principal** | Velocidade de 1.5x nos tópicos já praticados, 1x no objetivo 3.3, 1.25x nos tópicos novos (4 e 5) |
| **Duas sessões de laboratório por semana** | Sessão inteira de teclado: 45 min digitando (nunca copiando), 10 min de registro no caderno, 5 min de commit |
| **Aquecimento diário de 10 minutos** | Cinco comandos de memória, sem consultar. O que travar vira card no Notion na hora |
| **Aquecimento pautado pelos erros** | Os comandos vêm das questões erradas da autoavaliação anterior, não do acaso |
| **Autoavaliação na semana seguinte** | Respondida em um dia de curso, como abertura da sessão, com intervalo mínimo de 3 dias. Mede retenção, não memória de curto prazo |
| **Executar em vez de reler** | Conceito que resistiu a três leituras cede a uma execução de 15 segundos (lição do `sort`, Correção 50) |
| **Correção com mecanismo** | Cada erro é registrado com o motivo, não só com a resposta certa. O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |
| **Marcar os chutes** | No simulado, toda questão acertada por eliminação conta como erro para efeito de estudo |
| **Fila de dívidas** | Item adiado não some: entra no início do próximo bloco e fica registrado na tabela de dívidas abaixo |
| **Gate de aprovação** | Dois simulados seguidos com 85% ou mais na Semana 9. Sem isso, a prova é adiada em uma semana |
| **Sem dumps** | ITExams, Marks4Sure e semelhantes violam o acordo de confidencialidade da LPI |

---

## Situação na abertura — 29/09

### Concluído

| Item | Data |
|---|---|
| Sessão 5 da Semana 4 (`find` e desafio integrador) | 28/09 |
| Autoavaliação da Semana 4 — 14 de 20 | 29/09 |
| Correções 49 a 52 anotadas no caderno | 29/09 |
| Instalação do `bzip2` | 29/09 |
| Commits da Semana 4 | 29/09 |

### Adiado e ainda em aberto

| Item | Situação |
|---|---|
| **Curso, aulas 26 a 31** | Previsto para terça 29/09. Foi adiado na segunda e na terça |
| **Simulado diagnóstico** | Pendência mais antiga do plano, com quatro semanas de atraso. Data fixa: domingo 04/10 |
| **Voucher da prova** | Prazo original: 29/09 |

---

## Calendário revisado — segunda revisão, em 29/09

A segunda-feira foi consumida pela Sessão 5 da Semana 4 e a terça pela autoavaliação e pelas correções. O curso perdeu os dois dias. Em vez de criar um quarto dia de curso, as 18 aulas restantes (26 a 43) foram distribuídas em **dois blocos de 9 aulas**, na quarta e na quinta. Os laboratórios de sexta e sábado e o simulado de domingo **não mudam de dia**.

| Dia | Atividade | Tempo |
|---|---|---|
| Seg 28 | Sessão 5 da Semana 4 — `find` e desafio integrador | concluído |
| Ter 29 | Autoavaliação da Semana 4 · correções 49 a 52 · `bzip2` · commits | concluído |
| **Qua 30** | Voucher (10 min) · curso, aulas 26 a 34 · aquecimento — **realizado em parte: aulas 26 a 30, checkpoint na aula 31** | 1h25 |
| **Qui 01/10** | **Curso, aulas 31 a 43** (13 aulas; as de shell script a 1x) · aquecimento | cerca de 1h50 |
| Sex 02 | Laboratório 1 — fundamentos de shell script, `vi` e `nano` · aquecimento | 1h10 |
| Sáb 03 | ~~Laboratório 2 — os quatro scripts~~ — **transferido para a Semana 6** (terça 06/10) | — |
| **Dom 04** | **Simulado diagnóstico** · apuração · commits — **ampliado: ver o plano final abaixo** | — |

**Total a partir de quarta: 6h45**, dentro do teto de 7h do orçamento semanal, porém sem folga. O plano original previa 5h; as 1h45 a mais são o custo dos dois dias de curso perdidos.

**Regra de transbordo.** Se a quarta ou a quinta não fecharem as 9 aulas do dia:

1. As aulas de shell script (objetivo 3.3) têm prioridade e **precisam estar vistas antes do Laboratório 1**. Se necessário, elas passam à frente das demais.
2. As aulas restantes das faixas 26 a 37 podem transbordar para **segunda 05/10**, primeiro dia da Semana 6, antes das aulas de permissões. Nunca para sexta, sábado ou domingo.
3. O Laboratório 2 e o simulado **não são cortados nem movidos**.

**Atualização de 30/09.** A quarta fechou **5 das 9 aulas** previstas (26 a 30). As 4 restantes (31 a 34) passaram para a quinta, que agora tem **13 aulas (31 a 43)**, cerca de 1h30 de vídeo mais o aquecimento. No pior caso a semana passa de 6h45 para cerca de 7h10, 10 minutos acima do teto. A folga vem de duas decisões: (a) subir para **2x** nas aulas que só repetem conteúdo já praticado, como a navegação de hoje, que o próprio caderno marca como "já tratado nos labs"; e (b) aplicar a regra de transbordo, em que o que não couber na quinta e não for de shell script vai para a segunda 05/10. Se na quinta à noite as aulas de shell script não estiverem vistas, o Laboratório 1 de sexta começa com 20 minutos de vídeo.

**Atualização de 02/10 (superada pela atualização final logo abaixo).** A quinta não teve estudo e o Laboratório 1 de sexta foi feito em parte: blocos 1 e 2 concluídos. Os blocos 3 a 5 (`if`, `for`, código de saída) passam para o **sábado, antes do Laboratório 2**, porque os quatro scripts dependem deles. O bloco 6 (`vi` e `nano`) e o exercício das frutas ficam para depois do Laboratório 2 ou até segunda 05/10. O sábado passa de cerca de 1h35 para cerca de 2h20. O simulado de domingo **continua em data fixa**.

**Atualização de 02/10, à noite — plano final da Semana 5.** O sábado deixa de ser obrigatório e o fechamento da semana passa inteiro para o **domingo 04/10**: terminar o Laboratório 1 e fazer o simulado de 40 questões. O Laboratório 2 e as aulas 31 a 43 do curso passam para a **Semana 6** (ver `labs/semana-06.md`).

| Dia | Atividade | Tempo |
|---|---|---|
| Sáb 03 | **Opcional.** Se houver tempo, adiantar a Semana 6 nesta ordem: (1) Laboratório 1, blocos 3 a 5, 20 min; (2) aulas de shell script do curso, a 1x; (3) aquecimento | até 1h |
| **Dom 04** | Aquecimento · **simulado #1** (60 min) · apuração (25 min) · pausa · Laboratório 1, blocos 3 a 6 e exercício das frutas (45 min) · registro (10 min) · commits (5 min) | cerca de 2h35 |

**Ordem do domingo e por quê.** O simulado vem **primeiro**, com a cabeça descansada: é diagnóstico e mede o que você sabe hoje, antes de terminar o Laboratório 1. Os blocos 3 a 5 vêm logo depois porque são pré-requisito do Laboratório 2 da Semana 6. Se o tempo apertar, o corte segue esta ordem: **exercício das frutas**, depois **bloco 6** (`vi` e `nano`). Os dois vão para segunda 05/10, 25 minutos no total. O simulado e os blocos 3 a 5 não são cortados.

**O que passa para a Semana 6**

| Item | Novo prazo |
|---|---|
| Curso, aulas 31 a 43 (13 aulas) | Segunda 05/10 |
| Laboratório 2 — os scripts `backup.sh`, `contar.sh` e `usuario.sh` (o `filtrar.sh` fica opcional) | Terça 06/10 |
| Voucher da prova e agendamento | Quarta 07/10, 10 minutos |
| Comparação de compressão com o `bzip2` | Terça 06/10, no aquecimento |
| Registro das observações sobre arquivos ocultos | Segunda 05/10, 10 minutos |
| Limpeza: `rm 'sudo apt upgrade -y'` | Segunda 05/10, 30 segundos |
| Autoavaliação da Semana 5 | **Sexta 09/10**, em versão reduzida de 10 questões, três dias depois do Laboratório 2 |
| Exercício das frutas e bloco 6, **se cortados no domingo** | Segunda 05/10 |

**Novidade a partir desta semana: simulado geral todo domingo.** O simulado de 04/10 é o primeiro de uma série semanal. O calendário completo, as metas por simulado e a regra de adiamento da prova estão no plano geral, seções 7 e 11.

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
git add . && git commit -m "docs: semana 5 - sessao N" && git push
sudo poweroff
```

---

## Aquecimento diário — todos os dias até domingo

Dez minutos, de memória, digitando, na VM. Os cinco comandos saem dos erros das questões 7, 11, 13 e 14 da autoavaliação da Semana 4. Execute; não leia.

Preparação uma única vez (o `lab4` foi removido na limpeza da Semana 4):

```bash
cd ~ && mkdir -p lab5 && cd lab5

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
```

Os cinco comandos:

```bash
grep -v '^#' /etc/ssh/sshd_config | grep -v '^$'
printf '100\n25\n3\n9\n' | sort ; printf '100\n25\n3\n9\n' | sort -n
grep -c ERROR sistema.log ; grep -o ERROR sistema.log | wc -l
grep '^[AB]' funcionarios.csv ; grep '[^0-9]' funcionarios.csv
grep -E 'ERROR|WARN' sistema.log
```

**Rodízio.** Na quinta e no sábado, troque o quinto item pelo teste do `-f` do `tar`, que ataca a Correção 52. Rode dentro de `lab5`, onde o resíduo não atrapalha:

```bash
mkdir -p t && echo x > t/a.txt
tar -cvf certo.tar t/        # -f por último: cria certo.tar
tar -cfv errado.tar t/       # -f antes do v: o tar usa "v" como nome do arquivo
ls -l certo.tar v errado.tar 2>&1
rm -f v certo.tar errado.tar
```

**Item pendente da Semana 4**, uma única vez, no aquecimento de quarta: refazer a comparação de compressão agora que o `bzip2` existe.

```bash
seq 1 5000 > exemplo.log
tar -czf ex.tar.gz exemplo.log ; echo $?
tar -cjf ex.tar.bz2 exemplo.log ; echo $?
tar -cJf ex.tar.xz exemplo.log ; echo $?
ls -lh ex.tar.*
```

Os três `echo $?` precisam ser `0`, e os tamanhos precisam obedecer à regra **quanto mais lento, mais comprime**: `gzip` maior, `bzip2` no meio, `xz` menor.

---

## Curso — Matheus Muller

Posição atual (30/09): **checkpoint na aula 31**, com as aulas 26 a 30 assistidas. Restam 42 aulas (31 a 72); esta semana fecha mais 13 (31 a 43).

| Dia | Aulas | Velocidade | Tempo estimado |
|---|---|---|---|
| Qua 30/09 | 26 a 30 (5 aulas) — **concluídas** | 1.5x | — |
| Qui 01/10 | 31 a 43 (13 aulas) | 1.5x; **2x** nas que repetem conteúdo já praticado; **1x** nas de shell script | cerca de 1h30 |

Regras do curso:

- Ao chegar nas aulas de shell script (3.3), reduza para **1x**. O vídeo entrega o modelo mental que o laboratório de sexta transforma em prática.
- Anote no caderno **só o que o vídeo mostra e você ainda não sabia**. O que já foi praticado, o vídeo confirma e não ensina.
- Se o número exato das aulas de shell script não cair na faixa 35 a 43, ajuste a divisão entre quarta e quinta, mas mantenha a regra: o 3.3 vem visto **antes** da sexta.
- Aulas que só repetem o que já foi praticado (navegação, `ls`, variáveis de ambiente, comandos do Tópico 1) podem ir a **2x**. O critério é o seu próprio caderno: se ele já registra o assunto como "tratado nos labs", o vídeo é confirmação.
- Registre a aula em que parou ao fim de cada dia, na seção de registro abaixo.

---

## Laboratório 1 — Sexta 02/10 — Fundamentos de shell script

Sem vídeo dentro da sessão. 45 minutos de teclado, 10 de registro, 5 de commit.

### Blocos

**1. Primeiro script, shebang e execução (10 min)**

```bash
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

O que fixar: `#!` precisa ser os **dois primeiros caracteres** do arquivo; `./script` exige permissão `x` e usa o interpretador do shebang; `bash script` não exige `x`; a extensão `.sh` é convenção e não altera a execução.

**2. Variáveis e argumentos (10 min)**

```bash
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

Pontos de atenção: **sem espaço** ao redor do `=` na atribuição (`nome=Davi`, nunca `nome = Davi`); `$1` a `$9` são argumentos posicionais; `$#` é a quantidade; `$@` é a lista; `$0` é o nome do script. Aspas duplas expandem variáveis, aspas simples não.

**3. Decisões com `if` (10 min)**

```bash
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

| Operador | Compara |
|---|---|
| `-eq` `-ne` | igual, diferente (números) |
| `-lt` `-le` | menor, menor ou igual (números) |
| `-gt` `-ge` | maior, maior ou igual (números) |
| `=` ou `==` | igualdade de **texto** |
| `-f` `-d` | arquivo comum existe, diretório existe |
| `-z` | texto vazio |

O erro mais comum: `[ $1 -gt $2 ]` sem espaços internos, ou `[$1 -gt $2]`. Os espaços entre os colchetes e os operandos são **obrigatórios**, porque `[` é um comando, não uma sintaxe.

**4. Loops com `for` (5 min)**

```bash
for i in 1 2 3; do echo "volta $i"; done
for i in $(seq 1 5); do echo "n=$i"; done
for arq in /etc/*.conf; do echo "$arq"; done | head -3
```

**5. Código de saída (5 min)**

```bash
ls /etc > /dev/null ; echo $?        # 0
ls /naoexiste 2> /dev/null ; echo $? # diferente de 0
grep -q root /etc/passwd && echo "achou" || echo "nao achou"
```

O `$?` guarda o código do **último** comando: `0` é sucesso, qualquer outro valor é falha. O `exit N` define o código do próprio script. `&&` executa o segundo comando só se o primeiro der `0`; `||` só se der diferente de `0`. Regra 3 do plano: **saída na tela não é prova de sucesso**, então confira o `$?`.

**6. Editores `vi` e `nano` (10 min) — objetivo oficial**

```bash
nano ola.sh          # digite direto; Ctrl+O grava, Ctrl+X sai
vi ola.sh
```

No `vi`, memorize os três modos e as teclas de transição:

| De | Para | Tecla |
|---|---|---|
| Navegação (padrão ao abrir) | Inserção | `i` |
| Inserção | Navegação | `Esc` |
| Navegação | Comando | `:` |

No modo de comando: `:w` grava, `:q` sai, `:wq` grava e sai, `:q!` sai sem gravar. No `nano` não há modos; os atalhos aparecem no rodapé, com `^` significando `Ctrl` (`^O` grava, `^X` sai). Saia dos dois editores três vezes cada, sem consultar.

### Exercício de fixação — do material oficial

O LPI Learning Material (objetivo 3.3, Exercícios Guiados, script `guided1.sh` das frutas) traz um script com **vários erros de sintaxe** para corrigir. Digite-o exatamente como está, rode, leia cada mensagem de erro inteira e corrija um por vez. Só depois compare com as respostas. O exercício cobre exatamente os três pontos do início do documento: espaços na atribuição, espaços dentro de `[ ]` e aspas simples que impedem a expansão.

### Registro

Anote no caderno o comando, o que faz e o exemplo executado. Os erros e suas correções seguem a numeração global, a partir da **Correção 53**.

---

## Laboratório 2 — Terça 06/10 (Semana 6) — Os scripts

> **Transferido em 02/10 para a Semana 6.** Pré-requisito: Laboratório 1, blocos 3 a 5, feitos no domingo 04/10. Os três primeiros scripts são obrigatórios, porque exercitam exatamente o que a prova cobra: argumento, variável, `for`, `if` e código de saída. O `filtrar.sh` usa `while read`, que não consta na lista oficial, e passa a ser **opcional**.

Escreva em `~/lab5/scripts`, **um por vez**, testando cada um antes de passar ao seguinte. Ao terminar cada teste, rode `echo $?`.

| # | Script | Exercita |
|---|---|---|
| 1 | Backup com a data no nome | Substituição de comando, `tar`, variáveis, argumento |
| 2 | Contar arquivos por extensão | `for`, `find`, `wc`, pipeline dentro de script |
| 3 | Verificar se um usuário existe | `if`, `grep -q`, `$?`, `exit` com código |
| 4 | Ler um arquivo linha a linha e filtrar | `while read`, redirecionamento de entrada |

**Especificações**

1. `backup.sh <diretorio>` cria `backup-AAAA-MM-DD.tar.gz` no diretório atual. Sem argumento, imprime o uso e sai com código 1. Ao final imprime o nome do arquivo criado.
2. `contar.sh <diretorio>` imprime, para `txt`, `log` e `conf`, quantos arquivos com cada extensão existem abaixo do diretório, no formato `txt: 3`.
3. `usuario.sh <nome>` sai com **0** se o usuário existe em `/etc/passwd`, **1** se não existe e **2** se faltar o argumento. Sempre imprime uma frase dizendo o que encontrou.
4. `filtrar.sh <arquivo> <palavra>` lê o arquivo linha a linha e imprime só as linhas que contêm a palavra, numeradas.

**Testes de aceitação**

```bash
# 1
./backup.sh ~/lab5 ; echo $? ; ls -lh backup-*.tar.gz ; tar -tzf backup-*.tar.gz | head -3
./backup.sh ; echo $?                       # uso e código 1

# 2
./contar.sh /etc

# 3
./usuario.sh davi ; echo $?                 # 0
./usuario.sh fantasma ; echo $?             # 1
./usuario.sh ; echo $?                      # 2

# 4
./filtrar.sh ~/lab5/sistema.log ERROR
```

**Armadilhas conhecidas**

- Script 1: separe a variável do texto vizinho com chaves, `${data}`, e coloque as variáveis entre aspas duplas. Um diretório com espaço no nome quebra o `tar` sem aspas.
- Script 2: no `find`, as aspas em `"*.$ext"` impedem o shell de expandir o asterisco antes de o `find` recebê-lo. É a mesma lógica da Semana 4.
- Script 3: `grep -q "^$1:"` evita que `davi` case com `davidson`. O `-q` não imprime nada, e o resultado vem só pelo código de saída.
- Script 4: `while IFS= read -r linha; do ... done < "$1"`. O redirecionamento de entrada fica **depois** do `done`.

<details>
<summary>Soluções de referência — só depois de tentar</summary>

```bash
# backup.sh
#!/bin/bash
# Uso: ./backup.sh <diretorio>
if [ $# -ne 1 ]
then
  echo "Uso: $0 <diretorio>"
  exit 1
fi
data=$(date +%Y-%m-%d)
destino="backup-${data}.tar.gz"
tar -czf "$destino" "$1"
echo "Backup criado: $destino"
```

```bash
# contar.sh
#!/bin/bash
# Uso: ./contar.sh <diretorio>
for ext in txt log conf
do
  total=$(find "$1" -type f -name "*.$ext" 2>/dev/null | wc -l)
  echo "$ext: $total"
done
```

```bash
# usuario.sh
#!/bin/bash
# Uso: ./usuario.sh <nome>
if [ $# -ne 1 ]
then
  echo "Uso: $0 <nome>"
  exit 2
fi
if grep -q "^$1:" /etc/passwd
then
  echo "O usuario $1 existe"
  exit 0
else
  echo "O usuario $1 nao existe"
  exit 1
fi
```

```bash
# filtrar.sh
#!/bin/bash
# Uso: ./filtrar.sh <arquivo> <palavra>
n=0
while IFS= read -r linha
do
  n=$((n + 1))
  if echo "$linha" | grep -q "$2"
  then
    echo "$n: $linha"
  fi
done < "$1"
```

Há mais de uma resposta certa para quase todos. Se a sua chegou ao mesmo resultado por outro caminho, está correta.

</details>

**Depois dos quatro scripts:** uma leitura crítica de dois minutos por script. Cada variável está entre aspas? Cada `[ ]` tem espaços? O código de saída é o que a especificação pede?

---

## Simulado diagnóstico — Domingo 04/10

Esta é a pendência mais antiga do plano. Ela ocupa o lugar de uma prática porque **é** prática, e o resultado determina no que as práticas das Semanas 6 e 7 devem insistir.

**Este é o simulado #1 da série dominical.** A partir de agora há um simulado geral de 40 questões todo domingo. Em 04/10 ele é feito **antes** de terminar o Laboratório 1, para medir o que você sabe hoje. As metas dos próximos estão no plano geral, seção 7.

| Item | Valor |
|---|---|
| Arquivo | `praticas/simulado-01-diagnostico.md` |
| Questões e tempo | 40 questões, 60 minutos, cronometrado |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet |
| Corte do exame real | 500 de 800, cerca de 65%, ou **26 acertos** |
| Expectativa | Entre 60% e 75% (24 a 30 acertos) |
| Onde | Fora da VM, em papel ou em um arquivo separado |

**Como aplicar**

1. Cronometre 60 minutos e responda tudo, com o gabarito fechado.
2. Marque **cada questão em que chutou**, mesmo acertando.
3. Só depois abra o gabarito, confira e preencha a apuração no arquivo do simulado.
4. Passe o resultado para a tabela abaixo e liste os erros **por objetivo**, não por questão.

**Questões que retestam correções já registradas.** Aqui o simulado mede se o que foi corrigido ficou:

| Questão | Retesta |
|---|---|
| 18 | Correção 29 — a ordem em `> arquivo 2>&1` |
| 20 | Correções 33, 34 e 50 — `-k` escolhe a coluna do `sort` |
| 21 | Correção 36 — `uniq -u` mostra só o que nunca se repetiu |
| 22 | Correção 52 — `-f` do `tar` por último |
| 24 | Regex versus globbing — o `*` |

Se errar qualquer uma dessas cinco, o card do Notion correspondente volta para a fila do aquecimento.

**Tabela de resultado**

| Tópico | Peso | Questões | Acertos | Chutes acertados |
|---|---|---|---|---|
| 1. Comunidade e open source | 7 | 1 a 7 | | |
| 2. Encontrando seu caminho | 9 | 8 a 16 | | |
| 3. Poder da linha de comando | 9 | 17 a 25 | | |
| 4. Sistema operacional | 8 | 26 a 33 | | |
| 5. Segurança e permissões | 7 | 34 a 40 | | |
| **Total** | **40** | | | |

**Como ler o resultado**

- **Erros concentrados nos Tópicos 4 e 5**, ainda não estudados: é o esperado, e o plano está funcionando. As Semanas 6 e 7 endereçam esses tópicos.
- **Erros nos Tópicos 1, 2 ou 3**, que estão fechados: as autoavaliações mediram o que acabou de ser estudado, não o que ficou. Sinal para revisar antes de avançar, e as práticas das Semanas 6 e 7 passam a incluir esses objetivos.
- **Chutes acertados** contam como erro para efeito de estudo. A coluna existe para isso.
- **Abaixo de 24 acertos (60%)**: a Fase 1 precisa de uma sessão de revisão adicional na Semana 7, e o gate da Semana 9 é revisitado.

Depois do simulado, o resultado é registrado em `praticas/` e no plano geral.

---

## Pendências e fila de dívidas

| Item | Origem | Estado | Prazo |
|---|---|---|---|
| Curso, aulas 26 a 30 | Semana 5, terça 29/09 | **Pago em 30/09** | Concluído |
| Curso, aulas 31 a 43 | Semana 5, quarta 30/09 | Em aberto: sem registro de avanço desde o checkpoint da aula 31 | **Transferido para a Semana 6: segunda 05/10** |
| Laboratório 1, blocos 3 a 5 (`if`, `for`, código de saída) | Semana 5, sexta 02/10 | Em aberto; blocos 1 e 2 concluídos | **Dom 04/10**, depois do simulado (sábado, se houver tempo) |
| Laboratório 1, bloco 6 (`vi` e `nano`) | Semana 5, sexta 02/10 | Em aberto | Dom 04/10; se cortado, seg 05/10 |
| Exercício do script das frutas (material do LPI) | Semana 5, sexta 02/10 | Em aberto | Dom 04/10; se cortado, seg 05/10 |
| Laboratório 2 (`backup.sh`, `contar.sh`, `usuario.sh`; `filtrar.sh` opcional) | Semana 5, sábado 03/10 | **Transferido para a Semana 6** | Ter 06/10 |
| Voucher da prova e agendamento para 09/11 | Semana 5 | Em aberto, já adiado duas vezes | **Qua 07/10** |
| Simulado diagnóstico (simulado #1) | Semana 3 | Em aberto, 4 semanas de atraso | Dom 04/10, **primeira atividade do dia** |
| Reteste das 4 questões erradas da autoavaliação da Semana 4 | Semana 4 | No aquecimento diário | Até dom 04/10 |
| Comparação de compressão com o `bzip2` instalado | Semana 4 | `bzip2` instalado; falta refazer | Ter 06/10, no aquecimento |
| Registro das observações sobre arquivos ocultos | Semana 3 | Em aberto, adiado outra vez | Seg 05/10, 10 minutos |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | Semana 3 | Em aberto | Seg 05/10, 30 segundos |
| Autoavaliação da Semana 5 | Semana 5 | Reduzida a 10 questões; elaborada na quinta 08/10 | Sex 09/10 |
| `.wslconfig` limitando o WSL2 a 3 GB | Semana 0 | Sem prazo | Quando houver folga |
| Teste de restauração do snapshot | Semana 0 | Sem prazo | Quando houver folga |

---

## Registro do curso

Preencha ao fim de cada dia.

| Data | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|
| 30/09 | 26 a 30 (5 aulas) | **31 (checkpoint)** | `ls` e opções, `echo`, `$PATH`, `whoami`, `su`, `runlevel`, `init`, `uname`, navegação. Detalhe abaixo |
| 01/10 | | | |

### Registro do curso — 30/09 — aulas 26 a 30 (checkpoint na aula 31)

Conteúdo: `ls`, `echo` e `$PATH`, identidade e troca de usuário, níveis de execução, `uname` e navegação. A navegação já havia sido praticada nos laboratórios das Semanas 2 e 3, e o próprio caderno registra isso; o vídeo confirma. As anotações abaixo já estão **corrigidas**, e cada ajuste é explicado na seção de correções logo adiante.

**O comando `ls`**

| Opção | Origem | Função |
|---|---|---|
| `ls` | *list* | Lista arquivos e diretórios do diretório atual ou do informado |
| `-a` | *all* | Inclui os ocultos (nomes que começam com `.`), além das entradas `.` e `..` |
| `-l` | *long* | Formato longo, com permissões, dono, tamanho e data. Combina com o `-a`: `ls -la` |
| `-S` | *size* | Ordena por tamanho, do maior para o menor |
| `-r` | *reverse* | Inverte a ordem. `ls -lSr` vai do menor para o maior |
| `-R` | *recursive* | Desce por todos os subdiretórios. `ls -Rl` |
| `-h` | *human-readable* | Tamanhos em K, M e G. **Só tem efeito visível junto com `-l`**: `ls -lh` |

`ls -lSar` combina cinco opções: formato longo, por tamanho, incluindo ocultos, do menor para o maior.

**`echo` e a variável `$PATH`**

- O `echo` exibe uma string e também o conteúdo de variáveis: `echo $PATH`.
- O `$PATH` é a **lista de diretórios, separados por `:`, onde o shell procura o programa do comando digitado**. A busca vai da esquerda para a direita e **vale o primeiro que for encontrado**. Por isso a ordem muda qual `ls` é executado.
- `which ls` mostra qual arquivo o shell escolheu.

```bash
export PATH=$PATH:/opt        # acrescenta /opt ao final: é procurado por último
```

Prática resolvida: adicionar o `/opt` ao `$PATH` com `export PATH=$PATH:/opt`. Está correto.

**Identidade e troca de usuário**

| Comando | Função |
|---|---|
| `whoami` | Pergunta ao sistema quem é o usuário efetivo do processo |
| `echo $USER` e `echo $LOGNAME` | Variáveis de ambiente com o nome do usuário, definidas no login |
| `su usuario` | *Substitute user*: abre um shell como outro usuário, mantendo em boa parte o ambiente atual |
| `su - usuario` | O mesmo, mas como **shell de login**: carrega o ambiente completo do usuário e vai para o home dele |
| `su` (sem nome) | Troca para o `root` |

Na Ubuntu a conta `root` vem, por padrão, sem senha definida. Por isso `su -` sozinho falha com *Authentication failure*; o caminho é `sudo -i` ou `sudo su -`.

**Níveis de execução (runlevels)**

| Nível | Significado clássico (SysV) |
|---|---|
| 0 | Desligar |
| 1 | Modo monousuário (manutenção) |
| 2 a 4 | Multiusuário, sem interface gráfica (o 3 é o mais citado) |
| 5 | Multiusuário com interface gráfica |
| 6 | Reiniciar |

- `runlevel` imprime **dois valores**: o nível anterior e o atual. `N 5` quer dizer "sem nível anterior, atualmente 5".
- `init 0` desliga e `init 6` reinicia. Pede `sudo`, e na VM `init 0` encerra a máquina.
- O conceito é do *SysV init*. O systemd usa **targets**: `graphical.target` corresponde ao 5 e `multi-user.target` ao 3.

**`uname`**

| Opção | Mostra |
|---|---|
| `uname` | O nome do kernel: `Linux` |
| `-r` | *Release*: a versão do kernel em uso |
| `-v` | A versão de compilação do kernel, com o número da build e a data |
| `-m` | O nome da arquitetura da máquina, como `x86_64` |
| `-o` | O sistema operacional: `GNU/Linux` |
| `-a` | Todos os campos: kernel, **nome da máquina**, release, versão, arquitetura e sistema operacional |
| `--help` | A lista de opções |

Práticas resolvidas: `uname -r` devolveu `7.0.0-30-generic` e `uname -m` devolveu `x86_64`. Ambos estão corretos. O `7.0.0` é a versão do kernel, o `30` a revisão da distribuição e o `generic` o tipo de kernel.

**Navegação**

| Comando | Função |
|---|---|
| `pwd` | Mostra o diretório atual (*print working directory*) |
| `cd` | *Change directory* |
| `.` | O diretório atual |
| `..` | O diretório **pai**, um nível acima na árvore |
| `cd` sem argumento, ou `cd ~` | O diretório pessoal do usuário, como `/home/davi` |
| `cd -` | O diretório **anterior**, aquele em que você estava antes |

Práticas resolvidas: `cd /var/log`, `cd`, `cd -` e `cd ~`. Todas corretas.

### Correções desta sessão

**Correção 53 — `..` é o diretório pai, não o "anterior". Quarta ocorrência.**

A anotação diz "`..` → diretório anterior na árvore". O complemento "na árvore" mostra que a ideia está certa, mas a palavra **anterior** é justamente a que o plano reserva para outro comando:

| Símbolo | Nome certo | Em que se baseia |
|---|---|---|
| `..` | **Pai** | Hierarquia: um nível acima |
| `cd -` | **Anterior** | Histórico: onde eu estava antes |
| `.` | Atual | O ponto em que estou |

Partindo de `/var/log`, `cd ..` leva a `/var`, e `cd -` leva ao diretório em que você estava **antes** de entrar em `/var/log`, que pode ser qualquer um. O plano já registrava três ocorrências deste erro. A regra a fixar: **"anterior" só existe para o `cd -`; para o `..` a palavra é "pai"**.

**Correção 54 — `~` e `cd` sem argumento levam ao diretório pessoal, não a `/home`.**

A anotação diz "`~` ou `cd` → /home". O `/home` é o diretório que **contém** os diretórios pessoais de todos os usuários. O destino do `~` é o do usuário atual:

| Usuário | `~` e `cd` levam a |
|---|---|
| `davi` | `/home/davi` |
| `root` | `/root` |

A variável `$HOME` guarda o mesmo caminho. `cd /home` leva ao diretório pai de todos os homes, que é outro lugar.

**Correção 55 — a variável é `$PWD`, em maiúsculas, e o `cd -` depende do `$OLDPWD`.**

A anotação diz que o `pwd` "busca na variável `$pwd`". O Linux diferencia maiúsculas de minúsculas, então `$pwd` é **outra variável, inexistente e vazia**. A certa é `$PWD`, que o bash atualiza a cada `cd`. Existe um par:

| Variável | Guarda |
|---|---|
| `$PWD` | O diretório atual |
| `$OLDPWD` | O diretório em que você estava antes |

É o `$OLDPWD` que torna o `cd -` possível: o comando apenas troca os dois valores. É o mesmo cuidado com o `$SHELL` e o `$0` da Correção 38: a variável guarda um estado que o próprio shell mantém.

**Correção 56 — `uname -a` não traz a distribuição, e o `-o` também não.**

Três ajustes na lista do `uname`:

- **`-a`:** a anotação diz "kernel, versão da distribuição, data da build e arquitetura". O `uname` **não conhece a distribuição**. Entre os campos do `-a` está o **nome da máquina** (*hostname*), que a anotação não cita.
- **`-o`:** mostra `GNU/Linux`. Isso diz que o sistema operacional é Linux, **não qual distribuição**. Para saber o nome e a versão da distribuição, o arquivo é `/etc/os-release`. A questão 27 do simulado de domingo cobra exatamente isso.
- **`-v` e `-m`:** o `-v` não é só "data da build": é a versão de compilação, que **contém** o número da build e a data. O `-m` não responde "32 ou 64 bits", e sim o **nome** da arquitetura (`x86_64`, `aarch64`, `i686`); o número de bits se deduz do nome.

**Correção 57 — o `$PATH` não "armazena" comandos: é uma lista de onde procurar.**

Três pontos:

1. Os executáveis ficam nos diretórios. O `$PATH` guarda **apenas os nomes desses diretórios**.
2. A ordem importa e o primeiro encontrado vence. `PATH=$PATH:/opt` coloca o `/opt` por último; `PATH=/opt:$PATH` o coloca primeiro, e um programa de nome igual ao de um comando do sistema passaria a ser executado no lugar dele.
3. A alteração com `export` vale **só para a sessão atual**. Ao sair e entrar de novo, volta ao original. Para tornar permanente, a linha vai no `~/.bashrc`.

Há uma armadilha de prova: escrever `PATH=/opt` **sem** o `$PATH` apaga a lista inteira, e o shell passa a responder `command not found` até para o `ls`. A forma de acrescentar sem apagar é sempre `PATH=$PATH:novo`. O mesmo mecanismo explica por que scripts rodam com `./script.sh`: o diretório atual não está no `$PATH`. Isso volta no Laboratório 1.

**Correção 58 — o `runlevel` mostra o anterior e o atual, e o nível não é alterado por "comandos de desligamento".**

A anotação diz que o nível "é alterado por comandos de desligamento ou reinicialização". É uma simplificação que mistura duas coisas. O que acontece é o inverso: desligar e reiniciar **são** níveis (0 e 6), e quem muda de nível é o `init N` (ou `telinit N`). Em sistemas com systemd o equivalente é trocar o *target*, e o `runlevel` existe por compatibilidade. Para ver o que a sua VM usa, rode `systemctl get-default`.

**Correção 59 — `whoami` e `$USER` respondem a mesma pergunta por fontes diferentes.**

As três formas aparecem como equivalentes na anotação. Em uso normal devolvem o mesmo nome, mas a origem muda:

| Forma | De onde vem |
|---|---|
| `whoami` | Consulta o sistema: o usuário efetivo do processo naquele instante |
| `$USER` e `$LOGNAME` | Variáveis de ambiente, definidas no login e herdadas pelos processos filhos |

Quando um shell troca de usuário com `su` sem o `-`, as variáveis de ambiente podem continuar com o valor antigo, e aí os dois divergem. A fonte confiável é o `whoami`. É o mesmo princípio da Correção 38: a variável é herança do login, e o comando consulta o estado atual.

### Para executar na VM — 3 minutos

Conceito que resiste a leitura cede a uma execução (Correção 50). Rode e compare com o que está escrito acima:

```bash
echo $PWD ; pwd ; echo "[$pwd]"            # o último sai vazio: $pwd minúsculo não existe
cd /var/log ; echo $OLDPWD ; cd - ; pwd    # o cd - usa o OLDPWD
cd /home ; pwd ; cd ; pwd                  # /home não é o mesmo que o ~
echo $PATH | tr ':' '\n'                   # um diretório por linha
which ls ; ls -ld /bin                     # em geral /usr/bin/ls, com /bin como link
uname -a ; uname -o ; uname -v
head -3 /etc/os-release                    # a distribuição está aqui, não no uname
whoami ; echo $USER $LOGNAME
runlevel ; systemctl get-default
```

Duas verificações específicas da sua máquina: o resultado do `which ls` (a anotação traz `/bin/ls`, que é o caminho do vídeo; na Ubuntu Server recente o provável é `/usr/bin/ls`) e se o `runlevel` responde `N 5` ou `N 3`.

---

## Registro das sessões

### Laboratório 1 — sexta 02/10 — Fundamentos de shell script — PARCIAL (blocos 1 e 2)

| Bloco | Situação |
|---|---|
| 1. Primeiro script, shebang e execução | Concluído, com anotações |
| 2. Variáveis e argumentos | Concluído, com anotações |
| 3. Decisões com `if` | **Pendente** |
| 4. Loops com `for` | **Pendente** |
| 5. Código de saída | **Pendente** |
| 6. Editores `vi` e `nano` | **Pendente** |
| Exercício do script das frutas (material do LPI) | **Pendente** |

As anotações cobrem apenas os blocos 1 e 2. Os blocos 3 a 6 e o exercício não trazem anotação própria e foram tratados como não realizados. Se algum deles chegou a ser executado na VM, é só avisar e o registro é ajustado.

O que está registrado a seguir já está **corrigido**, e o ajuste é explicado na Correção 60 e nas observações.

#### Bloco 1 — Primeiro script, shebang e execução

**Vocabulário**

| Termo | Definição |
|---|---|
| Shell | O programa que interpreta os comandos digitados |
| `bash` | Um shell, o *Bourne Again Shell*, padrão na maioria das distribuições |
| Shell script | Um arquivo de texto com comandos para um shell executar. Além de comandos em sequência, aceita variáveis, condições e laços |
| Interpretador | O programa que lê e executa as instruções do script. No caso, o `bash` |

**O primeiro script, sem shebang**

```bash
echo 'echo "Hello World!"' > primeiro
```

| Parte | O que faz |
|---|---|
| `echo` externo | Escreve o texto que vem entre as aspas simples |
| Texto entre aspas simples | `echo "Hello World!"`. O `echo` interno **não é executado agora**: é só conteúdo |
| `>` | Direciona esse texto para o arquivo `primeiro`, que passa a conter a linha `echo "Hello World!"` |

Sequência observada:

```
./primeiro              Permission denied
ls -l primeiro          -rw-rw-r-- 1 davi davi 19 Oct  2 13:06 primeiro
chmod +x primeiro
./primeiro              Hello World
```

| Comando | Função |
|---|---|
| `ls -l primeiro` | Inspeciona o arquivo. Não há o `x` em nenhuma das três posições |
| `chmod +x primeiro` | `chmod` altera o modo (as permissões); `+x` acrescenta a de execução |

**Por que o primeiro script funcionou sem shebang.** O arquivo não é um binário nem traz `#!`. Quando o `bash` tenta executá-lo e o sistema recusa o formato, o próprio `bash` tenta interpretá-lo como script de shell. Funciona porque quem chamou foi um `bash`; a falta do shebang deixa o resultado **dependente de quem executa**. O shebang torna explícito qual interpretador usar.

**O segundo script, com shebang**

```bash
which bash                      # /usr/bin/bash
cat > ola.sh << 'EOF'
#!/bin/bash
# Primeiro script com shebang e comentario.
echo "Hello World!"
EOF
```

| Linha | Papel |
|---|---|
| `#!/bin/bash` | O shebang: diz qual interpretador executa o arquivo quando ele é chamado com `./ola.sh`. Precisa ser a **primeira linha**, sem espaço, comentário ou linha vazia antes |
| `# Primeiro script...` | Comentário, ignorado pelo interpretador |
| `echo "Hello World!"` | O comando em si |

| Parte do `cat > ola.sh << 'EOF'` | Função |
|---|---|
| `cat` | Lê o texto recebido e o escreve na saída |
| `> ola.sh` | Direciona essa saída para o arquivo |
| `<< 'EOF'` | Abre um *here-document*: o bloco de texto até a linha `EOF` vira a entrada do `cat` |

**Duas formas de executar**

| Forma | Exige `x`? | Quem escolhe o interpretador |
|---|---|---|
| `./ola.sh` | **Sim** | O shebang |
| `bash ola.sh` | Não, só precisa de permissão de leitura | Você, ao digitar `bash` |

Teste registrado, com o resultado correto:

```bash
chmod -x ola.sh
./ola.sh          # Permission denied
bash ola.sh       # continua funcionando
```

A extensão `.sh` é convenção e ajuda a reconhecer scripts; não altera a execução.

#### Bloco 2 — Variáveis e argumentos

```bash
./saudacao.sh Davi Morais
```

| Elemento | Valor neste exemplo |
|---|---|
| `$0` | `./saudacao.sh` |
| `$1` | `Davi` |
| `$2` | `Morais` |
| `$#` | `2` |
| `$@` | A lista dos argumentos: `Davi Morais` |

Resultados registrados e conferidos:

| Chamada | Saída |
|---|---|
| `./saudacao.sh Davi` | `Ola, Davi!` · `Script: ./saudacao.sh` · `Total de argumentos: 1` · `Todos: Davi` |
| `./saudacao.sh Davi Morais` | `Ola, Davi!` · `Total de argumentos: 2` · `Todos: Davi Morais` |
| `./saudacao.sh "Davi Morais"` | `$1` passa a valer `Davi Morais`, **1 argumento** |
| `./saudacao.sh` | `Ola, !` · `Total de argumentos: 0` · `Todos:` |

- `nome=$1` copia o primeiro argumento para a variável `nome`.
- A saudação usa só o `$1`, por isso o `Morais` não aparece. Para o nome completo, as aspas agrupam as duas palavras em um único argumento.
- **Aspas duplas** expandem variáveis e preservam espaços; **aspas simples** mantêm o texto literal:

```bash
nome=Davi
echo "Ola, $nome!"     # Ola, Davi!
echo 'Ola, $nome!'     # Ola, $nome!
```

#### Correção 60 — o `./` e o `Permission denied` têm causas diferentes

A anotação diz: "o `./` é usado porque o shell procura comandos nos diretórios do `PATH`, e a pasta atual não faz parte dessa lista, **ou seja**, o arquivo não tem permissão de execução (permission denied)". A primeira metade está certa. O "ou seja" liga duas coisas que não têm relação de causa:

| Fato | Explicação |
|---|---|
| O `./` é necessário | O diretório atual não está no `$PATH`. Sem o `./`, o shell procura só nos diretórios do `$PATH` e responde **`command not found`** |
| O `Permission denied` | O arquivo não tem o bit `x`. O erro vem **depois** de o shell já ter achado o arquivo |

O `./primeiro` informa o caminho explicitamente, então o shell **não consulta o `$PATH`**. Ele encontra o arquivo e só então descobre que não pode executá-lo. Os dois erros dizem coisas diferentes:

| Comando | Resultado | Significa |
|---|---|---|
| `primeiro` | `command not found` | O shell não achou nada com esse nome no `$PATH` |
| `./primeiro` sem `x` | `Permission denied` | O arquivo foi achado, mas não é executável |
| `./primeiro` com `x` | `Hello World` | Funcionou |

É a mesma lógica da Correção 57, agora aplicada a um caso real.

#### Observações (sem número)

- **O tamanho do arquivo.** O `ls -l` mostrou 19 bytes. O conteúdo esperado, `echo "Hello World!"` mais o fim de linha, ocupa **20 bytes**: 19 caracteres e 1 newline. Um byte a menos sugere uma diferença de um caractere no texto, provavelmente o `!`, e as anotações da execução trazem `Hello World` sem ele. Se foi só abreviação nas anotações, nada a corrigir; para confirmar, `cat primeiro`. É a Regra de bolso 2: leia o arquivo de volta.
- **O `'EOF'` entre aspas importa neste laboratório.** As aspas simples impedem o shell de expandir `$` dentro do bloco. O `saudacao.sh` tem `$1`, `$0` e `$#`: sem as aspas, o shell trocaria cada um pelo valor atual (vazio) **antes de gravar o arquivo**, e o script nasceria quebrado.
- **O `bash ola.sh` ignora o shebang.** Dentro desse comando, a linha `#!/bin/bash` é apenas um comentário. Vale o interpretador que você digitou.
- **O `+x` sem indicar a quem vale para todos:** dono, grupo e outros. Para só o dono seria `u+x`. As classes `u`, `g` e `o` voltam na Semana 6.
- **Permissão `rw-rw-r--`.** É o que a Ubuntu cria por padrão para arquivos novos, resultado da `umask` 002. A questão 40 do simulado de domingo parte de `rw-r--r--`, resultado de uma `umask` de 022. O mecanismo é o mesmo, e a `umask` é conteúdo da Semana 6.
- **Aspas curvas no caderno.** A anotação traz `“Davi Morais”` com aspas curvas, que editores de texto e o Notion inserem sozinhos. **No terminal elas não funcionam como aspas:** o shell as trata como texto comum. Ao copiar do caderno para a VM, use as aspas retas `"`.
- **Variável vazia some em silêncio.** No `./saudacao.sh` sem argumento o `$1` vale vazio e o `echo` imprime `Ola, !`, sem erro. Isso prepara o bloco 3: dentro de `[ ]`, uma variável vazia sem aspas desaparece e o `[` fica sem operando, o que gera erro de sintaxe.
- **Grafia.** `chmood` e `basg` nas anotações: o certo é `chmod` e `bash`.
- **O shebang e o `which`.** O `which bash` devolveu `/usr/bin/bash` e o shebang do roteiro é `/bin/bash`. Na Ubuntu recente o `/bin` é um link para `/usr/bin`, então os dois funcionam. A prova trabalha com `/bin/bash`.

#### O que aprendi

- **Shell script:** um arquivo de texto com comandos para um shell executar.
- **O shebang:** a primeira linha, `#!/bin/bash`, define qual interpretador executa o arquivo quando ele é chamado diretamente.
- **`./script` e `bash script`:** o primeiro exige `x` e usa o shebang; o segundo não exige `x` e usa o interpretador digitado.
- **`./` versus `Permission denied`:** o `./` evita o `$PATH`; o `Permission denied` vem da falta do `x`.
- **Argumentos:** `$0` é o script, `$1` a `$9` são os posicionais, `$#` é a quantidade e `$@` a lista. Nomes com espaço exigem aspas.
- **Aspas:** duplas expandem variáveis, simples mantêm o texto literal.

#### Para executar na VM — 3 minutos

Conceito que resiste a leitura cede a uma execução (Correção 50):

```bash
cd ~/lab5/scripts
primeiro                          # sem ./ : command not found
chmod -x primeiro ; ./primeiro    # Permission denied
chmod +x primeiro ; ./primeiro    # Hello World
wc -c primeiro ; cat primeiro     # 20 bytes esperados; confira o conteudo

cat > sem-aspas.sh << EOF
#!/bin/bash
echo "Ola, $1"
EOF
cat sem-aspas.sh                  # o $1 sumiu: o shell expandiu antes de gravar
```

#### Restante do Laboratório 1 — o que falta e quando

| Parte | Tempo | Quando | Por quê |
|---|---|---|---|
| Blocos 3, 4 e 5 (`if`, `for`, código de saída) | 20 min | **Domingo 04/10, depois do simulado** (ou sábado, se houver tempo) | São pré-requisito: os scripts do Laboratório 2 usam `if`, `for`, `$?` e `exit` |
| Bloco 6 (`vi` e `nano`) | 10 min | Domingo 04/10, depois dos blocos 3 a 5. Se cortado, segunda 05/10 | É objetivo oficial, mas os scripts não dependem dele |
| Exercício do script das frutas | 15 min | Domingo 04/10, por último. Se cortado, segunda 05/10 | Fixa os três erros de sintaxe típicos do 3.3 |

Com isso o domingo fecha em cerca de 2h35: simulado e apuração (1h25) mais Laboratório 1, registro e commits (1h10). *Atualizado em 02/10, à noite: o Laboratório 2 saiu da Semana 5.*

### Laboratório 2 — terça 06/10 (Semana 6)

*A preencher na Semana 6.*

### Correções da semana

A numeração segue a série global. A última da Semana 4 foi a **Correção 52**. As **Correções 53 a 59** foram registradas em 30/09, nas anotações do curso. A **Correção 60** foi registrada em 02/10, no Laboratório 1. A próxima é a **61**.

*Correções dos laboratórios: a preencher.*

### Resultado do simulado — domingo 04/10

| Campo | Valor |
|---|---|
| Data | |
| Tempo gasto | |
| Acertos | de 40 |
| Percentual | |
| Equivalente na escala LPI | acertos × 20 = pontos de 800 |
| Questões marcadas como chute | |

---

## Checklist da semana

- [x] Sessão 5 da Semana 4 — `find` e desafio integrador (28/09)
- [x] Autoavaliação da Semana 4 — 14 de 20 (29/09)
- [x] Correções 49 a 52 anotadas (29/09)
- [x] Instalação do `bzip2` (29/09)
- [x] Commits da Semana 4 (29/09)
- [ ] Voucher comprado e prova agendada para 09/11 — **transferido: quarta 07/10**
- [x] Curso, aulas 26 a 30 (quarta) — checkpoint na aula 31
- [ ] Curso, aulas 31 a 43 — **transferido: segunda 05/10 (Semana 6)**
- [ ] Comparação de compressão refeita com o `bzip2` — **transferido: terça 06/10**
- [ ] Aquecimento diário: quarta, quinta, sexta, sábado e domingo
- [ ] Laboratório 1 — **parcial em 02/10:** blocos 1 e 2 concluídos; faltam os blocos 3 a 6 (`if`, `for`, código de saída, `vi` e `nano`) e o exercício das frutas — **domingo 04/10, depois do simulado**
- [ ] Laboratório 2 — **transferido para terça 06/10 (Semana 6)**; `filtrar.sh` opcional
- [ ] Simulado #1, diagnóstico de 40 questões (domingo 04/10, **primeira atividade do dia**)
- [ ] Apuração do simulado por objetivo
- [ ] Observações sobre arquivos ocultos registradas — **transferido: segunda 05/10**
- [ ] Limpeza da home — **transferido: segunda 05/10**
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-05.md` com o Laboratório 1 completo, o **resultado do simulado #1** registrado e a apuração por objetivo. Os scripts do Laboratório 2 e o voucher passam para a Semana 6.

---

## Cola rápida — shell script

```
Executar        chmod +x s.sh && ./s.sh        bash s.sh (não exige x)
Shebang         #!/bin/bash                    (os dois primeiros caracteres)
Variável        nome=valor    (sem espaços)    "$nome"   ${nome}
Argumentos      $1 $2 ... $9   $#  $@  $0
Saída           echo "texto"
Comando em var  data=$(date +%Y-%m-%d)
Decisão         if [ $# -ne 2 ]; then ... elif ... else ... fi     (espaços dentro de [ ])
Números         -eq  -ne  -lt  -le  -gt  -ge
Texto           =  ==  -z          Arquivo: -f  -d
Loop for        for i in 1 2 3; do ... done       for i in $(seq 1 5); do ... done
Loop while      while IFS= read -r l; do ... done < "$arq"     (extra, fora da lista oficial)
Código de saída $?   exit 0   exit 1        && (se 0)    || (se diferente de 0)
Editor vi       i (inserir)  Esc (voltar)  :w  :q  :wq  :q!
Editor nano     Ctrl+O (grava)  Ctrl+X (sai)
```