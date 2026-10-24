# Reforços R3 e R4 — erros do simulado 02 — LPI Linux Essentials (010-160)

**Criado em:** 23/10/2026 · **Quando:** domingo 25/10 · **Origem:** os 14 erros do simulado 02 em conteúdo já estudado (`simulado-02.md`, seção "Questões erradas")

Os dois reforços atacam os blocos em que o simulado 02 concentrou os erros: **navegação, ajuda e redirecionamento** (R3, Tópicos 1 a 3) e **contas e permissões** (R4, Tópico 5). As questões **não repetem** as do simulado 02: testam o mesmo mecanismo por outro ângulo, porque é assim que o exame cobra. Quem decorou a resposta da questão anterior erra; quem entendeu o mecanismo acerta.

## Regras

| Item | Valor |
| --- | --- |
| Formato | 20 questões cada, **25 minutos** cada, cronometrados |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem Notion, sem internet. **Questão pesquisada conta como errada** |
| Ordem | R4 primeiro (o tópico mais fraco), depois R3, com 10 minutos de intervalo |
| Meta | **16 de 20 em cada um** (80%) |
| Chutes | Marque cada um, mesmo acertando |
| Escolha duas | Só conta se as duas estiverem certas |

**Dificuldade.** Mais perto do exame que os reforços R1 e R2: cinco alternativas, enunciados com cenário, saída de comando para interpretar e lacunas com a instrução que a prova usa: *"escreva só o comando, sem caminho e sem parâmetros"*. Se a lacuna pedir outra coisa (um caminho, três dígitos, um parâmetro com `$`), o enunciado diz.

**Depois de cada um:** confira o gabarito, anote só as erradas e as chutadas na apuração e leve as erradas para o Notion. Um erro que repete um card que você escreveu no sábado é o sinal mais importante do dia: marque-o como **reincidência**.

---

# R4 — Contas e permissões (Tópico 5)

**1. (escolha duas)** Em `/etc/passwd` está a linha abaixo. Quais afirmações são verdadeiras?

```
joao:x:1002:1002:Joao Lima:/home/joao:/usr/sbin/nologin
```

- A) O `x` indica que `joao` tem privilégios de administrador
- B) O hash da senha de `joao` está em `/etc/shadow`
- C) O grupo primário de `joao` é `/home/joao`
- D) `joao` não consegue abrir um shell interativo ao fazer login
- E) O UID 1002 dá a `joao` os mesmos privilégios do root

**2.** O que torna uma conta o superusuário do sistema?

- A) O segundo campo do `/etc/passwd` conter `x`
- B) O sétimo campo ser `/bin/bash`
- C) A conta pertencer ao grupo `users`
- D) O terceiro campo do `/etc/passwd`, o UID, ser `0`
- E) O nome da conta ser `admin`

**3. [lacuna]** Escreva o **caminho completo** do arquivo que guarda os hashes das senhas e as informações de expiração das contas, legível apenas pelo root e pelo grupo `shadow`: ______

**4.** Em `/etc/group` está a linha `dev:x:1005:ana,bob`. O que o quarto campo lista?

- A) Os membros **secundários** (suplementares) do grupo `dev`
- B) Os usuários cujo grupo **primário** é `dev`
- C) Os administradores do grupo
- D) Os donos dos arquivos do grupo
- E) As senhas dos membros do grupo

**5.** Qual é a notação octal de `rw-r-----`?

- A) `644`
- B) `604`
- C) `640`
- D) `460`
- E) `641`

**6.** Qual é a notação octal de `rwx--x---`?

- A) `711`
- B) `701`
- C) `700`
- D) `770`
- E) `710`

**7. (escolha duas)** Quais comandos deixam o arquivo `app` com `-rwxr-x--x` no `ls -l`, qualquer que seja a permissão anterior?

- A) `chmod 715 app`
- B) `chmod 755 app`
- C) `chmod 751 app`
- D) `chmod u=rwx,go=rx app`
- E) `chmod u=rwx,g=rx,o=x app`

**8.** Um arquivo tem permissão `640`. Qual é a permissão depois de `chmod g+w,o+x arquivo`?

- A) `671`
- B) `670`
- C) `661`
- D) `761`
- E) `641`

**9.** Um arquivo tem permissão `755`. Qual é a permissão depois de `chmod u-w,g-r,o= arquivo`?

- A) `550`
- B) `511`
- C) `501`
- D) `510`
- E) `410`

**10. [lacuna]** Um arquivo tem permissão `775`. Escreva **só os três dígitos** da permissão depois de `chmod a-x arquivo`: ______

