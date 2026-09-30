# Semana 5 — Shell script, simulado diagnóstico e reorganização do curso

Período: 28/09 a 04/10/2026 (segunda a domingo)
Objetivo da prova: 3.3 (Turning Commands into a Script), peso 4 de 40 — o maior peso individual do exame
Tópico 3, peso 9: com o 3.3 esta semana fecha os 4 pontos restantes (3.1 e 3.2 foram fechados na Semana 4)
Carga prevista a partir de 30/09: cerca de 6h45, distribuídas em 5 dias

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
| **Qua 30** | Voucher (10 min) · **curso, aulas 26 a 34** · aquecimento | 1h25 |
| **Qui 01/10** | **Curso, aulas 35 a 43** (as de shell script a 1x) · aquecimento | 1h25 |
| Sex 02 | Laboratório 1 — fundamentos de shell script, `vi` e `nano` · aquecimento | 1h10 |
| Sáb 03 | Laboratório 2 — os quatro scripts · aquecimento | 1h10 |
| **Dom 04** | **Simulado diagnóstico** · apuração · commits | 1h35 |

**Total a partir de quarta: 6h45**, dentro do teto de 7h do orçamento semanal, porém sem folga. O plano original previa 5h; as 1h45 a mais são o custo dos dois dias de curso perdidos.

**Regra de transbordo.** Se a quarta ou a quinta não fecharem as 9 aulas do dia:

1. As aulas de shell script (objetivo 3.3) têm prioridade e **precisam estar vistas antes do Laboratório 1**. Se necessário, elas passam à frente das demais.
2. As aulas restantes das faixas 26 a 37 podem transbordar para **segunda 05/10**, primeiro dia da Semana 6, antes das aulas de permissões. Nunca para sexta, sábado ou domingo.
3. O Laboratório 2 e o simulado **não são cortados nem movidos**.

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

Posição atual: **aula 26 de 72**. Restam 46 aulas; esta semana fecha 18 delas (26 a 43).

| Dia | Aulas | Velocidade | Tempo estimado |
|---|---|---|---|
| Qua 30/09 | 26 a 34 (9 aulas) | 1.5x | cerca de 1h05 |
| Qui 01/10 | 35 a 43 (9 aulas) | 1.5x, e **1x nas de shell script** | cerca de 1h15 |

Regras do curso:

- Ao chegar nas aulas de shell script (3.3), reduza para **1x**. O vídeo entrega o modelo mental que o laboratório de sexta transforma em prática.
- Anote no caderno **só o que o vídeo mostra e você ainda não sabia**. O que já foi praticado, o vídeo confirma e não ensina.
- Se o número exato das aulas de shell script não cair na faixa 35 a 43, ajuste a divisão entre quarta e quinta, mas mantenha a regra: o 3.3 vem visto **antes** da sexta.
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

## Laboratório 2 — Sábado 03/10 — Os quatro scripts

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
| Curso, aulas 26 a 34 | Semana 5, terça 29/09 | Adiado 2 dias | Qua 30/09 |
| Curso, aulas 35 a 43 | Semana 5, quarta 30/09 | Previsto | Qui 01/10 |
| Voucher da prova e agendamento para 09/11 | Semana 5 | Em aberto | Qua 30/09 |
| Simulado diagnóstico | Semana 3 | Em aberto, 4 semanas de atraso | Dom 04/10 |
| Reteste das 4 questões erradas da autoavaliação da Semana 4 | Semana 4 | No aquecimento diário | Até dom 04/10 |
| Comparação de compressão com o `bzip2` instalado | Semana 4 | `bzip2` instalado; falta refazer | Qua 30/09, no aquecimento |
| Registro das observações sobre arquivos ocultos | Semana 3 | Em aberto | Sex 02/10, no registro do Laboratório 1 |
| Limpeza: `rm 'sudo apt upgrade -y'` na home | Semana 3 | Em aberto | Qua 30/09, 30 segundos |
| Autoavaliação da Semana 5 | Semana 5 | Elaborada após o Laboratório 2 | Qua 07/10, aberta na Semana 6 |
| `.wslconfig` limitando o WSL2 a 3 GB | Semana 0 | Sem prazo | Quando houver folga |
| Teste de restauração do snapshot | Semana 0 | Sem prazo | Quando houver folga |

---

## Registro do curso

Preencha ao fim de cada dia.

| Data | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|
| 30/09 | | | |
| 01/10 | | | |

---

## Registro das sessões

### Laboratório 1 — sexta 02/10

*A preencher.*

### Laboratório 2 — sábado 03/10

*A preencher.*

### Correções da semana

A numeração segue a série global. A última da Semana 4 foi a **Correção 52**; a próxima é a **53**.

*A preencher.*

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
- [ ] Voucher comprado e prova agendada para 09/11
- [ ] Curso, aulas 26 a 34 (quarta)
- [ ] Curso, aulas 35 a 43 (quinta)
- [ ] Comparação de compressão refeita com o `bzip2`
- [ ] Aquecimento diário: quarta, quinta, sexta, sábado e domingo
- [ ] Laboratório 1 — fundamentos de shell script, `vi` e `nano` (sexta)
- [ ] Laboratório 2 — os quatro scripts (sábado)
- [ ] Simulado diagnóstico de 40 questões (domingo)
- [ ] Apuração do simulado por objetivo
- [ ] Observações sobre arquivos ocultos registradas
- [ ] Limpeza da home
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-05.md` preenchido, os **4 scripts** em `scripts/`, voucher comprado com a prova agendada e o resultado do simulado registrado.

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