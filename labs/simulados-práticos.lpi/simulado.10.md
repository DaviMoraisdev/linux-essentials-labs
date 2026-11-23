# Simulado 10 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 20/11/2026 para o **domingo 22/11**. É o **nível 3** do padrão novo: a maioria das questões traz uma **saída de comando ou um script** para ler e seguir linha a linha (`top`, `free`, `lsblk`, `ip addr`, `ss`, `dmesg`, `last`), com distratores que diferem em um detalhe. Fecha o **ponto de ajuste**, com os simulados 08 e 09. Nenhuma questão repete os simulados 02 a 09, os reforços ou os Exercícios da LPI.

Cinco alternativas por questão, **cinco questões de escolher duas** e cinco lacunas. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. Reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **28 acertos firmes** ou mais |

Faça **antes de qualquer outra tarefa do dia**. Anote as respostas em papel antes de abrir o gabarito e **marque cada chute**, mesmo acertando: sem essa marca, a contagem de firmes não vale.

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

**1.** Uma empresa quer incorporar ao seu produto **proprietário**, vendido e distribuído a clientes, uma biblioteca sob **GPLv3**, sem exceção de ligação. Qual é a situação?

- A) Pode, desde que cite o autor da biblioteca
- B) Pode, desde que não altere a biblioteca
- C) Pode, porque a GPLv3 só vale para uso comercial
- D) Pode, desde que pague a FSF
- E) Não pode manter o produto fechado: teria de distribuí-lo sob a GPLv3, ou trocar por uma biblioteca de licença permissiva ou LGPL

**2.** Um laboratório escolar tem computadores antigos, com pouca memória, e quer um sistema Linux com interface gráfica leve. Qual escolha é a mais adequada?

- A) Ubuntu com GNOME, o mais completo
- B) Red Hat Enterprise Linux em modo servidor, sem interface gráfica
- C) Uma distribuição com ambiente de desktop leve, como Xfce ou LXQt (por exemplo, Xubuntu ou Lubuntu)
- D) Arch Linux sem nenhum ambiente gráfico
- E) Qualquer distribuição *rolling release*

**3.** Quando a Oracle comprou o MySQL, parte da comunidade copiou o código e passou a desenvolver o MariaDB de forma independente. Como se chama isso, e por que foi possível?

- A) Pirataria; só foi possível porque ninguém processou
- B) *Rolling release*; o MySQL não tinha licença
- C) Patch; a Oracle autorizou
- D) *Fork*; a licença livre do MySQL (GPL) permite copiar, modificar e redistribuir o código
- E) Distribuição; a Linux Foundation decidiu

**4.** **(escolha duas)** Num Ubuntu recém-instalado, `sudo apt install nginx` responde *Unable to locate package nginx*. Quais ações fazem sentido?

- A) `sudo apt update`, para baixar a lista atual de pacotes dos repositórios
- B) `sudo rpm -i nginx`
- C) `sudo dpkg -i nginx`
- D) Conferir se o repositório certo está habilitado nas fontes do `apt` (em `/etc/apt/`)
- E) Reiniciar o computador

**5.** Chega um e-mail "do banco" pedindo para atualizar a senha pelo link `https://banco.seguro-atualizacao.xyz/login`. O que fazer?

- A) Não clicar: é provável *phishing*; acessar o banco digitando o endereço oficial ou pelo aplicativo
- B) Responder ao e-mail com a senha
- C) Clicar, porque o link tem HTTPS
- D) Clicar e conferir se o cadeado aparece
- E) Encaminhar para os colegas confirmarem

**6.** Uma equipe quer publicar uma aplicação web que precisa crescer rápido nos horários de pico. Não quer administrar servidores nem sistema operacional: só enviar o código. Qual modelo de nuvem atende?

- A) IaaS
- B) PaaS
- C) SaaS
- D) *On-premise*
- E) Máquinas virtuais no próprio escritório

**7. [lacuna]** Qual é o nome do sistema de controle de versão criado por Linus Torvalds em 2005, usado no desenvolvimento do kernel? Escreva só o nome do comando: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** Qual é a saída do último comando?

```bash
$ cd /tmp
$ mkdir -p a/b
$ cd a/b
$ cd ../..
$ cd -
$ pwd
```

- A) `/tmp`
- B) `/tmp/a`
- C) `/home/davi`
- D) `/`
- E) `/tmp/a/b`

**9.** Um diretório contém `log1.txt`, `log2.txt`, `log10.txt`, `Log3.txt` e `.log4.txt`. Qual é a saída de `ls log?.txt`?

- A) `log1.txt log2.txt Log3.txt`
- B) `log1.txt log2.txt log10.txt`
- C) `log1.txt log2.txt`
- D) `.log4.txt log1.txt log2.txt`
- E) `log1.txt log10.txt log2.txt Log3.txt`

**10.** Qual é a saída de `echo "Custo: \$5 e $((2*3)) itens em '$HOME'"` para o usuário `davi`?

- A) `Custo: $5 e $((2*3)) itens em '/home/davi'`
- B) `Custo: \$5 e 6 itens em '$HOME'`
- C) `Custo: 5 e 2*3 itens em /home/davi`
- D) `Custo: $5 e 6 itens em '/home/davi'`
- E) `Custo: $5 e 6 itens em $HOME`

**11.** Qual é a saída do último comando?

```bash
$ A=1
$ export B=2
$ bash -c 'echo "$A-$B"'
```

- A) `1-2`
- B) `1-`
- C) `-2`
- D) `$A-$B`
- E) `-`

**12.** Qual é o resultado das duas últimas linhas?

```bash
$ echo oi > orig
$ ln orig fisico
$ ln -s orig simbolico
$ rm orig
$ cat fisico
$ cat simbolico
```

- A) `oi` e `oi`
- B) `oi` e uma linha vazia
- C) Dois erros
- D) Um erro e `oi`
- E) `oi` e um erro (*No such file or directory*)

**13.** O usuário quer saber qual comando "lista dispositivos de bloco", mas não lembra o nome. Qual comando o ajuda a descobrir, pesquisando nas descrições do manual?

- A) `whatis block`
- B) `which block`
- C) `help block`
- D) `apropos block`
- E) `type block`

**14.** O usuário digita `mkdir projeto-final` e, em seguida, `cd !$`. O que acontece?

- A) Entra em `projeto-final`
- B) Repete o `mkdir`
- C) Dá erro, porque `!$` não existe no Bash
- D) Volta ao diretório anterior
- E) Entra na pasta pessoal

**15.** **(escolha duas)** Quais comandos copiam o diretório `fotos`, com **todo** o conteúdo, para dentro de `/backup`?

- A) `cp fotos /backup`
- B) `cp -r fotos /backup`
- C) `mv fotos /backup`
- D) `cp -R fotos /backup`
- E) `cp fotos/* /backup`

**16. [lacuna]** Qual comando mostra a descrição de uma linha de um comando, consultando o banco de dados do manual pelo **nome exato**? Escreva só o comando: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual é a saída do script?

```bash
#!/bin/bash
for n in 3 8 12; do
  if [ $n -gt 5 ]; then
    echo -n "$n "
  fi
done
echo
```

- A) `3 8 12`
- B) `3`
- C) `8 12`
- D) `12`
- E) `8`

**18.** Quais são as duas linhas mostradas?

```bash
grep -q root /etc/passwd
echo $?
grep -q naoexiste /etc/passwd
echo $?
```

- A) `0` e `1`
- B) `1` e `0`
- C) `0` e `0`
- D) `root` e nada
- E) `1` e `1`

**19.** O arquivo `vendas.csv` tem as linhas `1,ana,10`, `2,bia,5` e `3,ana,7`. Qual é a saída de `cut -d, -f2 vendas.csv | sort | uniq | wc -l`?

- A) `3`
- B) `2`
- C) `1`
- D) `ana bia`
- E) `22`

**20.** Qual é o conteúdo de `f.txt` no fim?

```bash
echo um > f.txt
echo dois >> f.txt
echo tres > f.txt
```

- A) `um`, `dois` e `tres`
- B) `dois` e `tres`
- C) `um` e `tres`
- D) `tres`
- E) Vazio

**21.** Qual é a saída de `echo "Linux Essentials" | tr 'a-z' 'A-Z'`?

- A) `Linux Essentials`
- B) `Lnx Essntls`
- C) `linux essentials`
- D) `L E`
- E) `LINUX ESSENTIALS`

**22.** O arquivo `log` tem as linhas `erro: disco`, `Erro: rede`, `aviso: erro antigo` e `ok`. Quais são as saídas de `grep -c '^erro' log` e de `grep -ic erro log`?

- A) `1` e `3`
- B) `2` e `3`
- C) `1` e `2`
- D) `3` e `3`
- E) `1` e `4`

**23.** Quais são as linhas mostradas por `./s.sh; echo $?`?

```bash
#!/bin/bash
[ -f /etc/hostname ] && echo existe
[ -d /etc/hostname ] || echo "nao e diretorio"
exit 3
```

- A) `existe` e `0`
- B) `existe`, `nao e diretorio` e `3`
- C) `nao e diretorio` e `3`
- D) `existe` e `3`
- E) `existe`, `nao e diretorio` e `0`

**24.** Num diretório com `a.txt` e `b.txt`, qual é a saída de `arquivos=$(ls *.txt); echo $arquivos`?

- A) `a.txt` e `b.txt` em linhas separadas
- B) `$(ls *.txt)`
- C) `a.txt b.txt`, na mesma linha
- D) `*.txt`
- E) `2`

**25. [lacuna]** Qual parâmetro especial, com o `$`, representa **todos os argumentos** do script, cada um como um item separado quando entre aspas? ______

---

## Tópico 4 — O sistema operacional Linux

**26.** O `top` mostra as linhas abaixo. O que se conclui?

```
Tasks: 120 total,   1 running, 118 sleeping,   0 stopped,   1 zombie
%Cpu(s):  2.0 us,  1.0 sy,  0.0 ni, 96.5 id,  0.5 wa
```

- A) A CPU está sobrecarregada
- B) O sistema está esperando o disco quase o tempo todo
- C) Há 118 processos parados
- D) Há 120 processos em execução
- E) A CPU está quase ociosa, e há um processo zumbi

**27.** O `free -h` mostra a linha abaixo. O que se conclui?

```
       total   used   free   shared  buff/cache  available
Mem:   3.8Gi  1.2Gi  300Mi   50Mi      2.3Gi       2.4Gi
```

- A) A memória está quase esgotada, porque só há 300Mi livres
- B) Há memória de sobra: cerca de 2.4Gi disponíveis, porque o cache pode ser liberado
- C) O sistema já está usando o swap
- D) A coluna `shared` indica um vazamento de memória
- E) É preciso apagar o cache à mão

**28.** O `lsblk` mostra a saída abaixo. Qual afirmação está correta?

```
NAME   SIZE TYPE MOUNTPOINTS
sda     40G disk
├─sda1   1G part /boot/efi
├─sda2  37G part /
└─sda3   2G part [SWAP]
sr0   1024M rom
```

- A) A raiz está em `sda2`, e o swap em `sda3`
- B) A raiz está em `sda1`, e o swap em `sda2`
- C) O `sr0` é um segundo disco rígido
- D) O swap fica em `/boot/efi`
- E) Há três discos

**29.** **(escolha duas)** O `ip addr show enp0s3` mostra a saída abaixo. Quais afirmações estão corretas?

```
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    link/ether 08:00:27:ab:cd:ef brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic enp0s3
    inet6 fe80::a00:27ff:feab:cdef/64 scope link
```

- A) O endereço MAC da placa é `08:00:27:ab:cd:ef`
- B) O IPv6 mostrado é global, alcançável pela internet
- C) A interface está desligada
- D) O endereço IPv4 é `10.0.2.15`, numa rede `/24`
- E) O endereço de broadcast é `10.0.2.15`

**30.** O `ss -tln` mostra as linhas abaixo. O que se conclui?

```
State  Recv-Q Send-Q Local Address:Port  Peer Address:Port
LISTEN 0      128          0.0.0.0:22          0.0.0.0:*
LISTEN 0      511        127.0.0.1:80          0.0.0.0:*
```

- A) Os dois serviços aceitam conexões de outras máquinas
- B) O SSH só aceita conexões locais
- C) O SSH (22) aceita conexões por todas as interfaces; o serviço web (80) só aceita conexões da própria máquina
- D) Nenhum serviço está em escuta
- E) As portas 22 e 80 são UDP

**31.** O `/etc/hosts` tem a linha `192.168.0.50 intranet`, o servidor DNS responde que `intranet` é `10.0.0.9`, e o `/etc/nsswitch.conf` tem `hosts: files dns`. Para onde vai o `ping intranet`?

- A) `10.0.0.9`
- B) Para nenhum: há conflito
- C) Para os dois, alternando
- D) `192.168.0.50`
- E) Para `127.0.0.1`

**32.** Logo depois de conectar um pendrive, o `dmesg` mostra as linhas abaixo. Qual é o arquivo de dispositivo do pendrive?

```
usb 1-1: new high-speed USB device number 3 using xhci_hcd
sd 2:0:0:0: [sdb] Attached SCSI removable disk
```

- A) `/dev/usb1`
- B) `/dev/sdb`
- C) `/dev/sda`
- D) `/dev/xhci`
- E) `/dev/sd2`

**33. [lacuna]** Escreva o **caminho completo** do arquivo que define a ordem de consulta de nomes, na linha `hosts:` (por exemplo, `files dns`): ______

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** **(escolha duas)** O diretório `relatorios` tem `drwxr-x--- 2 ana dev`. O usuário `bob` está no grupo `dev`; a usuária `carol`, não. O que é verdade?

- A) `bob` consegue listar o conteúdo
- B) `bob` consegue criar arquivos no diretório
- C) `carol` consegue entrar com `cd`
- D) `bob` consegue entrar com `cd`
- E) `carol` consegue listar o conteúdo

**35.** O `ls -ld` mostra as quatro linhas abaixo. Qual delas tem o **SGID**?

```
-rwsr-xr-x  root root   /usr/bin/passwd
drwxrwsr-x  root equipe /srv/equipe
drwxrwxrwt  root root   /tmp
-rwxr-xr-x  root root   /usr/bin/ls
```

- A) `/usr/bin/passwd`
- B) Nenhuma
- C) `/tmp`
- D) `/usr/bin/ls`
- E) `/srv/equipe`

**36.** A linha do `/etc/shadow` é `ana:$6$abc...:19700:0:90:7:::`. O que significa o `90`?

- A) Que a conta expira em 90 dias, mesmo trocando a senha
- B) O número mínimo de dias entre duas trocas
- C) O número máximo de dias que a senha vale até precisar ser trocada
- D) Os dias de aviso antes de a senha vencer
- E) A idade da conta

**37.** O administrador executou `sudo usermod -aG docker ana` com a `ana` conectada. Na mesma sessão, ela roda `groups` e o `docker` não aparece. Por quê?

- A) Os grupos são lidos no login: a `ana` precisa sair e entrar de novo (ou abrir uma nova sessão)
- B) O comando falhou sem mostrar erro
- C) O `-aG` não funciona com o grupo `docker`
- D) Só o root vê os grupos com `groups`
- E) O grupo precisa ser criado de novo

**38.** Um arquivo tem permissão `644`. Qual é a permissão depois de `chmod u+x,g=u,o-r arquivo`?

- A) `744`
- B) `770`
- C) `774`
- D) `760`
- E) `700`

**39.** **(escolha duas)** O `last` mostra as linhas abaixo. O que se conclui?

```
ana   pts/0   192.168.0.10   Fri Nov 20 09:12   still logged in
bob   pts/1   10.0.0.7       Fri Nov 20 08:00 - 08:30  (00:30)
```

- A) A `ana` ainda está conectada, a partir de `192.168.0.10`
- B) O `bob` ficou conectado por 30 minutos
- C) O `bob` ainda está conectado
- D) A `ana` se conectou a partir de `10.0.0.7`
- E) O sistema nunca foi reiniciado

**40. [lacuna]** Escreva o **caminho completo** do arquivo com os valores padrão para criar contas, como `UID_MIN` e `CREATE_HOME`: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **E** | Ao distribuir um programa que incorpora código GPL, o conjunto precisa seguir a GPL. A saída é usar uma biblioteca permissiva (MIT, BSD, Apache) ou LGPL (Q2 do simulado 09) |
| 2 | **C** | O que pesa na memória é o ambiente gráfico. Xfce e LXQt usam bem menos recursos que GNOME e KDE Plasma. Um servidor sem interface não atende o pedido de interface gráfica |
| 3 | **D** | *Fork* é um projeto que nasce de uma cópia do código de outro. As licenças livres garantem esse direito; o mesmo aconteceu com o OpenOffice, que deu origem ao LibreOffice |
| 4 | **A e D** | O `apt` procura no índice local, baixado pelo `apt update`; num sistema novo, ele pode estar vazio ou desatualizado. Se continuar faltando, o pacote pode estar num repositório desabilitado. O `rpm` é de outra família, e o `dpkg -i` precisa de um arquivo `.deb` |
| 5 | **A** | O domínio real é `seguro-atualizacao.xyz`, não o do banco: o resto é só um prefixo. HTTPS só cifra a conexão com o site falso (Q6 do simulado 07) |
| 6 | **B** | No PaaS o provedor cuida do sistema e da escala, e o cliente entrega a aplicação. No IaaS a equipe teria de administrar as máquinas virtuais; o SaaS é um programa pronto para usar |
| 7 | **`git`** | Grafia aceita: `git` |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **E** | `cd ../..` sobe duas vezes, de `/tmp/a/b` para `/tmp`. O `cd -` volta ao diretório anterior, `/tmp/a/b`, e o `pwd` confirma |
| 9 | **C** | O `?` casa exatamente **um** caractere: `log10.txt` tem dois. O `Log3.txt` começa com maiúscula, e o `.log4.txt` é oculto e começa com ponto |
| 10 | **D** | Dentro das aspas duplas: `\$` vira um `$` literal; `$((2*3))` é calculado (6); e as aspas simples **dentro** das duplas são só caracteres, sem efeito de proteção, por isso o `$HOME` é expandido |
| 11 | **C** | O `bash -c` é um processo filho: recebe só as variáveis exportadas. O `A` não foi exportado e chega vazio; o `B`, sim (Q9 do simulado 08) |
| 12 | **E** | O link físico aponta para o **inode**, que continua existindo enquanto houver um nome; o simbólico aponta para o **nome** `orig`, que sumiu, e fica quebrado (aulas 63 e 64) |
| 13 | **D** | O `apropos` (igual a `man -k`) procura uma palavra nas descrições curtas das páginas e devolve uma lista, onde aparece o `lsblk`. O `whatis` exige o **nome exato** do comando |
| 14 | **A** | O `!$` é o **último argumento** do comando anterior, `projeto-final`. O `!!` seria o comando inteiro (Q14 do simulado 07) |
| 15 | **B e D** | `-r` e `-R` são equivalentes no `cp` e copiam recursivamente. Sem eles, o `cp` recusa diretórios; o `mv` moveria em vez de copiar; o `fotos/*` copia o conteúdo solto, sem o diretório e sem os ocultos |
| 16 | **`whatis`** | Grafia aceita: `whatis`. O `apropos` procura por palavra nas descrições |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **C** | O laço testa os três números, e só 8 e 12 passam no `-gt 5`. O `echo -n` não quebra a linha, então os dois saem na mesma; o último `echo` fecha a linha |
| 18 | **A** | O `-q` deixa o `grep` silencioso; só o código de saída importa: `0` quando acha, `1` quando não acha (`2` seria erro, como arquivo inexistente) |
| 19 | **B** | O `cut` tira o segundo campo (`ana`, `bia`, `ana`); `sort` e `uniq` deixam `ana` e `bia`; o `wc -l` conta 2 vendedores diferentes |
| 20 | **D** | O terceiro `>` **zera** o arquivo antes de gravar. Só o `>>` acrescenta |
| 21 | **E** | O `tr` troca cada caractere do primeiro conjunto pelo correspondente do segundo: minúsculas viram maiúsculas, e o que já era maiúsculo fica igual |
| 22 | **A** | O `^erro` exige `erro` minúsculo no **início**: só a primeira linha. O `-i` ignora maiúsculas e o padrão sem `^` casa em qualquer posição: as três primeiras |
| 23 | **B** | O `-f` é verdadeiro, e o `&&` mostra `existe`. O `-d` é falso, e o `||` mostra a segunda linha. O `exit 3` define o código lido pelo `echo $?` |
| 24 | **C** | O `$(...)` guarda a saída do `ls`. Sem aspas no `echo`, o shell divide o valor e junta as palavras com um espaço. Com `echo "$arquivos"`, as quebras de linha seriam mantidas |
| 25 | **`$@`** | Grafia aceita: `$@` (ou `"$@"`). O `$#` é a **quantidade** de argumentos |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **E** | O `id` (*idle*) em 96,5% quer dizer CPU livre; o `wa` (espera de disco) está baixo. Há um processo `zombie`, e só 1 está executando agora |
| 27 | **B** | O `free` baixo é normal: o kernel usa a RAM sobrando como cache e a devolve quando um programa precisa. O número que conta é o `available` (Q29 do simulado 07) |
| 28 | **A** | Há um disco (`sda`) com três partições: `sda1` na partição EFI, `sda2` montada em `/` e `sda3` como swap. O `sr0` é a unidade óptica (`rom`) |
| 29 | **A e D** | O `link/ether` é o MAC; o `inet` é o IPv4 com o prefixo. O IPv6 começa com `fe80::`, que é de enlace local (`scope link`), válido só no segmento. O `UP` indica interface ligada, e o broadcast é o `brd 10.0.2.255` |
| 30 | **C** | `0.0.0.0` é "todas as interfaces IPv4"; `127.0.0.1`, só o *loopback*. O `-t` limita a TCP |
| 31 | **D** | A linha `hosts:` define a **ordem**: primeiro `files` (o `/etc/hosts`), depois `dns`. Como o nome já está no `/etc/hosts`, o DNS nem é consultado |
| 32 | **B** | O kernel registrou o disco removível como `sdb`, o que dá `/dev/sdb` (e `/dev/sdb1` para a primeira partição). O `sda` costuma ser o disco do sistema (Exercícios da LPI 4.3) |
| 33 | **`/etc/nsswitch.conf`** | Grafia aceita: `/etc/nsswitch.conf` |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **A e D** | O grupo tem `r-x`: lista (`r`) e entra (`x`), mas não cria (`w`). A `carol` cai nos outros, com `---`: não lista nem entra |
| 35 | **E** | O SGID aparece como `s` no trio do **grupo**: `rwx rws r-x`. O `passwd` tem `s` no dono (SUID), e o `/tmp` tem `t` nos outros (sticky). **4-2-1 = dono-grupo-outros = s-s-t** (Correção 84) |
| 36 | **C** | Depois do hash vêm: data da última troca, mínimo (0), **máximo (90)** e aviso (7). O exercício 5.2 da LPI usou os mesmos campos |
| 37 | **A** | A lista de grupos de um processo é definida quando a sessão começa. O `/etc/group` já foi atualizado, e o `groups ana` (com o nome) já mostraria o grupo, mas a sessão aberta só o ganha num novo login |
| 38 | **B** | As partes são aplicadas em ordem: o dono fica `rwx` (7); o `g=u` copia o dono, já com o `x`: `rwx` (7); os outros perdem o `r`: `---` (0). Resultado: `770` |
| 39 | **A e B** | O `still logged in` indica sessão aberta; o intervalo `08:00 - 08:30` e a duração `(00:30)` indicam sessão encerrada. O `last` lê o `/var/log/wtmp` |
| 40 | **`/etc/login.defs`** | Grafia aceita: `/etc/login.defs` (Exercícios da LPI 5.2) |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 1 | GPL e programas proprietários |
| 5 | HTTPS não garante legitimidade (Q6 do simulado 07) |
| 11 | `export` e processo filho (Q9 do simulado 08) |
| 12 | Links físico e simbólico (aulas 63 e 64) |
| 13 | `apropos` e `whatis` (Q13 do simulado 07) |
| 17 | Laço `for` com `if` em script |
| 18 | Códigos de saída (`$?`) |
| 22 | `grep` com `^` e `-i` (Q22 do simulado 07) |
| 23 | `&&`, `||` e `exit` (Q24 do simulado 07) |
| 27 | Coluna `available` do `free` (Q29 do simulado 07) |
| 34 | `r` e `x` em diretório (reincidência) |
| 35 | SUID, SGID e sticky pelo trio (reincidência, 6 vezes; Correção 84) |
| 38 | `chmod` simbólico com vírgula |
| 39 | `last` (aulas 59 a 63) |

</details>

---

# Apuração

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
| Data | 22/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |