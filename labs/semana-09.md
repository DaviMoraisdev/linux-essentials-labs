# Semana 9 — Conteúdo final: Tópico 4 e curso fechado

Período: 26/10 a 01/11/2026 (segunda a domingo)
Objetivos da prova: 4.1, 4.2, 4.3 e 4.4 — Tópico 4, peso 8 de 40
**Data da prova: segunda-feira, 30/11/2026**
Situação: **fechada em 02/11**, com as Práticas 3, 4 e 5 feitas
Marco da semana: **Tópico 4 praticado**. O simulado 03 passou para a terça 03/11. As aulas 41 a 72 e o bloco curto (4.1 e here document) passaram para a Semana 10, junto com a operação prática (`labs/operacao-pratica.md`)

**Semana refeita em 26/10, com a nova estratégia, e de novo em 29/10; fechada em 02/11.** As três práticas do Tópico 4 foram feitas: a Prática 3 entre 27 e 30/10, e as Práticas 4 e 5 até 02/11. O simulado 03, as aulas 41 a 72, o bloco curto e os Exercícios da LPI 4.2 e 4.3 estão nos primeiros dias da operação prática (`labs/operacao-pratica.md`).

O Tópico 4 nunca foi estudado como tópico, mas boa parte dele já foi encostada na prática: LVM e partições na Semana 0, `/proc` e `/dev` na Semana 3, portas e serviços na Semana 1, gerenciadores de pacotes no curso. A cobertura parte de cerca de 30%. No simulado 02, os quatro erros do tópico apontam o que mais precisa de atenção: **dispositivos `/dev/sd*` (Q30), `/etc/resolv.conf` (Q31), faixas IPv4 privadas (Q32) e `kill -9` (Q33)**. O sinal padrão do `kill` também caiu no simulado 01.

---

## Objetivos oficiais cobertos

Fonte: LPI Learning Material, versão 1.6, Tópico 4.

| Objetivo | Peso | Áreas-chave | Arquivos, termos e utilitários |
|---|---|---|---|
| 4.1 Escolhendo um sistema operacional | 1 | Windows, macOS e Linux; ciclo de vida das distribuições | Interface gráfica e linha de comando; LTS, estável, beta, rolling release |
| 4.2 Entendendo o hardware do computador | 2 | Hardware | Placas-mãe, processadores, fontes, drives ópticos, periféricos; discos e partições, `/dev/sd*`; drivers |
| 4.3 Onde os dados são armazenados | **3** | Programas e configuração, pacotes e banco de dados de pacotes; processos, endereços de memória, mensagens do sistema e logs | `ps`, `top`, `free`; `syslog`, `dmesg`; `/etc/`, `/var/log/`; `/boot/`, `/proc/`, `/dev/`, `/sys/` |
| 4.4 Seu computador na rede | 2 | Internet, rede, roteadores; configuração do cliente DNS; configuração da rede | `route`, `ip route show`; `ifconfig`, `ip addr show`; `netstat`, `ss`; `/etc/resolv.conf`, `/etc/hosts`; IPv4, IPv6; `ping`; `host` |

O 4.3, de peso 3, é o maior do tópico e o que mais se cobra em questões de "onde fica". Por isso aparece em duas práticas.

---

## Calendário da semana

**Refeito em 29/10 e fechado em 02/11.**

| Dia | Atividade | Situação |
|---|---|---|
| Seg 26 a qui 29 | Prática 3, bloco 1 (anotado em 27/10) | **feito** |
| Sex 30 | Prática 3, blocos 2 a 4; os Exercícios da LPI 4.2 foram para a sexta 06/11 | **feito** |
| Sáb 31 | Descanso | — |
| Dom 01 e seg 02/11 | **Práticas 4 e 5** | **feitas**; anotações da Prática 5 a recuperar |
| Ter 03/11 | **Simulado 03**, aulas 41 a 60 e Exercícios da LPI 4.3: já na operação prática (`labs/operacao-pratica.md`) | — |

Com as três práticas feitas, **o Tópico 4 está praticado**. O que resta de conteúdo (aulas 41 a 72, 4.1 e here document, Exercícios da LPI 4.2 e 4.3) está nos primeiros dias da operação prática.

---

## Antes de começar

Formato igual ao das práticas anteriores: **45 minutos de teclado, 10 de registro, 5 de commit**, prevendo a saída **antes** de executar. No fim de cada prática, **20 minutos de Exercícios Guiados e Exploratórios** da lição correspondente do PDF da LPI, sem consultar o texto.

Instale na VM o que pode faltar (o Ubuntu Server nem sempre traz):

```bash
sudo apt update && sudo apt install -y pciutils usbutils net-tools bind9-dnsutils
```

| Pacote | Traz |
|---|---|
| `pciutils` | `lspci` |
| `usbutils` | `lsusb` |
| `net-tools` | `ifconfig`, `route`, `netstat` (os comandos antigos que a prova ainda cita) |
| `bind9-dnsutils` | `dig` e `host` |

---

## Prática 3 — Hardware, discos e o mapa dos diretórios

Objetivos 4.2 e 4.3 (primeira parte).

### Bloco 1 — Processador, memória e barramentos (10 min)

```bash
lscpu | head -15
grep -m1 'model name' /proc/cpuinfo
grep -c processor /proc/cpuinfo
free -h
head -3 /proc/meminfo
lspci
lsusb
lsmod | head
```

Para o caderno: de onde o `lscpu` e o `free` tiram os números (os dois leem do `/proc`)? Quantos processadores a VM tem e por que bate com o que você configurou no VirtualBox? O que o `lsmod` lista? (Os **módulos do kernel** carregados, que é a forma como os **drivers** existem no Linux.)

### Bloco 2 — Discos e partições (10 min)

```bash
lsblk
lsblk -f
ls -l /dev/sd*
df -h
df -h -t tmpfs
du -sh /var/log
```

Para o caderno:

- A convenção de nomes: `sd` + letra do disco + número da partição. `/dev/sda3` é a **terceira partição do primeiro disco**. Qual seria a segunda partição do terceiro disco? (`/dev/sdc2`.)
- No `ls -l /dev/sd*`, a primeira letra é `b`: **dispositivo de bloco**. Compare com `ls -l /dev/tty /dev/null`, que começam com `c`, **dispositivo de caractere**.
- Por que o `/boot` está em `sda2`, fora do LVM? (O carregador de inicialização precisa ler o kernel antes de o LVM existir.)
- `df` mostra o espaço por **sistema de arquivos montado**; `du` mostra o espaço ocupado por **diretórios e arquivos**.

### Bloco 3 — O mapa dos diretórios (15 min)

```bash
ls /proc | head ; cat /proc/$$/status | head -5
cat /proc/version ; cat /proc/uptime
ls /sys ; ls /sys/class/net ; cat /sys/class/net/enp0s3/address
ls -l /dev/sda /dev/tty /dev/null /dev/zero
ls /boot
ls /etc | head ; cat /etc/os-release
ls /var/log
```

Preencha de memória e depois confira executando:

| Diretório | Real ou virtual | O que guarda | Um arquivo que você leu |
|---|---|---|---|
| `/proc` | | | |
| `/sys` | | | |
| `/dev` | | | |
| `/boot` | | | |
| `/etc` | | | |
| `/var/log` | | | |

Regra para fixar: **`/proc` é de processos** (e informações do kernel, como `cpuinfo` e `meminfo`); **`/sys` é de dispositivos e drivers, organizados pelo kernel**; **`/dev` são os arquivos de dispositivo** que os programas abrem. Os três são montados pelo kernel e não ocupam disco.

### Bloco 4 — Programas, configuração e banco de dados de pacotes (10 min)

```bash
which ls ; dpkg -S /usr/bin/ls
dpkg -L coreutils | head
dpkg -l | wc -l
ls /var/lib/dpkg | head
ls /etc/ssh
```

No container Rocky, o equivalente:

```bash
docker run -it --rm rockylinux/rockylinux:10 bash
rpm -qf /usr/bin/ls ; rpm -ql coreutils | head ; rpm -qa | wc -l ; ls /var/lib/rpm
```

Para o caderno: o programa mora em `/usr/bin`, a configuração em `/etc`, e o **banco de dados de pacotes** em `/var/lib/dpkg` (Debian) ou `/var/lib/rpm` (Red Hat). `dpkg -S` e `rpm -qf` respondem "de qual pacote veio este arquivo?".

### Exercícios da LPI (20 min, ao fim da sessão)

Exercícios Guiados e Exploratórios da lição 4.2. Responda **sem consultar o texto**, depois confira em "Respostas aos Exercícios". Anote só as questões erradas.

## Prática 4 — Processos, memória e logs

Objetivo 4.3 (segunda parte), o de maior peso do tópico.

### Bloco 1 — Listar processos (10 min)

```bash
ps
ps aux | head
ps -ef | head
ps aux --sort=-%cpu | head -5
echo $$ ; ps -p $$
```

Para o caderno: o que significam as colunas `PID`, `USER`, `%CPU`, `%MEM` e `STAT` do `ps aux`? Qual é o processo de PID 1 e por quê? O `ps` é uma **foto**; o `top`, a seguir, é um **filme**.

### Bloco 2 — `top` e memória (10 min)

```bash
top
```

Dentro do `top`: `P` ordena por CPU, `M` por memória, `k` pede um PID para encerrar, `q` sai. Depois:

```bash
free -h
uptime
cat /proc/loadavg
```

Para o caderno: o que é *load average* e o que são os três números (1, 5 e 15 minutos)? Por que a coluna `available` do `free` importa mais que a `free`?

### Bloco 3 — Primeiro e segundo plano, e sinais (15 min)

```bash
sleep 300 &
jobs
sleep 400
# pressione Ctrl+Z
jobs
bg
jobs
fg %1
# pressione Ctrl+C
kill -l | head -3
sleep 500 & echo $!
kill $!            # prediga: qual sinal foi enviado?
sleep 600 &
kill -9 $!
jobs
```

Para o caderno, com o **mecanismo**:

| Sinal | Número | Efeito |
|---|---|---|
| `SIGTERM` | 15 | **Padrão do `kill`.** Pede para o processo encerrar; ele pode tratar o pedido e limpar o que precisa |
| `SIGKILL` | 9 | Encerra à força, pelo kernel; o processo não pode tratar nem ignorar |
| `SIGHUP` | 1 | Historicamente, "o terminal caiu"; muitos serviços o usam para reler a configuração |
| `SIGINT` | 2 | O que o `Ctrl+C` envia |

`&` inicia em segundo plano; `Ctrl+Z` suspende; `bg` continua em segundo plano; `fg` traz para o primeiro plano; `jobs` lista os trabalhos **deste shell**.

### Bloco 4 — Mensagens do sistema e logs (10 min)

```bash
sudo dmesg | tail
sudo dmesg | grep -i enp0s3
ls -l /var/log
sudo tail -5 /var/log/syslog
logger "teste do lab de logs"
sudo grep "teste do lab" /var/log/syslog
journalctl -n 10 --no-pager
```

Para o caderno: o `dmesg` mostra o **buffer de mensagens do kernel** (inicialização, drivers, dispositivos conectados); o **syslog** (no Ubuntu, o serviço `rsyslog`) grava as mensagens do sistema e dos serviços em arquivos de `/var/log`; o `journalctl` lê o diário do `systemd`. Se o `/var/log/syslog` não existir na sua VM, anote isso: indica que só o journal está ativo.

### Exercícios da LPI (20 min, ao fim da sessão)

Exercícios Guiados e Exploratórios da lição 4.3 (lições 1 e 2). Responda **sem consultar o texto**, depois confira em "Respostas aos Exercícios". Anote só as questões erradas.

## Prática 5 — Rede

Objetivo 4.4. Na VM, a rede é a do VirtualBox em modo NAT, que você já conhece da Semana 0.

### Bloco 1 — Interfaces e endereços (10 min)

```bash
ip addr show
ip -4 addr show enp0s3
ip -6 addr show enp0s3
ifconfig
```

Para o caderno: identifique `lo` (`127.0.0.1` e `::1`, a própria máquina) e `enp0s3` (`10.0.2.15/24`). O endereço IPv6 que começa com `fe80::` é **link-local**: existe só no enlace. O `ifconfig` é o comando antigo (pacote `net-tools`); o `ip` é o atual. A prova cobra os dois nomes.

### Bloco 2 — Roteamento (10 min)

```bash
ip route show
route -n
ping -c 3 10.0.2.2
ping -c 3 1.1.1.1
```

Para o caderno: a linha `default via 10.0.2.2` é a **rota padrão**: tudo o que não é da rede local vai para esse roteador, que no NAT do VirtualBox é o próprio host. O `-c 3` faz o `ping` parar depois de três pacotes.

### Bloco 3 — DNS (15 min)

```bash
cat /etc/resolv.conf
cat /etc/hosts
host lpi.org
dig lpi.org +short
ping -c 1 lpi.org
echo '127.0.0.1 labteste' | sudo tee -a /etc/hosts
ping -c 1 labteste
sudo sed -i '/labteste/d' /etc/hosts
```

Para o caderno: o `/etc/resolv.conf` diz **quais servidores DNS** consultar (no Ubuntu aparece `127.0.0.53`, o resolvedor local do `systemd-resolved`); o `/etc/hosts` é uma **tabela local**, consultada antes do DNS, e por isso o `labteste` funcionou sem servidor nenhum. O `host` dá uma resposta curta; o `dig`, a detalhada.

### Bloco 4 — Sockets e portas (10 min)

```bash
ss -tuln
ss -tlnp | grep 22
sudo ss -tlnp
ss -s
netstat -tuln
```

Para o caderno: no `ss -tuln`, `t` é TCP, `u` UDP, `l` só as portas **escutando**, `n` mostra números em vez de nomes. Ache o `sshd` na porta **22**. O `netstat` é o equivalente antigo (`net-tools`).

**Teoria para o caderno (5 min, sem terminal):**

| Tema | O que fixar |
|---|---|
| Faixas IPv4 privadas | `10.0.0.0/8`, `172.16.0.0/12` (de `172.16` a `172.31`) e `192.168.0.0/16` |
| IPv4 e IPv6 | 32 bits em decimal (`192.168.0.1`) contra 128 bits em hexadecimal (`2001:db8::1`); `::` abrevia uma sequência de zeros, uma vez por endereço |
| Máscara | `/24` equivale a `255.255.255.0` |
| TCP e UDP | TCP com conexão e confirmação; UDP sem conexão, mais leve (DNS usa UDP 53) |
| Portas comuns | 22 SSH, 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS |
| DHCP | Entrega IP, máscara, rota padrão e DNS automaticamente; é o que deu o `10.0.2.15` à VM |

### Exercícios da LPI (20 min, ao fim da sessão)

Exercícios Guiados e Exploratórios da lição 4.4. Responda **sem consultar o texto**, depois confira em "Respostas aos Exercícios". Anote só as questões erradas.

## Bloco curto — 4.1, here document e NDG

### 4.1, leitura e exercícios (30 min)

Leia a lição 4.1 do PDF e responda aos Exercícios. Para o caderno, uma tabela de três colunas (Windows, macOS, Linux) com: licença, kernel (o macOS usa o Darwin), interface padrão e como se instala software. E o ciclo de vida: versão **beta** (teste), **estável**, **LTS** (suporte estendido com atualizações de segurança por vários anos, como o Ubuntu 26.04 da sua VM) e **rolling release** (atualização contínua, sem versões fixas, como o Arch).

### Here document (15 min)

Na VM:

```bash
nome=Davi
cat << FIM
Ola, $nome
Hoje: $(date +%d/%m)
FIM
cat << 'FIM'
Ola, $nome
FIM
cat << FIM > lista.txt
um
dois
FIM
cat lista.txt ; wc -l lista.txt
```

Para o caderno: o `<<` alimenta a **entrada padrão** do comando com as linhas seguintes, até a linha que contém **só** o delimitador; o delimitador não entra no texto. Sem aspas no delimitador, variáveis e `$(...)` são expandidas; com aspas (`'FIM'`), o texto é literal. Não confundir com o `<`, que lê de um **arquivo**, nem com o `>>`, que acrescenta a um arquivo.

### NDG (30 min, opcional)

Quizzes dos capítulos de hardware, processos e rede e do capítulo de permissões, no NDG Linux Essentials. Anote só as questões erradas.

---

## Registro das sessões

### Prática 3 — 27 e 30/10 — CONCLUÍDA (Exercícios da LPI 4.2 na Semana 10)

**Bloco 1 anotado em 27/10; blocos 2 a 4 em 30/10.** Os Exercícios da LPI 4.2 foram para a Semana 10, na sexta 06/11, junto com o bloco curto (ajuste de 30/10).

#### Bloco 1 — Processador, memória e barramentos

| Comando | O que faz | Resultado na VM |
|---|---|---|
| `lscpu \| head -15` | Resume a arquitetura e os processadores | — |
| `grep -m1 'model name' /proc/cpuinfo` | Mostra o modelo do processador | Uma linha |
| `grep -c processor /proc/cpuinfo` | Conta as linhas com `processor`: uma por processador lógico | **2** |
| `free -h` | Memória total, usada e livre, e o swap, em unidades legíveis (MiB, GiB) | — |
| `head -3 /proc/meminfo` | As primeiras linhas de onde o `free` tira os números (`MemTotal`, `MemFree`, `MemAvailable`) | — |
| `lspci` | Dispositivos no barramento PCI/PCI Express; na VM, os virtuais do VirtualBox (vídeo, rede) | — |
| `lsusb` | Dispositivos USB visíveis | — |
| `lsmod \| head` | Módulos carregados no kernel | — |

**Para o caderno, revisado:**

| Pergunta | Resposta |
|---|---|
| De onde o `lscpu` e o `free` tiram os números? | O `free` lê o `/proc/meminfo`; o `lscpu` lê o `/proc/cpuinfo` e o `/sys`. São arquivos virtuais, gerados pelo kernel na hora em que são lidos: não ocupam disco |
| Quantos processadores a VM tem? | **2 lógicos**, as 2 vCPUs configuradas no VirtualBox na criação da VM |
| O que o `lsmod` lista? | Os **módulos do kernel** carregados, que é a forma como a maioria dos **drivers** existe no Linux. Nem todo módulo é driver, e alguns drivers vêm embutidos no próprio kernel |

**Correções:**

1. **O `-m1` do `grep` não "diz onde está o conteúdo".** É `--max-count=1`: o `grep` para depois da **primeira** linha que casa. Sem ele, o `/proc/cpuinfo` repete o bloco para cada processador, e o `model name` sairia duas vezes na sua VM. Ver Correção 76.
2. **Swap** é um espaço **em disco** (partição ou arquivo) usado quando a RAM enche. É mais lento que a RAM; "reserva" é uma boa forma de lembrar.
3. Grafia: "kerne" → **kernel**; "mémoria" → **memória**.

O resto está certo, e a nuance sobre módulos e drivers vai além do que o roteiro pedia.

#### Bloco 2 — Discos e partições

Saída do `lsblk` na VM:

```
NAME                      MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
sda                         8:0    0   25G  0 disk
├─sda1                      8:1    0    1M  0 part
├─sda2                      8:2    0    2G  0 part /boot
└─sda3                      8:3    0   23G  0 part
  └─ubuntu--vg-ubuntu--lv 252:0    0   23G  0 lvm  /
sr0                        11:0    1 1024M  1 rom
```

| Item | Leitura |
|---|---|
| `sda` | O disco (`TYPE` `disk`) |
| `sda1` | Partição de 1 MiB, sem sistema de arquivos: é a partição de *BIOS boot* que o GRUB usa em discos GPT |
| `sda2` | `/boot`, 2 GiB, fora do LVM |
| `sda3` | Partição que serve de volume físico do LVM |
| `ubuntu--vg-ubuntu--lv` | Volume lógico do LVM, montado em `/` |
| `sr0` | **Drive óptico** virtual (CD/DVD) do VirtualBox: `RM` 1 = removível, `RO` 1 = somente leitura, `TYPE` `rom`. É o "drive óptico" que o objetivo 4.2 cita |

**LVM** (*Logical Volume Manager*): camada entre os discos físicos e os volumes que o sistema monta, que permite aumentar, reduzir e juntar espaço com flexibilidade. Foi o que permitiu estender o volume para 23 GiB na Semana 0.

| Comando | O que faz |
|---|---|
| `lsblk -f` | Acrescenta as colunas de **sistema de arquivos**: `FSTYPE` (`ext4`, `LVM2_member`), `UUID`, rótulo, espaço livre e uso |
| `ls -l /dev/sd*` | O **shell** expande o `*` para os nomes que começam com `/dev/sd`; o `ls` lista os quatro: `sda`, `sda1`, `sda2`, `sda3` |
| `df -h` | Espaço livre e usado **por sistema de arquivos montado** |
| `df -h -t tmpfs` | Só os sistemas de arquivos do tipo `tmpfs`: temporários, em memória virtual (RAM e, se preciso, swap) |
| `du -sh /var/log` | Espaço ocupado por **um diretório** e tudo dentro dele: `-s` resume em um total, `-h` em unidades legíveis |

No `ls -l /dev/sd*`, onde normalmente fica o tamanho aparece `8, 0`, `8, 1`... São os números **major** e **minor**: o major (8) identifica o driver do disco, e o minor, cada dispositivo ou partição. Arquivo de dispositivo não tem tamanho.

**Para o caderno, revisado:**

| Pergunta | Resposta |
|---|---|
| Segunda partição do terceiro disco | `/dev/sdc2`: `sd` + `c` (terceiro disco: a, b, c) + `2` |
| O que é o `b` no `ls -l /dev/sda`? | **Dispositivo de bloco**: lê e grava em blocos, como discos e partições. O `/dev/tty` e o `/dev/null` começam com `c`: **dispositivo de caractere**, um fluxo de bytes |
| Por que o `/boot` está em `sda2`, fora do LVM? | *Estava em branco.* O carregador de inicialização (GRUB) precisa ler o kernel e o `initramfs` **antes** de o LVM existir; quem ativa o LVM é o próprio `initramfs`, já carregado. Por isso o `/boot` fica numa partição comum |
| `df` contra `du` | `df` mostra o espaço **por sistema de arquivos montado**; `du` soma o espaço **ocupado por diretórios e arquivos**. Medem coisas diferentes, por isso os números não batem |

#### Bloco 3 — O mapa dos diretórios

| Comando | O que mostra |
|---|---|
| `ls /proc \| head` | Diretórios com **números**, um para cada processo em execução (o número é o PID), e arquivos do kernel, como `cpuinfo` e `meminfo` |
| `cat /proc/$$/status \| head -5` | O `$$` vira o **PID do shell atual**; as primeiras linhas do `status` trazem o nome do processo (`bash`), o estado e o PID |
| `cat /proc/version` | A versão do kernel e o compilador usado |
| `cat /proc/uptime` | Dois números: segundos desde a inicialização e segundos somados de CPU ociosa (com mais de uma CPU, o segundo pode passar do primeiro) |
| `ls /sys/class/net` | `enp0s3` (a placa de rede da VM) e `lo` (*loopback*, a comunicação da máquina com ela mesma) |
| `cat /sys/class/net/enp0s3/address` | O **endereço MAC** da placa. O prefixo `08:00:27` é o do VirtualBox |
| `ls -l /dev/sda /dev/tty /dev/null /dev/zero` | `/dev/sda` é bloco (`b`); os outros três são caractere (`c`). `/dev/tty`: o terminal do processo; `/dev/null`: descarta o que recebe; `/dev/zero`: devolve zeros |
| `ls /boot` | `vmlinuz-*` (o kernel), `initrd.img-*` (o `initramfs`) e o diretório `grub` |
| `cat /etc/os-release` | Nome e versão da distribuição. No Ubuntu, `/etc/os-release` é um link para `/usr/lib/os-release` |
| `ls /var/log` | Os logs de sistema e de programas. Parte das mensagens fica no **journal do systemd**, lido com `journalctl` |

**Tabela de memória, revisada:**

| Diretório | Real ou virtual | O que guarda | Um arquivo lido |
|---|---|---|---|
| `/proc` | Virtual | Processos (um diretório por PID) e informações do kernel | `/proc/cpuinfo` |
| `/sys` | Virtual | Dispositivos, barramentos e drivers, organizados pelo kernel | `/sys/class/net/enp0s3/address` |
| `/dev` | Virtual (`devtmpfs`) | Arquivos de dispositivo que os programas abrem | `/dev/null` |
| `/boot` | Real, em disco | Kernel, `initramfs` e carregador de inicialização | `vmlinuz-*` |
| `/etc` | Real, em disco | Configuração do sistema e dos programas | `/etc/os-release` |
| `/var/log` | Real, em disco | Logs | Escreva o nome de um que apareceu na VM, como `dpkg.log` ou `auth.log` |

#### Bloco 4 — Programas, configuração e banco de dados de pacotes

| Comando | Resultado e leitura |
|---|---|
| `which ls` | `/usr/bin/ls`: o primeiro executável chamado `ls` nos diretórios do `PATH` |
| `dpkg -S /usr/bin/ls` | `coreutils: /usr/bin/ls`. Do **arquivo para o pacote** |
| `dpkg -L coreutils \| head` | Os arquivos instalados pelo pacote. Do **pacote para os arquivos** |
| `dpkg -l \| wc -l` | Uma estimativa da quantidade de pacotes: a saída tem linhas de cabeçalho e pode listar pacotes em outros estados, além de instalados |
| `ls /var/lib/dpkg` | O **banco de dados do `dpkg`**: o registro dos pacotes instalados |
| `ls /etc/ssh` | A configuração do SSH: `sshd_config`, `ssh_config` e as chaves do servidor |

| Item | Onde fica |
|---|---|
| Executáveis de programas | `/usr/bin` |
| Configuração do sistema | `/etc` |
| Banco de dados de pacotes no Debian e no Ubuntu | `/var/lib/dpkg` |
| Banco de dados RPM na família Red Hat | Tradicionalmente `/var/lib/rpm`; nas versões recentes, `/usr/lib/sysimage/rpm`, com link no lugar antigo |

O equivalente no container Rocky (`rpm -qf`, `rpm -ql`, `rpm -qa`) ficou sem resultado registrado. Não é pendência: os quatro pares para a prova são `dpkg -S` e `rpm -qf` (arquivo → pacote), `dpkg -L` e `rpm -ql` (pacote → arquivos).

**Correções dos blocos 2 a 4:**

1. **Os dois números do bloco 3 são do `/proc/uptime`, não do `/proc/$$/status`.** No caderno, a explicação do tempo desde a inicialização e do tempo ocioso ficou embaixo do `status`. Ver Correção 77.
2. **`lsblk -f`** não mostra "as partições dos arquivos `sda` no `/dev`"; ele acrescenta as colunas de sistema de arquivos (`FSTYPE`, `UUID`, uso). A explicação da convenção `sd` + letra + número, que estava embaixo dele, está certa, mas pertence ao `ls -l /dev/sd*`.
3. **`sr0`** ficou sem leitura: é o drive óptico virtual, cobrado no 4.2.
4. As duas perguntas finais do bloco 2 (`/boot` fora do LVM; `df` contra `du`) estavam em branco no "Para o caderno". A segunda já estava respondida na sua tabela; a primeira está respondida acima.
5. Grafia: `enp03s` → **`enp0s3`**; "man so systemd" → **journal do systemd**; "onjetos" → **objetos**; "armazenmento" → **armazenamento**; "inicializção" → **inicialização**; "fornceu" → **forneceu**; "camingo" → **caminho**.

O bloco 4 está todo certo, incluindo duas nuances que o roteiro não pedia: o `dpkg -l | wc -l` como estimativa e o local variável do banco RPM.

### Prática 4 — até 02/11 — CONCLUÍDA (Exercícios da LPI 4.3 na terça 03/11)

#### Bloco 1 — Listar processos

| Comando | O que mostra |
|---|---|
| `ps` | Sem opções: os processos do seu usuário ligados ao terminal atual |
| `ps aux` | Os processos de todos os usuários, inclusive os sem terminal |
| `ps -ef` | Outra listagem completa, com a coluna `PPID`, o PID do processo pai |
| `ps aux --sort=-%cpu \| head -5` | Os que mais usam CPU, em ordem decrescente |
| `echo $$ ; ps -p $$` | O PID do shell atual e o processo desse PID |

**Um processo** é um programa em execução. Cada um tem um PID e um processo pai (PPID).

| Coluna do `ps aux` | Significado |
|---|---|
| `PID` | Número que identifica o processo |
| `USER` | Usuário efetivo com que o processo roda |
| `%CPU` | Percentual de CPU calculado pelo `ps` |
| `%MEM` | Memória residente do processo, em percentual da RAM física |
| `STAT` | Estado: `R` executando ou pronto; `S` dormindo, espera interrompível; `D` espera ininterruptível, quase sempre entrada e saída; `T` suspenso; `Z` zumbi, terminou e espera o pai recolher o status |

**PID 1** (*estava em branco*): é o **`systemd`**, o processo de inicialização (*init*). É o primeiro processo que o kernel inicia; todos os outros descendem dele, e ele adota os processos que ficam órfãos. Para ver: `ps -p 1 -o pid,comm`.

O `ps` é uma **foto**; o `top`, um **filme**.

#### Bloco 2 — `top` e memória

| Coluna do `free` | Significado |
|---|---|
| `free` | RAM completamente sem uso |
| `buff/cache` | RAM usada como buffer e cache para acelerar o acesso a disco; o kernel a devolve quando um programa precisa |
| `available` | Estimativa da RAM disponível para programas novos sem recorrer ao swap: a livre mais a que pode ser recuperada do cache |

**Por que a `available` importa mais:** pouca memória em `free` não é falta de RAM, porque o Linux usa a RAM ociosa como cache. A `available` já desconta isso. O `free` lê tudo do `/proc/meminfo`.

**Load average** (`uptime`, `cat /proc/loadavg`): a média de tarefas executando ou esperando CPU, mais as em espera ininterruptível (`D`), nos últimos **1, 5 e 15 minutos**. Não é percentual: compare com a quantidade de CPUs lógicas. Na sua VM, com 2 vCPUs, um load de 2,0 é a capacidade cheia.

Dentro do `top`: `P` ordena por CPU, `M` por memória, `k` pede um PID para enviar um sinal, `q` sai.

#### Bloco 3 — Primeiro e segundo plano, e sinais

| Passo | O que acontece |
|---|---|
| `sleep 300 &` | Roda **300 segundos** em segundo plano e libera o prompt. O shell mostra `[1] 8585`: `[1]` é o **número do trabalho** neste shell; `8585`, o **PID** no sistema |
| `sleep 400` | Roda em **primeiro plano**: o terminal fica **ocupado**, sem prompt, até o comando terminar |
| `Ctrl+Z` | Envia `SIGTSTP` (20): o processo é **suspenso** e aparece como `Stopped` no `jobs` |
| `bg` | Continua o trabalho suspenso **em segundo plano** (`Running`) |
| `fg %1` | Traz o trabalho 1, o `sleep 300`, para o primeiro plano |
| `Ctrl+C` | Envia `SIGINT` (2) ao processo em primeiro plano, que termina |
| `sleep 500 & echo $!` | O `$!` guarda o PID do último comando iniciado em segundo plano |
| `kill $!` | Envia `SIGTERM` (15), o padrão do `kill`; o `jobs` mostra `Terminated` |
| `kill -9 $!` | Envia `SIGKILL` (9); o `jobs` mostra `Killed` |

| Sinal | Número | Mecanismo e efeito |
|---|---|---|
| `SIGHUP` | 1 | Historicamente, a perda do terminal; muitos serviços o tratam como pedido para reler a configuração |
| `SIGINT` | 2 | Enviado pelo `Ctrl+C`; a ação padrão é encerrar |
| `SIGKILL` | 9 | O kernel encerra o processo sem passar pelo programa: não pode ser capturado, bloqueado nem ignorado |
| `SIGTERM` | 15 | **Padrão do `kill`.** Pedido de encerramento; o programa pode tratá-lo e fazer a limpeza antes de sair |
| `SIGCONT` | 18 | Continua um processo suspenso (é o que o `bg` e o `fg` enviam) |
| `SIGTSTP` | 20 | Enviado pelo `Ctrl+Z`; a ação padrão é suspender |

`&` inicia em segundo plano; `Ctrl+Z` suspende; `bg` continua em segundo plano; `fg` traz para o primeiro plano; `jobs` lista os trabalhos **deste shell**, não os processos do sistema.

#### Bloco 4 — Mensagens do sistema e logs

| Recurso | Função |
|---|---|
| `dmesg` | Lê o **buffer de mensagens do kernel**: inicialização, drivers, dispositivos conectados. `sudo dmesg \| grep -i enp0s3` filtra as da placa de rede |
| `rsyslog` | O serviço de **syslog** do Ubuntu: recebe as mensagens do sistema e dos serviços e as grava em arquivos de `/var/log`, como o `/var/log/syslog` |
| `/var/log` | Onde ficam os arquivos de log |
| `systemd-journald` | Coleta e guarda os registros no **journal** do `systemd` |
| `journalctl` | Lê o journal; `-n 10` mostra as últimas dez entradas, `--no-pager` imprime direto no terminal |
| `logger` | Envia uma mensagem ao sistema de logs; não imprime confirmação |

O roteiro pedia anotar se o `/var/log/syslog` existe na VM. Isso não ficou registrado: se o `sudo tail -5 /var/log/syslog` e o `grep` do `logger` funcionaram, ele existe e o `rsyslog` está ativo; se deram "No such file", só o journal está ativo.

**Correções:**

1. **`sleep 300` espera 300 segundos** (5 minutos), não 30.
2. **O primeiro plano ocupa o terminal.** No `sleep 400`, o terminal não fica "aguardando comando": fica bloqueado, sem prompt, até o processo terminar ou ser suspenso. O `Ctrl+Z` não é um pedido do terminal; é você que envia o `SIGTSTP`. Ver Correção 78.
3. **No `fg %1`, o encerramento é pelo `Ctrl+C`**, como no roteiro. Com o processo em primeiro plano não há prompt para digitar `kill %1`; o `kill %1` serve para um trabalho em **segundo plano**.
4. **PID 1** estava em branco: é o `systemd` (resposta acima).
5. A linha `echo $ps -p$` saiu embaralhada: o comando é `echo $$ ; ps -p $$`.
6. O `-F` do `grep` (texto literal) está certo, mas não estava no comando do roteiro, que foi `sudo grep "teste do lab" /var/log/syslog`.
7. Grafia: **`Ctrl`**, e não `Crtl`, pela **terceira vez** (autoavaliação da Semana 5, caderno da Semana 5 e aqui); "slepp" → **sleep**; "acerelar" → **acelerar**; "availiable" → **available**; "possibildade" → **possibilidade**.

Os blocos 2 e 4 estão muito bons: a explicação do `available` e a do *load average*, incluindo a espera ininterruptível e a relação com o número de CPUs, vão além do que a prova cobra.

#### Exercícios da LPI 4.3

A lista de 13 exercícios ficou registrada sem respostas. **Vão para a terça 03/11**, depois do simulado 03 e das aulas: só os Guiados (1 a 6) e o complemento (10 a 13), sem consultar. Os Exploratórios (7 a 9) são opcionais. Anote só as erradas.

### Prática 5 — até 02/11 — CONCLUÍDA (anotações a recuperar)

Feita, mas as anotações se perderam. Quando recuperá-las, eu reviso e registro aqui. Se não forem recuperadas, não é pendência: o 4.4 (rede) volta no R2 (09/11), no treino V7 e nos simulados.

### Simulado 03

Passou para a **terça 03/11**, primeiro dia da operação prática. Registro no próprio `simulado-03.md` e em `labs/operacao-pratica.md`.

### Correções da semana

A numeração segue a série global. **A próxima é a 79.** Correção numerada só para erro de laboratório e de curso.

#### Correção 76 — o `-m1` do `grep` limita a quantidade de linhas

O caderno diz que o `-m1` serve "para dizer onde está o conteúdo desejado". O `-m` é `--max-count`: `-m1` faz o `grep` **parar na primeira linha que casa**. No `/proc/cpuinfo`, cada processador lógico tem o seu bloco, com o seu `model name`; com 2 vCPUs, `grep 'model name' /proc/cpuinfo` imprime duas linhas iguais, e `grep -m1` imprime uma. Para ver: rode os dois lado a lado. Não confundir com o `-c`, que **conta** as linhas, nem com o `-n`, que **numera**.


#### Correção 77 — tempo desde a inicialização é o `/proc/uptime`, não o `/proc/$$/status`

O caderno pôs a explicação dos dois números (segundos desde a inicialização e segundos de CPU ociosa) embaixo do `cat /proc/$$/status`. Eles são a saída do `cat /proc/uptime`. O `/proc/$$/status` descreve **um processo**, o shell atual: `Name: bash`, `State`, `Pid`, `PPid`, memória usada. A diferença é a regra do `/proc`: um diretório **por PID**, com os dados daquele processo, e arquivos **soltos** na raiz, como `uptime`, `version`, `cpuinfo` e `meminfo`, com dados do sistema inteiro. Para ver: `cat /proc/uptime ; head -5 /proc/$$/status`.


#### Correção 78 — em primeiro plano, o terminal fica ocupado; o `Ctrl+Z` suspende

O caderno diz que, no `sleep 400`, "o terminal fica aguardando comando e pede para digitar `Ctrl+Z`". Em **primeiro plano**, o processo é dono do terminal: não há prompt até ele terminar. O `Ctrl+Z` é você que pressiona, e o terminal traduz em `SIGTSTP` (20), que **suspende** o processo (`Stopped`) e devolve o prompt. A partir daí: `bg` continua em segundo plano; `fg` traz de volta; `kill %N` encerra um trabalho que **não** está em primeiro plano. Com o processo em primeiro plano, quem encerra é o `Ctrl+C` (`SIGINT`). Para ver: `sleep 400`, `Ctrl+Z`, `jobs`, `bg`, `jobs`, `kill %1`, `jobs`.


| # | Tema | Origem |
|---|---|---|
| 76 | O `-m1` do `grep` é *max-count*: para depois da primeira linha que casa, não "diz onde está o conteúdo" | Prática 3, bloco 1, 27/10 |
| 77 | Os números de tempo desde a inicialização e de CPU ociosa são do `/proc/uptime`; o `/proc/$$/status` descreve um processo | Prática 3, bloco 3, 30/10 |
| 78 | Em primeiro plano o terminal fica ocupado, sem prompt; o `Ctrl+Z` envia `SIGTSTP` e suspende | Prática 4, bloco 3 |

---

## Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Seg 26 a qui 29 | — | | Prática 3, bloco 1 |
| Sex 30 | 1h | | Prática 3, blocos 2 a 4 (feito) |
| Sáb 31 | — | | Descanso |
| Dom 01 e seg 02/11 | — | | Práticas 4 e 5 (feitas) |

---

## Checklist da semana

- [x] Prática 3, bloco 1 (27/10)
- [x] Pacotes instalados na VM (`pciutils`, `usbutils`, `net-tools`, `bind9-dnsutils`)
- [x] Prática 3, blocos 2 a 4 (sexta 30/10)
- [x] Prática 4 (até 02/11)
- [x] Prática 5 (até 02/11)
- [ ] Anotações da Prática 5 repassadas aqui
- [ ] Exercícios da LPI 4.3 (terça 03/11, na operação prática)
- [ ] Exercícios da LPI 4.2 (sexta 06/11, na operação prática)
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-09.md` preenchido com as Práticas 3, 4 e 5. O Tópico 4 está praticado; as aulas, o bloco curto e os exercícios fecham o conteúdo nos primeiros dias da operação prática.

---

## Cola rápida — Tópico 4

**Onde fica cada coisa**

| Diretório | O que guarda | Real ou virtual |
|---|---|---|
| `/etc` | Configuração do sistema | Real |
| `/var/log` | Logs (`syslog` no Debian e Ubuntu, `messages` no Red Hat) | Real |
| `/var/lib/dpkg` · `/var/lib/rpm` | Banco de dados de pacotes | Real |
| `/boot` | Kernel (`vmlinuz`), `initramfs` e carregador de inicialização | Real |
| `/proc` | Processos (um diretório por PID) e informações do kernel (`cpuinfo`, `meminfo`) | Virtual |
| `/sys` | Dispositivos, barramentos e drivers, organizados pelo kernel | Virtual |
| `/dev` | Arquivos de dispositivo (`sda`, `tty`, `null`) | Virtual |
| `/run`, `/dev/shm` | Dados temporários em RAM (`tmpfs`) | Virtual |

**Hardware**

| Comando | Mostra |
|---|---|
| `lscpu` | Processador |
| `free -h` | Memória e swap, em formato legível |
| `lsblk` | Discos e partições em árvore |
| `df -h` · `du -sh` | Espaço por sistema de arquivos montado · espaço ocupado por um diretório |
| `lspci` · `lsusb` | Dispositivos PCI · USB |
| `lsmod` | Módulos do kernel carregados (drivers) |
| `dmesg` | Buffer de mensagens do kernel |

**Processos**

| Comando | Faz |
|---|---|
| `ps aux` · `ps -ef` | Foto dos processos |
| `top` | Lista contínua; `P` ordena por CPU, `M` por memória, `k` encerra, `q` sai |
| `kill PID` | Envia `SIGTERM` (15) |
| `kill -9 PID` | Envia `SIGKILL` (9) |
| `comando &` · `jobs` · `fg` · `bg` · `Ctrl+Z` | Segundo plano · lista · primeiro plano · retoma no segundo plano · suspende |

**Rede**

| Atual | Antigo | Mostra |
|---|---|---|
| `ip addr show` | `ifconfig` | Endereços das interfaces |
| `ip route show` | `route` | Tabela de rotas e rota padrão |
| `ss -tuln` | `netstat -tuln` | Portas TCP e UDP em escuta |
| `ping -c 3 host` | — | Conectividade |
| `host nome` · `dig nome` | — | Consulta DNS, curta · detalhada |

| Arquivo | Papel |
|---|---|
| `/etc/hosts` | Tabela local de nomes, consultada antes do DNS |
| `/etc/resolv.conf` | Servidores DNS (`nameserver`) |

Faixas IPv4 privadas: `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`. IPv4 tem 32 bits em decimal; IPv6 tem 128 bits em hexadecimal, e o `::` abrevia uma sequência de zeros **uma vez** por endereço. Portas: 22 SSH, 25 SMTP, 53 DNS, 80 HTTP, 443 HTTPS.