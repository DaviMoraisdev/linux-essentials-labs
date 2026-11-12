# Banco de lacunas — LPI Linux Essentials (010-160)

**Criado em:** 26/10/2026 · **Uso:** aquecimento de 5 minutos, todo dia da operação prática (`labs/operacao-pratica.md`), uma série por dia, na ordem

São **120 lacunas em 24 séries de cinco**. Cada série mistura tópicos, porque é assim que a prova chega: uma questão de licença seguida de uma de permissão. O formato de lacuna é o único em que o chute não funciona, por isso é o retrato mais fiel do que está fixado.

## Regras

| Regra | Detalhe |
|---|---|
| Tempo | 5 minutos para as cinco, de memória, escrevendo no papel |
| Forma | Escreva **só o que foi pedido**: o comando sem caminho, sem `sudo` e sem opções, salvo quando o enunciado pedir a opção, o caminho ou o `$`. Maiúsculas e minúsculas contam |
| Conferência | Abra o gabarito da série só depois das cinco |
| Erro | Marque na tabela de controle no fim do arquivo. Erro **de forma** (resposta certa escrita errado) conta como erro |
| Repetição | Uma lacuna errada volta **três séries depois**. Desde 11/11, as que voltam ficam **escritas dentro da própria série**, logo depois do gabarito dela, na seção "Retornos": basta responder a série inteira |

As do Tópico 4 dependem das Práticas 3 a 5 e por isso só começam com a operação, na terça 03/11.

---

## Série 01

1. *(Tópico 1)* Tipo de licença que exige que versões modificadas e distribuídas mantenham a mesma licença do original (uma palavra): ______
2. *(Tópico 2)* Comando que mostra o caminho completo do diretório atual: ______
3. *(Tópico 3)* Opção do `tar` que extrai (com o hífen): ______
4. *(Tópico 4)* Comando que mostra uma foto dos processos no momento em que roda: ______
5. *(Tópico 5)* Caminho do arquivo com os hashes das senhas: ______

<details>
<summary>Gabarito da série 01</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `copyleft` | — |
| 2 | `pwd` | — |
| 3 | `-x` | — |
| 4 | `ps` | — |
| 5 | `/etc/shadow` | — |

</details>

## Série 02

1. *(Tópico 2)* Comando interno do Bash que mostra a ajuda dos comandos internos: ______
2. *(Tópico 3)* Opção do `tar` que comprime com gzip: ______
3. *(Tópico 4)* Comando que mostra os processos continuamente, atualizando a tela: ______
4. *(Tópico 5)* Caminho do arquivo com os grupos e seus membros secundários: ______
5. *(Tópico 1)* Sigla da fundação criada por Richard Stallman que publica a GPL: ______

<details>
<summary>Gabarito da série 02</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `help` | — |
| 2 | `-z` | — |
| 3 | `top` | — |
| 4 | `/etc/group` | — |
| 5 | `FSF` | — |

</details>

## Série 03

1. *(Tópico 3)* Opção do `tar` que comprime com bzip2: ______
2. *(Tópico 4)* Comando que mostra o uso de memória e de swap: ______
3. *(Tópico 5)* Caminho do diretório cujo conteúdo é copiado para a pasta pessoal de cada usuário novo: ______
4. *(Tópico 1)* Distribuição comunitária que serve de base (*upstream*) para o Red Hat Enterprise Linux: ______
5. *(Tópico 2)* Comando interno que informa se um nome é alias, comando interno ou programa em disco: ______

<details>
<summary>Gabarito da série 03</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `-j` | — |
| 2 | `free` | — |
| 3 | `/etc/skel` | — |
| 4 | `Fedora` | — |
| 5 | `type` | — |

</details>

## Série 04

1. *(Tópico 4)* Comando que mostra as mensagens do buffer do kernel: ______
2. *(Tópico 5)* UID do superusuário: ______
3. *(Tópico 1)* Ferramenta de baixo nível que instala pacotes `.deb`: ______
4. *(Tópico 2)* Comando que faz a mesma busca que `man -k`: ______
5. *(Tópico 3)* Opção do `tar` que comprime com xz: ______

