# Reforço das dicas recorrentes de prova — LPI Linux Essentials (010-160)

**Criado em:** 06/10/2026 · **Origem das dicas:** relato de candidatos, encontrado por você na internet (fonte não oficial)

Este arquivo reúne as quatro dicas recorrentes, o que o plano já cobre de cada uma, as regras para as questões de preenchimento e o primeiro **mini-simulado de reforço (R1)**, com 20 questões e gabarito comentado. O resultado de cada reforço é registrado em `resultados_simulados.md`, seções 2.5 e 4.

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
| Sáb 24/10 | Simulado 02 já traz o mínimo da seção 2.1; apurar o desempenho por tema | dentro do simulado |
| Qua 21/10 | Prática 3 (Semana 8): mapa dos diretórios virtuais, `/proc`, `/sys` e `/dev` lado a lado | dentro da Prática 3 |
| Seg 26/10 | Here document estudado como conceito, no bloco curto | 15 min |
| **Ter 27/10** | **Mini-simulado R2** (seção 8): inclui `/sys`, rede e processos | 35 min |
| **Qua 28/10** | **Mini-simulado R1** (20 questões, 25 min) e apuração (10 min) | 35 min |
| Semanas 9 a 11 | Aquecimento rotativo pelas cinco frentes (seção 2.3), nos dias sem simulado | 10 min/dia |

### 2.3 Aquecimento rotativo (a partir de 26/10)

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

## 6. Mini-simulado R1 — Quarta 28/10

**Regras:** 20 questões, 25 minutos, sem consulta, **marcando cada chute**. Nas questões de preenchimento (marcadas com **[lacuna]**), escreva só a resposta, seguindo a seção 4. Aberto o gabarito, anote apenas as erradas e as chutadas, corrija no Notion e registre o resultado em `resultados_simulados.md`, seções 2.5 e 4.

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

## 8. Mini-simulado R2 — Terça 27/10

**Regras:** as mesmas do R1. 20 questões, 25 minutos, sem consulta, **marcando cada chute**. Nas questões **[lacuna]**, escreva só a resposta, seguindo a seção 4. Registre o resultado em `resultados_simulados.md`, seções 2.5 e 4.

**Metas:** 15 de 20. Além das quatro frentes, o R2 cobre o que a Semana 8 acrescentou: `/sys`, processos e rede. Nenhuma questão repete o R1.

### Permissões

**1.** Depois de `chmod 750 projeto`, em que `projeto` é um diretório, como ele aparece no `ls -ld`?

- A) `drwxr-x---`
- B) `drwxr-xr-x`
- C) `drwx-----x`
- D) `drw-r-x---`

**2. [lacuna]** Em um diretório com sticky bit, se os outros têm permissão de execução, a letra que aparece no lugar do `x` deles é: ______

**3.** O que significa o `S` maiúsculo em `-rwSr--r--`?

- A) O SGID está ligado e o grupo tem `x`
- B) O SUID está ligado, mas o dono não tem `x`
- C) O arquivo é um socket
- D) O sticky bit está ligado

**4.** Um arquivo tem permissão `755`. Qual é a permissão depois de `chmod o-rwx arquivo`?

- A) `700`
- B) `750`
- C) `754`
- D) `705`

### `tar` e compressão

**5.** Qual comando extrai `site.tar.gz` **dentro do diretório** `/tmp/site`, sem precisar entrar nele antes?

- A) `tar -xzf site.tar.gz /tmp/site`
- B) `tar -xzf site.tar.gz -C /tmp/site`
- C) `tar -czf site.tar.gz -C /tmp/site`
- D) `tar -xzf /tmp/site site.tar.gz`

**6. [lacuna]** O comando que descomprime um arquivo `.gz`, o par do `gzip`, é: ______

**7.** Qual comando cria o arquivo `docs.zip` com o diretório `docs` e tudo o que há dentro dele?

- A) `zip docs.zip docs`
- B) `zip -r docs.zip docs`
- C) `unzip -r docs.zip docs`
- D) `tar -zip docs.zip docs`

### Redirecionamento

**8.** O que faz `ls /etc /naoexiste &> tudo.txt`?

- A) Grava só a listagem de `/etc` em `tudo.txt`
- B) Grava só a mensagem de erro em `tudo.txt`
- C) Grava a listagem e a mensagem de erro em `tudo.txt`
- D) Executa o `ls` em segundo plano e grava a saída em `tudo.txt`

**9.** O que faz `sort < nomes.txt > ordenados.txt`?

- A) Ordena `ordenados.txt` e grava em `nomes.txt`
- B) Lê `nomes.txt`, ordena e grava o resultado em `ordenados.txt`
- C) Dá erro: não se pode usar `<` e `>` no mesmo comando
- D) Acrescenta `nomes.txt` ao final de `ordenados.txt`

**10. [lacuna]** O operador que entrega a um comando várias linhas escritas no próprio script, até uma palavra delimitadora, é: ______

### Diretórios

**11.** Em qual caminho cada interface de rede aparece como um subdiretório, organizado pelo kernel?

- A) `/proc/net/dev`
- B) `/sys/class/net`
- C) `/dev/net`
- D) `/etc/network`

**12. [lacuna]** O diretório que guarda o kernel e o `initramfs` é: /______

**13.** Em uma distribuição Debian, onde fica o banco de dados que registra os pacotes instalados?

- A) `/etc/apt`
- B) `/var/cache/apt`
- C) `/var/lib/dpkg`
- D) `/usr/share/doc`

### Processos

**14.** Dentro do `top`, qual tecla ordena os processos por uso de memória?

- A) `P`
- B) `M`
- C) `k`
- D) `q`

**15.** Qual é a diferença entre `kill 1234` e `kill -9 1234`?

