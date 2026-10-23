# Semana 8 — Tópico 4, o sistema operacional Linux

Período: 19/10 a 25/10/2026 (segunda a domingo)
Objetivos da prova: 4.1, 4.2, 4.3 e 4.4 — Tópico 4, peso 8 de 40
**Data da prova: segunda-feira, 23/11/2026**
Carga prevista: cerca de 8h
Marco da semana: **Checkpoint B, segunda 26/10** (movido de domingo em 21/10). Ao fim da Prática 5, no domingo 25/10, os cinco tópicos da prova foram estudados

O Tópico 4 nunca foi estudado como tópico, mas boa parte dele já foi encostada na prática: LVM e partições na Semana 0, `/proc` e `/dev` na Semana 3, portas e serviços na Semana 1, gerenciadores de pacotes no curso. A cobertura parte de cerca de 30%, não de zero. No simulado 01, os dois erros deste tópico foram chutes: `top` (Q28) e o sinal padrão do `kill` (Q29).

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

**Refeito em 19, 20, 21 e 22/10.** O Checkpoint A deu vermelho, e esta semana abre com as dívidas da Semana 7. A Prática 2 terminou na terça 20/10, os Exercícios da LPI 5.1 a 5.4 foram resolvidos na quarta 21/10 e as correções das Práticas 1 e 2 foram feitas na quinta 22/10. **O simulado 02 não saiu na quinta e vai para a sexta 23/10**, como primeira atividade. O simulado 03 e o **Checkpoint B** ficam na **segunda 26/10**.

| Dia | Atividade | Tempo |
|---|---|---|
| Ter 20 | Prática 2, blocos 5 e 6 | **feito** |
| Qua 21 | Exercícios da LPI 5.1 a 5.4 resolvidos | **feito** |
| Qui 22 | Cards de correção no Notion e correções das Práticas 1 e 2 no caderno | **feito** |
| **Sex 23** | **Simulado 02** (60 min, primeira atividade) e apuração (25 min) · **Prática 3** — hardware, discos e o mapa dos diretórios (4.2 e 4.3), com Exercícios da LPI 4.2 | cerca de 2h45 |
| **Sáb 24** | **Autoavaliação da Semana 6** (30 min, primeira atividade; questões em `labs/semana-07.md`, seção 6) · **Prática 4** — processos, memória e logs (4.3), com Exercícios da LPI 4.3 · resíduos da Prática 2 (10 min) · curso, aulas 41 a 56 | cerca de 3h20 |
| **Dom 25** | **Prática 5** — rede (4.4), com Exercícios da LPI 4.4 · curso, aulas 57 a 72 | cerca de 2h40 |
| **Seg 26** (Semana 9) | **Simulado 03** (60 min) e apuração (25 min) · **Checkpoint B** | cerca de 1h40 |
| Ter 27 (Semana 9) | **R2** (35 min) · **bloco curto**: 4.1 e here document (45 min) | cerca de 1h20 |
| Qua 28 (Semana 9) | **Autoavaliação da Semana 8** (30 min, três dias depois da Prática 5) · **R1** (35 min) | cerca de 1h05 |

**Regra para o simulado 02, decidida em 22/10:** esta é a quarta data dele (17, 21, 22 e 23/10). **Se não sair na sexta, ele sai do plano**, e o simulado 03 de segunda assume a medição. Empurrá-lo de novo tiraria espaço das Práticas 3 a 5, que são conteúdo nunca estudado.

**Total de sexta a domingo: cerca de 8h45.** Se faltar tempo, corte nesta ordem:

| Ordem | Corte | Efeito |
|---|---|---|
| 1 | Exercícios Exploratórios da LPI do Tópico 4 (mantendo os Guiados) | Saem |
| 2 | Aulas que não couberem no fim de semana | Segunda 26/10 e terça 27/10, 30 minutos antes da atividade do dia |
| 3 | Simulado 02 | Sai, pela regra acima |

**Não se cortam:** as Práticas 3, 4 e 5, a autoavaliação da Semana 6 e o simulado 03. Sem as práticas, o Tópico 4 (8 dos 40 pontos) chega ao simulado sem estudo.

**O curso não trava as práticas.** Os roteiros do Tópico 4 funcionam com a leitura do PDF; as aulas 58 a 72, se chegarem depois das práticas, confirmam em vez de ensinar, como aconteceu com o shell script.

**Aquecimento (10 min, nos dias de prática):** cinco comandos da prática anterior, de memória. Na sexta, o conteúdo da Prática 2 (conversões e bits especiais).

## Dívidas práticas — situação em 22/10

Tudo o que está atrasado em relação ao plano. Depois desta lista paga, só restam conteúdo novo e simulados.