<details>
<summary>Gabarito da série 04</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `dmesg` | — |
| 2 | `0` | — |
| 3 | `dpkg` | — |
| 4 | `apropos` | — |
| 5 | `-J` | — |

</details>

## Série 05

1. *(Tópico 5)* Comando que mostra o UID, o GID e os grupos de um usuário: ______
2. *(Tópico 1)* Ferramenta de baixo nível que instala pacotes `.rpm`: ______
3. *(Tópico 2)* Número da seção do manual que documenta formatos de arquivo, como o do `/etc/passwd`: ______
4. *(Tópico 3)* Opção do `tar` que lista o conteúdo sem extrair: ______
5. *(Tópico 4)* Caminho do diretório dos arquivos de log: ______

<details>
<summary>Gabarito da série 05</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `id` | — |
| 2 | `rpm` | — |
| 3 | `5` | — |
| 4 | `-t` | — |
| 5 | `/var/log` | — |

</details>

## Série 06

1. *(Tópico 1)* Gerenciador de pacotes de alto nível do Fedora e do RHEL atuais: ______
2. *(Tópico 2)* Número da seção do manual dos comandos de administração do sistema: ______
3. *(Tópico 3)* Opção do `tar` que recebe o nome do arquivo e por isso vem por último no grupo: ______
4. *(Tópico 4)* Caminho do diretório com o kernel e o `initramfs`: ______
5. *(Tópico 5)* Comando que lista os últimos logins, lendo o `/var/log/wtmp`: ______

<details>
<summary>Gabarito da série 06</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `dnf` | `yum` é o antecessor; a prova atual aceita o `dnf` |
| 2 | `8` | — |
| 3 | `-f` | — |
| 4 | `/boot` | — |
| 5 | `last` | — |

</details>

## Série 07

1. *(Tópico 2)* Comando que reconstrói o banco de dados consultado pelo `locate`: ______
2. *(Tópico 3)* Comando que descompacta um arquivo `.gz` (sem opções): ______
3. *(Tópico 4)* Caminho do sistema de arquivos virtual com um diretório para cada PID: ______
4. *(Tópico 5)* Comando que altera o dono de um arquivo: ______
5. *(Tópico 1)* Gerenciador de pacotes de alto nível do openSUSE: ______

<details>
<summary>Gabarito da série 07</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `updatedb` | — |
| 2 | `gunzip` | — |
| 3 | `/proc` | — |
| 4 | `chown` | — |
| 5 | `zypper` | — |

</details>

## Série 08

1. *(Tópico 3)* Comando que extrai um arquivo `.zip`: ______
2. *(Tópico 4)* Caminho do sistema de arquivos virtual que organiza dispositivos, barramentos e drivers: ______
3. *(Tópico 5)* Comando feito para alterar só o grupo de um arquivo: ______
4. *(Tópico 1)* Suíte de escritório livre, derivada do OpenOffice, presente na maioria das distribuições: ______
5. *(Tópico 2)* Comando que mostra o caminho do executável que seria usado para um nome, procurando no `PATH`: ______

<details>
<summary>Gabarito da série 08</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `unzip` | — |
| 2 | `/sys` | — |
| 3 | `chgrp` | — |
| 4 | `LibreOffice` | — |
| 5 | `which` | — |

</details>

## Série 09

1. *(Tópico 4)* Nome do sinal que o `kill` envia quando nenhum é informado: ______
2. *(Tópico 5)* Opções do `usermod`, juntas e com o hífen, que acrescentam um grupo secundário sem retirar os outros: ______
3. *(Tópico 1)* Programa livre para editar fotografias (imagens rasterizadas): ______
4. *(Tópico 2)* Variável de ambiente com a lista de diretórios onde o shell procura comandos: ______
5. *(Tópico 3)* Operador que acrescenta a saída ao final de um arquivo, sem apagar o conteúdo: ______

<details>
<summary>Gabarito da série 09</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `SIGTERM` | `TERM` ou `15` |
| 2 | `-aG` | — |
| 3 | `GIMP` | — |
| 4 | `PATH` | — |
| 5 | `>>` | — |

