# Resultados dos simulados e correções — LPI Linux Essentials (010-160)

**Aluno:** Davi · **Prova:** 09/11/2026 (confirmação no pré-checkpoint de 07/10) · **Criado em:** 06/10/2026 · **Última atualização:** 06/10/2026

Este arquivo reúne, em um só lugar, **todos os números de desempenho** do plano: os simulados, as autoavaliações por tópico, os checkpoints e as correções registradas desde a Semana 2. Ele não substitui o plano geral (`plano-linux-essentials-010-160.md`) nem os arquivos semanais; ele os resume e os mantém comparáveis.

Arquivos relacionados:

| Arquivo | O que traz |
|---|---|
| `praticas-simulado-01-resultado-05-10.md` | A prova do simulado #1 corrigida, questão por questão |
| `semana-06-permissoes.md` | O texto completo das Correções 62 a 72 |
| `plano-linux-essentials-010-160.md` | Seção 7 (série de simulados), seção 9 (erros recorrentes) e seção 11 (checkpoints) |
| `praticas-fontes-de-simulados.md` | De onde vêm as questões |

---

## 1. Como este documento funciona

### 1.1 Regras vigentes (desde 06/10/2026)

**Simulados: só se anotam as questões erradas.** Para cada simulado, este arquivo guarda a apuração por tópico, a lista das questões erradas e das chutadas, e a comparação com o simulado anterior. A **correção em si**, a explicação do mecanismo, é feita por você nos cards do Notion. Não se abre mais correção numerada para erro de simulado.

**Erros antigos de comandos já dominados vão para a retaguarda.** Eles saem do aquecimento diário e das pendências. Voltam de duas formas: nos próprios simulados, que continuam medindo se o erro reaparece, e na revisão leve da Semana 10, pelos cards do Notion. A lista está na seção 7.

**A numeração das correções continua para laboratório e curso.** A próxima é a **73**.

### 1.2 Rotina após cada simulado

1. Responder cronometrado, sem consulta, **marcando cada chute**. A partir do #2, usar pelo menos 45 minutos e reservar os últimos 15 para uma segunda passada.
2. Abrir o gabarito só depois de responder tudo.
3. Apurar por tópico: acertos e chutes acertados.
4. Copiar o modelo da seção 4 e preencher: tabela do simulado, tabela por tópico, **questões erradas** e **chutes acertados**.
5. Corrigir as questões erradas no Notion, com as suas palavras, no mesmo dia.
6. Atualizar as tabelas da seção 2 deste arquivo.

### 1.3 Conversões úteis

| Percentual | Acertos de 40 | Escala LPI (acertos × 20) |
|---|---|---|
| 60% | 24 | 480 |
| 65% (corte do exame real) | 26 | 520 |
| 70% | 28 | 560 |
| 75% | 30 | 600 |
| 85% | 34 | 680 |

O exame real aprova com **500 de 800 pontos**, cerca de 65%, ou 26 acertos. A escala acima é uma aproximação (acertos × 20), útil para comparar; a pontuação oficial da LPI pode ponderar as questões de outra forma.

**Acerto firme** é o acerto não marcado como chute. Ele é o número que mede conhecimento. Um acerto por chute conta como acerto na nota, e como lacuna no estudo.

---

## 2. Painel de resultados

### 2.1 Série de simulados

| # | Data | Fonte | Meta | Acertos | % | Chutes acertados | Acertos firmes | Tempo | Situação |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Seg 05/10 | `simulado-01-diagnostico` | Diagnóstico (esperado de 24 a 30) | **28** | **70%** | 5 | **23** | 20 min 31 s | **Concluído** |
| 2 | Dom 11/10 | `simulado-02` (pedir qui 08/10, pronto sex 09/10) | **24 ou mais** (Checkpoint A) | | | | | | A fazer |
| 3 | Dom 18/10 | `simulado-03` | **28 ou mais** (Checkpoint B) | | | | | | A fazer |
| 4 | Qui 22/10 | Exame final de prática do NDG | 28 ou mais | | | | | | A fazer |
| 5 | Dom 25/10 | `simulado-05` | **30 ou mais** | | | | | | A fazer |
| 6 | Ter 27/10 | `simulado-06` | Acompanhar | | | | | | A fazer |
| 7 | Qui 29/10 | `simulado-07` | 34 ou mais | | | | | | A fazer |
| 8 | Dom 01/11 | `simulado-08` | **34 ou mais** (Gate) | | | | | | A fazer |
| 9 | Qui 05/11 | `simulado-09` | 34 ou mais (final) | | | | | | A fazer |

Não há simulado no domingo 08/11, véspera da prova.

### 2.2 Acertos por tópico, simulado a simulado

Formato: acertos de questões, e entre parênteses os chutes acertados. Copie a coluna do simulado novo conforme ele for feito.

| Tópico | Peso | #1 | #2 | #3 | #4 | #5 | #6 | #7 | #8 | #9 |
|---|---|---|---|---|---|---|---|---|---|---|
| 1. Comunidade e open source | 7 | 5/7 (0) | | | | | | | | |
| 2. Encontrando seu caminho | 9 | 5/9 (0) | | | | | | | | |
| 3. Poder da linha de comando | 9 | 9/9 (1) | | | | | | | | |
| 4. Sistema operacional | 8 | 6/8 (1) | | | | | | | | |
| 5. Segurança e permissões | 7 | 3/7 (3) | | | | | | | | |
| **Total** | **40** | **28/40 (5)** | | | | | | | | |

### 2.3 Autoavaliações por tópico

As autoavaliações medem a retenção do conteúdo de uma semana. Desde a Semana 4, são respondidas na semana seguinte, com pelo menos três dias de intervalo.

| Autoavaliação | Conteúdo | Data | Questões | Acertos | Meta | Observação |
|---|---|---|---|---|---|---|
| Semana 2 | Conteúdo da Semana 2 | 14/09 | 15 | **14** | 12 | Respondida no dia do estudo. O único erro foi a Q9, sobre o `export` |
| Semana 3 | Arquivos, links e pacotes | 19/09 | 20 | **20** | 16 | Respondida no dia do estudo. Gerou as Correções 27 e 28 (justificativas) |
| Semana 4 | Objetivos 3.1 e 3.2, filtros e compactação | 29/09 | 20 | **14** | 16 | Abaixo da meta. Respondida quatro dias depois do estudo. Gerou as Correções 49 a 52 |
| Semana 5 | Shell script | Sex 09/10 | 10 | | **8** | A fazer. Versão reduzida |
| Semana 6 | Tópico 5, permissões | Sex 16/10 | 10 | | A definir | A fazer |

Leitura: a de 29/09 (14/20, quatro dias depois do estudo) e o simulado #1 são os dados de retenção mais distantes do estudo disponíveis até aqui.

### 2.4 Checkpoints

Os critérios completos estão na seção 11 do plano geral.

| Checkpoint | Data | Critérios | Situação | Resultado e decisão |
|---|---|---|---|---|
| Pré-checkpoint | Qua 07/10 | Simulado #1 feito e Laboratório 2 feito | **Os dois cumpridos em 06/10** | **Compra do voucher adiada em 08/10** (decisão de Davi). Gatilho: média dos três últimos simulados com 30 ou mais; primeira avaliação em 22/10. Data-alvo 09/11, sem agendamento |
| A | Dom 11/10 | Curso até a aula 57; Laboratório 2; Práticas 1 e 2; simulado #2 com 24 ou mais; **gatilho do voucher registrado** (substituiu "voucher e agendamento" em 08/10) | **Critérios 2 e 5 cumpridos** (06/10 e 08/10) | |
| B | Dom 18/10 | Curso fechado (aula 72); práticas feitas; simulado #3 com 28 ou mais | | |
| Gate | Dom 01/11 | Dois simulados consecutivos com 34 ou mais entre os de 27/10, 29/10 e 01/11; laboratório integrador | | |
| Final | Qui 05/11 | 34 ou mais: ir. De 30 a 33: ir com revisão leve. Abaixo de 30: remarcar, se a janela permitir | | |

### 2.5 Dicas recorrentes de prova, por tema

Temas que aparecem com frequência nos relatos de candidatos (ver `praticas-reforco-dicas-recorrentes.md`). Formato: acertos de questões do tema. O simulado #1 não tinha esta marcação por tema, então só os mini-simulados de reforço e os simulados a partir do #2 preenchem a tabela.

| Tema | Mínimo por simulado | R1 (13/10) | #2 (11/10) | R2 (20/10) | #3 (18/10) | #5 | #7 | #8 | #9 |
|---|---|---|---|---|---|---|---|---|---|
| Permissões | 4 | /5 | | | | | | | |
| `tar` e compressão | 2 | /4 | | | | | | | |
| Redirecionamento (com `<<`) | 3 | /5 | | | | | | | |
| Diretórios virtuais e `/var` | 3 | /4 | | | | | | | |
| **Questões de preencher a lacuna** | 5 | /6 | | | | | | | |

Regra de leitura: um tema abaixo de 60% em um reforço ou simulado vira o foco do aquecimento da semana seguinte. Nas lacunas, anote também se o erro foi de **conteúdo** ou de **forma** (sublinhado, caminho, flag a mais, caixa).

---

## 3. Simulado #1 — 05/10/2026

### 3.1 Registro

| Campo | Valor |
|---|---|
| Fonte | `simulado-01-diagnostico`, 40 questões, distribuição de pesos do exame |
| Condições | 60 minutos, sem consulta |
| Tempo gasto | 20 min 31 s (restaram 39 min 29 s) |
| Acertos | **28 de 40 (70%)**, equivalente a **560 de 800** |
| Corte do exame real | 26 acertos. Resultado **acima do corte** |
| Chutes marcados | 10: 22, 28, 29, 33, 34, 35, 36, 37, 39 e 40 |
| Chutes acertados | 5 (22, 33, 34, 36, 39) |
| Chutes errados | 5 (28, 29, 35, 37, 40) |
| Acertos firmes | **23 de 40 (57,5%)** |
| Erros | 12: 7 com convicção e 5 chutados |

### 3.2 Por tópico

| Tópico | Peso | Questões | Acertos | % | Chutes acertados | Acertos firmes | Erros com convicção | Erros chutados |
|---|---|---|---|---|---|---|---|---|
| 1. Comunidade e open source | 7 | 1 a 7 | 5 | 71% | 0 | 5 | 2 (Q3, Q7) | 0 |
| 2. Encontrando seu caminho | 9 | 8 a 16 | 5 | 56% | 0 | 5 | 4 (Q10, Q14, Q15, Q16) | 0 |
| 3. Poder da linha de comando | 9 | 17 a 25 | **9** | **100%** | 1 | 8 | 0 | 0 |
| 4. Sistema operacional | 8 | 26 a 33 | 6 | 75% | 1 | 5 | 0 | 2 (Q28, Q29) |
| 5. Segurança e permissões | 7 | 34 a 40 | 3 | 43% | 3 | **0** | 1 (Q38) | 3 (Q35, Q37, Q40) |
| **Total** | **40** | | **28** | **70%** | **5** | **23** | **7** | **5** |

### 3.3 Leitura

**O resultado cumpre o diagnóstico, com uma ressalva.** O 70% está na parte alta da expectativa (24 a 30), mas só 23 acertos são firmes. Sem os chutes, o desempenho ficaria em 57,5%, abaixo do corte de 65%.

**O Tópico 3 sustentou.** Nove de nove, com apenas um acerto por chute (Q22). As questões 18, 20, 21 e 24 retestavam correções antigas e foram acertadas com firmeza.

**A fragilidade está nos Tópicos 1 e 2.** Seis dos sete erros com convicção caíram neles. Foram estudados nas Semanas 1 a 3 e só tinham sido medidos por autoavaliações feitas no mesmo dia do estudo. Nesses tópicos a confiança foi maior do que o acerto.

**A calibração foi boa onde não há estudo.** Os cinco erros marcados como chute estão nos Tópicos 4 e 5, ainda não estudados. O plano está funcionando nesse ponto.

**O Tópico 5 não tem nenhum acerto firme.** Os três acertos foram chutes. É a prioridade da Semana 6.

**Tempo.** 20 min 31 s de 60, cerca de 31 segundos por questão; o exame dá 90 segundos por questão. Com tanto tempo sobrando, vale usá-lo: para o simulado #2, usar pelo menos 45 minutos, com segunda passada.