| # | Dívida | Desde | Situação em 22/10 | Quando |
|---|---|---|---|---|
| 1 | **Simulado 02** (40 questões) | 17/10 | Não feito | **Sex 23/10**, primeira atividade. Se não sair, sai do plano |
| 2 | Correções no caderno da Prática 1 (7 campos do `/etc/passwd`, arquivo do `last`, Correção 75) | 15/10 | **Feito em 22/10** | — |
| 3 | Correções no caderno da Prática 2 (`rwr`, 4644, tabela do bloco 4, `sudo chmod 3775`) | 19/10 | **Feito em 22/10** | — |
| 4 | **Resíduos da Prática 2:** resultado do `sudo -u bob rm /srv/Box/a`; link com `ln -s ~/lab6/alvo link`; `getent passwd alice bob carol teste_sem_nome ; getent group dev ops` | 20/10 | A fazer | Sáb 24/10, 10 min |
| 5 | **Cards no Notion:** 71 a 75, os três sem número (Q6 da autoavaliação da Semana 5, `x` em diretório, 4644) e os erros da primeira tentativa dos Exercícios da LPI 5.1 a 5.4 | 21/10 | Em parte: 60 a 70 anotados em 22/10 | Sex 23/10, depois do simulado 02, 15 min |
| 6 | **`cheatsheets/permissoes.md`**, escrito à mão | 19/10 | A fazer | Sáb 24/10, depois da autoavaliação |
| 7 | **Curso, aulas 41 a 72** | 15/10 | Parado na aula 40 | Sáb 24 e dom 25/10 |

Os itens 6 e 7 são os únicos que não são exercício; ficam porque a cola é o que você vai ler na revisão final, e o curso é um dos dois objetivos da preparação.

**Não estão atrasados** (ainda no prazo): autoavaliação da Semana 6 (sáb 24), Práticas 3, 4 e 5, simulado 03 e Checkpoint B (seg 26), R2 e bloco curto (ter 27), autoavaliação da Semana 8 e R1 (qua 28).

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

### NDG (30 min, opcional desde 19/10)

Quizzes dos capítulos de hardware, processos e rede e do capítulo de permissões, no NDG Linux Essentials. Anote só as questões erradas.

---

## Mini-simulado R1 — Quarta 28/10 (Semana 9)

Remarcado em 19/10. 20 questões, 25 minutos, sobre as quatro frentes das dicas recorrentes e 6 lacunas. Está em `labs/simulados-práticos.lpi/praticas_simulados.md`, seção 6, com gabarito na seção 7. Meta: 15 de 20.

---

## Autoavaliação da Semana 8 — Quarta 28/10

Dez questões sobre o Tópico 4, respondidas **sem consultar**, três dias depois da Prática 5, como primeira atividade da quarta 28/10. É a **última autoavaliação do plano**: a partir da Semana 9, com os cinco tópicos estudados, os simulados assumem a medição. Escreva as respostas à mão e só depois abra o gabarito.

1. Qual a diferença entre uma versão **LTS** e uma distribuição **rolling release**? Dê um exemplo de cada.
2. O que é um **driver**, e como os drivers existem no Linux? Qual comando lista os que estão carregados?
3. Qual o nome do arquivo de dispositivo da **primeira partição do segundo disco** SATA? No `ls -l /dev/sda`, o que significa a primeira letra `b`?
4. Explique a diferença entre `/proc`, `/sys` e `/dev`, com um arquivo ou diretório de cada.
5. Em que diretório ficam: (a) os arquivos de configuração do sistema; (b) os logs; (c) o kernel e o `initramfs`; (d) o banco de dados de pacotes de uma distribuição Debian?
6. Qual a diferença entre `ps` e `top`? Dentro do `top`, que tecla ordena por uso de memória?
7. Qual sinal o `kill` envia quando nenhum é informado? Qual a diferença entre ele e o `SIGKILL`? Que sinal o `Ctrl+C` envia?
8. Um processo foi iniciado com `sleep 300 &`. Quais comandos (a) listam os trabalhos do shell, (b) trazem esse processo para o primeiro plano e (c) devolvem ao segundo plano um processo suspenso com `Ctrl+Z`?
9. Escreva o comando atual e o antigo para: (a) ver os endereços IP das interfaces; (b) ver a rota padrão; (c) ver as portas TCP em escuta.
10. Para que servem o `/etc/hosts` e o `/etc/resolv.conf`? Quais são as três faixas de endereços IPv4 privados?

| Campo | Valor |
|---|---|
| Acertos | de 10 |
| Meta | 8 ou mais |
| Questões erradas | |
| Erros viram | lista das questões erradas aqui; a correção fica no Notion |

<details>
<summary>Gabarito (abra só depois de responder)</summary>

1. **LTS** (*Long Term Support*) recebe correções de segurança e de bugs por vários anos, sem trocar de versão principal; exemplo: Ubuntu 26.04 LTS, o da sua VM. **Rolling release** não tem versões fixas: o sistema é atualizado continuamente; exemplos: Arch Linux, openSUSE Tumbleweed.
2. Driver é o software que traduz pedidos padrão do sistema para as operações específicas de um dispositivo. No Linux, a maioria dos drivers são **módulos do kernel**, carregados quando o dispositivo precisa deles. `lsmod` lista os carregados.
3. `/dev/sdb1`: `sd`, letra do disco (`a` o primeiro, `b` o segundo) e número da partição. O `b` indica **dispositivo de bloco** (lê e grava em blocos, como discos); o `c` indicaria dispositivo de caractere, como `/dev/tty`.
4. `/proc`: processos e informações do kernel (`/proc/cpuinfo`, `/proc/meminfo`, um diretório por PID). `/sys`: dispositivos, barramentos e drivers organizados pelo kernel (`/sys/class/net`). `/dev`: os arquivos de dispositivo que os programas abrem (`/dev/sda`, `/dev/null`). Os três são montados pelo kernel e não ocupam disco.
5. (a) `/etc`; (b) `/var/log`; (c) `/boot`; (d) `/var/lib/dpkg`.
6. O `ps` é uma foto: lista os processos no instante em que roda. O `top` é contínuo: atualiza a lista a cada poucos segundos e mostra carga, memória e CPU. No `top`, `M` ordena por memória (`P` por CPU).
7. `SIGTERM` (15): pede para o processo encerrar, e ele pode tratar o pedido e terminar de forma limpa. `SIGKILL` (9, com `kill -9`) é aplicado pelo kernel e não pode ser tratado nem ignorado. O `Ctrl+C` envia `SIGINT` (2).
8. (a) `jobs`; (b) `fg` (ou `fg %1`); (c) `bg`.
9. (a) `ip addr show` e `ifconfig`; (b) `ip route show` e `route`; (c) `ss -tln` e `netstat -tln`.
10. O `/etc/hosts` é uma tabela local de nomes e endereços, consultada antes do DNS. O `/etc/resolv.conf` diz quais servidores DNS consultar (linhas `nameserver`). Faixas privadas: `10.0.0.0/8`, `172.16.0.0/12` (de `172.16` a `172.31`) e `192.168.0.0/16`.

</details>

---

## Simulado 03 — Segunda 26/10

| Item | Valor |
|---|---|
| Arquivo | `labs/simulados-práticos.lpi/simulado-03.md` |
| Formato | 40 questões, 60 minutos, sem consulta; pelo menos 45 minutos de uso, com segunda passada |
| Meta | **28 ou mais** (Checkpoint B) |
| Registro | No próprio arquivo e em `resultados_simulados.md` |

É o primeiro simulado com os cinco tópicos estudados. Marque cada chute; anote só as questões erradas e as chutadas, e corrija no Notion.

---

## Checkpoint B — Segunda 26/10, à noite (movido de domingo em 21/10)

| # | Critério | Cumprido |
|---|---|---|
| 1 | Curso fechado (aula 72) | |
| 2 | Práticas 3, 4 e 5 feitas e registradas | |
| 3 | Simulado 03 com **28 ou mais** acertos | |

| Resultado | Condição | Decisão |
|---|---|---|
| **Verde** | Os três cumpridos | Mantém 23/11 |
| **Amarelo** | Um falhou | Mantém 23/11, mas o Gate de 08/11 fica sem folga |
| **Vermelho** | Dois ou mais falharam | Mover a prova para **30/11** |

**Como o Checkpoint A deu vermelho, este checkpoint decide a data:** verde ou amarelo mantêm 23/11; vermelho move a prova para 30/11, o limite absoluto. Regra completa em `PLANO.md`, seção 11.

---

## Registro das sessões

### Exercícios da LPI 5.1 a 5.4 — quarta 21/10 — CONCLUÍDOS

Entregue como um guia em PDF com os **43 exercícios resolvidos** (5.1 G1 a G5 e E1 a E7; 5.2 G1 e G2 e E1 a E8; 5.3 G1 a G6 e E1 a E5; 5.4 G1 a G5 e E1 a E5).

**Revisão:** as resoluções estão corretas, inclusive os pontos em que o guia corrige o gabarito do PDF da LPI. Os mais úteis para a prova:

| Exercício | Ponto |
|---|---|
| 5.2 G2 | Grupo primário não aparece na lista de membros do `/etc/group`; `!` no hash é senha bloqueada; `0` na última troca obriga a trocar no próximo login |
| 5.3 G4 | O `s` na posição do grupo é **SGID**, não SUID; e o Linux ignora SUID e SGID em scripts |
| 5.3 G6 | `drwxr-xr-t` = 1755; `----r--r--` = 0044; `drwxr-sr-x` = 2755 |
| 5.3 E2 | Binário executa com `--x`; script precisa de `r`, porque o interpretador lê o arquivo |
| 5.4 E3 | Contador de links 4 = quatro nomes no total, três além do mostrado |
| 5.4 E4 | Symlink relativo resolve a partir do diretório **onde o link está**; o `mv` muda o alvo encontrado |
| 5.4 E5 | O `lrwxrwxrwx` do link não dá acesso: vale a permissão do alvo |

**Ponto de método.** O PDF é um guia resolvido, não o registro das suas respostas. O roteiro pedia responder sem consultar e anotar só as questões erradas. Para o Notion, leve as questões em que a sua **primeira resposta** errou. Se a resolução foi lida antes de responder, registre aqui "estudo, sem medição": a medição do Tópico 5 fica com o simulado 02 (sexta 23/10) e a autoavaliação da Semana 6 (sábado 24/10).

Questões erradas na primeira tentativa: *a preencher.*

**Aviso sobre a versão da prova**, que o guia traz e foi conferido no site da LPI em 21/10: a versão atual é a **2.0, exame 010-200**; a **1.6, exame 010-160**, que este plano cobre, fica disponível **até abril de 2027**. Ao agendar na Pearson VUE, escolha o **010-160**.

### Simulado 02 — sexta 23/10

*A preencher.* Registre também em `labs/simulados-práticos.lpi/resultados_simulados.md`.

### Prática 3 — sexta 23/10

*A preencher.*

### Prática 4 — sábado 24/10

*A preencher.*

### Autoavaliação da Semana 6 — sábado 24/10

*A preencher.* Acertos: de 10.

### Prática 5 — domingo 25/10

*A preencher.*

### Simulado 03 — segunda 26/10

*A preencher.* Registre também em `labs/simulados-práticos.lpi/resultados_simulados.md`.

### Curso, aulas 41 a 72

| Data | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|
| | | | |

### Bloco curto — terça 27/10

*A preencher.*

### Autoavaliação da Semana 8 — quarta 28/10

*A preencher.* Acertos: de 10.

### Correções da semana

A numeração segue a série global. **A próxima é a 76.** Erros de simulado e de autoavaliação não geram correção numerada; vão para o Notion.

| # | Tema | Origem |
|---|---|---|
| | | |

---

## Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Ter 20 | — | | Prática 2, blocos 5 e 6 |
| Qua 21 | — | | Exercícios da LPI 5.1 a 5.4 |
| Qui 22 | 2h10 | | Cards no Notion e correções no caderno; o simulado 02 não saiu |
| Sex 23 | 2h45 | | Simulado 02 e Prática 3 |
| Sáb 24 | 3h20 | | Autoavaliação S6, Prática 4, resíduos e aulas 41 a 56 |
| Dom 25 | 2h40 | | Prática 5 e aulas 57 a 72 |
| Seg 26 | 1h40 | | Simulado 03 e Checkpoint B |

---

## Checklist da semana

- [x] Prática 2 terminada, blocos 5 e 6 (terça 20/10)
- [x] Exercícios da LPI 5.1 a 5.4 resolvidos (quarta 21/10)
- [x] Cards 60 a 70 no Notion (quinta 22/10)
- [ ] Cards 71 a 75, os três sem número e os erros dos Exercícios da LPI no Notion (sexta 23/10)
- [ ] Simulado 02 e apuração (sexta 23/10)
- [x] Correções das Práticas 1 e 2 no caderno (quinta 22/10)
- [ ] Resíduos da Prática 2 (sábado 24/10)
- [ ] `cheatsheets/permissoes.md` escrito à mão
- [ ] Pacotes instalados na VM (`pciutils`, `usbutils`, `net-tools`, `bind9-dnsutils`)
- [ ] Prática 3, com Exercícios da LPI 4.2 (sexta 23/10)
- [ ] Autoavaliação da Semana 6 (sábado 24/10)
- [ ] Prática 4, com Exercícios da LPI 4.3 (sábado 24/10)
- [ ] Prática 5, com Exercícios da LPI 4.4 (domingo 25/10)
- [ ] Curso, aulas 41 a 72 (sábado e domingo)
- [ ] Simulado 03 e apuração por tópico e por tema (segunda 26/10)
- [ ] Checkpoint B preenchido (segunda 26/10)
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-08.md` preenchido, a Prática 2 fechada, as Práticas 3 a 5, os simulados 02 e 03, a autoavaliação da Semana 6, o curso fechado e o Checkpoint B preenchido.

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