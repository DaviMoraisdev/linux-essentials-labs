# Simulado 11 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 26/11/2026. É o **simulado final, calibrado como a prova**: o número de questões de cada objetivo segue o peso oficial do 010-160 (1.1: 2, 1.2: 2, 1.3: 1, 1.4: 2; 2.1: 3, 2.2: 2, 2.3: 2, 2.4: 2; 3.1: 2, 3.2: 3, 3.3: 4; 4.1: 1, 4.2: 2, 4.3: 3, 4.4: 2; 5.1: 2, 5.2: 2, 5.3: 2, 5.4: 1), com mistura de questões diretas e de situação, como na prova. Retesta as reincidências da seção 7 do `revisao-final.md` e cobre os três assuntos que faltavam, levantados em 24/11 (DNS reverso, a origem da saída do `id` e o arquivo de uma conta removida). Nenhuma questão repete os simulados 02 a 10.

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

**1.** Qual sequência descreve corretamente a origem de três distribuições populares?

- A) O Linux Mint deriva do Ubuntu, que deriva do Debian
- B) O Ubuntu deriva do Fedora, que deriva do Debian
- C) O Debian deriva do Ubuntu, que deriva do Linux Mint
- D) O Linux Mint deriva do Red Hat Enterprise Linux
- E) As três são independentes e não compartilham pacotes

**2.** Um roteador doméstico, uma smart TV e um termostato inteligente rodam Linux. Como se chama esse uso, e por que o Linux é comum nele?

- A) Sistemas embarcados; porque o kernel é livre, adaptável a hardware pequeno e não cobra licença por aparelho
- B) Computação em nuvem; porque os aparelhos dependem da internet
- C) Desktop; porque os aparelhos têm interface gráfica
- D) Servidores; porque todos os aparelhos hospedam sites
- E) Virtualização; porque cada aparelho é uma máquina virtual

**3.** **(escolha duas)** Uma loja virtual precisa de um **banco de dados relacional** open source. Quais programas atendem?

- A) NGINX
- B) MariaDB
- C) Samba
- D) PostgreSQL
- E) Thunderbird

**4.** Um desenvolvedor escreve um programa em **C** e outro em **Python**. Qual afirmação está correta?

- A) Os dois precisam ser compilados antes de rodar
- B) O programa em Python vira um executável binário ao ser salvo
- C) O programa em C é compilado para código de máquina antes de rodar; o em Python é executado por um interpretador
- D) Nenhum dos dois roda no Linux sem uma máquina virtual Java
- E) O C é interpretado e o Python é compilado

**5.** Uma empresa distribui a versão básica do seu programa sob licença livre e vende, à parte, módulos extras proprietários para clientes corporativos. Que modelo de negócio é esse?

- A) Licença dupla
- B) SaaS
- C) *Fork*
- D) Doação
- E) *Open core*

**6.** Uma usuária abre uma **janela privada** do navegador para acessar o webmail num computador compartilhado. O que essa janela garante?

- A) Que o provedor de internet não vê os sites acessados
- B) Que o histórico, os cookies e os dados de formulário daquela janela são apagados ao fechá-la
- C) Que a conexão passa a ser cifrada, mesmo em sites HTTP
- D) Que os arquivos baixados são apagados ao fechar
- E) Que o endereço IP fica oculto para os sites

**7. [lacuna]** Qual é o comando do GnuPG usado para gerar chaves, cifrar e assinar arquivos? Escreva só o comando: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** Qual é a saída do último comando?

```bash
$ ARQ=nota
$ echo "$ARQ_1 ${ARQ}_1"
```

- A) `nota_1 nota_1`
- B) ` nota_1`, com um espaço no início
- C) `$ARQ_1 nota_1`
- D) `nota_1 ${ARQ}_1`
- E) Erro de sintaxe

**9.** O comando `type ls cd` mostra `ls is aliased to 'ls --color=auto'` e `cd is a shell builtin`. O que se conclui?

- A) Os dois são programas em `/usr/bin`
- B) Os dois precisam de `sudo`
- C) O `cd` é um alias para o `ls`
- D) O `ls` não existe no sistema
- E) O `ls` digitado executa, na verdade, `ls --color=auto`, e o `cd` é um comando interno do Bash, sem arquivo em disco

**10.** **(escolha duas)** Para o usuário `davi`, quais comandos mostram `/home/davi`?

- A) `echo ~`
- B) `echo $HOME`
- C) `echo '$HOME'`
- D) `echo "~"`
- E) `echo $home`

**11.** Durante a leitura de uma página do `man`, o usuário quer **procurar** a palavra `recursive` no texto. O que ele digita?

- A) `:recursive`
- B) `Ctrl+F recursive`
- C) `/recursive` e Enter (`n` vai para a próxima ocorrência)
- D) `grep recursive`
- E) `man -k recursive`

**12.** O nome `passwd` existe na seção 1 (o comando) e na seção 5 (o formato do arquivo `/etc/passwd`) do manual. O que abre `man passwd`?

- A) A seção 5
- B) As duas, uma depois da outra
- C) Nenhuma: é preciso informar a seção
- D) A página da **seção 1**, a primeira encontrada na ordem de busca
- E) A página do `/etc/shadow`

**13.** O usuário está em `/usr/share/doc` e executa `cd ../../lib/../bin`. Qual é o diretório final?

- A) `/usr/share/bin`
- B) `/usr/lib/bin`
- C) `/bin`
- D) `/usr/bin`
- E) `/usr/share/lib/bin`

**14.** Qual é a diferença entre `ls -l /etc` e `ls -ld /etc`?

- A) Nenhuma
- B) O segundo lista também os subdiretórios
- C) O primeiro lista o conteúdo de `/etc`; o segundo mostra só a linha do próprio diretório `/etc`, com as permissões dele
- D) O segundo mostra os arquivos ocultos
- E) O primeiro só mostra diretórios

**15.** Existe um **diretório** `arquivo`. O que faz `mv relatorio.txt arquivo`?

- A) Renomeia `relatorio.txt` para `arquivo`, apagando o diretório
- B) Move `relatorio.txt` para dentro do diretório, como `arquivo/relatorio.txt`
- C) Dá erro, porque o destino já existe
- D) Copia o arquivo e mantém o original
- E) Pede confirmação

**16. [lacuna]** Qual opção do `cp` pergunta antes de sobrescrever um arquivo que já existe no destino? Escreva só a opção, com o hífen: ______

---

## Tópico 3 — O poder da linha de comando

**17.** O que faz `tar -xzf site.tar.gz -C /srv/www`?

- A) Cria `site.tar.gz` com o conteúdo de `/srv/www`
- B) Lista o conteúdo do pacote
- C) Extrai o pacote comprimido com gzip para dentro de `/srv/www`
- D) Extrai o pacote no diretório atual e copia para `/srv/www`
- E) Comprime `/srv/www` com bzip2

**18.** **(escolha duas)** Quais comandos substituem `app.log` por uma versão **comprimida**, sem deixar o original?

- A) `gzip app.log`
- B) `tar -cf app.tar app.log`
- C) `zip app.zip app.log`
- D) `xz app.log`
- E) `cat app.log > app.log.gz`

**19.** O que mostra a última linha deste pipeline?

```bash
cut -d: -f7 /etc/passwd | sort | uniq -c | sort -nr | head -1
```

- A) O primeiro shell em ordem alfabética
- B) O nome do primeiro usuário
- C) O total de usuários
- D) O shell mais usado nas contas, com a quantidade de contas na frente
- E) O último campo da primeira linha do `/etc/passwd`

**20.** O que fica em cada arquivo depois de `ls /etc/hostname /naoexiste > saida.txt 2> erro.txt`?

- A) Os dois textos em `saida.txt`; `erro.txt` vazio
- B) Nada nos dois, porque o comando falhou
- C) Os dois textos na tela; os dois arquivos vazios
- D) A mensagem de erro em `saida.txt` e o nome em `erro.txt`
- E) `/etc/hostname` em `saida.txt` e a mensagem *No such file or directory* em `erro.txt`; nada na tela

**21. [lacuna]** Qual comando lê a entrada padrão e a envia **ao mesmo tempo** para a tela e para um arquivo, como em `ls | ____ lista.txt`? Escreva só o comando: ______

**22.** O script `backup.sh` tem a linha `echo "$0 recebeu $# itens: $1"`. Qual é a saída de `./backup.sh /home /etc`?

- A) `./backup.sh recebeu 3 itens: /home`
- B) `./backup.sh recebeu 2 itens: /home`
- C) `backup.sh recebeu 2 itens: /etc`
- D) `./backup.sh recebeu 2 itens: /home /etc`
- E) `/home recebeu 1 itens: /etc`

**23.** Num diretório com `a.txt` e `b.txt`, o que faz o laço abaixo?

```bash
for f in *.txt; do
  mv "$f" "$f.bak"
done
```

- A) Cria cópias `a.txt.bak` e `b.txt.bak`, mantendo os originais
- B) Renomeia para `a.bak` e `b.bak`
- C) Renomeia os dois para `a.txt.bak` e `b.txt.bak`
- D) Cria um arquivo chamado `*.txt.bak`
- E) Dá erro, porque o `mv` não aceita variáveis

**24.** Qual é a saída de `./verifica.sh; echo $?`, executado **sem argumentos**?

```bash
#!/bin/bash
if [ -z "$1" ]; then
  echo "uso: $0 arquivo"
  exit 2
fi
echo ok
```

- A) `ok` e `0`
- B) `uso: ./verifica.sh arquivo` e `0`
- C) `uso: ./verifica.sh arquivo`, `ok` e `2`
- D) `uso: ./verifica.sh arquivo` e `2`
- E) Só `2`

**25.** Um administrador abriu um arquivo no `vi`, editou o texto e quer **salvar e sair**. O que ele faz?

- A) `Ctrl+X` e depois `Y`
- B) Digita `exit`
- C) `Esc` e depois `:q!`
- D) `Ctrl+S`
- E) `Esc` e depois `:wq`

---

## Tópico 4 — O sistema operacional Linux

**26.** Uma versão de uma distribuição chegou ao **fim de vida** (EOL). O que isso significa para quem continua usando?

- A) O sistema para de funcionar na data
- B) Os programas instalados são removidos
- C) A versão passa a ser *rolling release*
- D) A versão vira LTS automaticamente
- E) O sistema continua funcionando, mas deixa de receber correções de segurança; o certo é migrar para uma versão suportada

**27.** O `free -h` mostra o swap quase cheio e a coluna `available` perto de zero, e o sistema está lento. O que acontece?

- A) Falta memória RAM: o sistema está usando o swap, que fica em disco e é muito mais lento
- B) O disco está cheio
- C) A CPU está sobrecarregada
- D) O cache precisa ser apagado à mão
- E) Está normal: o swap cheio é sinal de bom uso

**28.** Uma placa de rede nova não funciona porque o driver não foi carregado. Qual comando carrega o **módulo** do kernel correspondente?

- A) `lsmod`
- B) `modprobe`
- C) `lspci`
- D) `dmesg`
- E) `insmod -l`

**29.** **(escolha duas)** Quais diretórios são sistemas de arquivos **virtuais**, montados pelo kernel na memória, sem arquivos gravados em disco?

- A) `/proc`
- B) `/etc`
- C) `/var/log`
- D) `/sys`
- E) `/usr`

**30.** Por que `cat /var/log/wtmp` mostra caracteres estranhos, e como ler esse arquivo?

- A) Porque ele é **binário**; é lido com o comando `last`
- B) Porque o arquivo está corrompido; é preciso apagá-lo
- C) Porque está comprimido com gzip; é lido com `zcat`
- D) Porque falta o `sudo`; com ele, o `cat` funciona
- E) Porque está cifrado; é lido com `gpg`

**31. [lacuna]** Na maioria das distribuições atuais, qual programa é o processo de PID 1, o primeiro iniciado pelo kernel? Escreva só o nome: ______

**32.** Qual tipo de registro DNS faz o caminho **inverso**, do endereço IP para o nome, e onde ele fica?

- A) Registro A, na zona do domínio
- B) Registro CNAME, como apelido do IP
- C) Registro MX, porque o e-mail usa IP
- D) Registro AAAA, para IPv4
- E) Registro **PTR**, numa zona especial em que o IP aparece de trás para frente sob `in-addr.arpa` (por exemplo, `165.100.51.198.in-addr.arpa`)