**11.** Como aparece no `ls -ld` um diretório depois de `chmod 2770 dir`?

- A) `drwxrwS---`
- B) `drwsrwx---`
- C) `drwxrws---`
- D) `drwxrwx--T`
- E) `drwxrwx--t`

**12.** Como aparece no `ls -ld` um diretório depois de `chmod 1770 /srv/compart`?

- A) `drwxrwx--t`
- B) `drwxrws---`
- C) `drwsrwx---`
- D) `drwxrwxrwt`
- E) `drwxrwx--T`

**13.** O `ls -l /usr/bin/passwd` mostra `-rwsr-xr-x 1 root root`. Qual é a permissão em octal, com o bit especial?

- A) `4755`
- B) `755`
- C) `2755`
- D) `1755`
- E) `4555`

**14.** Um arquivo aparece como `-rwxr-Sr--`. Qual é a permissão em octal, com o bit especial?

- A) `2754`
- B) `4744`
- C) `1744`
- D) `2744`
- E) `744`

**15.** O usuário `bob` está nos grupos secundários `dev` e `docker`. Qual comando o acrescenta ao grupo `ops` **sem** tirá-lo dos outros?

- A) `usermod -G ops bob`
- B) `usermod -g ops bob`
- C) `usermod -aG ops bob`
- D) `groupadd ops bob`
- E) `usermod -a ops bob`

**16. (escolha duas)** Quais comandos mudam **só o grupo** de `relatorio.txt` para `financeiro`, sem alterar o dono?

- A) `chown financeiro relatorio.txt`
- B) `chgrp financeiro relatorio.txt`
- C) `chmod g=financeiro relatorio.txt`
- D) `usermod -g financeiro relatorio.txt`
- E) `chown :financeiro relatorio.txt`

**17.** O diretório `cofre` pertence ao root e tem permissão `711` (`rwx--x--x`). Dentro dele está `nota.txt`, com permissão `644`. A usuária `ana`, que não é dona nem do grupo, sabe o nome do arquivo. O que ela consegue fazer?

- A) Ler o arquivo com `cat cofre/nota.txt`
- B) Listar o conteúdo com `ls cofre`
- C) Criar arquivos dentro de `cofre`
- D) Nada, porque não tem `r` no diretório
- E) Apagar `nota.txt`

**18. (escolha duas)** O diretório `/srv/publico` tem `drwxrwxrwt` e pertence ao root. O usuário `bob` criou nele o arquivo `bob.txt`, com `-rw-rw-rw-`. O que a usuária `ana` consegue fazer?

- A) Apagar `bob.txt`
- B) Alterar o conteúdo de `bob.txt`
- C) Criar o seu próprio arquivo em `/srv/publico`
- D) Renomear `bob.txt`
- E) Apagar `bob.txt`, desde que esteja no grupo de `bob`

**19. [lacuna]** Qual comando mostra o UID, o GID principal e todos os grupos do usuário atual? Escreva só o comando, sem caminho e sem parâmetros: ______

**20.** O usuário `davi` está no grupo `sudo`. Qual comando abre um shell de login como root pedindo a senha **do próprio davi**?

- A) `su -`
- B) `passwd root`
- C) `id root`
- D) `login root`
- E) `sudo -i`

---

# R3 — Navegação, ajuda e redirecionamento (Tópicos 1 a 3)

**1. (escolha duas)** A usuária `ana` está em `/usr/share/doc`. Quais comandos a levam para `/usr/share`?

- A) `cd ../..`
- B) `cd ./share`
- C) `cd ..`
- D) `cd ~/share`
- E) `cd /usr/share`

**2.** O usuário está em `/etc/ssh` e executa `cd ../../tmp`. O que o `pwd` mostra em seguida?

- A) `/etc/tmp`
- B) `/etc/ssh/tmp`
- C) `/home/usuario/tmp`
- D) `/tmp`
- E) Nada: o comando falha

**3.** O usuário `davi`, cuja pasta pessoal é `/home/davi`, está em `/var/log`. Qual comando **não** o leva para a pasta pessoal?

- A) `cd /home`
- B) `cd`
- C) `cd ~`
- D) `cd $HOME`
- E) `cd ~davi`

**4.** O usuário está em `/home/davi/projetos` e executa `ls ./docs`. Qual diretório é listado?

- A) `/home/davi/docs`
- B) `/docs`
- C) `/home/davi/projetos/docs`
- D) `/home/docs`
- E) O diretório atual, porque `./` é ignorado

**5. [lacuna]** Qual comando interno do Bash informa se um nome é um alias, um comando interno ou um programa em disco? Escreva só o comando, sem caminho e sem parâmetros: ______

**6. (escolha duas)** Quais afirmações sobre as fontes de ajuda estão corretas?

- A) `man cd` sempre abre uma página de manual própria do `cd`
- B) `help cd` mostra a ajuda do comando interno `cd`
- C) `help` funciona para qualquer programa em `/usr/bin`
- D) `ls --help` mostra um resumo das opções do `ls`
- E) `info` só funciona para comandos internos

**7.** Um administrador quer ler a documentação do **formato do arquivo** crontab, e não do comando `crontab`. Qual comando ele usa?

- A) `man crontab`
- B) `man 1 crontab`
- C) `man -k crontab`
- D) `crontab -h`
- E) `man 5 crontab`

**8.** O que faz `man -k compress`?

- A) Procura a palavra nas descrições curtas das páginas de manual e lista as que casam, como o `apropos`
- B) Abre a página de manual do comando `compress`
- C) Abre a seção `k` do manual
- D) Compacta a página de manual do `compress`
- E) Lista as teclas de atalho do `man`

**9. (escolha duas)** `fotos` é um diretório com arquivos dentro. Quais comandos **falham**?

- A) `cp fotos /tmp`
- B) `mv fotos /tmp`
- C) `cp -r fotos /tmp`
- D) `mv fotos imagens`
- E) `rmdir fotos`

**10.** No diretório atual existem `a.txt` e `b.txt`. O usuário executa `mv a.txt b.txt`, sem opções e sem alias configurado. O que acontece?

- A) O `mv` falha, porque `b.txt` já existe
- B) O conteúdo de `a.txt` é acrescentado ao final de `b.txt`
- C) `b.txt` é substituído pelo conteúdo de `a.txt`, e `a.txt` deixa de existir
- D) O `mv` cria `b.txt.1`
- E) O `mv` sempre pede confirmação antes de sobrescrever

**11.** Depois de `ls /etc /nao-existe 2>&1 > saida.txt`, onde aparece a mensagem de erro sobre `/nao-existe`?

- A) Em `saida.txt`
- B) Em lugar nenhum: é descartada
- C) Em `/dev/null`
- D) No terminal
- E) Em `saida.txt` e no terminal

**12. (escolha duas)** Quais comandos gravam a saída padrão **e** os erros de `find / -name '*.conf'` em `tudo.log`?

- A) `find / -name '*.conf' 2>&1 > tudo.log`
- B) `find / -name '*.conf' > tudo.log 2>&1`
- C) `find / -name '*.conf' 2> tudo.log`
- D) `find / -name '*.conf' &> tudo.log`
- E) `find / -name '*.conf' | tudo.log`

**13.** O que mostra `find / -name passwd 2>/dev/null | wc -l`?

- A) Quantas mensagens de erro o `find` gerou
- B) Nada, porque a saída foi para `/dev/null`
- C) A soma dos caminhos encontrados e das mensagens de erro
- D) O conteúdo dos arquivos `passwd`
- E) Quantos caminhos chamados `passwd` foram encontrados, sem as mensagens de erro

**14.** Qual comando mostra as linhas de `config.txt` que **não** começam com `#`?

- A) `grep -v '^#' config.txt`
- B) `grep '^#' config.txt`
- C) `grep -c '#' config.txt`
- D) `grep -n '^#' config.txt`
- E) `grep -i '#' config.txt`

**15. (escolha duas)** Quais afirmações sobre as opções do `grep` estão corretas?

- A) `-v` ativa o modo detalhado
- B) `-n` inverte a busca
- C) `-c` mostra a quantidade de linhas que casam, em vez das linhas
- D) `-r` conta as ocorrências
- E) `-i` ignora a diferença entre maiúsculas e minúsculas

**16.** O script `args.sh` contém só a linha `echo $0 $# $1`. Qual é a saída de `./args.sh um dois`?

- A) `args.sh 3 um`
- B) `um 2 dois`
- C) `./args.sh 3 um`
- D) `./args.sh 2 um`
- E) `2 um dois`

**17.** O script `copia.sh` começa assim:

```bash
if [ $# -ne 2 ]; then
  echo "uso: $0 origem destino"
  exit 1
fi
```

O que acontece com `./copia.sh a.txt`?

- A) Copia `a.txt` para o diretório atual
- B) Mostra a mensagem de uso e continua o script
- C) Mostra a mensagem de uso e termina com código de saída 1
- D) Dá erro de sintaxe no `[`
- E) Espera o usuário digitar o segundo argumento

**18. [lacuna]** Qual parâmetro especial guarda o código de saída do último comando executado? Escreva **com** o `$`: ______

**19.** Uma designer precisa criar um logotipo que possa ser ampliado para um outdoor sem perder qualidade. Qual programa de código aberto é o mais indicado?

- A) GIMP
- B) Blender
- C) Audacity
- D) LibreOffice Impress
- E) Inkscape

**20. [lacuna]** Na família Red Hat, qual ferramenta de baixo nível instala um arquivo `.rpm`, papel equivalente ao do `dpkg` no Debian? Escreva só o comando, sem caminho e sem parâmetros: ______

---

# Gabarito

**Não abra antes de responder as 20 questões do reforço.**

<details>
<summary>Gabarito comentado do R4</summary>

| Q | Resposta | Comentário | Erro do simulado 02 |
|---|---|---|---|
| 1 | **B e D** | O `x` só diz que a senha está no shadow. `/usr/sbin/nologin` no sétimo campo impede o shell interativo. O quarto campo (1002) é o GID; o sexto é a pasta pessoal | Q34 |
| 2 | **D** | Superusuário é **UID 0**, terceiro campo. Nome, grupo e shell não importam | Q34 |
| 3 | **`/etc/shadow`** | Grafia aceita: `/etc/shadow`. Aqui o enunciado pede o caminho | Q34 |
| 4 | **A** | O quarto campo do `/etc/group` lista os membros **secundários**. Quem tem `dev` como **primário** aparece no quarto campo do `/etc/passwd`, com o GID 1005 | Correção 75 |
| 5 | **C** | `rw-` 6, `r--` 4, `---` **0** | Q36 |
| 6 | **E** | `rwx` 7, `--x` 1, `---` **0** | Q36 |
| 7 | **C e E** | 751 = `rwx r-x --x`. `go=rx` daria `r-x` aos outros (755); `715` inverte grupo e outros | Q36 |
| 8 | **A** | Grupo: 4 + 2 = 6. Outros: 0 + 1 = 1. Dono inalterado: 6 | Q37 |
| 9 | **D** | Dono: 7 − 2 = 5. Grupo: 5 − 4 = 1. Outros: `o=` sem nada zera, 0 | Q37 |
| 10 | **`664`** | `a` = todos: cada trio perde o `x`. 7 − 1 = 6, 7 − 1 = 6, 5 − 1 = 4 | Q37 |
| 11 | **C** | O `2` é SGID e aparece no `x` do **grupo**. O grupo tem `x` (o 7 de `770`), então `s` minúsculo | Q38 |
| 12 | **E** | O `1` é sticky e aparece no `x` dos **outros**. Os outros têm `0`, sem `x`, então `T` maiúsculo | Q38 |
| 13 | **A** | `s` no trio do dono é SUID (4); o resto é `755` | Q38 |
| 14 | **D** | `S` no trio do grupo: SGID (2) **sem** `x`. Grupo `r-S` vale 4, não 5. Dono 7, outros 4: `2744` | Q38 |
| 15 | **C** | `-a` (*append*) com `-G` acrescenta. Sem o `-a`, o `-G` **substitui** a lista. `-g` minúsculo muda o grupo **primário** | Simulado 02, Q35 (acerto) |
| 16 | **B e E** | `chgrp grupo arquivo` e `chown :grupo arquivo`. O `chown financeiro` muda o **dono** | Q40 (pesquisada) |
| 17 | **A** | No diretório, `x` permite **atravessar** e acessar uma entrada pelo nome; `r` permite **listar**; `w` permite criar e apagar. Ela tem só `x`, e o arquivo dá `r` aos outros | Card sem número: `x` em diretório |
| 18 | **B e C** | O sticky bit protege o **nome** dentro do diretório (apagar e renomear), não o **conteúdo** do arquivo. O conteúdo segue a permissão do próprio arquivo, `rw-` para os outros | Q39 (acerto) |
| 19 | **`id`** | Grafia aceita: `id`. O `groups` mostra só os grupos; o `whoami`, só o nome | — |
| 20 | **E** | O `sudo` pede a senha **de quem executa**; o `su -` pede a senha **da conta de destino**, a do root | Autoavaliação da Semana 6, Q4 |

</details>

<details>
<summary>Gabarito comentado do R3</summary>

| Q | Resposta | Comentário | Erro do simulado 02 |
|---|---|---|---|
| 1 | **C e E** | `..` é o pai: de `/usr/share/doc` vai para `/usr/share`. `../..` sobe dois níveis (`/usr`). `./share` procuraria `/usr/share/doc/share` | Q10 |
| 2 | **D** | `/etc/ssh` → `..` = `/etc` → `..` = `/` → `tmp` = `/tmp` | Q10 |
| 3 | **A** | `/home` é o diretório que contém as pastas pessoais. `cd`, `cd ~`, `cd $HOME` e `cd ~davi` vão para `/home/davi` | Q9 (Correção 54) |
| 4 | **C** | `.` é o diretório atual: `./docs` é `docs` dentro dele | Q10 |
| 5 | **`type`** | Grafia aceita: `type`. Exemplo: `type cd` responde "cd is a shell builtin" | Q13 (Correção 74) |
| 6 | **B e D** | O `help` é para os internos do Bash; `--help` é a ajuda curta de cada programa. O `man cd` pode até existir em algumas distribuições, como página geral dos internos, mas não "sempre" | Q13 |
| 7 | **E** | Seção 5, formatos de arquivo. `man crontab` abre a seção 1, a do comando | Q16 |
| 8 | **A** | `-k` é *keyword*: busca, não abre. Equivale a `apropos compress` | Q16 |
| 9 | **A e E** | O `cp` precisa de `-r` para copiar diretório; o `rmdir` só remove diretório vazio. O `mv` move e renomeia diretórios sem opção | Q14 |
| 10 | **C** | Sem `-i`, o `mv` sobrescreve o destino sem perguntar | Q14 |
| 11 | **D** | Da esquerda para a direita: no momento do `2>&1`, a saída padrão ainda é o terminal; o erro vai para lá. Só depois a saída padrão vai para o arquivo | Q19 (Correção 29) |
| 12 | **B e D** | `> arq 2>&1` e `&> arq` juntam as duas saídas. `2>&1 > arq` é a armadilha da questão 11 | Q19 (Correção 29) |
| 13 | **E** | O `2>/dev/null` descarta só os erros; a saída padrão segue pelo pipe e o `wc -l` conta as linhas | Q19 |
| 14 | **A** | `-v` inverte; `^#` casa as linhas que **começam** com `#`. Invertido: as que não começam | Q22 (Correção 49) |
| 15 | **C e E** | `-v` é *invert*, `-n` numera, `-r` é recursivo | Q22 (Correção 49) |
| 16 | **D** | `$0` é o nome **como foi chamado** (`./args.sh`), `$#` conta só os argumentos (2), `$1` é `um` | Q24 |
| 17 | **C** | Um argumento, e `-ne 2` é verdadeiro: imprime o uso e o `exit 1` encerra com código 1 | Q24 e Q6 da autoavaliação da Semana 5 |
| 18 | **`$?`** | Grafia aceita: `$?`. Zero é sucesso; diferente de zero é erro | — |
| 19 | **E** | Inkscape é vetorial: escala sem perder qualidade. GIMP é raster (fotos); Blender, 3D; Audacity, áudio; Impress, apresentações | Q5 |
| 20 | **`rpm`** | Grafia aceita: `rpm`. Pares: `apt` e `dpkg` no Debian; `dnf` (ou `yum`) e `rpm` no Red Hat | Q7 |

</details>

---

# Apuração

## R4 — domingo 25/10

| Campo | Valor |
| --- | --- |
| Tempo gasto | |
| Acertos | de 20 (meta: 16) |
| Chutes marcados | |
| Erros de forma nas lacunas | |
| Reincidências (erro que repete um card de sábado) | |

| Bloco | Questões | Acertos |
| --- | --- | --- |
| `/etc/passwd`, `/etc/shadow`, `/etc/group` | 1 a 4 | /4 |
| Octal e simbólico | 5 a 10 | /6 |
| Bits especiais | 11 a 14 | /4 |
| Grupos, dono e acesso | 15 a 20 | /6 |

## R3 — domingo 25/10

| Campo | Valor |
| --- | --- |
| Tempo gasto | |
| Acertos | de 20 (meta: 16) |
| Chutes marcados | |
| Erros de forma nas lacunas | |
| Reincidências (erro que repete um card de sábado) | |

| Bloco | Questões | Acertos |
| --- | --- | --- |
| Caminhos e navegação | 1 a 4 | /4 |
| Ajuda e `man` | 5 a 8 | /4 |
| `mv` e `cp` | 9 e 10 | /2 |
| Redirecionamento | 11 a 13 | /3 |
| `grep` | 14 e 15 | /2 |
| Scripts | 16 a 18 | /3 |
| Tópico 1 | 19 e 20 | /2 |

## Questões erradas

| Reforço | Q | Você marcou | Gabarito | Convicção ou chute | Reincidência? | Corrigida no Notion |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |

**Leitura.** Um bloco com menos da metade de acertos é sinal de que o card de sábado não fixou o mecanismo. Nesse caso, a correção é **executar na VM** os comandos do bloco, não reescrever o card.