### 3.4 Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Tipo | Onde está tratada |
|---|---|---|---|---|---|---|
| 3 | 1 | Distribuição *upstream* do RHEL | Debian | Fedora | Convicção | Correção 62 |
| 7 | 1 | Tecnologia em que cada sistema tem seu próprio kernel | Contêineres | Virtualização por hipervisor | Convicção | Correção 63 |
| 10 | 2 | O que faz `cd -` | Vai para o diretório pai | Volta ao diretório anterior | Convicção | Correção 64 |
| 14 | 2 | Significado de `/usr` | *User* | *Unix System Resources* | Convicção | Correção 65 |
| 15 | 2 | Diretório virtual com informações dos processos | `/dev` | `/proc` | Convicção | Correção 66 |
| 16 | 2 | Documentação completa do `cp` | `cp --manual` | `man cp` | Convicção | Correção 67 |
| 28 | 4 | Processos em tempo real | Alternativa D (o `free -h` mostra memória) | `top` | Chute | Semana 7, Prática 1 |
| 29 | 4 | Sinal padrão do `kill` | Alternativa A | `SIGTERM` (15); o `SIGKILL` (9) só com `kill -9` | Chute | Semana 7, Prática 1 |
| 35 | 5 | Último campo do `/etc/passwd` | Alternativa D | Shell de login (7º campo; o GID é o 4º) | Chute | Semana 6, Prática 1 |
| 37 | 5 | `rw-r--r--` em octal | 664 | 644 | Chute | Aquecimento de conversões |
| 38 | 5 | Mudar dono e grupo de um arquivo | `chmod davi:financeiro` | `chown davi:financeiro` | Convicção | Correção 68 |
| 40 | 5 | Quem retira permissões de arquivo novo | Alternativa C | `umask` | Chute | Baixa prioridade: fora da lista oficial do 5.3 |

Na Q37, o 664 que você marcou é justamente o padrão dos arquivos novos na sua VM. Pode ter sido o que você vê no terminal, e não a conversão pedida.

### 3.5 Chutes acertados

São acertos sem confirmação. Contam como lacuna de estudo.

| Q | Tópico | Tema |
|---|---|---|
| 22 | 3 | Comando que cria `backup.tar.gz` (o `-f` do `tar`, Correção 52) |
| 33 | 4 | Diretório dos arquivos de log, segundo o FHS |
| 34 | 5 | Arquivo das senhas criptografadas (`/etc/shadow`) |
| 36 | 5 | Significado de `rwxr-xr--` |
| 39 | 5 | O que o `x` concede em um diretório |

### 3.6 Retestes de correções antigas

| Q | Retestava | Resultado |
|---|---|---|
| 18 | Correção 29, a ordem em `> arquivo 2>&1` | Acerto firme |
| 20 | Correções 33, 34 e 50, o `-k` do `sort` | Acerto firme |
| 21 | Correção 36, o `uniq -u` | Acerto firme |
| 22 | Correção 52, o `-f` do `tar` | Acerto **por chute** |
| 24 | Regex `ab*c` | Acerto firme |

### 3.7 Observação de forma

Na Q11 a resposta foi `PATH`, com um sublinhado na frente. No exame real, em campo de preenchimento, escreva **só a palavra**.

---

## 4. Modelo de registro para os próximos simulados

Copie este bloco para cada simulado, trocando o número e a data. Preencha as tabelas e leve as questões erradas ao Notion.

### Simulado #N — data

| Campo | Valor |
|---|---|
| Fonte | |
| Tempo gasto | |
| Segunda passada (minutos usados nas marcadas) | |
| Acertos | de 40 |
| Percentual e escala LPI | |
| Chutes marcados | |
| Chutes acertados e chutes errados | |
| Acertos firmes | |
| Meta | |

| Tópico | Peso | Questões | Acertos | Chutes acertados |
|---|---|---|---|---|
| 1. Comunidade e open source | 7 | | | |
| 2. Encontrando seu caminho | 9 | | | |
| 3. Poder da linha de comando | 9 | | | |
| 4. Sistema operacional | 8 | | | |
| 5. Segurança e permissões | 7 | | | |
| **Total** | **40** | | | |

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Corrigida no Notion |
|---|---|---|---|---|---|---|
| | | | | | | |

Chutes acertados: Q, tópico, tema.

Comparação com o simulado anterior: o que errava e agora acerta, o que continua errando, o que apareceu de novo.

Decisão ou checkpoint associado: .

### Mini-simulado de reforço R1 — 13/10/2026

| Campo | Valor |
|---|---|
| Fonte | `praticas-reforco-dicas-recorrentes.md`, seção 6 |
| Tempo gasto | |
| Acertos | de 20 (meta: 15) |
| Chutes marcados | |
| Erros de forma nas lacunas | |

*A preencher na terça 13/10. A apuração por tema vai na tabela da seção 2.5.*

### Simulado #2 — 11/10/2026

| Campo | Valor |
|---|---|
| Fonte | `simulado-02` |
| Tempo gasto | |
| Acertos | de 40 |
| Meta | **24 ou mais** (Checkpoint A) |

*A preencher no domingo 11/10. Observação: o simulado vem antes da Prática 2 (permissões), então separe as questões de permissões na leitura.*

---

## 5. Índice de correções (1 a 72)

Total: **72 correções** em cinco semanas. O texto completo de cada uma está no arquivo da semana indicada. A numeração é global e contínua; a próxima é a **73**.

| Semana | Correções | Quantidade |
|---|---|---|
| 2 | 1 a 16 | 16 |
| 3 | 17 a 28 | 12 |
| 4 | 29 a 52 | 24 |
| 5 | 53 a 61 | 9 |
| 6 (simulado #1 e curso) | 62 a 72 | 11 |

Nota de 06/10: o fechamento da Semana 4 dizia "dez correções (43 a 52)". As correções da Semana 4 são, na verdade, 29 a 52, num total de 24, e a soma de 52 correções até a Semana 4 confere.

### Semana 2 — arquivo `semana-02-linha-de-comando.md`

| # | Tema | Origem |
|---|---|---|
| 1 | `cd ..` não é "anterior" | Sessão 1, 09/09 |
| 2 | Registro do `cd -` (voltou a `/var/log`) | Sessão 1 |
| 3 | `ls` lista o conteúdo do diretório atual; `ls -R` entra nos subdiretórios | Sessão 1 |
| 4 | `ls -h` sozinho não muda a listagem | Sessão 1 |
| 5 | `echo` exibe qualquer texto (o shell expande `$VAR` antes) | Sessão 1 |
| 6 | `/log` não existe: é `/var/log` | Pendência de 09/09 |
| 7 | O `echo $?` deve vir logo após o comando | Pendência de 09/09 |
| 8 | `type ls` = alias | Sessão 3, 10/09 |
| 9 | O `which ls` devolve `/usr/bin/ls`, com a barra inicial | Sessão 3 |
| 10 | Digitação: `/usr/share/doc`, não `/usr/share/odc` | Sessão 3 |
| 11 | Brace expansion `{01..20}` não é globbing | Sessão 4, 13/09 |
| 12 | Direção da herança de variáveis | Sessão 4 |
| 13 | O que o `grep` filtra | Sessão 4 |
| 14 | Digitação: `env | wc -l`, não `emv` | Sessão 4 |
| 15 | O `tar` empacota; a compressão é uma flag | Sessão 4 |
| 16 | O `history` lê `~/.bash_history` | Sessão 4 |

### Semana 3 — arquivo `semana-03-arquivos-e-links.md`

| # | Tema | Origem |
|---|---|---|
| 17 | `sources.list` → formato deb822 | Curso `.deb`, 15/09 |
| 18 | `apt upgrade` não "exclui o kernel" | Curso `.deb` |
| 19 | `dist-upgrade` não é upgrade de distribuição | Curso `.deb` |
| 20 | Sintaxe do `apt-get dist-upgrade` | Curso `.deb` |
| 21 | `apt update` atualiza o índice local | Curso `.deb` |
| 22 | Flags do `rpm -ivh` | Curso `.rpm`, 17/09 |
| 23 | `yum check-update` | Curso `.rpm` |
| 24 | `yum clean packages` | Curso `.rpm` |
| 25 | O `head` corta a listagem | FHS, 17/09 |
| 26 | `2> /dev/null`, com a barra | FHS, 17/09 |
| 27 | Hard link não é cópia | Autoavaliação, 19/09 |
| 28 | `apt-get -f install` conserta (não força) | Autoavaliação |

### Semana 4 — arquivo `semana-04-filtros-e-compactacao.md`

| # | Tema | Origem |
|---|---|---|
| 29 | O que o `2>&1` realmente faz | Semana 4 |
| 30 | Quem abre o arquivo no `<` é o shell, não o comando | Semana 4 |
| 31 | As linhas de `Permission denied` não eram arquivos encontrados | Semana 4 |
| 32 | `sort` sem `-n` é crescente, não decrescente | Semana 4 |
| 33 e 34 | O `-k` escolhe a coluna (*key*); não "separa" e não é "setor" | Semana 4 |
| 35 | O pipeline próprio traz o cabeçalho e responde outra pergunta | Semana 4 |
| 36 | `uniq -u` não "remove as duplicatas" | Semana 4 |
| 37 | A troca de shell vale no próximo login, não após reiniciar | Semana 4 |
| 38 | `$SHELL` mostra o shell configurado, não o que está rodando | Semana 4 |
| 39 | O `grep ERROR` não falhou por causa de maiúsculas | Semana 4 |
| 40 | `-f1,4` são as colunas 1 e 4, não "de 1 a 4" | Semana 4 |
| 41 | Um `.tar.bz2` com 0 bytes indica que o comando falhou | Semana 4 |
| 42 | A ordem de compressão está invertida | Semana 4 |
| 43 | `-size -1033c` não é "exatamente 1033 bytes" | Semana 4 |
| 44 | O `-o` do `find` não distribui os filtros anteriores | Semana 4 |
| 45 | `/etc/passwd` é um arquivo; o último `sort -rn` ordena pela contagem | Semana 4 |
| 46 | No `-exec`, o `wc -l` conta as linhas dentro de cada arquivo | Semana 4 |
| 47 | `tail -n +2` descarta o cabeçalho; o `sort -u` não é o `uniq` | Semana 4 |
| 48 | O `2>/dev/null` não vem "após o pipe" | Semana 4 |
| 49 | `grep -v` é *invert*, não *verbose* | Autoavaliação, 29/09 |
| 50 | `sort` sem `-n` não inverte a ordem (quarta ocorrência) | Autoavaliação |
| 51 | Os dois significados do `^` e a posição que os distingue | Autoavaliação |
| 52 | O `-f` do `tar` vem por último porque consome o argumento seguinte | Autoavaliação |

### Semana 5 — arquivo `semana-05-shell-script.md`

| # | Tema | Origem |
|---|---|---|
| 53 | `..` é o diretório pai, não o "anterior" (quarta ocorrência) | Curso, 30/09 |
| 54 | `~` e `cd` sem argumento levam ao diretório pessoal, não a `/home` | Curso |
| 55 | A variável é `$PWD`, em maiúsculas; o `cd -` depende de `$OLDPWD` | Curso |
| 56 | `uname -a` não traz a distribuição, e o `-o` também não | Curso |
| 57 | O `$PATH` é uma lista de onde procurar, não "armazena comandos" | Curso |
| 58 | `runlevel` mostra o anterior e o atual; o nível não muda por "comandos de desligamento" | Curso |
| 59 | `whoami` e `$USER` respondem à mesma pergunta por fontes diferentes | Curso |
| 60 | O `./` e o `Permission denied` têm causas diferentes | Laboratório 1, bloco 1, 02/10 |
| 61 | O `2` do `2>` e o `2` do `$?` não têm relação | Laboratório 1, bloco 5, 04/10 |

### Semana 6 — arquivo `semana-06-permissoes.md` (simulado #1 e curso)

| # | Tema | Questão |
|---|---|---|
| 62 | O *upstream* do RHEL é o Fedora, não o Debian | Q3 |
| 63 | Contêiner compartilha o kernel; a máquina virtual tem o seu | Q7 |
| 64 | `..` sobe na árvore, `-` volta no histórico (quinta ocorrência) | Q10 |
| 65 | `/usr` não é *user* | Q14 |
| 66 | `/proc` é de processos, `/dev` é de dispositivos | Q15 |
| 67 | `man` é o manual; o `--manual` não existe no `cp` | Q16 |
| 68 | `chmod` muda permissões, `chown` muda o dono | Q38 |
| 69 | `~/.bashrc` é de shell interativo sem login, e a diferença é login ou não | Curso, 08/10 |
| 70 | `?` casa um caractere qualquer; `{}` não é globbing (2ª ocorrência da Correção 11) | Curso, 08/10 |
| 71 | Variáveis exportadas são herdadas por processos filhos; `set` mostra tudo, `env` só as exportadas (2ª ocorrência da Correção 12) | Curso, 08/10 |
| 72 | `\` escapa um caractere e não produz `\n`; aspas duplas ainda expandem | Curso, 08/10 |

O Laboratório 2 (06/10) não gerou correção numerada: não houve erro conceitual.

---

## 6. Erros que se repetiram

| Erro | Ocorrências | Correções | Mecanismo |
|---|---|---|---|
| `cd ..` e `cd -` trocados | **5** | 1, 53 e 64 | `..` é o pai (espaço); `-` é o anterior (tempo) |
| `sort` sem `-n` descrito como "invertendo a ordem" | **4** | 32, 33 e 34, 50 | As duas formas são crescentes; só o `-r` inverte; `-k` é coluna |
| Resultado certo pelo motivo errado (`2>&1`, hard link, `-f` do `tar`) | 3 | 29, 27, 52 | O resultado certo pelo motivo errado quebra quando a pergunta muda de ângulo |
| Direção da herança de variáveis (pai para filho) | 2 | 12 e 71 | A variável exportada vai para o **processo filho**, nunca para "outras sessões" |
| `{}` tratado como globbing | 2 | 11 e 70 | A expansão de chaves cria nomes antes do comando, sem olhar o disco; o globbing só enxerga o que já existe |
| `grep -v` entendido como *verbose* | 1 | 49 | É *invert*; no `grep` é a exceção, nos demais comandos o `-v` é *verbose* |

**Padrão novo, do simulado #1:** nos Tópicos 1 e 2, a confiança foi maior que o acerto. Seis dos sete erros com convicção caíram neles.

**Situação desde 06/10:** estes erros estão na retaguarda (seção 7). Os simulados dizem se eles voltam.

---

## 7. Fila de retaguarda

Itens antigos de conteúdo já estudado, tirados da rotina diária em 06/10 para não competir com o conteúdo novo. Cada item volta **nos simulados** e na **revisão leve da Semana 10** (segunda 02/11 a quarta 04/11), pelos cards do Notion.

| Item | Origem | Observação |
|---|---|---|
| Correções 62 a 67 (Tópicos 1 e 2 do simulado #1) | Semana 6 | A Correção 68 (`chmod` e `chown`) é do Tópico 5 e continua ativa |
| `cd ..` e `cd -` | Correções 1, 53 e 64 | Quinta ocorrência; o simulado mede se volta |
| Reteste das quatro questões erradas da autoavaliação da Semana 4 | Semana 4 | Correções 49 a 52 |
| Reteste das questões 18, 20, 21, 22 e 24 do simulado #1 | Semana 5 | A 22 foi acerto por chute |
| Comparação de compressão com o `bzip2` | Semana 4 | Primeiro corte da fila; sem registro em 06/10 |
| Saídas do `teste.sh` e das três saídas de `vi` e `nano` | Semana 5 | Primeiro corte da fila; sem registro em 06/10 |
| `.wslconfig` limitando o WSL2 a 3 GB | Semana 0 | Sem prazo |
| Teste de restauração do snapshot | Semana 0 | Sem prazo |

**O que não está na retaguarda:** o conteúdo atual. Tópico 5 (Semana 6) e Tópico 4 (Semana 7) permanecem no aquecimento e nas práticas, inclusive os chutes errados e o par `chmod` e `chown`.

---

## 8. Notion: controle das correções

| Item | Estado |
|---|---|
| Correções 60 a 68 | Cards anotados em 05/10, conforme informado |
| Questões erradas do simulado #1 | Correções 62 a 68 anotadas; os cinco chutes errados viram ênfase de estudo, sem card |
| Correções 69 a 72 (curso, 08/10) | A anotar no Notion |
| Questões erradas do simulado #2 | A corrigir no Notion no mesmo dia do simulado (11/10) |

---

## 9. Histórico deste documento

| Data | Alteração |
|---|---|
| 06/10/2026 | Criação. Reúne o simulado #1, as autoavaliações, os checkpoints, o índice das correções 1 a 68, os erros recorrentes e a fila de retaguarda. Registra as regras de 06/10 (só anotar questões erradas; correção no Notion; retaguarda de erros antigos) |
| 06/10/2026 | Acrescentadas a seção 2.5 (dicas recorrentes por tema) e o registro do mini-simulado de reforço R1 na seção 4 |
| 08/10/2026 | Correções 69 a 72 (curso, 08/10); pré-checkpoint com a compra do voucher adiada (gatilho: média dos três últimos simulados ≥ 30); simulado #2 de volta ao domingo 11/10; autoavaliação da Semana 5 na sexta 09/10 |