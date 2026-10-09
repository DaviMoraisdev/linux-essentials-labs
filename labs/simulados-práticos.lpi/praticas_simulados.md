# Reforço das dicas recorrentes de prova — LPI Linux Essentials (010-160)

**Criado em:** 06/10/2026 · **Origem das dicas:** relato de candidatos, encontrado por você na internet (fonte não oficial)

Este arquivo reúne as quatro dicas recorrentes, o que o plano já cobre de cada uma, as regras para as questões de preenchimento e o primeiro **mini-simulado de reforço (R1)**, com 20 questões e gabarito comentado. O resultado de cada reforço é registrado em `praticas-resultados-simulados-e-correcoes.md`, seções 2.5 e 4.

---

## 1. As dicas e a verificação contra o material oficial

As dicas não são oficiais, então foram conferidas contra o PDF da LPI (versão 1.6) e contra o histórico do plano.

| Dica | Está no material oficial? | Onde o plano já cobre | Lacuna a fechar |
|---|---|---|---|
| Permissões, com r = 4, w = 2, x = 1 | Sim, lição 5.3 | Aquecimento diário e Prática 2 da Semana 6; Correção 68 | Medir nos simulados, não só no aquecimento |
| `tar` e flags de compressão | Sim, lição 3.1 | Semana 4; Correções 15, 41, 42 e 52; Q22 do simulado #1 foi **acerto por chute** | Está na retaguarda. Volta pelos simulados e por este reforço |
| Redirecionamento `>`, `>>`, `2>`, `<<` | Sim, lição 3.2: o PDF traz a seção "Here documents" | Semana 4 e Correção 29; Correção 30 | O `<<` foi usado muitas vezes para criar arquivos, mas **nunca estudado como conceito** |
| `/proc`, `/sys`, `/dev`, `/var` | Sim: `/proc`, `/dev` e `/sys` na lição 4.3; `/var` no FHS | `/proc` e `/dev` na Semana 3; Correção 66 (Q15 errada); `/sys` só entra na Semana 7 | Praticar o mapa dos quatro lado a lado |
| Questões de preencher a lacuna | Formato do exame | Q11 do simulado #1 (resposta `PATH` com sublinhado) | Nunca foram treinadas como formato; entram a partir do simulado #2 |

**Leitura.** A dica sobre `<<` e a dica sobre lacunas apontam os dois pontos onde o plano estava mais fino. As outras duas confirmam que o plano já está no caminho, e agora ganham um número mínimo de questões por simulado.

---

## 2. Como o reforço entra no plano

### 2.1 Número mínimo de questões por tema, a partir do simulado #2

Os temas se sobrepõem às questões dos cinco tópicos; não são questões extras.

| Tema | Mínimo por simulado | Observação |
|---|---|---|
| Permissões (octal, simbólico, `chmod`, `chown`, SUID, SGID e sticky bit) | 4 | Incluir conversão nos dois sentidos |
| `tar` e compressão (`-c`, `-x`, `-t`, `-z`, `-j`, `-J`, `-f`, extensões) | 2 | Incluir a ordem do `-f` |
| Redirecionamento (`>`, `>>`, `2>`, `<`, `<<`, `&>`, `2>&1`) | 3 | Incluir `<<` com o delimitador |
| Diretórios virtuais e `/var` (`/proc`, `/sys`, `/dev`, `/var`) | 3 | Incluir pelo menos uma de contraste, como `/proc` contra `/dev` |
| **Preenchimento de lacuna** (resposta digitada) | **5** | Qualquer tópico |

### 2.2 Onde cada reforço acontece

| Quando | O que | Tempo |
|---|---|---|
| Qui 08/10 | Pedir o `simulado-02` com as quatro exigências da seção 3 | 2 min |
| Dom 11/10 | Simulado #2 já traz o mínimo da seção 2.1; apurar o desempenho por tema | dentro do simulado |
| **Ter 13/10** | **Mini-simulado R1** (20 questões, 25 min) e apuração (10 min). Substitui o aquecimento do dia | 35 min, sendo 25 novos |
| Prática 1 da Semana 7 | Mapa dos diretórios virtuais: `/proc`, `/sys`, `/dev` lado a lado, com `cat` de um arquivo de cada | dentro da Prática 1 |
| **Ter 20/10** | **Mini-simulado R2**, pedido até sex 16/10: inclui `/sys`, rede e processos da Semana 7 | 35 min |
| Semanas 8 e 9 | Aquecimento rotativo pelas cinco frentes (seção 2.3) | 10 min/dia, como hoje |

### 2.3 Aquecimento rotativo (a partir de 19/10)

| Dia | Frente do aquecimento |
|---|---|
| Segunda | Permissões: cinco conversões cronometradas |
| Terça | `tar`: cinco comandos de montar, listar e extrair, escritos à mão |
| Quarta | Redirecionamento: cinco linhas, incluindo `<<` e `2>&1` |
| Quinta | Mapa dos diretórios: cinco perguntas "onde fica ...?" |
| Sexta | Lacunas: cinco frases para completar com **uma palavra** |

Nos dias de simulado, o simulado substitui o aquecimento, como já é a regra.

---

## 3. Instrução para pedir o `simulado-02` (e os seguintes)

Acrescente ao pedido, além do que já está definido (mais difícil, com cenário, pegadinhas, múltipla resposta e distratores plausíveis):

1. Incluir o mínimo de questões por tema da seção 2.1.
2. Incluir **5 questões de preencher a lacuna**, com resposta de uma palavra ou de um comando curto.
3. Colocar uma **tabela de temas no gabarito**: número da questão, tema da seção 2.1 e tópico do exame.
4. Fazer as questões de preenchimento aceitarem uma única grafia correta, sem ambiguidade, e dizer qual.

---

## 4. Regras para as questões de preencher a lacuna

O exame de preenchimento compara o que você digitou com a resposta esperada. Por isso:

1. **Escreva só o que foi pedido.** Se a pergunta é "qual comando", digite o comando, sem caminho (`chown`, não `/usr/bin/chown`) e sem flags, salvo se a pergunta pedir as flags.
2. **Nada de enfeite.** Sem sublinhado, sem `$`, sem aspas, sem ponto final. No simulado #1, a Q11 foi respondida com um sublinhado na frente de `PATH`.
3. **Maiúsculas e minúsculas contam.** No Linux, `PATH` e `path` são nomes diferentes; o comando é sempre em minúsculas.
4. **Leia o que a lacuna pede.** "O diretório ____" pode pedir `/proc` ou só `proc`, conforme a barra já estar no enunciado. Se a barra está escrita antes da lacuna, não repita.
5. **Não tem alternativa para dar dica.** Responda de memória antes de olhar qualquer coisa; é um formato em que o acerto por chute é quase impossível, então o resultado é um retrato fiel do que você sabe.
6. **Se travou, escreva o que você acha que é.** Lacuna em branco vale zero; palpite tem alguma chance.

---

## 5. Cola das quatro frentes

### 5.1 Permissões

| Símbolo | Valor |
|---|---|
| `r` | 4 |
| `w` | 2 |
| `x` | 1 |

Cada dígito soma os valores de um grupo, na ordem **dono, grupo, outros**. Exemplos: `rwxr-x--x` = 751; `rw-r--r--` = 644; `rwxrwxrwx` = 777.

`chmod` muda permissões; `chown` muda dono e grupo (`chown dono:grupo arquivo`); `chgrp` muda só o grupo.

### 5.2 `tar` e compressão

| Quero | Comando |
|---|---|
| Criar com gzip | `tar -czf nome.tar.gz diretório/` |
| Criar com bzip2 | `tar -cjf nome.tar.bz2 diretório/` |
| Criar com xz | `tar -cJf nome.tar.xz diretório/` |
| Listar o conteúdo | `tar -tf nome.tar` (ou `-tzf`, `-tjf`) |
| Extrair | `tar -xzf nome.tar.gz` (ou `-xjf`, `-xJf`) |

O `-f` vai **por último** entre as flags, porque consome o argumento seguinte: o nome do arquivo. O `tar` empacota; quem comprime é a flag `z`, `j` ou `J`. O `gzip arquivo` cria `arquivo.gz` e **remove** o original.

### 5.3 Redirecionamento

| Operador | Efeito |
|---|---|
| `>` | Saída padrão para um arquivo; **sobrescreve** |
| `>>` | Saída padrão para um arquivo; **acrescenta** |
| `2>` | Saída de erro para um arquivo; sobrescreve |
| `<` | Um arquivo vira a entrada do comando |
| `<<` | *Here document*: as linhas seguintes, até o delimitador, viram a entrada |
| `&>` | Saída e erro para o mesmo arquivo |
| `> arq 2>&1` | Saída e erro no arquivo (a **ordem** importa) |

No `<< FIM`, a palavra `FIM` é só o **delimitador**: ela não é exibida nem entra no conteúdo.

### 5.4 Diretórios virtuais e `/var`

| Diretório | O que guarda |
|---|---|
| `/proc` | Sistema de arquivos virtual: processos (um diretório por PID), CPU (`/proc/cpuinfo`), memória (`/proc/meminfo`) e configuração do kernel (`/proc/sys`) |
| `/sys` | `sysfs`: informações sobre dispositivos de hardware, organizadas em categorias (por exemplo, `/sys/class/net/enp0s3/address`) |
| `/dev` | Arquivos de dispositivo (blocos como `/dev/sda1`, caracteres como `/dev/tty`) e especiais (`/dev/null`, `/dev/zero`, `/dev/urandom`) |
| `/var` | Dados **variáveis**: logs em `/var/log`, filas em `/var/spool`, cache em `/var/cache`, temporários que sobrevivem ao reinício em `/var/tmp` |

Mnemônico: **proc de processos, dev de dispositivos, sys de hardware organizado, var de variável.**

---

## 6. Mini-simulado R1 — Terça 13/10

**Regras:** 20 questões, 25 minutos, sem consulta, **marcando cada chute**. Nas questões de preenchimento (marcadas com **[lacuna]**), escreva só a resposta, seguindo a seção 4. Aberto o gabarito, anote apenas as erradas e as chutadas, corrija no Notion e registre o resultado em `praticas-resultados-simulados-e-correcoes.md`, seções 2.5 e 4.

**Metas:** 15 de 20 (75%) é o mínimo. A leitura mais importante é o **acerto por tema**: um tema abaixo de 60% vira o foco do aquecimento da semana seguinte.

### Permissões

**1.** Qual é a representação octal de `-rwxr-x--x`?

A) 755 · B) 751 · C) 741 · D) 651

**2.** Um arquivo tem permissão `640`. Depois de `chmod g+w,o+r arquivo`, a permissão será:

A) 664 · B) 666 · C) 660 · D) 644

**3. [lacuna]** O comando que altera o **dono** de um arquivo é: ______

**4.** Um usuário tem apenas `r--` sobre um diretório. Qual afirmação é verdadeira?

A) Ele consegue entrar no diretório com `cd` e listar os nomes
B) Ele consegue listar os nomes, mas não entrar com `cd` nem ver os detalhes dos arquivos
C) Ele consegue entrar, mas não listar
D) Ele não consegue fazer nada com o diretório

**5.** O que significa o `s` em `-rwsr-xr-x`?

A) O arquivo é compartilhado em rede
B) O arquivo executa com as permissões do **dono**
C) O arquivo executa com as permissões do grupo
D) Só o dono pode apagar o arquivo

### tar e compressão

**6.** Qual comando cria um arquivo compactado com gzip chamado `docs.tar.gz` a partir do diretório `docs`?

A) `tar -czf docs.tar.gz docs/`
B) `tar -cjf docs.tar.gz docs/`
C) `tar -xzf docs.tar.gz docs/`
D) `tar -czf docs/ docs.tar.gz`

**7. [lacuna]** Para **listar** o conteúdo de `backup.tar` sem extrair, completando o comando `tar -__f backup.tar`, a letra que falta é: ______

**8.** Qual flag do `tar` comprime com **bzip2**?

A) `-z` · B) `-j` · C) `-J` · D) `-b`

**9.** O que acontece ao executar `gzip arq.txt` em um diretório com o arquivo `arq.txt`?

A) Cria `arq.txt.gz` e mantém `arq.txt`
B) Cria `arq.txt.gz` e remove `arq.txt`
C) Cria `arq.gz`, sem a extensão original
D) Cria um diretório `arq.txt` com o arquivo comprimido

### Redirecionamento

**10.** Sequência: `echo a > f` · `echo b >> f` · `echo c > f` · `cat f`. Qual é a saída?

A) `a`, `b` e `c` em três linhas
B) `a` e `b`
C) `c`
D) `b` e `c`

**11.** O comando `ls /etc /naoexiste 2> erros.txt` grava em `erros.txt`:

A) A listagem de `/etc` e a mensagem de erro
B) Apenas a mensagem de erro
C) Apenas a listagem de `/etc`
D) Nada: o `2>` só funciona com `>`

**12.** No comando abaixo, qual é o papel da palavra `FIM`?

```
cat << FIM
primeira linha
segunda linha
FIM
```

A) É o nome do arquivo criado
B) É o delimitador que encerra a entrada; não faz parte do conteúdo
C) É o texto que o `cat` imprime primeiro
D) É uma variável do shell

**13. [lacuna]** O operador que **acrescenta** a saída ao final de um arquivo, sem apagar o conteúdo, é: ______

**14.** Qual é o efeito de `ls /etc /nao > t.txt 2>&1`?

A) Só a saída normal vai para `t.txt`; o erro aparece no terminal
B) Saída normal e erro vão para `t.txt`
C) Cria um arquivo chamado `1`
D) Só o erro vai para `t.txt`

### Diretórios virtuais e /var

**15.** Qual diretório contém um subdiretório numerado para cada processo em execução?

A) `/dev` · B) `/var` · C) `/proc` · D) `/etc`

**16. [lacuna]** O diretório que guarda os arquivos de dispositivo, como `sda` e `tty`, é: /______

**17.** Onde ficam, normalmente, os arquivos de log do sistema?

A) `/etc/log` · B) `/var/log` · C) `/proc/log` · D) `/usr/log`

**18.** Sem usar nenhum comando de hardware, onde se lê as informações da CPU diretamente?

A) `/dev/cpu` · B) `/var/cpuinfo` · C) `/proc/cpuinfo` · D) `/etc/cpuinfo`

### Lacunas gerais

**19. [lacuna]** O comando que exibe o caminho completo do diretório atual é: ______

**20. [lacuna]** A variável de ambiente que guarda a lista de diretórios onde o shell procura comandos é: ______

---

## 7. Gabarito comentado do R1

| Q | Tema | Tópico | Resposta | Por quê |
|---|---|---|---|---|
| 1 | Permissões | 5.3 | **B** (751) | dono `rwx` = 7, grupo `r-x` = 5, outros `--x` = 1 |
| 2 | Permissões | 5.3 | **A** (664) | `640` com `g+w` vira `660`; com `o+r` vira `664` |
| 3 | Permissões | 5.3 | **chown** | `chmod` muda permissões; `chown` muda dono. É a Correção 68 |
| 4 | Permissões | 5.3 | **B** | O `r` lista os nomes. Sem `x`, não se atravessa o diretório: nem `cd`, nem acesso aos detalhes |
| 5 | Permissões | 5.3 | **B** | `s` no lugar do `x` do dono é o SUID: o programa roda com as permissões do dono |
| 6 | tar | 3.1 | **A** | `c` cria, `z` gzip, `f` por último com o nome. B usa `j` (bzip2); C extrai; D inverte a ordem |
| 7 | tar | 3.1 | **t** | `-tf` lista. `-cf` cria e `-xf` extrai |
| 8 | tar | 3.1 | **B** | `j` é bzip2; `z` é gzip; `J` (maiúsculo) é xz |
| 9 | Compressão | 3.1 | **B** | O `gzip` substitui o original pelo `.gz`. Para manter, use `gzip -k` |
| 10 | Redirecionamento | 3.2 | **C** | O `>` do terceiro comando sobrescreve o arquivo; só `c` sobra |
| 11 | Redirecionamento | 3.2 | **B** | `2>` redireciona só o canal de erro (stderr, canal 2) |
| 12 | Redirecionamento | 3.2 | **B** | No *here document*, a palavra depois do `<<` é o delimitador; o `cat` mostra só as linhas entre as marcas |
| 13 | Redirecionamento | 3.2 | **>>** | O `>` sobrescreve; o `>>` acrescenta |
| 14 | Redirecionamento | 3.2 | **B** | `> t.txt` aponta o canal 1 para o arquivo; `2>&1` aponta o 2 para onde o 1 está. É a Correção 29 |
| 15 | Diretórios | 4.3 | **C** | `/proc` tem um diretório por PID. É a Correção 66 |
| 16 | Diretórios | 4.3 | **dev** | A barra já está no enunciado; escreva só `dev` |
| 17 | Diretórios | 2 (FHS) | **B** | `/var` guarda dados variáveis; os logs ficam em `/var/log` |
| 18 | Diretórios | 4.3 | **C** | `/proc/cpuinfo`. Para memória, `/proc/meminfo` |
| 19 | Lacuna geral | 2 | **pwd** | *Print working directory* |
| 20 | Lacuna geral | 2 | **PATH** | Em maiúsculas, sem sublinhado e sem `$`. É a Q11 do simulado #1 |

**Verificação:** os comandos das questões 2, 6, 9, 10, 11, 12 e 14 foram executados em um shell antes de fechar o gabarito, e as saídas conferem.

### Apuração por tema

| Tema | Questões | Acertos | Chutes acertados |
|---|---|---|---|
| Permissões | 1 a 5 | /5 | |
| `tar` e compressão | 6 a 9 | /4 | |
| Redirecionamento | 10 a 14 | /5 | |
| Diretórios virtuais e `/var` | 15 a 18 | /4 | |
| Lacunas gerais | 19 e 20 | /2 | |
| **Todas as questões [lacuna]** | 3, 7, 13, 16, 19, 20 | /6 | |
| **Total** | | /20 | |

---

## 8. R2 — Terça 20/10 (a pedir até sexta 16/10)

Mesmo formato, 20 questões, 25 minutos. Conteúdo: as quatro frentes de novo, com **`/sys` incluído** e questões sobre `top`, `kill` e sinais, `free` e rede da Semana 7, mais 6 lacunas. Peça com a mesma instrução da seção 3.

---

## 9. Histórico

| Data | Alteração |
|---|---|
| 06/10/2026 | Criação, a partir das dicas recorrentes trazidas por Davi. Verificação contra o PDF oficial; mini-simulado R1; regras de lacuna; cola das quatro frentes |