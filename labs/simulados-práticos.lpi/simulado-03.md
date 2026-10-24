# Simulado 03 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 18/10/2026; aplicado na **sexta 30/10** (movido em 21 e 23/10), depois das Práticas 3 a 5 e do curso fechado. É o primeiro com os cinco tópicos estudados e vale para o **Checkpoint B**.

Mesmo nível do simulado 02: enunciados com cenário, pegadinhas de comando, três questões de escolher duas respostas e cinco de preencher a lacuna. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. **Use pelo menos 45** e reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **28 ou mais** (Checkpoint B) |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando.

Nas questões **[lacuna]**, escreva só o que foi pedido: sem caminho, sem flags, sem sublinhado, sem aspas, sem ponto final. Maiúsculas e minúsculas contam.

Nas questões **(escolha duas)**, a questão só conta como certa se as duas respostas estiverem certas.

## Distribuição por tópico

| Tópico | Peso | Questões |
| --- | --- | --- |
| 1. A comunidade Linux e uma carreira em open source | 7 | 1 a 7 |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 8 a 16 |
| 3. O poder da linha de comando | 9 | 17 a 25 |
| 4. O sistema operacional Linux | 8 | 26 a 33 |
| 5. Segurança e permissões de arquivo | 7 | 34 a 40 |

---

## Tópico 1 — A comunidade Linux e uma carreira em open source

**1.** Qual destas **não** é uma das quatro liberdades do software livre, segundo a Free Software Foundation?

- A) Executar o programa para qualquer propósito
- B) Estudar como o programa funciona e adaptá-lo
- C) Redistribuir cópias
- D) Obter o programa sem pagar nada

**2.** Uma empresa quer usar uma biblioteca de código aberto em um produto proprietário, ligando-a ao seu programa sem abrir o código do próprio produto. Qual licença da biblioteca foi pensada para esse caso?

- A) GPLv3
- B) LGPL
- C) AGPLv3
- D) GPLv2

**3.** Qual destas distribuições segue o modelo de **rolling release**?

- A) Debian estável
- B) Ubuntu LTS
- C) Arch Linux
- D) Red Hat Enterprise Linux

**4.** Um desenvolvedor precisa gerar um executável binário que rode sem que o usuário instale um interpretador. Qual linguagem é tipicamente usada dessa forma?

- A) Python
- B) Bash
- C) C
- D) JavaScript

**5.** **(escolha duas)** Quais pares associam corretamente o serviço à sua porta padrão?

- A) SSH — 22
- B) HTTP — 443
- C) DNS — 53
- D) SMTP — 110
- E) HTTPS — 80

**6.** Qual destes **não** é um ambiente de desktop, e sim um protocolo de servidor gráfico?

- A) GNOME
- B) KDE Plasma
- C) Xfce
- D) Wayland

**7. [lacuna]** O kernel Linux é distribuído sob a licença ______, versão 2. Escreva só a sigla.

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** Um usuário quer ver as permissões e o dono **do próprio diretório** `/etc`, e não a lista do que há dentro dele. Qual comando usar?

- A) `ls -l /etc`
- B) `ls -ld /etc`
- C) `ls -a /etc`
- D) `ls -R /etc`

**9.** O comando `mkdir projetos/2026/outubro` falha porque `projetos` não existe. Qual opção cria toda a estrutura de uma vez?

- A) `mkdir -r projetos/2026/outubro`
- B) `mkdir -f projetos/2026/outubro`
- C) `mkdir -p projetos/2026/outubro`
- D) `mkdir -a projetos/2026/outubro`

**10. [lacuna]** O comando que cria um arquivo vazio, ou atualiza a data de modificação de um arquivo que já existe, é: ______

**11.** O comando `cp dados copia` responde `cp: -r not specified; omitting directory 'dados'`. O que resolve?

- A) `cp -f dados copia`
- B) `cp -r dados copia`
- C) `cp -i dados copia`
- D) `mv dados copia`

**12.** Um diretório contém `img1.png`, `img2.png` e `img10.png`. Qual é a saída de `ls img[0-9][0-9].png`?

- A) `img1.png img2.png`
- B) `img10.png`
- C) `img1.png img2.png img10.png`
- D) Nenhuma: o comando dá erro de sintaxe

**13.** Qual destes é um caminho **absoluto**?

- A) `../docs`
- B) `docs/relatorio.txt`
- C) `/var/log/../tmp`
- D) `./script.sh`

**14.** **(escolha duas)** Quais comandos procuram páginas de manual por uma palavra-chave no nome **e na descrição**?

- A) `whatis`
- B) `apropos`
- C) `man -k`
- D) `info`
- E) `which`

**15.** O arquivo `notas.txt` tem um link simbólico `atalho` e um hard link `copia`. O usuário apaga `notas.txt`. O que acontece?

- A) Os dois links continuam mostrando o conteúdo
- B) Os dois links ficam quebrados
- C) `copia` continua mostrando o conteúdo; `atalho` fica quebrado
- D) `atalho` continua mostrando o conteúdo; `copia` fica quebrado

**16.** Qual comando torna a variável `EDITOR` visível para os programas iniciados a partir do shell atual?

- A) `set EDITOR`
- B) `export EDITOR`
- C) `env EDITOR`
- D) `unset EDITOR`

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando lista o conteúdo de `backup.tar.xz` **sem extrair**?

- A) `tar -xJf backup.tar.xz`
- B) `tar -tJf backup.tar.xz`
- C) `tar -tzf backup.tar.xz`
- D) `tar -cJf backup.tar.xz`

**18. [lacuna]** Para criar um arquivo `.tar.xz`, a opção do `tar` que aciona a compressão xz é a letra: ______ (escreva só a letra, respeitando maiúscula ou minúscula)

**19.** Um script roda todas as noites com `./limpeza.sh 2>> erros.log`. O que acontece com `erros.log` a cada execução?

- A) É apagado e recebe a saída normal do script
- B) Recebe as mensagens de erro, acrescentadas ao final do que já existia
- C) Recebe as mensagens de erro, substituindo o conteúdo anterior
- D) Recebe a saída normal e os erros, acrescentados ao final

**20.** O arquivo `nomes.txt` tem 12 linhas. Qual é a saída de `wc -l < nomes.txt`?

- A) `12 nomes.txt`
- B) `12`
- C) `nomes.txt 12`
- D) Erro: o `wc` precisa receber o nome do arquivo como argumento

**21.** Qual é a saída do trecho abaixo, executado pelo usuário `davi`?

```bash
cat << 'FIM'
$HOME
FIM
```

- A) `/home/davi`
- B) `$HOME`
- C) `'$HOME'`
- D) Nada: o `cat` fica esperando a entrada do teclado

**22.** Qual comando **conta** as linhas vazias de `config.txt`?

- A) `grep -c '^$' config.txt`
- B) `grep -v '^$' config.txt`
- C) `grep -c '$^' config.txt`
- D) `wc -l config.txt`

**23.** O que faz `sort -t: -k3 -n /etc/passwd`?

- A) Ordena as linhas pelo terceiro campo, o UID, em ordem numérica crescente
- B) Ordena as linhas pelas três primeiras letras, em ordem alfabética
- C) Mostra só o terceiro campo de cada linha, ordenado
- D) Ordena pelo terceiro campo em ordem decrescente

**24.** Em um diretório **sem nenhum** arquivo `.log`, qual é a saída de `for f in *.log; do echo "$f"; done`?

- A) Nenhuma: o laço não executa
- B) `*.log`
- C) Uma mensagem de erro do `for`
- D) A lista de todos os arquivos do diretório

**25.** O script `fim.sh` termina com a linha `exit 3`. Qual é a saída de `./fim.sh ; echo $?`, supondo que o script não imprime nada antes?

- A) `0`
- B) `1`
- C) `3`
- D) Nada: o `exit` encerra também o shell que chamou o script

---

## Tópico 4 — O sistema operacional Linux

**26. [lacuna]** O comando que lista os dispositivos de bloco, como discos e partições, em forma de árvore, é: ______

**27.** Qual arquivo traz o total de memória e a memória disponível, e é a fonte de onde o `free` tira os números?

- A) `/dev/mem`
- B) `/proc/meminfo`
- C) `/etc/meminfo`
- D) `/sys/memory`

**28.** O que acontece com tudo o que é escrito em `/dev/null`?

- A) É gravado em um arquivo oculto da pasta pessoal
- B) É enviado para o log do sistema
- C) É descartado
- D) Fica na memória até o próximo reinício

**29.** Um usuário roda `sleep 600 &` e depois `jobs`, que mostra `[1]+ Running sleep 600 &`. O que faz `fg %1`?

- A) Encerra o trabalho 1
- B) Traz o trabalho 1 para o primeiro plano
- C) Suspende o trabalho 1
- D) Coloca o trabalho 1 em segundo plano

**30.** O que mostra o comando `ss -tln`?

- A) As conexões UDP estabelecidas, com o nome dos serviços
- B) Os sockets TCP em escuta, com os endereços e portas em forma numérica
- C) A tabela de roteamento
- D) Todas as interfaces de rede e seus endereços IP

**31.** Qual comando mostra a tabela de roteamento, incluindo a rota padrão?

- A) `ip addr show`
- B) `ip route show`
- C) `ss -r`
- D) `host -r`

**32.** Qual destes é um endereço IPv6 válido escrito na forma abreviada?

- A) `192.168.0.300`
- B) `2001:db8::1`
- C) `2001::db8::1`
- D) `fe80:0:0:0:0:0:0:0:1`

**33.** Em uma distribuição Debian ou Ubuntu com o `rsyslog`, qual é o arquivo de log geral do sistema?

- A) `/etc/syslog`
- B) `/var/log/syslog`
- C) `/proc/log`
- D) `/dev/log`

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Em `/etc/group`, a linha é `dev:x:1001:bob,carol`. O que o último campo informa?

- A) Os usuários que podem administrar o grupo
- B) Os membros que têm `dev` como grupo secundário
- C) Os usuários que têm `dev` como grupo primário
- D) As senhas criptografadas de `bob` e `carol`

**35.** Ao criar um usuário com `useradd -m ana`, de onde vêm os arquivos iniciais da pasta `/home/ana`, como o `.bashrc`?

- A) Do `/etc/default`
- B) Do `/etc/skel`
- C) Da pasta pessoal do root
- D) São criados vazios pelo `useradd`

**36. [lacuna]** A notação octal completa, com o bit especial, de `rwsr-xr-x` é: ______

**37.** Depois de `chmod 640 relatorio.txt`, como o arquivo aparece no `ls -l`?

- A) `-rw-r-----`
- B) `-rw-r--r--`
- C) `-rwxr-----`
- D) `-rw-rw----`

**38.** O administrador executa `chmod g+s /srv/projeto`, um diretório do grupo `dev`. Qual é o efeito?

- A) Os arquivos dentro dele passam a rodar com os privilégios do grupo
- B) Só o dono de cada arquivo pode apagá-lo
- C) Os arquivos criados dentro dele herdam o grupo `dev`
- D) O diretório passa a ser oculto para quem não é do grupo

**39.** O diretório `privado` tem permissão `drwxr-x--x` e pertence a outro usuário e a outro grupo. O que você consegue fazer nele?

- A) Listar o conteúdo com `ls`, mas não entrar com `cd`
- B) Entrar com `cd` e acessar um arquivo cujo nome já conhece, mas não listar o conteúdo
- C) Listar e entrar, mas não ler nenhum arquivo
- D) Nada: sem `r`, o diretório fica totalmente inacessível

**40.** **(escolha duas)** Quais comandos permitem a um usuário autorizado executar um comando com os privilégios do root?

- A) `sudo comando`
- B) `su -c 'comando'`
- C) `chown root comando`
- D) `passwd root`
- E) `id root`

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>

## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **D** | "Livre" é de liberdade, não de preço. As quatro liberdades são executar, estudar e modificar, redistribuir e distribuir versões modificadas |
| 2 | **B** | A LGPL é um copyleft fraco: permite ligar a biblioteca a software proprietário. GPL e AGPL exigiriam abrir o produto |
| 3 | **C** | O Arch não tem versões fixas. Debian estável, Ubuntu LTS e RHEL têm versões com ciclo definido |
| 4 | **C** | C é compilada para código de máquina. Python, Bash e JavaScript precisam de um interpretador |
| 5 | **A e C** | SSH 22 e DNS 53. HTTP é 80, HTTPS é 443 e SMTP é 25 (110 é POP3) |
| 6 | **D** | Wayland, como o X11, é o protocolo que desenha na tela. GNOME, KDE Plasma e Xfce são ambientes de desktop que rodam sobre ele |
| 7 | **`GPL`** | Grafia aceita: `GPL`. O kernel é GPL versão 2, sem a cláusula "ou posterior" |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **B** | O `-d` mostra o próprio diretório em vez do conteúdo |
| 9 | **C** | O `-p` (*parents*) cria os diretórios intermediários, e não dá erro se já existirem |
| 10 | **`touch`** | Grafia aceita: `touch` |
| 11 | **B** | O `cp` só copia diretórios com `-r` (recursivo) |
| 12 | **B** | Cada `[0-9]` casa exatamente um dígito. São dois, então só `img10.png` tem dois dígitos no lugar |
| 13 | **C** | Começa em `/`, portanto é absoluto, mesmo com o `..` no meio. O `..` sobe de `/var/log` para `/var` |
| 14 | **B e C** | `apropos` e `man -k` são o mesmo recurso. O `whatis` (igual a `man -f`) procura só o nome exato |
| 15 | **C** | O hard link aponta para o mesmo inode, que só é liberado quando o último nome some. O simbólico aponta para o **nome** `notas.txt`, que deixou de existir (Correção 27) |
| 16 | **B** | O `export` marca a variável para ser herdada pelos processos filhos (Correção 71) |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **B** | `-t` lista, `-J` é xz, `-f` indica o arquivo. A opção C usaria gzip num arquivo xz |
| 18 | **`J`** | Grafia aceita: `J`, maiúscula. O `-j` minúsculo é bzip2 e o `-z` é gzip |
| 19 | **B** | `2>>` acrescenta só o fluxo de erro. Com `2>` o arquivo seria sobrescrito |
| 20 | **B** | Com `<`, quem abre o arquivo é o shell, e o `wc` lê da entrada padrão sem conhecer o nome. Por isso sai só o número (Correção 30) |
| 21 | **B** | Com o delimitador entre aspas, o here document é literal: nada é expandido |
| 22 | **A** | `^$` é uma linha que começa e termina sem nada no meio; `-c` conta. O `-v` mostraria as não vazias |
| 23 | **A** | `-t:` usa os dois-pontos como separador, `-k3` escolhe a terceira coluna, `-n` ordena como número. Sem `-r`, a ordem é crescente (Correções 32 a 34) |
| 24 | **B** | Quando o padrão não casa com nada, o Bash entrega o texto `*.log` literalmente. É o mesmo comportamento do `echo *.md` registrado na Semana 3 |
| 25 | **C** | O `exit 3` define o código de saída do script, e o `$?` o mostra logo em seguida. O script roda em um processo filho, então o shell que o chamou continua aberto |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **`lsblk`** | Grafia aceita: `lsblk` |
| 27 | **B** | O `/proc/meminfo` é gerado pelo kernel. O `/dev/mem` existe, mas é o dispositivo de acesso direto à memória física, não um relatório |
| 28 | **C** | O `/dev/null` descarta tudo o que recebe. Por isso `2>/dev/null` some com as mensagens de erro |
| 29 | **B** | `fg` traz para o primeiro plano; `bg` retoma no segundo plano; `Ctrl+Z` suspende |
| 30 | **B** | `-t` TCP, `-l` só os que estão em escuta, `-n` números em vez de nomes |
| 31 | **B** | A linha `default via ...` é a rota padrão. O `route` é o equivalente antigo |
| 32 | **B** | O `::` substitui uma sequência de zeros e só pode aparecer **uma vez**. A opção D tem nove grupos (o máximo é oito) e a A é um IPv4 inválido (300 passa de 255) |
| 33 | **B** | No Red Hat o equivalente é `/var/log/messages`. O `/dev/log` existe, mas é o socket por onde os programas **enviam** mensagens ao syslog, não o arquivo de log |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **B** | Os quatro campos do `/etc/group`: nome, `x`, GID e lista de membros. Quem tem o grupo como primário aparece no `/etc/passwd`, não nessa lista |
| 35 | **B** | O `-m` cria a pasta pessoal e copia para ela o conteúdo do `/etc/skel` |
| 36 | **`4755`** | Grafia aceita: `4755`. O `s` no lugar do `x` do dono é o SUID (4) com o `x` presente; o resto é `rwxr-xr-x`, 755 |
| 37 | **A** | 6 = `rw-`, 4 = `r--`, 0 = `---` |
| 38 | **C** | SGID em diretório: os arquivos novos herdam o grupo do diretório. A opção B descreve o sticky bit |
| 39 | **B** | Para os outros sobrou só o `x`: dá para atravessar o diretório e abrir um nome conhecido, mas sem `r` não dá para listar |
| 40 | **A e B** | O `sudo` usa a sua senha e a política do `sudoers`; o `su -c` roda o comando como root com a senha do root. As outras não executam nada como root |

## Tabela de temas

| Tema | Mínimo | Questões | Total |
|---|---|---|---|
| Permissões | 4 | 36, 37, 38, 39 | 4 |
| `tar` e compressão | 2 | 17, 18 | 2 |
| Redirecionamento (com `<<`) | 3 | 19, 20, 21 | 3 |
| Diretórios virtuais e `/var` | 3 | 27, 28, 33 | 3 |
| Preencher a lacuna | 5 | 7, 10, 18, 26, 36 | 5 |

## Questões que retestam erros antigos

| Q | Erro de origem |
|---|---|
| 15 | Correção 27 (hard link não é cópia) |
| 16 | Correções 12 e 71 (herança de variáveis) |
| 20 | Correção 30 (quem abre o arquivo no `<`) |
| 23 | Correções 32 a 34 e 50 (`sort`, `-k` e `-n`) |
| 24 | Semana 3 (padrão sem correspondência) |
| 29 | Q28 e Q29 do simulado 01 (processos) |
| 34 e 35 | Prática 1 (`/etc/group` e `/etc/skel`) |

</details>

---

# Apuração

Preencha depois de conferir o gabarito.

| Tópico | Peso | Questões | Acertos | Chutes acertados |
| --- | --- | --- | --- | --- |
| 1. Comunidade e open source | 7 | 1 a 7 | | |
| 2. Encontrando seu caminho | 9 | 8 a 16 | | |
| 3. Poder da linha de comando | 9 | 17 a 25 | | |
| 4. Sistema operacional | 8 | 26 a 33 | | |
| 5. Segurança e permissões | 7 | 34 a 40 | | |
| **Total** | **40** | | | |

| Tema | Questões | Acertos |
| --- | --- | --- |
| Permissões | 4 | |
| `tar` e compressão | 2 | |
| Redirecionamento | 3 | |
| Diretórios virtuais | 3 | |
| Lacunas | 5 | |

## Registro

| Campo | Valor |
| --- | --- |
| Data | 30/10/2026 |
| Tempo gasto | |
| Minutos usados na segunda passada | |
| Acertos | de 40 |
| Percentual e escala LPI | |
| Questões marcadas como chute | |
| Chutes acertados e chutes errados | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

Só as erradas e as chutadas. A correção vai para o Notion, com as suas palavras.

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Corrigida no Notion |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |

**Comparação com os simulados 01 e 02:** o que errava e agora acerta, o que continua errando, o que apareceu de novo.