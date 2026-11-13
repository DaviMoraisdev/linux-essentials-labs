# Simulado 06 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 12/11/2026 para a **sexta 13/11**, na operação prática. Retesta os erros do simulado 04 (contêineres, `tee`, `ps`, IPv6, `/etc/shadow`, SGID, `x` em diretório) e as reincidências da lista da operação (`$#`, seções do `man`, `/home`).

Cinco alternativas por questão, três questões de escolher duas e cinco lacunas com a instrução que a prova usa. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame. Nenhuma repete os simulados 02 a 05.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. **Use pelo menos 45** e reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **28 acertos firmes** ou mais |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando. **Leia a alternativa inteira antes de marcar**: no simulado 04, quatro dos cinco erros do Tópico 5 foram de leitura, não de conteúdo.

Nas questões **[lacuna]**, escreva só o que foi pedido: sem caminho (salvo se o enunciado pedir), sem `sudo`, sem opções, sem explicação ao lado.

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

**1.** Um administrador precisa rodar, no mesmo servidor físico, um Windows Server e um Linux, **cada um com o próprio kernel**. Qual tecnologia atende?

- A) Contêineres
- B) `chroot`
- C) Namespaces do kernel
- D) Hipervisor com máquinas virtuais
- E) Um gerenciador de pacotes

**2.** Qual família de licenças é a mais usada para obras que **não são software**, como textos, fotos e músicas, com variantes que permitem ou não o uso comercial?

- A) GPL
- B) Creative Commons
- C) BSD
- D) MIT
- E) Apache

**3.** **(escolha duas)** Quais destes são navegadores web de código aberto?

- A) Firefox
- B) Safari
- C) Microsoft Edge
- D) Chromium
- E) Opera

**4.** Qual destes programas open source é um **cliente de e-mail** para desktop?

- A) Apache
- B) Blender
- C) Thunderbird
- D) Inkscape
- E) Nextcloud

**5.** Qual é a principal função de um **gerenciador de senhas**?

- A) Trocar a senha do root a cada login
- B) Guardar a mesma senha para todos os sites
- C) Desativar a autenticação de dois fatores
- D) Enviar as senhas por e-mail ao usuário
- E) Gerar e guardar, em um cofre cifrado, senhas fortes e diferentes para cada serviço

**6.** Em qual modelo de nuvem o cliente recebe **máquinas virtuais** e fica responsável pelo sistema operacional, pelas atualizações e pelos programas instalados?

- A) IaaS
- B) SaaS
- C) PaaS
- D) FaaS
- E) Nenhum: em nuvem o provedor sempre administra o sistema

**7. [lacuna]** Qual é o nome do projeto, iniciado por Richard Stallman em 1983, que criou grande parte das ferramentas usadas junto com o kernel Linux? Escreva só o nome, uma palavra: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O script `args.sh` contém só a linha `echo $0 $#`. Qual é a saída de `./args.sh x y z`?

- A) `./args.sh 4`
- B) `args.sh 3`
- C) `./args.sh 3`
- D) `x 3`
- E) `./args.sh x y z`

**9.** Qual é a diferença entre `man 1 passwd` e `man 5 passwd`?

- A) A seção 1 é a versão antiga e a 5 é a atual
- B) A seção 1 descreve o comando `passwd`; a seção 5 descreve o formato do arquivo `/etc/passwd`
- C) A seção 1 é para usuários comuns e a 5 só abre para o root
- D) A seção 5 descreve os comandos de administração
- E) Nenhuma: as duas abrem a mesma página

**10.** O usuário `davi` tem a pasta pessoal `/home/davi`. Qual comando **não** o leva para lá?

- A) `cd`
- B) `cd ~`
- C) `cd $HOME`
- D) `cd ~davi`
- E) `cd /home`

**11.** Um diretório contém `foto1.jpg`, `foto2.png`, `foto3.jpg` e `doc.jpg`. Qual é a saída de `ls foto*.jpg`?

- A) `foto1.jpg foto3.jpg`
- B) `foto1.jpg foto2.png foto3.jpg`
- C) `foto1.jpg foto3.jpg doc.jpg`
- D) `foto*.jpg`
- E) Um erro, porque o `*` exige um número