**33.** Uma máquina tem `192.168.10.77/24` e a rota `default via 192.168.10.1`. Para onde ela envia um pacote destinado a `192.168.11.5`?

- A) Direto para `192.168.11.5`, porque os dois endereços começam com `192.168`
- B) Para o gateway `192.168.10.1`, porque o destino está fora da rede `192.168.10.0/24`
- C) Para `127.0.0.1`
- D) Para o servidor DNS
- E) Para nenhum lugar: o pacote é descartado

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** **(escolha duas)** O comando `id bob` mostra `uid=1002(bob) gid=1002(bob) groups=1002(bob),33(www-data)`. De quais arquivos vêm essas informações?

- A) `/etc/passwd`
- B) `/etc/shadow`
- C) `/etc/group`
- D) `/etc/skel`
- E) `/etc/login.defs`

**35.** Qual arquivo define quais usuários e grupos podem usar o `sudo`, e como ele deve ser editado?

- A) `/etc/passwd`, com qualquer editor
- B) `~/.bashrc`, com o `nano`
- C) `/etc/group`, com `usermod`
- D) `/etc/shadow`, com `passwd`
- E) `/etc/sudoers`, com o comando `visudo`, que confere a sintaxe antes de gravar

**36.** A conta `joao` foi removida com `userdel joao`, **sem** `-r`. Ele tinha o arquivo `/srv/dados/plano.txt`. O que acontece com o arquivo?

- A) É apagado junto com a conta
- B) Passa a pertencer ao root
- C) É movido para `/tmp`
- D) Fica bloqueado para todos
- E) Continua lá, e o `ls -l` passa a mostrar o **número** do UID antigo no lugar do nome do dono

**37.** Qual comando faz `dev` ser o **grupo primário** da conta `carla`?

- A) `chgrp dev carla`
- B) `usermod -aG dev carla`
- C) `usermod -g dev carla`
- D) `groupadd dev carla`
- E) `chown :dev carla`

**38.** Qual é a permissão de `projeto` depois de `chmod 2770 projeto`, se ele é um diretório?

- A) `drwxrwx--T`
- B) `drwsrwx---`
- C) `drwxrws---`
- D) `drwxrwS---`
- E) `drwxrwx--t`

**39.** O diretório `entrada` tem `drwx-wx-wx` e pertence ao root. O que um usuário comum consegue fazer nele?

- A) Listar e apagar qualquer arquivo
- B) Nada
- C) Listar os nomes, mas não criar arquivos
- D) Criar arquivos (`w` e `x`), mas não listar o conteúdo (sem `r`)
- E) Só entrar com `cd`