</details>

### Retornos para responder com a série 09 (quinta 12/11)

Itens errados nas séries 01, 02 e 03 que ainda não voltaram. Responda sem abrir os gabaritos.

- *(Tópico 1, série 01)* Tipo de licença que exige que versões modificadas e distribuídas mantenham a mesma licença do original (uma palavra): ______
- *(Tópico 3, série 01)* Opção do `tar` que extrai (com o hífen): ______
- *(Tópico 4, série 01)* Comando que mostra uma foto dos processos no momento em que roda: ______
- *(Tópico 2, série 02)* Comando interno do Bash que mostra a ajuda dos comandos internos: ______
- *(Tópico 3, série 02)* Opção do `tar` que comprime com gzip: ______
- *(Tópico 4, série 02)* Comando que mostra os processos continuamente, atualizando a tela: ______
- *(Tópico 5, série 02)* Caminho do arquivo com os grupos e seus membros secundários: ______
- *(Tópico 1, série 02)* Sigla da fundação criada por Richard Stallman que publica a GPL: ______
- *(Tópico 5, série 03)* Caminho do diretório cujo conteúdo é copiado para a pasta pessoal de cada usuário novo: ______

O `/etc/shadow` (série 01, item 5) saiu da lista: foi escrito certo, de memória, na Q3 do R4.

## Série 10

1. *(Tópico 5)* Comando que cria um grupo: ______
2. *(Tópico 1)* Programa livre para desenho vetorial, como logotipos: ______
3. *(Tópico 2)* Variável de ambiente com o caminho da pasta pessoal do usuário: ______
4. *(Tópico 3)* Operador que redireciona só a saída de erro, sobrescrevendo o arquivo: ______
5. *(Tópico 4)* Número do sinal que não pode ser tratado nem ignorado pelo processo: ______

<details>
<summary>Gabarito da série 10</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `groupadd` | — |
| 2 | `Inkscape` | — |
| 3 | `HOME` | — |
| 4 | `2>` | — |
| 5 | `9` | — |

</details>

### Retornos para responder com a série 10 (sexta 13/11)

- *(Tópico 2, série 07)* Comando que reconstrói o banco de dados consultado pelo `locate`: ______
- *(Tópico 4, série 07)* Caminho do sistema de arquivos virtual com um diretório para cada PID: ______

## Série 11

1. *(Tópico 1)* Programa livre para modelagem e animação 3D: ______
2. *(Tópico 2)* Comando interno que torna uma variável disponível para os processos filhos: ______
3. *(Tópico 3)* Operador que faz a entrada padrão vir de um arquivo: ______
4. *(Tópico 4)* Nome do sinal enviado pelo `Ctrl+C`: ______
5. *(Tópico 5)* Comando que define ou troca a senha de um usuário: ______

<details>
<summary>Gabarito da série 11</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `Blender` | — |
| 2 | `export` | — |
| 3 | `<` | — |
| 4 | `SIGINT` | `INT` ou `2` |
| 5 | `passwd` | — |

</details>

### Retorno para responder com a série 11 (sábado 14/11)

- *(Tópico 1, série 08)* Suíte de escritório livre, derivada do OpenOffice, presente na maioria das distribuições (o nome completo): ______

## Série 12

1. *(Tópico 2)* Comando interno que apaga uma variável do shell: ______
2. *(Tópico 3)* Operador do *here document*: ______
3. *(Tópico 4)* Comando interno que traz um trabalho para o primeiro plano: ______
4. *(Tópico 5)* Comando que remove uma conta de usuário: ______
5. *(Tópico 1)* Programa livre para gravar e editar áudio: ______

<details>
<summary>Gabarito da série 12</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `unset` | — |
| 2 | `<<` | — |
| 3 | `fg` | — |
| 4 | `userdel` | — |
| 5 | `Audacity` | — |

</details>

## Série 13

1. *(Tópico 3)* Forma curta do Bash para mandar a saída padrão e a de erro ao mesmo arquivo: ______
2. *(Tópico 4)* Comando interno que lista os trabalhos do shell: ______
3. *(Tópico 5)* Octal de `rwxr-x---`: ______
4. *(Tópico 1)* Servidor web open source criado por Igor Sysoev, muito usado como proxy reverso: ______
5. *(Tópico 2)* Opção do `ls` que mostra também os arquivos ocultos (escreva com o hífen): ______

<details>
<summary>Gabarito da série 13</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `&>` | — |
| 2 | `jobs` | — |
| 3 | `750` | — |
| 4 | `nginx` | `NGINX` |
| 5 | `-a` | `-A`, que omite `.` e `..` |

</details>

## Série 14

1. *(Tópico 4)* Comando que lista os módulos do kernel carregados: ______
2. *(Tópico 5)* Octal de `rw-r--r--`: ______
3. *(Tópico 1)* Banco de dados relacional open source do qual o MariaDB é um *fork*: ______
4. *(Tópico 2)* Comando que remove um diretório, desde que ele esteja vazio: ______
5. *(Tópico 3)* Caminho do arquivo especial que descarta tudo o que recebe: ______

<details>
<summary>Gabarito da série 14</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `lsmod` | — |
| 2 | `644` | — |
| 3 | `MySQL` | — |
| 4 | `rmdir` | — |
| 5 | `/dev/null` | — |

</details>

## Série 15

1. *(Tópico 5)* Octal, com o bit especial, de `rwsr-xr-x`: ______
2. *(Tópico 1)* Sigla de quatro letras para *Free and Open Source Software*: ______
3. *(Tópico 2)* Opção do `cp` necessária para copiar um diretório com o conteúdo (com o hífen): ______
4. *(Tópico 3)* Caractere que liga a saída de um comando à entrada do seguinte: ______
5. *(Tópico 4)* Comando que lista discos e partições em árvore: ______

<details>
<summary>Gabarito da série 15</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `4755` | — |
| 2 | `FOSS` | — |
| 3 | `-r` | `-R` |
| 4 | `\|` | — |
| 5 | `lsblk` | — |

</details>

## Série 16

1. *(Tópico 1)* Sigla da organização que mantém a *Open Source Definition*: ______
2. *(Tópico 2)* Opção do `mkdir` que cria também os diretórios pais que faltam (com o hífen): ______
3. *(Tópico 3)* Opção do `grep` que ignora a diferença entre maiúsculas e minúsculas: ______
4. *(Tópico 4)* Comando que lista os dispositivos PCI: ______
5. *(Tópico 5)* Octal, com o bit especial, de `drwxrwxrwt`: ______

<details>
<summary>Gabarito da série 16</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `OSI` | — |
| 2 | `-p` | — |
| 3 | `-i` | — |
| 4 | `lspci` | — |
| 5 | `1777` | — |

</details>

## Série 17

1. *(Tópico 2)* Comando que identifica o tipo de um arquivo pelo conteúdo, e não pela extensão: ______
2. *(Tópico 3)* Opção do `grep` que mostra as linhas que **não** casam: ______
3. *(Tópico 4)* Caminho do arquivo de dispositivo da **segunda partição do primeiro** disco SATA: ______
4. *(Tópico 5)* Sigla do bit que faz um executável rodar com as permissões do dono: ______
5. *(Tópico 1)* Licenças como MIT e BSD, que permitem incorporar o código em software proprietário, são chamadas de licenças ______ (uma palavra)

<details>
<summary>Gabarito da série 17</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `file` | — |
| 2 | `-v` | — |
| 3 | `/dev/sda2` | — |
| 4 | `SUID` | — |
| 5 | `permissivas` | `permissiva` |

</details>

## Série 18

1. *(Tópico 3)* Opção do `grep` que mostra só a quantidade de linhas que casam: ______
2. *(Tópico 4)* Caminho do arquivo que lista os servidores DNS: ______
3. *(Tópico 5)* Letra que aparece no lugar do `x` dos outros quando o sticky bit está ligado e os outros **não** têm `x`: ______
4. *(Tópico 1)* Software que cria e executa máquinas virtuais, cada uma com o próprio kernel: ______
5. *(Tópico 2)* Comando interno que lista os comandos digitados anteriormente: ______

<details>
<summary>Gabarito da série 18</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `-c` | — |
| 2 | `/etc/resolv.conf` | — |
| 3 | `T` | — |
| 4 | `hipervisor` | `hypervisor` |
| 5 | `history` | — |

</details>

## Série 19

1. *(Tópico 4)* Caminho do arquivo com a tabela local de nomes, consultada antes do DNS: ______
2. *(Tópico 5)* Octal final de um arquivo `640` depois de `chmod g+w`: ______
3. *(Tópico 1)* Sigla do modelo de nuvem em que o cliente recebe máquinas virtuais e administra o sistema operacional: ______
4. *(Tópico 2)* Caractere curinga que casa exatamente um caractere qualquer: ______
5. *(Tópico 3)* Comando que conta linhas, palavras e bytes: ______

<details>
<summary>Gabarito da série 19</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `/etc/hosts` | — |
| 2 | `660` | — |
| 3 | `IaaS` | — |
| 4 | `?` | — |
| 5 | `wc` | — |

</details>

## Série 20

1. *(Tópico 5)* Forma simbólica, com nove caracteres, de `751`: ______
2. *(Tópico 1)* No sentido estrito, *Linux* é o nome de qual componente do sistema operacional (uma palavra): ______
3. *(Tópico 2)* Caractere que o shell expande para a pasta pessoal do usuário: ______
4. *(Tópico 3)* Opção do `sort` que ordena por valor numérico: ______
5. *(Tópico 4)* Comando atual (sem subcomando) que substitui o `ifconfig` e o `route`: ______

<details>
<summary>Gabarito da série 20</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `rwxr-x--x` | — |
| 2 | `kernel` | `núcleo` |
| 3 | `~` | — |
| 4 | `-n` | — |
| 5 | `ip` | — |

</details>

## Série 21

1. *(Tópico 2)* Argumento do `cd` que volta ao diretório anterior: ______
2. *(Tópico 3)* Comando que junta linhas repetidas **vizinhas**: ______
3. *(Tópico 3)* Parâmetro especial com a quantidade de argumentos do script (escreva com o `$`): ______
4. *(Tópico 4)* Comando atual que substitui o `netstat` para listar sockets e portas: ______
5. *(Tópico 5)* Opção do `ln` que cria um link simbólico (com o hífen): ______

<details>
<summary>Gabarito da série 21</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `-` | — |
| 2 | `uniq` | — |
| 3 | `$#` | — |
| 4 | `ss` | — |
| 5 | `-s` | — |

</details>

## Série 22

1. *(Tópico 3)* Comando que extrai colunas usando um delimitador: ______
2. *(Tópico 3)* Parâmetro especial com o código de saída do último comando (com o `$`): ______
3. *(Tópico 4)* Porta TCP padrão do SSH: ______
4. *(Tópico 5)* Comando que executa um único comando como root, pedindo a senha do próprio usuário: ______
5. *(Tópico 2)* Os dois caracteres que representam o diretório pai: ______

<details>
<summary>Gabarito da série 22</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `cut` | — |
| 2 | `$?` | — |
| 3 | `22` | — |
| 4 | `sudo` | — |
| 5 | `..` | — |

</details>

## Série 23

1. *(Tópico 3)* Palavra que fecha um bloco `if` no Bash: ______
2. *(Tópico 4)* Quantidade de bits de um endereço IPv6: ______
3. *(Tópico 5)* Opção do `ls` que mostra o próprio diretório, e não o conteúdo dele (com o hífen): ______
4. *(Tópico 2)* Comando que procura arquivos percorrendo o disco no momento da busca: ______
5. *(Tópico 3)* Em expressão regular, caractere que ancora o início da linha: ______

<details>
<summary>Gabarito da série 23</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `fi` | — |
| 2 | `128` | — |
| 3 | `-d` | — |
| 4 | `find` | — |
| 5 | `^` | — |

</details>

## Série 24

1. *(Tópico 4)* Sigla das versões de distribuição com suporte estendido por vários anos: ______
2. *(Tópico 5)* Octal final de um arquivo `775` depois de `chmod g-w`: ______
3. *(Tópico 2)* Comando que renomeia um arquivo: ______
4. *(Tópico 3)* Os dois caracteres do início da primeira linha de um script, antes do caminho do interpretador: ______
5. *(Tópico 3)* Editor de texto modal, de duas letras, presente em quase todo sistema Unix: ______

<details>
<summary>Gabarito da série 24</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `LTS` | — |
| 2 | `755` | — |
| 3 | `mv` | — |
| 4 | `#!` | — |
| 5 | `vi` | `vim` |

</details>

---

## Lacunas extras — erros do R4

Respondidas com a série 08, na quarta 11/11: **2 de 2** (`2744` e `chgrp`). Os dois erros do R4 estão fechados. Saem dos dois erros do R4 (`reforco-r3-r4.md`) e substituem o treino na VM que não foi feito em 09/11.

1. *(Tópico 5)* Octal completo, com o bit especial, de `-rwxr-Sr--`: ______
2. *(Tópico 5)* Comando que muda **só o grupo** de um arquivo, sem mexer no dono (só o nome do comando): ______

<details>
<summary>Gabarito das lacunas extras</summary>

| # | Resposta | Também aceito |
|---|---|---|
| 1 | `2744` | — (o `S` está no trio do grupo: SGID, que vale 2) |
| 2 | `chgrp` | `chown` não vale aqui: ele muda o grupo só na forma `chown :grupo arquivo` |

</details>

## Controle

| Série | Data | Acertos | Erradas (número e motivo: conteúdo ou forma) | Volta na série |
|---|---|---|---|---|
| 01 | 04/11 | **1 de 5** (conteúdo: 3) | 1 forma ("Licença Copyleft"; vale só `copyleft`) · 3 forma ("-x - extract"; vale só `-x`) · 4 em branco (`ps`) · 5 em branco (`/etc/shadow`) | Qui 12/11: escritas dentro da série 09 |
| 02 | 04/11 | **0 de 5** (conteúdo: 1) | 1 em branco (`help`) · 2 conteúdo ("tar.gz"; a opção é `-z`) · 3 em branco (`top`) · 4 em branco (`/etc/group`) · 5 forma ("FSF - Free Software Foundation"; vale só `FSF`) | Qui 12/11: escritas dentro da série 09 |
| 03 | 05/11 | **4 de 5** | 3 em branco (`/etc/skel`; no simulado 03, a Q35 sobre o mesmo arquivo saiu certa: reconhecer é mais fácil que lembrar) | Qui 12/11: escrita dentro da série 09 |
| 04 | 07/11 | **5 de 5** | Nenhuma | — |
| 05 | 07/11 | **5 de 5** | Nenhuma. A 3 (`5`, seção de formatos de arquivo) é o mesmo ponto que você errou na Q7 do R3: lembrado na lacuna, mas não reconhecido na alternativa | — |
| 06 | 09/11 | **5 de 5** | Nenhuma | — |
| 07 | 10/11 | **3 de 5** (conteúdo: 5) | 2 de forma: `update db` (é `updatedb`, junto) e `proc` (o pedido é o caminho: `/proc`). Na 4, `sudo chown` foi aceito, mas o comando é só `chown` | Sex 13/11: escritas dentro da série 10 |
| 08 | 11/11 | **4 de 5** (conteúdo: 5) | 1 de forma: `Libre` (o nome é `LibreOffice`). As 2 extras do R4 vieram certas: `2744` e `chgrp` | Sáb 14/11: escrita dentro da série 11 |
| 09 | | de 5 | | |
| 10 | | de 5 | | |
| 11 | | de 5 | | |
| 12 | | de 5 | | |
| 13 | | de 5 | | |
| 14 | | de 5 | | |
| 15 | | de 5 | | |
| 16 | | de 5 | | |
| 17 | | de 5 | | |
| 18 | | de 5 | | |
| 19 | | de 5 | | |
| 20 | | de 5 | | |
| 21 | | de 5 | | |
| 22 | | de 5 | | |
| 23 | | de 5 | | |
| 24 | | de 5 | | |