**12.** Qual comando informa o **tipo de conteúdo** de um arquivo, como `ASCII text` ou `ELF 64-bit executable`, sem depender da extensão?

- A) `type`
- B) `stat`
- C) `ls -l`
- D) `file`
- E) `which`

**13.** **(escolha duas)** Quais comandos encontram **arquivos pelo nome**?

- A) `find`
- B) `grep`
- C) `locate`
- D) `whatis`
- E) `cut`

**14.** Qual comando procura, dentro de `/var`, arquivos **maiores que 100 MB**?

- A) `find /var -size 100M`
- B) `find /var -name +100M`
- C) `find /var -size +100M`
- D) `locate /var -size +100M`
- E) `ls -S /var +100M`

**15.** Qual comando **remove** a variável `NOME` do shell atual?

- A) `unset NOME`
- B) `export -n NOME`
- C) `NOME=`
- D) `env -u NOME`
- E) `rm NOME`

**16. [lacuna]** Qual comando interno mostra a lista dos comandos digitados anteriormente no shell, numerados? Escreva só o comando, sem parâmetros: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando mostra a listagem do `ls` na tela **e** a grava em `lista.txt` ao mesmo tempo?

- A) `ls > lista.txt`
- B) `ls | tee lista.txt`
- C) `ls >> lista.txt`
- D) `ls | cat lista.txt`
- E) `ls 2> lista.txt`

**18.** O usuário executa `ls /etc /naoexiste > saida.txt`. O que acontece com a mensagem de erro sobre `/naoexiste`?

- A) Vai para `saida.txt`, antes da listagem
- B) É descartada
- C) Vai para `/dev/null`
- D) Impede que o `ls` liste o `/etc`
- E) Aparece na tela

**19.** Qual comando cria `docs.tar.gz` com o diretório `docs`?

- A) `tar -xzf docs.tar.gz docs`
- B) `tar -czf docs.tar.gz docs`
- C) `tar -cjf docs.tar.gz docs`
- D) `tar -czf docs docs.tar.gz`
- E) `tar -tzf docs.tar.gz docs`

**20. [lacuna]** Qual comando descomprime um arquivo `.xz`? Escreva só o comando, sem caminho e sem parâmetros: ______

**21.** Qual opção do `grep` faz a busca **ignorar a diferença** entre maiúsculas e minúsculas?

- A) `-v`
- B) `-c`
- C) `-i`
- D) `-n`
- E) `-r`

**22.** Qual comando mostra só os **nomes dos usuários**, o primeiro campo de cada linha do `/etc/passwd`?

- A) `cut -f1 /etc/passwd`
- B) `cut -d: -f1 /etc/passwd`
- C) `cut -d, -f1 /etc/passwd`
- D) `cut -c1 /etc/passwd`
- E) `sort -k1 /etc/passwd`

**23.** O que mostra `wc -w relatorio.txt`?

- A) O número de linhas
- B) O número de caracteres
- C) O tamanho em bytes
- D) O número de palavras
- E) As palavras repetidas

**24.** Qual é a saída do trecho abaixo?

```bash
for n in a b c; do
  echo "item $n"
done
```

- A) `item a b c`
- B) `item $n`, três vezes
- C) Três linhas: `item a`, `item b` e `item c`
- D) Só `item c`
- E) Um erro, porque falta o `then`

**25.** Qual é a saída de `ls /naoexiste ; echo $?`, além da mensagem de erro?

- A) `0`
- B) Um número diferente de zero
- C) `/naoexiste`
- D) Uma linha vazia
- E) `-1`

---

## Tópico 4 — O sistema operacional Linux

**26.** Qual comando lista os processos de **todos os usuários**, com o caminho completo do comando, no estilo **Unix (System V)**, com hífen?

- A) `ps`
- B) `ps -u`
- C) `jobs`
- D) `ps -ef`
- E) `top -n 1`

**27.** Quantos bits tem um endereço **IPv6**?

- A) 32
- B) 48
- C) 64
- D) 128
- E) 256

**28.** Qual arquivo associa nomes a endereços IP **localmente**, sem consultar um servidor DNS?

- A) `/etc/resolv.conf`
- B) `/etc/hostname`
- C) `/etc/hosts`
- D) `/etc/nsswitch.conf`
- E) `/etc/network`

**29.** A saída de `ip route` tem a linha `default via 192.168.0.1 dev eth0`. O que ela informa?

- A) Que `192.168.0.1` é o endereço da própria máquina
- B) Que `192.168.0.1` é o servidor DNS
- C) Que a interface `eth0` está desligada
- D) Que `192.168.0.1` é o gateway padrão, usado para destinos fora das redes conhecidas
- E) Que só a rede `192.168.0.0` está acessível

**30.** Qual comando mostra o uso de memória e de swap em unidades **legíveis**, como MiB e GiB?

- A) `free -h`
- B) `df -h`
- C) `du -h`
- D) `top -h`
- E) `lsblk -h`

**31.** O que o comando `dmesg` mostra?

- A) Todo o conteúdo da memória RAM
- B) As mensagens do buffer de anel do kernel, como as da inicialização e da conexão de dispositivos
- C) Os logins e logouts dos usuários
- D) Os processos em execução
- E) O conteúdo do `/var/log/auth.log`

**32. [lacuna]** Qual comando testa se outro computador responde na rede, enviando pacotes ICMP de eco? Escreva só o comando, sem parâmetros: ______

**33.** Em um sistema com `systemd`, qual comando consulta os registros do **journal**, inclusive filtrando por serviço com `-u`?

- A) `dmesg`
- B) `last`
- C) `syslog`
- D) `tail /var/log/journal`
- E) `journalctl`

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Uma linha do `/etc/shadow` é `ana:!$6$xYz...:19500:0:99999:7:::`. O que indica o `!` antes do hash?

- A) Que `ana` é administradora
- B) Que a senha de `ana` está bloqueada, e ela não entra com senha
- C) Que a conta não tem senha nenhuma
- D) Que a senha expira hoje
- E) Que o hash foi movido para o `/etc/passwd`

**35.** Como aparece no `ls -l` um arquivo com permissão `2755`?

- A) `-rwsr-xr-x`
- B) `-rwxr-xr-t`
- C) `-rwxr-Sr-x`
- D) `-rwxrwxr-x`
- E) `-rwxr-sr-x`

**36.** O diretório `arquivos` tem `drwx-----x`, pertence a `bob` e ao grupo `bob`. A usuária `ana` sabe que dentro dele existe `leia.txt`, com `-rw-r--r--`. O que ela consegue?

- A) Listar o diretório com `ls arquivos`
- B) Criar arquivos dentro de `arquivos`
- C) Ler o arquivo com `cat arquivos/leia.txt`
- D) Nada, porque não tem `r` no diretório
- E) Apagar `leia.txt`

**37.** **(escolha duas)** Quais comandos alteram **contas ou grupos** do sistema, e não arquivos?

- A) `usermod`
- B) `chgrp`
- C) `chmod`
- D) `groupadd`
- E) `chown`

**38.** Qual é a notação octal de `rw-rw-r--`?

- A) `644`
- B) `664`
- C) `666`
- D) `764`
- E) `464`

**39.** Qual comando mostra os **grupos** a que o usuário atual pertence, e só eles?

- A) `groups`
- B) `whoami`
- C) `who`
- D) `last`
- E) `id -u`

**40. [lacuna]** Qual comando altera as **permissões** de um arquivo? Escreva só o comando, sem caminho e sem parâmetros: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **D** | Cada máquina virtual tem o próprio kernel, e o hipervisor reparte o hardware entre elas. Contêineres, `chroot` e namespaces **compartilham** o kernel do hospedeiro, então não rodam outro sistema operacional (Q4 do simulado 04; Correção 63) |
| 2 | **B** | Creative Commons (CC BY, CC BY-SA, CC BY-NC e outras) foi feita para obras culturais. GPL, BSD, MIT e Apache são licenças de software |
| 3 | **A e D** | Firefox (Mozilla) e Chromium (a base aberta do Chrome) são de código aberto. Safari, Edge e Opera são proprietários, ainda que o Edge e o Opera usem o motor do Chromium |
| 4 | **C** | Thunderbird, da Mozilla, é o cliente de e-mail. Apache é servidor web; Blender faz 3D; Inkscape, desenho vetorial; Nextcloud, nuvem de arquivos |
| 5 | **E** | O gerenciador permite usar uma senha única e forte por serviço sem precisar decorá-las; o cofre fica cifrado por uma senha mestra. Reutilizar a mesma senha é justamente o risco que ele evita |
| 6 | **A** | IaaS (infraestrutura como serviço): o provedor entrega a máquina virtual, e o cliente administra dali para cima. No PaaS o provedor cuida do sistema; no SaaS, de tudo |
| 7 | **`GNU`** | Grafia aceita: `GNU`. Por isso a FSF fala em GNU/Linux: o kernel é o Linux, e boa parte do resto (compilador, shell, utilitários) veio do projeto GNU |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **C** | O `$0` sai exatamente como o script foi chamado (`./args.sh`), e o `$#` conta só os argumentos, sem o `$0`: três (reincidência do `$#`; Q16 do R3) |
| 9 | **B** | Seção 1: comandos do usuário. Seção 5: formatos de arquivo. Seção 8: comandos de administração (Q7 do R3) |
| 10 | **E** | O `/home` contém as pastas pessoais, mas não é a pasta de ninguém. `cd` sozinho, `cd ~`, `cd $HOME` e `cd ~davi` levam a `/home/davi` (reincidência: `/home` tratado como a pasta pessoal) |
| 11 | **A** | O `*` casa qualquer sequência, inclusive vazia, mas o nome precisa começar com `foto` e terminar com `.jpg` |
| 12 | **D** | O `file` examina o conteúdo. O `type` diz se um **nome de comando** é interno, alias ou programa; o `stat` mostra os metadados (inode, datas, permissões) |
| 13 | **A e C** | O `find` percorre o disco na hora; o `locate` consulta o banco gerado pelo `updatedb`. O `grep` procura texto **dentro** dos arquivos; o `whatis` consulta o manual |
| 14 | **C** | No `find`, `-size +100M` é "maior que"; `-size -100M` seria "menor que" e `100M` sem sinal, "exatamente". O `locate` não filtra por tamanho |
| 15 | **A** | O `unset` apaga a variável. `NOME=` deixa a variável existindo com valor vazio; `export -n` só tira a marca de exportação; `env -u` vale só para o comando que o `env` executa |
| 16 | **`history`** | Grafia aceita: `history`. A lista fica em `~/.bash_history`, e `!NNN` reexecuta a linha NNN |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **B** | O `tee` copia o que recebe para a tela **e** para o arquivo; com `-a`, acrescenta em vez de sobrescrever. O `>` grava só no arquivo (Q20 do simulado 04) |
| 18 | **E** | O `>` redireciona só o canal 1. A mensagem de erro sai pelo canal 2, que continua ligado ao terminal; a listagem do `/etc` vai para o arquivo |
| 19 | **B** | `-c` cria, `-z` usa gzip, `-f` vem seguido do nome do arquivo a criar e, por último, o que entra nele. O `-j` geraria bzip2, e na D o nome do arquivo está trocado com o do diretório (Correção 80) |
| 20 | **`unxz`** | Grafia aceita: `unxz`. Também funciona `xz -d`, mas a lacuna pede só o comando |
| 21 | **C** | `-i` é *ignore case*. `-v` inverte (mostra as linhas que **não** casam), `-c` conta, `-n` numera e `-r` desce pelos diretórios |
| 22 | **B** | Os campos do `/etc/passwd` são separados por `:`, então é preciso `-d:`. Sem `-d`, o `cut` usa tabulação; `-c1` pegaria só o primeiro caractere |
| 23 | **D** | `-w` conta palavras, `-l` linhas e `-c` bytes. Sem opção, o `wc` mostra os três |
| 24 | **C** | O laço roda uma vez para cada palavra da lista, e as aspas **duplas** expandem o `$n`. O `then` é do `if`; o `for` usa `do` e `done` |
| 25 | **B** | O `$?` guarda o código de saída do último comando: `0` é sucesso e qualquer outro valor é erro. O `ls` responde com 2 quando o caminho não existe |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **D** | `ps -ef` é o estilo Unix (`-e` todos, `-f` formato completo); `ps aux` é o equivalente no estilo BSD, sem hífen. O `ps` sozinho mostra só os processos do terminal atual (Q29 do simulado 04) |
| 27 | **D** | IPv6 tem 128 bits, escritos em oito grupos hexadecimais. O IPv4 tem 32 bits; 48 bits é o tamanho do endereço MAC; 64 é o tamanho usual do prefixo de rede de uma sub-rede IPv6 (Q32 do simulado 04) |
| 28 | **C** | O `/etc/hosts` tem linhas `IP nome`. O `/etc/resolv.conf` diz **quais servidores DNS** consultar; o `/etc/hostname` guarda o nome da própria máquina; o `/etc/nsswitch.conf` define a ordem de consulta (`files dns`) |
| 29 | **D** | A rota `default` diz por onde sai todo o tráfego que não tem rota mais específica: pelo roteador `192.168.0.1`, através da `eth0` |
| 30 | **A** | `free -h` mostra memória e swap. O `df -h` mostra o espaço dos sistemas de arquivos, e o `du -h`, o espaço ocupado por arquivos e diretórios |
| 31 | **B** | O `dmesg` lê o buffer de anel (*ring buffer*) do kernel. Não é um despejo da memória (Correção 82). Os logins ficam no `wtmp`, lido pelo `last` |
| 32 | **`ping`** | Grafia aceita: `ping`. Com `-c 4`, envia só quatro pacotes |
| 33 | **E** | `journalctl -u ssh` mostra os registros do serviço `ssh`; `journalctl -k`, só os do kernel. O journal é binário, por isso não se lê com `tail` |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **B** | `!` ou `*` no campo do hash bloqueiam o login por senha; o `usermod -L` coloca o `!` e o `usermod -U` o retira. Quem é administrador é o UID 0 (Q34 do simulado 04) |
| 35 | **E** | O `2` é SGID e aparece no `x` do **grupo**; o grupo tem `x` (5), então `s` minúsculo. O SUID (4) estaria no dono, e o sticky (1), nos outros como `t` (Q38 do simulado 04; Q14 do R4) |
| 36 | **C** | Em diretório, o `x` deixa atravessar e abrir um nome **conhecido**; sem `r`, ela não lista, e sem `w`, não cria nem apaga. O arquivo tem `r` para os outros, então o `cat` funciona (Q39 do simulado 04) |
| 37 | **A e D** | `usermod` altera uma conta e `groupadd` cria um grupo. `chgrp`, `chmod` e `chown` mudam o grupo, as permissões e o dono **de arquivos** (Q16 do R4) |
| 38 | **B** | `rw-` = 6, `rw-` = 6, `r--` = 4 |
| 39 | **A** | O `groups` lista os grupos; o `id` mostraria também o UID e o GID. O `whoami` mostra o nome do usuário; o `id -u`, só o UID |
| 40 | **`chmod`** | Grafia aceita: `chmod` |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 1 | Contêineres contra máquinas virtuais (Q4 do simulado 04; Correção 63) |
| 8 | `$#` (reincidência, 3 vezes) |
| 9 | Seções do `man` (Q7 do R3) |
| 10 | `/home` contra a pasta pessoal (reincidência) |
| 17 | `tee` (Q20 do simulado 04) |
| 19 | Letras do `tar` (Correção 80) |
| 26 | `ps` de todos os usuários (Q29 do simulado 04) |
| 27 | IPv6 com 128 bits (Q32 do simulado 04) |
| 31 | `dmesg` (Correção 82) |
| 34 | `!` no `/etc/shadow` (Q34 do simulado 04) |
| 35 | SGID no grupo (Q38 do simulado 04; Q14 do R4) |
| 36 | `x` em diretório (Q39 do simulado 04) |
| 37 | Comandos de conta contra comandos de arquivo (Q16 do R4) |

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

## Registro

| Campo | Valor |
| --- | --- |
| Data | 13/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |