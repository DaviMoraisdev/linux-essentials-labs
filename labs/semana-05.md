# Semana 5 — Shell script, simulado diagnóstico e reorganização do curso

Período: 28/09 a 04/10/2026 (segunda a domingo)
Objetivo da prova: 3.3 (Turning Commands into a Script), peso 4 de 40 — o maior peso individual do exame
Tópico 3, peso 9: com o 3.3 esta semana fecha os 4 pontos restantes (3.1 e 3.2 foram fechados na Semana 4)
Fechamento em 04/10: **Laboratório 1 completo** e **exercício das frutas feito**. O simulado #1, o Laboratório 2, a autoavaliação e as aulas 31 a 43 passam para a Semana 6

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
| **Dom 04** | Laboratório 1, blocos 3 a 6 e exercício das frutas — **realizado**. Simulado #1 **não realizado**: passou para a segunda 05/10 | — |

**Total a partir de quarta: 6h45**, dentro do teto de 7h do orçamento semanal, porém sem folga. O plano original previa 5h; as 1h45 a mais são o custo dos dois dias de curso perdidos.

**Regra de transbordo.** Se a quarta ou a quinta não fecharem as 9 aulas do dia:

1. As aulas de shell script (objetivo 3.3) têm prioridade e **precisam estar vistas antes do Laboratório 1**. Se necessário, elas passam à frente das demais.
2. As aulas restantes das faixas 26 a 37 podem transbordar para **segunda 05/10**, primeiro dia da Semana 6, antes das aulas de permissões. Nunca para sexta, sábado ou domingo.
3. O Laboratório 2 e o simulado **não são cortados nem movidos**.

**Atualização de 30/09.** A quarta fechou **5 das 9 aulas** previstas (26 a 30). As 4 restantes (31 a 34) passaram para a quinta, que agora tem **13 aulas (31 a 43)**, cerca de 1h30 de vídeo mais o aquecimento. No pior caso a semana passa de 6h45 para cerca de 7h10, 10 minutos acima do teto. A folga vem de duas decisões: (a) subir para **2x** nas aulas que só repetem conteúdo já praticado, como a navegação de hoje, que o próprio caderno marca como "já tratado nos labs"; e (b) aplicar a regra de transbordo, em que o que não couber na quinta e não for de shell script vai para a segunda 05/10. Se na quinta à noite as aulas de shell script não estiverem vistas, o Laboratório 1 de sexta começa com 20 minutos de vídeo.

**Atualização de 02/10 (superada pela atualização final logo abaixo).** A quinta não teve estudo e o Laboratório 1 de sexta foi feito em parte: blocos 1 e 2 concluídos. Os blocos 3 a 5 (`if`, `for`, código de saída) passam para o **sábado, antes do Laboratório 2**, porque os quatro scripts dependem deles. O bloco 6 (`vi` e `nano`) e o exercício das frutas ficam para depois do Laboratório 2 ou até segunda 05/10. O sábado passa de cerca de 1h35 para cerca de 2h20. O simulado de domingo **continua em data fixa**.

**Atualização de 02/10, à noite — plano da Semana 5 (superada pela atualização de 04/10, abaixo).** O sábado deixa de ser obrigatório e o fechamento da semana passa inteiro para o **domingo 04/10**: terminar o Laboratório 1 e fazer o simulado de 40 questões. O Laboratório 2 e as aulas 31 a 43 do curso passam para a **Semana 6** (ver `labs/semana-06.md`).

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
| Autoavaliação da Semana 5 | **Sexta 09/10**, em versão reduzida de 10 questões, três dias depois do Laboratório 2 |
| Exercício das frutas e bloco 6, **se cortados no domingo** | Segunda 05/10 |

**Novidade a partir desta semana: simulado geral todo domingo.** O primeiro da série, o simulado #1, estava previsto para 04/10 e passou para a **segunda 05/10**. O calendário completo, as metas por simulado e a regra de adiamento da prova estão no plano geral, seções 7 e 11.

**Atualização de 04/10 — fechamento da Semana 5.** O domingo rendeu o Laboratório 1 inteiro e o exercício das frutas. O simulado não coube. A Semana 5 fecha assim:

| Item | Situação em 04/10 |
|---|---|
| Laboratório 1, blocos 1 e 2 | Concluídos em 02/10 |
| Laboratório 1, blocos 3 a 6 | **Concluídos em 04/10**, com anotações |
| Exercício do script das frutas | **Concluído em 04/10**, com os quatro erros corrigidos |
| Simulado #1 (40 questões) | **Não realizado.** Segunda 05/10, primeira atividade do dia |
| Laboratório 2 | Transferido para terça 06/10 |
| Autoavaliação da Semana 5 | Transferida para sexta 09/10, em versão de 10 questões |
| Curso, aulas 31 a 43 | Transferido para quarta 07/10, a 2x, porque o conteúdo já foi praticado no Laboratório 1 |
| Correção das semanas e revisão prática | Entra na Semana 6, depois da apuração do simulado #1 (ver `labs/semana-06.md`) |

O que mudou na prática: o simulado #1 agora mede o shell script **depois** do Laboratório 1 completo, e não antes. Isso é menos limpo como diagnóstico do 3.3, mas mede melhor o que importa: quanto ficou depois de praticar.

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

## Simulado diagnóstico (#1) — transferido de domingo 04/10 para Segunda 05/10

Esta é a pendência mais antiga do plano. Ela ocupa o lugar de uma prática porque **é** prática, e o resultado determina no que as práticas das Semanas 6 e 7 devem insistir.

**Este é o simulado #1 da série.** Não foi feito no domingo 04/10 e passou para a **segunda 05/10**, como primeira atividade do dia. Como o Laboratório 1 já está completo, ele mede o shell script depois da prática. Dali em diante a série segue aos domingos, com as metas do plano geral, seção 7. **O resultado é registrado no arquivo da Semana 6.**

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
| Curso, aulas 31 a 43 | Semana 5, quarta 30/09 | Em aberto: sem registro de avanço desde o checkpoint da aula 31 | **Transferido para a Semana 6: quarta 07/10**, a 2x |
| Laboratório 1, blocos 3 a 5 (`if`, `for`, código de saída) | Semana 5, sexta 02/10 | **Concluído em 04/10** | — |
| Laboratório 1, bloco 6 (`vi` e `nano`) | Semana 5, sexta 02/10 | **Concluído em 04/10**, mas sem registro das saídas dos editores | Ter 06/10, 3 minutos no aquecimento |
| Exercício do script das frutas (material do LPI) | Semana 5, sexta 02/10 | **Concluído em 04/10** | — |
| Laboratório 2 (`backup.sh`, `contar.sh`, `usuario.sh`; `filtrar.sh` opcional) | Semana 5, sábado 03/10 | **Concluído em 06/10** (registro na Semana 6) | — |
| Voucher da prova e agendamento para 09/11 | Semana 5 | Em aberto, já adiado duas vezes | **Qua 07/10** |
| Simulado diagnóstico (simulado #1) | Semana 3 | Em aberto, adiado de novo: não coube no domingo | **Seg 05/10**, primeira atividade do dia |
| Reteste das 4 questões erradas da autoavaliação da Semana 4 | Semana 4 | No aquecimento diário; as questões 18, 20, 21, 22 e 24 do simulado #1 também retestam | Seg 05/10 |
| Comparação de compressão com o `bzip2` instalado | Semana 4 | `bzip2` instalado; falta refazer | Ter 06/10, no aquecimento |
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
- **`-o`:** mostra `GNU/Linux`. Isso diz que o sistema operacional é Linux, **não qual distribuição**. Para saber o nome e a versão da distribuição, o arquivo é `/etc/os-release`. A questão 27 do simulado #1 cobra exatamente isso.
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

### Laboratório 1 — Fundamentos de shell script — COMPLETO (blocos 1 e 2 em 02/10; blocos 3 a 6 e frutas em 04/10)

| Bloco | Situação |
|---|---|
| 1. Primeiro script, shebang e execução | Concluído em 02/10, com anotações |
| 2. Variáveis e argumentos | Concluído em 02/10, com anotações |
| 3. Decisões com `if` | Concluído em 04/10, com anotações |
| 4. Loops com `for` | Concluído em 04/10, com anotações |
| 5. Código de saída | Concluído em 04/10, com anotações. **Correção 61** |
| 6. Editores `vi` e `nano` | Concluído em 04/10, com anotações. Saídas dos editores sem registro |
| Exercício do script das frutas (material do LPI) | Concluído em 04/10, quatro erros corrigidos |

O registro dos blocos 1 e 2 já está **corrigido**, e o ajuste é explicado na Correção 60 e nas observações. Os blocos 3 a 6 e o exercício das frutas vêm depois da seção "Para executar na VM — 3 minutos", mais abaixo. **Observação sobre o caderno:** o seu arquivo de domingo ainda traz, nos blocos 1 e 2, o texto original, com o "ou seja" da Correção 60. Vale ajustar a anotação no Notion.

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
- **Permissão `rw-rw-r--`.** É o que a Ubuntu cria por padrão para arquivos novos, resultado da `umask` 002. A questão 40 do simulado #1 parte de `rw-r--r--`, resultado de uma `umask` de 022. O mecanismo é o mesmo, e a `umask` é conteúdo da Semana 6.
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

#### Bloco 3 — Decisões com `if`

Estrutura registrada:

```bash
if teste
then
    # roda quando o teste retorna sucesso (código 0)
elif outro_teste
then
    # roda quando o anterior falhou e este passou
else
    # roda nos casos restantes
fi
```

| Palavra | Papel |
|---|---|
| `if` | Inicia a decisão |
| `then` | Inicia o bloco executado quando a condição é verdadeira |
| `elif` | Testa outra condição se a anterior falhou |
| `else` | Trata os casos restantes |
| `fi` | **Encerra o `if`** (é `if` ao contrário) |

Operadores numéricos: `-eq` igual, `-ne` diferente, `-lt` menor, `-le` menor ou igual, `-gt` maior, `-ge` maior ou igual. Para texto, `=`. Para arquivos, `-f` (arquivo comum) e `-d` (diretório). Para texto vazio, `-z`.

O `teste.sh` do roteiro começa com uma **guarda**: `[ $# -ne 2 ]` confere se vieram exatamente dois argumentos e, se não vieram, imprime o uso e sai com `exit 1`, antes de tocar em `$1` e `$2`. Saídas esperadas das quatro chamadas, que as anotações **não registram**; confira na VM:

| Chamada | Saída esperada | Código |
|---|---|---|
| `./teste.sh 3 1` | `3 e maior que 1` | 0 |
| `./teste.sh 2 2` | `Iguais` | 0 |
| `./teste.sh 1 5` | `1 e menor que 5` | 0 |
| `./teste.sh 1` | `Uso: ./teste.sh <n1> <n2>` | 1 |

Os três pontos de atenção do 3.3, agora com um caso concreto cada: espaços dentro de `[ ]` são obrigatórios (`[` é um comando); `=` compara texto e `-eq` compara número; variável sem aspas se parte em palavras.

#### Bloco 4 — Loops com `for`

| Parte de `for i in 1 2 3; do echo "volta $i"; done` | Papel |
|---|---|
| `for` | Inicia a repetição |
| `i` | Variável que recebe cada item da lista |
| `in 1 2 3` | A lista de valores percorridos |
| `do` | Inicia os comandos repetidos |
| `done` | **Encerra o laço** |

Cada repetição é uma **iteração**. As três formas do roteiro:

| Comando | O que gera |
|---|---|
| `for i in 1 2 3` | Os três valores escritos na linha |
| `for i in $(seq 1 5)` | `seq 1 5` gera 1 a 5. É **substituição de comando**: o shell executa o interno e usa a saída no externo |
| `for arq in /etc/*.conf` | O shell expande o padrão para os caminhos que casam. Saída registrada, com `head -3`: `/etc/adduser.conf`, `/etc/debconf.conf`, `/etc/deluser.conf` |

#### Bloco 5 — Código de saída

Um comando produz três coisas diferentes: **saída normal** (resultados), **saída de erro** (mensagens sobre problemas) e **código de saída** (um número que diz como terminou).

| Comando | O que faz |
|---|---|
| `ls /etc > /dev/null ; echo $?` | `/dev/null` descarta o que recebe. O `$?` guarda o código do comando anterior. Saída: `0` |
| `ls /naoexiste 2> /dev/null ; echo $?` | O `2>` descarta a mensagem de erro. O código continua indicando falha. Saída: `2` |
| `grep -q root /etc/passwd && echo "achou" \|\| echo "nao achou"` | O `-q` suprime as linhas e deixa só o código. `&&` executa se o `grep` deu `0`. Saída: `achou` |

`0` é sucesso e qualquer outro valor é falha. `&&` executa o segundo comando só se o primeiro deu `0`; `||` só se deu diferente de `0`. O `exit N` define o código do próprio script.

#### Correção 61 — o `2` do `2>` e o `2` do `$?` não têm relação

A anotação do bloco 5 diz, sobre a saída `2` do `ls /naoexiste`: "**2 → erro stderr**". São dois números 2 diferentes, que coincidem por acaso:

| O `2` | Onde aparece | Significa |
|---|---|---|
| `2>` | No redirecionamento | O **fluxo** número 2, a saída de erro padrão (stderr) |
| `$?` valendo `2` | No resultado do `echo $?` | O **código de saída** do `ls`: terminou com status 2, que o `ls` usa para "problema sério", como um argumento que não existe |

Um é um **canal de texto**, o outro é um **número devolvido ao terminar**. Eles podem andar juntos ou separados:

| Comando | Texto em stderr? | Código |
|---|---|---|
| `ls /naoexiste` | Sim | 2 |
| `grep -q xyz /etc/passwd` | **Não** | **1** (não achou, e nenhuma mensagem de erro) |
| `echo oi >&2` | Sim (o `>&2` manda o texto para o stderr) | **0** |

O código não depende de para onde o erro foi: `ls /naoexiste > /dev/null` mostra a mensagem na tela e continua devolvendo `2`. Mecanismo: o **fluxo** diz **onde** a mensagem sai; o **código** diz **como** o programa terminou.

#### Bloco 6 — Editores `vi` e `nano`

| Editor | O que foi registrado |
|---|---|
| `nano` | `Ctrl+O` grava (confirme o nome com Enter). `Ctrl+X` sai e, se houver alteração não salva, pergunta o que fazer |
| `vi` | Três modos: **normal** (mover o cursor e editar), **inserção** (digitar texto) e **linha de comando** (comandos iniciados por `:`) |

Teclas de transição do `vi`, que as anotações **não trazem** e a prova cobra:

| De | Para | Tecla |
|---|---|---|
| Normal (modo ao abrir) | Inserção | `i` |
| Inserção | Normal | `Esc` |
| Normal | Linha de comando | `:` |

Comandos: `:w` grava, `:q` sai, `:wq` grava e sai, `:q!` sai **sem** gravar. No `nano` não há modos; os atalhos aparecem no rodapé, com `^` significando `Ctrl`.

O roteiro pedia **sair de cada editor três vezes, sem consultar**. As anotações não registram isso. Fica no "Para executar na VM" abaixo.

#### Exercício das frutas — o script `frutas.sh`

O exercício do material oficial traz um script com erros de sintaxe para corrigir, um por vez. Versão digitada com os erros:

```bash
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
```

Mensagens registradas na primeira execução: `./frutas.sh: line 3: fruta1: command not found` e `./frutas.sh: line 14: syntax error near unexpected token 'done'`.

| # | Linha | Erro | Como se manifesta | Correção |
|---|---|---|---|---|
| 1 | 3 | `fruta1 = Macas`, com espaços em volta do `=` | `fruta1: command not found`: o shell lê `fruta1` como **comando** e `=` e `Macas` como argumentos | `fruta1=Macas` |
| 2 | 6 | `[$1`, sem espaço depois do `[` | Com `$1` valendo 2, o shell lê `[2` como um comando. Esperado: `[2: command not found`. Ele não aparece nas mensagens registradas porque o erro 4 impede o bloco de rodar | `[ $1 -gt $2 ]` |
| 3 | 8 | `echo '$fruta1 venceram!'`, com aspas simples | **Nenhuma mensagem.** O script roda e imprime o texto literal `$fruta1 venceram!` | Aspas duplas: `"$fruta1 venceram!"` |
| 4 | 14 | `done` no lugar de `fi` | `syntax error near unexpected token 'done'` | `fi` |

Versão final, com os resultados registrados:

```bash
#!/bin/bash

fruta1=Macas
fruta2=Laranjas

if [ $1 -gt $2 ]
then
echo "$fruta1 venceram!"
elif [ "$1" -eq "$2" ]
then
echo "Empate!"
else
echo "$fruta2 venceram!"
fi
```

| Chamada | Saída |
|---|---|
| `./frutas.sh 2 5` | `Laranjas venceram!` |
| `./frutas.sh 5 2` | `Macas venceram!` |
| `./frutas.sh 3 3` | `Empate!` |

#### Observações dos blocos 3 a 6 e das frutas (sem número)

- **Três erros, três jeitos de falhar.** O erro 1 produz mensagem e o script continua. O erro 4 é um erro de **sintaxe** e impede o bloco inteiro de rodar. O erro 3 **não produz mensagem nenhuma**, e é o mais perigoso dos quatro: a saída parece plausível e está errada. É a Regra 3 do plano: saída na tela não é prova de sucesso.
- **Por que o erro 1 aparece antes do erro 4**, apesar de estar na linha 3 e o outro na 14: o `bash` executa a linha 3 e só então lê o bloco `if ... fi` inteiro, onde encontra o erro de sintaxe. Por isso as duas mensagens vêm nessa ordem. É uma leitura coerente com o que você registrou, e vale confirmar corrigindo só o erro 4 e rodando de novo.
- **A anotação do erro 3** diz "corrigir para aspas duplas e atribuir o valor da variável `fruta1` corretamente". São dois problemas independentes: as aspas duplas resolvem a **expansão** (erro 3); a atribuição correta é o erro 1.
- **`fi` e `done` são pares diferentes.** `if` fecha com `fi`; `for` e `while` fecham com `done`. Trocar um pelo outro é o erro 4.
- **Aspas nos testes.** O `if` da correção usa `[ $1 -gt $2 ]` sem aspas, enquanto o `elif` usa `[ "$1" -eq "$2" ]`. Os dois funcionam com argumentos normais. Com argumento vazio os dois falham, mas de jeitos diferentes: sem aspas o `[` perde um operando; com aspas o erro passa a ser sobre expressão inteira. Prefira `"$1"` e deixe a guarda do `$#` impedir o caso (o "Para executar" abaixo mostra as duas mensagens).
- **O `*` do `for arq in /etc/*.conf`** é **globbing**: o shell o expande antes de o `for` rodar. É o mesmo `*` da questão 24 do simulado, que na regex tem outro significado.
- **Grafia.** `Crtl` nas anotações do `nano` é `Ctrl`.

#### O que aprendi nos blocos 3 a 6 e nas frutas

- **`if`:** `then` abre, `elif` e `else` tratam os outros casos, `fi` fecha. Espaços dentro de `[ ]` são obrigatórios.
- **`-eq` e `=`:** `-eq` compara número, `=` compara texto.
- **`for`:** `done` fecha o laço. `$(seq 1 5)` é substituição de comando.
- **Código de saída:** `$?` guarda o do último comando. `0` é sucesso. Não confundir o número do **fluxo** (`2>`) com o **código** (`$?`).
- **`&&` e `||`:** o primeiro executa se deu `0`, o segundo se deu diferente de `0`.
- **Editores:** `nano` grava com `Ctrl+O` e sai com `Ctrl+X`. O `vi` tem três modos, e `:wq` grava e sai.
- **Erro silencioso é o pior erro:** aspas simples não geram mensagem.

#### Para executar na VM — 5 minutos

Conceito que resiste a leitura cede a uma execução (Correção 50):

```bash
cd ~/lab5/scripts
./teste.sh 3 1 ; echo $?
./teste.sh 1 ; echo $?                          # uso e código 1

ls /etc > /dev/null ; echo $? ; echo $?         # 0 e depois 0: o segundo $? é do echo
ls /naoexiste 2> /dev/null ; echo $? ; echo $?  # 2 e depois 0
grep -q xyz /etc/passwd ; echo $?               # 1, sem mensagem nenhuma

x= ; [ $x -gt 1 ] ; echo $?                     # leia a mensagem exata
[ "$x" -gt 1 ] ; echo $?                        # e agora? A mensagem muda
```

Depois, o `nano` e o `vi`, **três saídas de cada um**, sem consultar: `Ctrl+X` no `nano`; `Esc` e `:q!` no `vi`; `Esc` e `:wq` no `vi`.

### Fechamento do Laboratório 1

| Parte | Situação |
|---|---|
| Blocos 1 a 6 | Concluídos, com anotações |
| Exercício das frutas | Concluído |
| Correções do laboratório | **60** e **61** |
| Execuções pendentes | Os dois blocos "Para executar na VM" (3 e 5 minutos) |
| Registro das saídas do `teste.sh` e das três saídas de cada editor | Pendente |

*Atualizado em 04/10: o Laboratório 1 está completo. O Laboratório 2 saiu da Semana 5 e foi para a Semana 6.*

### Laboratório 2 — terça 06/10 (Semana 6)

**Concluído em 06/10.** Os três scripts obrigatórios foram escritos e testados. O registro corrigido está em `labs/semana-06.md`, seção "Registro das sessões".

### Correções da semana

A numeração segue a série global. A última da Semana 4 foi a **Correção 52**. As **Correções 53 a 59** foram registradas em 30/09, nas anotações do curso. A **Correção 60** foi registrada em 02/10, no bloco 2 do Laboratório 1, e a **Correção 61** em 04/10, no bloco 5. **A próxima é a 62.** As correções que o simulado #1 gerar continuam a série a partir daí.

| # | Tema | Origem |
|---|---|---|
| 60 | O `./` e o `Permission denied` têm causas diferentes | Laboratório 1, bloco 1 |
| 61 | O `2` do `2>` e o `2` do `$?` não têm relação | Laboratório 1, bloco 5 |

Os cards das Correções 60 e 61 no Notion foram anotados (confirmado em 05/10). Mecanismo da 61: o fluxo diz **onde** a mensagem sai, o código diz **como** o programa terminou.

### Resultado do simulado #1

Transferido para a **segunda 05/10**. O resultado, a apuração por objetivo e as correções são registrados no arquivo da **Semana 6** (`labs/semana-06.md`), seção "Simulado #1".

---

## Checklist da semana

- [x] Sessão 5 da Semana 4 — `find` e desafio integrador (28/09)
- [x] Autoavaliação da Semana 4 — 14 de 20 (29/09)
- [x] Correções 49 a 52 anotadas (29/09)
- [x] Instalação do `bzip2` (29/09)
- [x] Commits da Semana 4 (29/09)
- [ ] Voucher comprado e prova agendada para 09/11 — **transferido: quarta 07/10**
- [x] Curso, aulas 26 a 30 (quarta) — checkpoint na aula 31
- [x] Curso, aulas 31 a 43 — **transferido: quarta 07/10 (Semana 6)**
- [x] Comparação de compressão refeita com o `bzip2` — **transferido: terça 06/10**
- [x] Laboratório 1 — blocos 1 e 2 (02/10) e blocos 3 a 6 (04/10)
- [x] Exercício do script das frutas (04/10)
- [x] Correções 60 e 61 registradas
- [x] Laboratório 2 — concluído em 06/10 (Semana 6); `filtrar.sh` opcional, não feito
- [x] Simulado #1, diagnóstico de 40 questões — **transferido: segunda 05/10, primeira atividade do dia**
- [x] Apuração do simulado por objetivo — **segunda 05/10**
- [x] Observações sobre arquivos ocultos — dívida encerrada em 05/10, a pedido (comandos já dominados)
- [x] Limpeza da home — já estava quitada desde a Semana 3 (confirmado em 05/10)
- [x] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-05.md` com o **Laboratório 1 completo** e o exercício das frutas, e as Correções 60 e 61. **Entregue em 04/10.** O simulado #1, os scripts do Laboratório 2, a autoavaliação e o voucher passam para a Semana 6.

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