- A) Nenhuma: os dois enviam `SIGKILL`
- B) O primeiro envia `SIGTERM`, que o processo pode tratar; o segundo envia `SIGKILL`, que não pode ser tratado nem ignorado
- C) O primeiro suspende o processo; o segundo o encerra
- D) O primeiro encerra o processo 1234; o segundo encerra os 9 primeiros processos

**16. [lacuna]** O comando que lista os trabalhos (*jobs*) iniciados no shell atual é: ______

**17.** No `free -h`, o que a coluna `available` representa?

- A) A memória que nunca foi usada desde o boot
- B) A memória que pode ser entregue a novos programas sem recorrer à swap, contando o cache que pode ser liberado
- C) O tamanho da swap
- D) A memória reservada para o kernel

### Rede

**18.** O `/etc/resolv.conf` da VM tem a linha `nameserver 127.0.0.53`. O que ela significa?

- A) O DNS da VM está desligado
- B) As consultas de DNS vão para um resolvedor local, que roda na própria máquina
- C) A VM só consegue resolver os nomes do `/etc/hosts`
- D) O IP da VM é `127.0.0.53`

**19.** Qual é a diferença entre `host lpi.org` e `ping -c 1 lpi.org`?

- A) Nenhuma: os dois só consultam o DNS
- B) O `host` consulta o DNS e mostra o endereço; o `ping` resolve o nome e testa se a máquina responde
- C) O `host` testa a conectividade; o `ping` consulta o DNS
- D) O `ping` só funciona com endereços IP

**20. [lacuna]** O comando atual que substitui o `ifconfig` e o `route` é: ______

---

### Gabarito comentado do R2

<details>
<summary>Abra só depois de responder</summary>

| Q | Tema | Tópico | Resposta | Por quê |
|---|---|---|---|---|
| 1 | Permissões | 5.3 | **A** | 7 = `rwx`, 5 = `r-x`, 0 = `---`, com o `d` de diretório |
| 2 | Permissões | 5.4 | **t** | `t` minúsculo: sticky ligado e `x` presente. Sem o `x`, seria `T` |
| 3 | Permissões | 5.3 | **B** | `S` maiúsculo no lugar do `x` do dono: SUID ligado sem permissão de execução |
| 4 | Permissões | 5.3 | **B** | Os outros perdem tudo: `r-x` vira `---` |
| 5 | tar | 3.1 | **B** | O `-C` muda para o diretório antes de extrair. Na A, `/tmp/site` seria tratado como um item a extrair |
| 6 | Compressão | 3.1 | **gunzip** | Equivale a `gzip -d` |
| 7 | Compressão | 3.1 | **B** | O `zip` precisa do `-r` para entrar no diretório. O `unzip` extrai |
| 8 | Redirecionamento | 3.2 | **C** | O `&>` manda os fluxos 1 e 2 para o mesmo arquivo, como `> tudo.txt 2>&1` |
| 9 | Redirecionamento | 3.2 | **B** | O shell abre `nomes.txt` como entrada e `ordenados.txt` como saída antes de o `sort` rodar |
| 10 | Redirecionamento | 3.2 | **<<** | O *here document*. Não confundir com `<`, que lê de um arquivo |
| 11 | Diretórios | 4.3 | **B** | `/sys/class/net` traz um diretório por interface (`lo`, `enp0s3`) |
| 12 | Diretórios | 4.3 | **boot** | A barra já está no enunciado |
| 13 | Diretórios | 4.3 | **C** | O `/var/cache/apt` guarda os `.deb` baixados, não o registro do que está instalado |
| 14 | Processos | 4.3 | **B** | `M` memória, `P` CPU, `k` encerra, `q` sai |
| 15 | Processos | 4.3 | **B** | Sem número, o `kill` envia `SIGTERM` (15) |
| 16 | Processos | 4.3 | **jobs** | — |
| 17 | Processos | 4.3 | **B** | O `free` coloca no `available` também o cache que o kernel libera quando precisa |
| 18 | Rede | 4.4 | **B** | No Ubuntu, `127.0.0.53` é o `systemd-resolved`, que repassa as consultas aos servidores reais |
| 19 | Rede | 4.4 | **B** | O `ping` também resolve o nome, mas o objetivo dele é testar a conectividade |
| 20 | Rede | 4.4 | **ip** | `ip addr show` substitui o `ifconfig`; `ip route show` substitui o `route` |

### Apuração por tema

| Tema | Questões | Acertos | Chutes acertados |
|---|---|---|---|
| Permissões | 1 a 4 | /4 | |
| `tar` e compressão | 5 a 7 | /3 | |
| Redirecionamento | 8 a 10 | /3 | |
| Diretórios virtuais e `/var` | 11 a 13 | /3 | |
| Processos | 14 a 17 | /4 | |
| Rede | 18 a 20 | /3 | |
| **Todas as questões [lacuna]** | 2, 6, 10, 12, 16, 20 | /6 | |
| **Total** | | /20 | |

</details>

---

## 9. Histórico

| Data | Alteração |
|---|---|
| 06/10/2026 | Criação, a partir das dicas recorrentes trazidas por Davi. Verificação contra o PDF oficial; mini-simulado R1; regras de lacuna; cola das quatro frentes |
| 13/10/2026 | Nova estratégia (prova em 23/11): R1 movido para sex 23/10, depois do Tópico 4; R2 para ter 27/10; aquecimento rotativo a partir de 26/10; simulado 02 escrito com os mínimos por tema |
| 18/10/2026 | Mini-simulado R2 escrito, com processos, rede e `/sys` |
| 19/10/2026 | R1 remarcado para qua 28/10, depois do R2, para o simulado 02 caber no sábado 24/10 |