**40. [lacuna]** Qual opção do `ls` mostra o número do **inode** de cada arquivo, útil para conferir se dois nomes são hard links do mesmo arquivo? Escreva só a opção, com o hífen: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **A** | A linhagem é Debian → Ubuntu → Linux Mint: as três usam `.deb` e `apt`. O Fedora é da família Red Hat (`.rpm`, `dnf`) |
| 2 | **A** | Embarcado é o computador dentro de um aparelho com função fixa. O Linux domina esse uso pelo custo zero de licença e pela facilidade de adaptar o kernel; o Android é o exemplo mais conhecido |
| 3 | **B e D** | MariaDB e PostgreSQL são bancos relacionais (SQL). O NGINX é servidor web, o Samba compartilha arquivos com o Windows e o Thunderbird é cliente de e-mail |
| 4 | **C** | C (como C++, Go e Rust) é compilado para um executável; Python (como Bash, Perl e PHP) é lido e executado pelo interpretador na hora. O Java fica no meio: compila para *bytecode* que roda na JVM |
| 5 | **E** | No *open core* o núcleo é livre e as extensões pagas são fechadas. Na licença dupla, o **mesmo** código é oferecido sob GPL e sob uma licença comercial, à escolha do cliente |
| 6 | **B** | A janela privada só deixa de **guardar** dados no computador local. A rede, o provedor e os sites continuam vendo o acesso e o IP; downloads ficam no disco. Para esconder o IP é preciso uma VPN ou o Tor |
| 7 | **`gpg`** | Grafia aceita: `gpg` (ou `gpg2`). Lembre: cifra-se com a chave **pública** do destinatário; assina-se com a **privada** do remetente |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **B** | O sublinhado faz parte de nomes de variável: o shell procura `ARQ_1`, que não existe, e põe nada no lugar. As chaves delimitam o nome: `${ARQ}_1` vira `nota_1` |
| 9 | **E** | O `type` diz como o shell vai interpretar cada nome: alias, interno (*builtin*) ou arquivo. Por ser interno, a ajuda do `cd` vem do `help cd` |
| 10 | **A e B** | O `~` sem aspas e a variável `HOME` expandem para a pasta pessoal. Entre aspas (simples ou duplas) o `~` não expande; as aspas simples impedem o `$HOME`; e `home` minúsculo é outra variável, vazia |
| 11 | **C** | O `man` usa o paginador `less`: `/texto` procura para frente, `n` repete, `q` sai. O `man -k` procura nas descrições de **todas** as páginas, não dentro da página aberta |
| 12 | **D** | Sem número, o `man` mostra a primeira seção que tiver o nome, e a seção 1 vem antes. Para o formato do arquivo: `man 5 passwd`. O `whatis passwd` lista as duas |
| 13 | **D** | Passo a passo: `..` vai para `/usr/share`; `..` vai para `/usr`; `lib` entra em `/usr/lib`; `..` volta a `/usr`; `bin` entra em `/usr/bin` |
| 14 | **C** | O `-d` trata o diretório como um item, sem entrar nele. É o jeito de ver as permissões de um diretório; o `ls -l` sozinho mostraria as dos arquivos dentro dele |
| 15 | **B** | Quando o destino é um diretório existente, o `mv` move para dentro dele, mantendo o nome. Só renomeia quando o destino **não** existe |
| 16 | **`-i`** | Grafia aceita: `-i` (*interactive*). Vale o mesmo para `mv -i` e `rm -i` |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **C** | `-x` extrai, `-z` gzip, `-f` o pacote; o `-C` muda o diretório de destino antes de extrair. Sem `-C`, tudo cai no diretório atual |
| 18 | **A e D** | `gzip`, `bzip2` e `xz` trocam o arquivo pelo comprimido (`app.log.gz`, `app.log.xz`). O `tar -cf` só empacota, sem comprimir; o `zip` cria o `.zip` e mantém o original; o `cat` só copia com outro nome |
| 19 | **D** | O `cut` pega o sétimo campo (o shell); `sort` junta os iguais; `uniq -c` conta; `sort -nr` põe a maior contagem primeiro; `head -1` fica com ela |
| 20 | **E** | O canal 1 (saída) vai para `saida.txt` e o canal 2 (erro) para `erro.txt`. O `ls` ainda lista o que existe, mesmo com um argumento inválido |
| 21 | **`tee`** | Grafia aceita: `tee`. Com `-a`, acrescenta ao arquivo em vez de sobrescrever |
| 22 | **B** | `$0` é o nome usado para chamar o script, `./backup.sh`; o `$#` conta só os argumentos depois dele (2); o `$1` é o primeiro, `/home` |
| 23 | **C** | O curinga vira a lista `a.txt b.txt`; a cada volta, `$f` recebe um nome e o `mv` acrescenta `.bak` ao **nome inteiro**. O `mv` renomeia, não copia |
| 24 | **D** | Sem argumentos, o `$1` está vazio e o `-z` é verdadeiro: sai a mensagem de uso e o `exit 2` encerra o script antes do `echo ok`. O `$?` mostra o 2 |
| 25 | **E** | O `vi` é modal: `Esc` volta ao modo de comando, `:w` grava e `:q` sai; `:wq` faz os dois. O `:q!` sai **sem** salvar. `Ctrl+X` é o jeito de sair do `nano` |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **E** | O fim de vida encerra o suporte: sem atualizações de segurança, cada falha nova fica aberta. Por isso servidores usam versões LTS e planejam a troca antes do EOL |
| 27 | **A** | O swap é uma área do **disco** usada quando a RAM acaba. Com `available` baixo e swap em uso, os programas esperam o disco. Diferente do caso em que só o `free` está baixo por causa do cache (Q27 do simulado 10) |
| 28 | **B** | No Linux, a maior parte dos drivers são módulos do kernel. O `modprobe nome` carrega o módulo e as dependências; o `lsmod` só **lista** os carregados; o `lspci` mostra o hardware PCI |
| 29 | **A e D** | O `/proc` (processos e dados do kernel) e o `/sys` (dispositivos e drivers) são gerados pelo kernel na hora. O `/etc`, o `/var/log` e o `/usr` são diretórios comuns no disco |
| 30 | **A** | O `wtmp` (logins), o `btmp` (falhas, lido com `lastb`) e o journal do systemd são binários. O `syslog` e o `auth.log` são texto e podem ser lidos com `cat`, `less` e `grep` |
| 31 | **`systemd`** | Grafia aceita: `systemd` (`init` nos sistemas antigos com SysV init) |
| 32 | **E** | O DNS reverso usa PTR. O IPv4 `198.51.100.165` vira `165.100.51.198.in-addr.arpa`, porque o DNS lê do mais específico para o mais geral; no IPv6 a zona é `ip6.arpa` |
| 33 | **B** | Com `/24`, a rede local é `192.168.10.0` a `192.168.10.255`. O terceiro número muda (11), então o destino é de outra rede e o pacote vai para o gateway da rota padrão |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **A e C** | O UID, o GID primário e o nome vêm do `/etc/passwd`; os nomes dos grupos e a participação como membro secundário vêm do `/etc/group`. O `/etc/shadow` guarda só os hashes e as datas de senha |
| 35 | **E** | As regras do `sudo` ficam no `/etc/sudoers` (e em `/etc/sudoers.d/`). O `visudo` evita que um erro de sintaxe tranque o acesso de administrador. No Ubuntu, o grupo `sudo` já está liberado lá; no RHEL, o `wheel` |
| 36 | **E** | O `userdel` só apaga a conta (e, com `-r`, a pasta pessoal e o e-mail). Arquivos fora da pasta pessoal continuam com o UID antigo; sem nome para traduzir, o `ls -l` mostra o número. Se uma conta nova receber esse UID, herda os arquivos |
| 37 | **C** | O `-g` minúsculo do `usermod` troca o grupo **primário** da conta; o `-aG` acrescenta um grupo **secundário**. O `chgrp` e o `chown` mudam o grupo de **arquivos**, não de contas |
| 38 | **C** | **4-2-1 = dono-grupo-outros = s-s-t.** O 2 é o SGID, que aparece no trio do **grupo**; como o grupo tem `x`, a letra é `s` minúscula. Em diretório, os arquivos criados lá herdam o grupo do diretório |
| 39 | **D** | No diretório, `w` com `x` permite criar e apagar entradas; sem `r`, o `ls` falha. É o modelo de uma "caixa de entrega": cada um deixa o arquivo, mas não vê os dos outros (sem sticky bit, porém, poderia apagá-los pelo nome) |
| 40 | **`-i`** | Grafia aceita: `-i`. Dois hard links mostram o mesmo número de inode, e o contador de links do `ls -l` fica maior que 1 |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 8 | Chaves e nomes de variável (aspas e expansão, Tópico 2) |
| 13 | `..` passo a passo (reincidência, 7 vezes) |
| 19 | `sort`, `uniq -c` e `sort -nr` (reincidência) |
| 20 | Canal 2 e redirecionamento (reincidência) |
| 22 | `$#` sem o `$0` (reincidência, 4 vezes) |
| 32 | DNS reverso, PTR e `in-addr.arpa` (assunto que faltava, levantado em 24/11) |
| 33 | `/24` e gateway (reincidência) |
| 34 | Arquivos de contas: origem da saída do `id` (assunto que faltava, levantado em 24/11) |
| 36 | Arquivo de conta removida mostra o UID numérico (assunto que faltava, levantado em 24/11) |
| 37 | Conta contra arquivo: `usermod -g` contra `chgrp` (reincidência, 4 vezes) |
| 38 | Bit especial no trio certo (reincidência, 7 vezes; Correção 84) |
| 39 | `r`, `w` e `x` em diretório (reincidência) |

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
| Data | 26/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |