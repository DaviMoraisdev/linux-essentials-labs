# Revisão final — Linux Essentials 010-160

Guia de revisão da última semana antes da prova de **segunda 30/11/2026**. Reúne o que mais cai, por tópico, e os seus erros que se repetiram nos simulados 01 a 08. Escrito em 22/11/2026.

## 0. Como usar

| Dia | Bloco | Seções deste guia |
| --- | --- | --- |
| Seg 23/11 | **R1 — Segurança e permissões** (Tópico 5) | 6 e 7 |
| Ter 24/11 | **R2 — Linha de comando e scripts** (Tópico 3) | 4 e 7 |
| Qua 25/11 | **R3 — Sistema operacional e rede** (Tópico 4) | 5 e 7 |
| Qui 26/11 | **R4 — Comunidade e navegação** (Tópicos 1 e 2) | 2, 3 e 7 |
| Sex 27/11 | Refazer as erradas dos simulados 09 a 12 | 7 e 8 |
| Sáb 28/11 | Só a cola da seção 9, depois do simulado 2 do curso | 9 |
| Dom 29/11 | Descanso. No máximo, 15 minutos na seção 9 | 9 |

Em cada bloco: leia a seção (20 min), feche o guia e escreva de memória, numa folha, as linhas marcadas como **cai sempre** (10 min); depois rode na VM os comandos que errar (20 min).

---

## 1. A prova

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos |
| Aprovação | 500 de 800 pontos (cerca de 26 acertos) |
| Tipos | Múltipla escolha com uma resposta, múltipla escolha com mais de uma resposta (o enunciado diz quantas) e lacuna (digitar a resposta) |
| Pesos | Tópico 1: 7 · Tópico 2: 9 · Tópico 3: 9 · Tópico 4: 8 · Tópico 5: 7 |

**Estratégia.** Primeira passada em 40 minutos, respondendo tudo e marcando as dúvidas; segunda passada nas marcadas. Nas lacunas, digite **só** o pedido: sem `sudo`, sem opções, sem explicação; caminho completo apenas quando o enunciado pedir. Em "escolha duas", confira **cada** alternativa contra o pedido inteiro.

---

## 2. Tópico 1 — Comunidade Linux e open source

| Assunto | Cai sempre |
| --- | --- |
| Famílias | **Debian**: Ubuntu, Mint, Raspberry Pi OS; `.deb`, `dpkg` (baixo nível), `apt` (alto nível). **Red Hat**: Fedora, RHEL, CentOS, Rocky, Alma; `.rpm`, `rpm` (baixo), `dnf`/`yum` (alto). **SUSE**: openSUSE, SLES; `zypper` |
| Ciclos | **LTS**: suporte longo (Ubuntu LTS 5 anos ou mais). **Enterprise** (RHEL): versão nova a cada cerca de 3 anos, **suporte** de cerca de 10. ***Rolling release***: atualização contínua, sem versão maior (Arch, openSUSE Tumbleweed) |
| Embarcados | **Android** usa o kernel Linux (celular, TV, carro). **Raspberry Pi**: placa ARM barata; Raspberry Pi OS deriva do Debian |
| Aplicativos | Escritório: LibreOffice (Writer, Calc, Impress). Navegador: Firefox, Chromium. E-mail: Thunderbird. Imagem: GIMP (raster), Inkscape (vetor). 3D: Blender. Áudio: Audacity. Vídeo: VLC. Web: Apache, NGINX. Banco: MariaDB, PostgreSQL, MySQL. Compartilhamento: **Samba** (com Windows), **NFS** (entre Linux) |
| Linguagens | Compiladas: C, C++, Go, Rust. Interpretadas: Python, Perl, Bash, PHP, JavaScript. Java compila para *bytecode* (JVM) |
| Licenças | **Copyleft**: GPL (derivadas distribuídas seguem a GPL), LGPL (bibliotecas; programa proprietário pode usar), **AGPL** (alcança uso como serviço em rede). **Permissivas**: MIT, BSD, Apache 2.0. Obras culturais: **Creative Commons** (BY atribuição, SA mesma licença, NC sem uso comercial, ND sem derivadas) |
| Regras da GPL | Obrigação nasce na **distribuição**: uso interno não obriga a publicar. Cobrar é permitido. MIT dentro de GPL: o conjunto sai sob GPL |
| Organizações | **FSF**: software livre, quatro liberdades (0 executar, 1 estudar e modificar, 2 redistribuir, 3 distribuir modificadas). **OSI**: *Open Source Definition*. **Linux Foundation**: mantém o kernel. FLOSS = *Free/Libre Open Source Software* |
| Modelos | *Open core*, suporte e consultoria, SaaS sobre software livre, licença dupla |
| Nuvem | **IaaS**: você administra o sistema da máquina virtual. **PaaS**: só envia o código. **SaaS**: usa o programa pronto |
| Virtualização | **Máquina virtual**: kernel **próprio**, sobre um hipervisor. **Contêiner**: **compartilha** o kernel do hospedeiro, sobe em segundos |
| Segurança e privacidade | HTTPS cifra a conexão, **não** garante que o site é legítimo. Cookies de **terceiros** rastreiam entre sites. GnuPG: cifra-se com a chave **pública do destinatário**; assina-se com a **privada** do remetente. Senha forte e única com gerenciador de senhas, mais autenticação em dois fatores |

---

## 3. Tópico 2 — Encontrando seu caminho

| Assunto | Cai sempre |
| --- | --- |
| Comandos internos | `cd`, `echo`, `export`, `alias`, `history`, `jobs`, `fg`, `bg`, `type`, `help`. Ajuda deles: **`help cd`**. `type` diz se é alias, interno ou programa |
| Aspas | Duplas expandem `$var` e `$(cmd)`; simples não expandem nada; `\` protege o próximo caractere. Aspas simples **dentro** de duplas são só caracteres |
| Variáveis | `nome=valor` **sem espaço** em volta do `=`. Sem `export`, o processo filho (`bash -c`, script) não enxerga. `unset` apaga. `env` e `printenv` listam as de ambiente. `PATH`, `HOME`, `PWD`, `OLDPWD` (usado pelo `cd -`), `USER`, `SHELL` |
| Histórico | `~/.bash_history`. `!!` repete o comando inteiro; `!$` é o último argumento |
| Ajuda | `man` (seções: **1** comandos, **5** formatos de arquivo, **8** administração; `man 5 passwd`), `man -k` = `apropos` (busca por palavra), `whatis` (nome exato, uma linha), `info` (formato GNU com nós), `/usr/share/doc` (README, changelog) |
| Caminhos | Absoluto começa com `/`. `.` atual, `..` pai, `~` pasta pessoal, `~ana` pasta da `ana`. `cd -` volta ao **anterior** (só um). Siga `..` passo a passo na margem |
| `ls` | `-a` ocultos, `-l` longo, `-h` tamanhos legíveis, `-t` mais **recente** primeiro, `-r` inverte, `-S` por tamanho, `-R` recursivo, `-d` o próprio diretório, `-i` inode |
| Curingas | `*` qualquer sequência (não casa o ponto inicial dos ocultos), `?` **um** caractere, `[ab]` um da lista, `[!0-9]` um que não seja dígito. Diferencia maiúsculas |
| Arquivos | `mkdir -p` cria os pais. `rmdir` só vazio. `rm -r` com conteúdo, `rm -i` pergunta, `rm -f` força. `cp -r` diretórios; com várias origens, o destino tem de ser **diretório existente**. `mv` com destino inexistente **renomeia**. `touch` cria vazio ou atualiza a data |
| Busca | `find /dir -name "*.conf"` (`-iname` ignora maiúsculas, `-type f` / `-type d`, `-size +100M`). `locate` consulta o banco do **`updatedb`** (arquivo novo não aparece na hora). `which` procura no `PATH` |

---

## 4. Tópico 3 — O poder da linha de comando

| Assunto | Cai sempre |
| --- | --- |
| `tar` | `-c` cria, `-x` extrai, `-t` lista, `-v` detalha, `-f` **arquivo** (vem por último no grupo), `-C dir` destino. Compressão: `-z` gzip (`.tar.gz`, `.tgz`), `-j` bzip2 (`.tar.bz2`), **`-J` xz** (`.tar.xz`). O GNU tar detecta a compressão sozinho na extração (`tar -xf`) |
| Compressores | `gzip`/`gunzip`, `bzip2`/`bunzip2`, `xz`/`unxz`: comprimem **um** arquivo e trocam o original. `xz arq.tar` gera `arq.tar.xz`. `zip -r pacote.zip dir` e `unzip` empacotam e comprimem |
| Canais | 0 entrada, 1 saída, 2 erro. `>` sobrescreve, `>>` acrescenta, `2>` só erro, `&>` os dois, `<` entrada de arquivo, `<<` *here document*, `\|` pipe |
| Ordem | Da esquerda para a direita: `cmd > arq 2>&1` junta os dois no arquivo; `cmd 2>&1 > arq` deixa o erro na tela. `sort f > f` **zera** o arquivo antes do `sort` ler |
| Filtros | `grep` (`-i` ignora maiúsculas, `-v` inverte, `-c` conta, `-r` recursivo, `-E` estendida, `-w` palavra). `sort` (`-n` numérico, `-r` inverso, `-u` único, `-t: -k3`). `uniq` só junta **vizinhas** (`-c` conta): **sempre depois de `sort`**. `cut -d: -f1`. `wc -l -w -c`. `head -n`, `tail -n`, `tail -f`. `tr 'a-z' 'A-Z'`, `tr -d '-'`, `tr -s ' '`. `tee` mostra e grava |
| Expressões regulares | `^` início, `$` fim, `.` um caractere, `*` zero ou mais do anterior, `+` um ou mais (com `-E`), `?` opcional (com `-E`), `[abc]`, `[^abc]`, `a\|b` alternativa (com `-E`) |
| Scripts | `#!/bin/bash` na primeira linha; `chmod +x` para `./script.sh`, ou `bash script.sh` sem permissão. `$0` nome do script, `$1` primeiro argumento, **`$#` quantidade de argumentos (sem o `$0`)**, `$@` todos, `$?` código do último comando (0 = sucesso) |
| Testes | `[ -f arq ]` arquivo comum, `[ -d dir ]` diretório, `[ -e x ]` existe, `[ -z "$v" ]` vazio, `[ -n "$v" ]` não vazio, `-eq -ne -lt -gt` números, `=` e `!=` texto. Espaço dentro dos colchetes |
| Controle | `if ... then ... elif ... else ... fi`; `for x in lista; do ... done`; `while`; `exit N`. `a && b` roda `b` só se `a` deu certo; `a \|\| b` roda `b` só se `a` falhou. `$((2+3))` conta; `$(cmd)` substitui pela saída |

---

## 5. Tópico 4 — O sistema operacional Linux

| Assunto | Cai sempre |
| --- | --- |
| Diretórios | `/etc` configuração, `/var/log` logs, `/var/tmp` temporários que sobrevivem ao boot, `/tmp` temporários (pode ser limpo), `/run` dados da execução (zerado no boot), `/boot` kernel e initramfs, `/home`, `/root`, `/usr/bin`, `/usr/share/doc`, `/opt` |
| Virtuais | `/proc` (um diretório por PID; `/proc/cpuinfo`, `/proc/meminfo`, `/proc/version`), `/sys` (dispositivos, barramentos, drivers), `/dev` (arquivos de dispositivo) |
| Dispositivos | `/dev/sda2` = segunda partição do primeiro disco SATA. NVMe: `/dev/nvme0n1p1`. IDE antigo: `/dev/hda`. `/dev/null` descarta, `/dev/zero` zeros, `/dev/random` aleatório. `b` no `ls -l` = bloco, `c` = caractere |
| Hardware | `lsblk` (discos em árvore), `lspci`, `lsusb`, `lsmod` (módulos), `uname -r` (versão do kernel), `uname -m` (arquitetura), `dmesg` (buffer de anel do kernel, inclusive o pendrive recém-conectado) |
| Processos | `ps` (só o terminal atual), **`ps aux`** (BSD) e **`ps -ef`** (Unix) para todos. `top` (estados `R`, `S`, `T`, `Z` zumbi; *load average* de 1, 5 e 15 minutos). `kill PID` manda `SIGTERM` (15, pedido educado); `kill -9` = `SIGKILL`; `killall nome`. `Ctrl+C` = `SIGINT`, `Ctrl+Z` suspende, `jobs`, `fg %1`, `bg`, `cmd &` |
| Memória | `free -h`: o número que importa é o **`available`**; `free` baixo é normal (cache). Swap cheio e `available` baixo = falta de RAM |
| Logs | Debian e Ubuntu: `/var/log/syslog`, `/var/log/auth.log` (logins e `sudo`), `/var/log/kern.log`. Red Hat: `/var/log/messages`. `journalctl` (`-u ssh`, `-k`). `last` lê o `/var/log/wtmp`; `lastb` o `btmp` |
| Rede | IPv4: 32 bits; **IPv6: 128 bits**, hexadecimal, `::` uma vez só, `fe80::` enlace local. Privados: `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`. Loopback: `127.0.0.1` e `::1`. `/24` = **254 hosts** (tira rede e broadcast). Destino fora da rede local passa pelo **gateway** (`default via` no `ip route`) |
| Comandos de rede | `ip addr` (endereços e MAC), `ip route` (rotas), `ss -tln` (TCP em escuta; `-u` UDP), `ping`, `host` e `dig` (DNS), `netstat` (antigo), `ifconfig` (antigo) |
| Nomes | `/etc/hosts` (tabela local), `/etc/resolv.conf` (servidores DNS, `nameserver`), `/etc/nsswitch.conf` (ordem: `hosts: files dns`), `/etc/hostname`. IP responde e o nome não: problema de **DNS** |
| Portas | 22 SSH, 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS |

---

## 6. Tópico 5 — Segurança e permissões

| Assunto | Cai sempre |
| --- | --- |
| Contas | **root = UID 0**. Contas de sistema: UID abaixo de 1000, shell `nologin`. `id`, `groups`, `whoami`, `who` (quem está logado), `w` (logado e o que faz), `last` (histórico) |
| Arquivos de contas | `/etc/passwd` (nome:x:UID:GID:GECOS:pasta:shell; o `x` indica que o hash está no shadow), **`/etc/shadow`** (hashes; `!` ou `*` = senha bloqueada; campos de mínimo, **máximo**, aviso), `/etc/group` (quarto campo = membros secundários), `/etc/gshadow`, `/etc/skel` (copiado na criação da pasta), `/etc/login.defs` |
| Comandos de **conta** | `useradd -m -G grupo nome`, `usermod -aG grupo nome` (acrescenta sem tirar), `userdel -r`, `groupadd`, `groupdel`, `passwd`. Grupo novo vale **no próximo login** |
| Comandos de **arquivo** | `chmod`, `chown dono:grupo`, `chown :grupo`, `chgrp grupo`, `-R` recursivo |
| `su` e `sudo` | `su -` pede a senha do **root** e abre login completo; `su` sem `-` mantém o ambiente. `sudo` pede a senha **do próprio usuário** e registra no log; `sudo -i` e `sudo su -` abrem shell de root com a senha do usuário |
| Octal | `r` 4, `w` 2, `x` 1; trio a trio: `rw-r-----` = 640, `rwxr-x--x` = 751 |
| Simbólico | `u g o a`, `+ - =`, **sem espaço depois da vírgula**: `chmod u+x,go-w arq`. As partes são aplicadas em ordem (`g=u` copia o dono já alterado). Dígitos que faltam são zeros à esquerda: `chmod 4` = `0004` |
| Em diretório | **`r`** lista os nomes, **`x`** entra e abre um nome conhecido (mínimo para o `cd`: `--x`), **`w`** cria e **apaga** (mesmo arquivos de outros), a não ser com sticky bit |
| Bits especiais | **4-2-1 = dono-grupo-outros = s-s-t.** **SUID 4**: `s` no dono; roda com o UID do dono (`/usr/bin/passwd`, `-rwsr-xr-x` = 4755). **SGID 2**: `s` no grupo; em diretório, arquivos criados herdam o **grupo do diretório** (`drwxrwsr-x` = 2775). **Sticky 1**: `t` nos outros; só o dono do arquivo, o dono do diretório e o root apagam (`/tmp`, `drwxrwxrwt` = 1777). Maiúscula (`S`, `T`) = sem o `x` daquele trio |
| Gravar | `>>` também é **escrita**: com `640`, o grupo não acrescenta |
| Links | **Físico** (`ln`): mesmo inode, sobrevive à remoção do original, não cruza sistemas de arquivos nem aponta para diretórios. **Simbólico** (`ln -s alvo nome`): aponta para o **nome**, quebra se o alvo some, cruza sistemas de arquivos, `l` no `ls -l` |

---

## 7. Seus erros que se repetiram

Os dez pontos que mais voltaram nos simulados 01 a 08 e nas lacunas. Leia a regra, cubra a coluna e explique em voz alta.

| # | Erro | Vezes | Regra |
| --- | --- | --- | --- |
| 1 | Bit especial no trio errado | 7 | O **dígito** diz o bit, o bit diz o trio: 4 dono (`s`), 2 grupo (`s`), 1 outros (`t`). SGID em diretório: arquivo herda o grupo do diretório |
| 2 | Espaço que muda o comando | 14 (com forma das lacunas) | Espaço separa argumentos: `chmod u+x,go-w`, `PATH="$PATH:..."`, `x=5`, sem espaço. Na lacuna, só o pedido |
| 3 | `$#` contando o `$0` | 4 | `$#` = palavras **depois** do nome do script |
| 4 | Comando de conta contra comando de arquivo | 4 | Arquivo: `chmod`, `chown`, `chgrp`. Conta e grupo: `useradd`, `usermod`, `groupadd`, `passwd` |
| 5 | Arquivos de contas | 4 | `!` no `/etc/shadow` = bloqueada; administrador = UID 0; `useradd` grava em `passwd`, `shadow` e `group`; `/etc/hosts` é de rede |
| 6 | Contêiner contra máquina virtual | 3 | Contêiner divide o kernel; máquina virtual tem o seu |
| 7 | `x` e `r` em diretório | 3 | `x` entra, `r` lista, `w` cria e apaga |
| 8 | Canal 2 e ordem do `2>&1` | 3 | `>` leva só o canal 1. `> arq 2>&1`, nessa ordem |
| 9 | `uniq` sem `sort`, `sort` sem `-n` | 2 | `sort \| uniq -c \| sort -nr`. Sem `-n`, `10` vem antes de `9` |
| 10 | Rede `/24` e gateway | 2 | 254 hosts. O que está fora da rede local sai pelo gateway |

---

## 8. Armadilhas de leitura

Metade dos seus erros nos simulados 04 a 08 foi de leitura, com o conteúdo sabido em outro formato. Antes de marcar:

1. **Sublinhe a palavra-chave**: "não", "só", "todos", "sem", "próprio kernel", "dentro de", "acrescenta".
2. **Em situação, faça o passo a passo na margem** (`cd`, pipeline, script): escreva o resultado de cada etapa.
3. **Em "escolha duas", teste cada alternativa contra o pedido inteiro** (servidor web **e** banco; dono **e** grupo).
4. **Se duas alternativas parecem certas, procure o detalhe**: uma letra de opção (`-j` e `-J`), a ordem (`2>&1` antes ou depois), um sinal (`+100M`).
5. **Marque a dúvida como chute** e volte na segunda passada.

---

## 9. Cola de uma página (sábado e domingo)

- **Bits:** 4-2-1 = dono-grupo-outros = s-s-t. SGID em diretório herda o grupo. Sticky: só o dono apaga.
- **Diretório:** `r` lista, `x` entra, `w` cria e apaga.
- **`$#`** sem o `$0`. **`$?`** 0 = sucesso. **`-d`** diretório, **`-f`** arquivo, **`-z`** vazio.
- **Redirecionamento:** `> arq 2>&1`. `>>` acrescenta. `sort f > f` zera.
- **Pipeline:** `sort | uniq -c | sort -nr | head`. `head -n 5 | tail -n 1` = quinta linha.
- **`tar`:** `-z` gz, `-j` bz2, `-J` xz; `-c` cria, `-x` extrai, `-t` lista.
- **Rede:** IPv6 128 bits. `/24` = 254 hosts. Fora da rede: gateway. IP responde e nome não: DNS (`/etc/resolv.conf`). `/etc/hosts` antes do DNS.
- **Processos:** `ps aux` ou `ps -ef`. `kill` = 15; `-9` = força. `Ctrl+Z` suspende, `fg` volta.
- **Contas:** UID 0 = root. `!` no shadow = bloqueada. `usermod -aG`. Conta: `usermod`; arquivo: `chgrp`/`chmod`.
- **Licenças:** GPL na distribuição; AGPL em rede; LGPL deixa proprietário usar a biblioteca. OSI define *open source*; FSF, software livre.
- **Virtualização:** contêiner divide o kernel; máquina virtual tem o seu. IaaS administra o sistema; PaaS só o código; SaaS usa pronto.