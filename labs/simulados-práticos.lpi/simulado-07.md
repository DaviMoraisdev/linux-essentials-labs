# Simulado 07 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 13/11/2026 para o sábado 14/11 e remarcado para a **segunda 16/11**. É o primeiro no **novo padrão** pedido em 13/11: questões de situação, em que é preciso seguir o que o comando faz passo a passo, e alternativas que diferem em um detalhe, como nas questões de exemplo públicas do exame. Nenhuma questão repete os simulados 02 a 06, os reforços R2 a R4 ou os Exercícios da LPI.

Cinco alternativas por questão, **cinco questões de escolher duas** e cinco lacunas. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. Reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **28 acertos firmes** ou mais |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando. Nas questões de situação, **siga o comando passo a passo** antes de olhar as alternativas.

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

**1.** Um usuário de Debian baixou o instalador `editor-2.1.x86_64.rpm` do site de um projeto. Qual afirmação descreve corretamente a situação?

- A) O `dpkg -i` instala pacotes `.rpm` sem problemas
- B) O `apt` converte o `.rpm` em `.deb` automaticamente na instalação
- C) O `.rpm` é o formato das famílias Red Hat e SUSE; no Debian, o adequado é obter a versão `.deb`, de preferência pelo `apt`
- D) `rpm` e `dpkg` são o mesmo programa com nomes diferentes
- E) Pacotes `.rpm` só funcionam no Fedora

**2.** **(escolha duas)** Uma escola quer montar, só com software livre, um servidor web e um banco de dados relacional. Quais pares atendem?

- A) NGINX e MariaDB
- B) Samba e Thunderbird
- C) IIS e SQL Server
- D) Apache HTTPD e PostgreSQL
- E) NFS e LibreOffice

**3.** Vários servidores Linux precisam montar o mesmo diretório remoto como se fosse um sistema de arquivos local. Qual serviço é o mais indicado?

- A) NFS
- B) Samba
- C) Apache
- D) Postfix
- E) OpenSSH

**4.** Um desenvolvedor junta, em um só programa, um código sob licença MIT e outro sob GPLv3, e distribui o resultado. Sob qual licença o programa combinado pode ser distribuído?

- A) Só sob a MIT, que é a mais permissiva
- B) Sob qualquer licença, inclusive proprietária
- C) Sob a GPLv3, mantendo os avisos de copyright da parte MIT
- D) Sob nenhuma: as duas licenças não podem ser combinadas
- E) Sob domínio público

**5.** Qual organização mantém a *Open Source Definition* e aprova licenças como "open source"?

- A) Free Software Foundation (FSF)
- B) Linux Foundation
- C) Projeto GNU
- D) Open Source Initiative (OSI)
- E) Apache Software Foundation

**6.** Ao acessar o site do banco, o navegador mostra `https://` e o cadeado. O que isso garante?

- A) Que o site é legítimo e não é uma fraude
- B) Que o computador está livre de vírus
- C) Que a navegação é anônima
- D) Que nenhum cookie será gravado
- E) Que a comunicação entre o navegador e o servidor está cifrada

**7. [lacuna]** Qual editor de texto de terminal, presente em praticamente toda distribuição, trabalha com um modo de comando e um modo de inserção? Escreva só o nome do comando: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** **(escolha duas)** A usuária `ana` está em `/home/ana/projetos`. Quais comandos listam o conteúdo de `/home/ana/docs`?

- A) `ls ../docs`
- B) `ls ./docs`
- C) `ls /docs`
- D) `ls ~ana/docs`
- E) `ls ../../docs`

**9.** O que mostra `ls -ltr` em um diretório com vários arquivos?

- A) A listagem longa, do arquivo modificado mais recentemente para o mais antigo
- B) A listagem longa, do mais antigo para o mais recente, com o mais novo no fim
- C) A listagem longa, ordenada pelo tamanho
- D) A listagem longa de todos os subdiretórios, recursivamente
- E) A listagem longa em ordem alfabética inversa

**10.** Depois de `x=10`, qual é a saída de `echo "$x"'$x'\$x`?

- A) `101010`
- B) `10$x10`
- C) `$x$x$x`
- D) `10 $x $x`
- E) `10$x$x`

**11.** No diretório atual há o arquivo `a.txt` e o diretório `backup`; `salvos` não existe. Depois de `mv a.txt backup` e, em seguida, `mv backup salvos`, onde está o arquivo?

- A) `./a.txt`
- B) `./backup/a.txt`
- C) `./salvos`, que agora é um arquivo
- D) `./salvos/a.txt`
- E) Em lugar nenhum: o segundo `mv` falha sem `-r`

**12.** Onde ficam, normalmente, os arquivos extras de documentação dos pacotes instalados, como `README` e `changelog`?

- A) `/usr/share/doc`
- B) `/var/doc`
- C) `/etc/doc`
- D) `/usr/man`
- E) `/opt/doc`

**13.** A página de manual do `tar` avisa que a documentação completa está em outro formato, com nós e links de navegação. Qual comando a abre?

- A) `man -k tar`
- B) `help tar`
- C) `info tar`
- D) `whatis tar`
- E) `apropos tar`

**14.** O usuário digita `apt update` e recebe *Permission denied*. Qual linha repete o mesmo comando com `sudo`, sem redigitá-lo?

- A) `sudo !$`
- B) `sudo -r`
- C) `sudo history`
- D) `sudo !!`
- E) `sudo $?`

**15.** Qual comando encontra, dentro de `/srv`, somente **diretórios** chamados `logs`, `Logs` ou `LOGS`?

- A) `find /srv -type f -iname logs`
- B) `find /srv -type d -name logs`
- C) `locate -d /srv logs`
- D) `ls -R /srv | grep -i logs`
- E) `find /srv -type d -iname logs`

**16. [lacuna]** Qual variável de ambiente guarda o diretório em que o usuário estava antes do último `cd`, usada pelo `cd -`? Escreva só o nome da variável, sem `$`: ______

---

## Tópico 3 — O poder da linha de comando

**17.** **(escolha duas)** Quais comandos extraem `site.tar.gz` no diretório atual?

- A) `tar -xzf site.tar.gz`
- B) `tar -czf site.tar.gz`
- C) `gzip site.tar.gz`
- D) `tar -tf site.tar.gz`
- E) `tar -xf site.tar.gz`

**18.** O usuário executa `ls /etc/hostname /nada 2>&1 > out.txt`. O que acontece?

- A) Tudo vai para `out.txt`
- B) Tudo aparece na tela e `out.txt` fica vazio
- C) `out.txt` recebe `/etc/hostname`, e a mensagem de erro sobre `/nada` aparece na tela
- D) `out.txt` recebe só a mensagem de erro
- E) O comando falha por erro de sintaxe

**19.** O que mostra `grep -v '^#' /etc/ssh/sshd_config | grep -v '^$' | wc -l`?

- A) O número de linhas que não são comentário nem vazias
- B) O número de linhas de comentário
- C) O número de linhas vazias
- D) As linhas que começam com `$`
- E) O número de palavras do arquivo

**20.** O arquivo `numeros.txt` tem as linhas `10`, `9` e `100`. Qual é a saída de `sort numeros.txt`?

- A) `9`, `10`, `100`
- B) `100`, `10`, `9`
- C) `10`, `9`, `100`
- D) `10`, `100`, `9`
- E) `9`, `100`, `10`

**21.** O arquivo `nomes.txt` tem as linhas `ana`, `bia` e `ana`, nessa ordem. Qual é a saída de `uniq nomes.txt`?

- A) `ana` e `bia`
- B) `ana`
- C) `ana`, `bia` e `ana`
- D) `bia`
- E) `2 ana` e `1 bia`

**22.** Qual comando mostra as linhas de `app.log` que contêm `erro` **ou** `falha`?

- A) `grep 'erro|falha' app.log`
- B) `grep -E 'erro|falha' app.log`
- C) `grep erro falha app.log`
- D) `grep -v 'erro|falha' app.log`
- E) `grep -c 'erro|falha' app.log`

**23.** O script `backup.sh` começa com `#!/bin/bash` e tem permissão `-rw-r--r--`. Qual comando o executa **sem** alterar a permissão?

- A) `./backup.sh`
- B) `backup.sh`
- C) `exec backup.sh`
- D) `bash backup.sh`
- E) `sudo ./backup.sh`

**24.** O script `v.sh` contém o trecho abaixo. Quais são as duas linhas mostradas por `./v.sh ; echo $?`?

```bash
#!/bin/bash
if [ -z "$1" ]; then
  echo "uso: $0 arquivo"
  exit 1
fi
echo "ok: $1"
```

- A) `ok:` e `0`
- B) `uso: ./v.sh arquivo` e `1`
- C) `uso: v.sh arquivo` e `0`
- D) `uso: $0 arquivo` e `1`
- E) `ok:` e `1`

**25. [lacuna]** Quais são os dois caracteres que abrem a primeira linha de um script para indicar o interpretador, como em `______/bin/bash`? ______

---

## Tópico 4 — O sistema operacional Linux

**26.** Um computador tem um único SSD NVMe com duas partições. Como elas aparecem em `/dev`?

- A) `/dev/sda1` e `/dev/sda2`
- B) `/dev/nvme0p1` e `/dev/nvme0p2`
- C) `/dev/hda1` e `/dev/hda2`
- D) `/dev/nvme1` e `/dev/nvme2`
- E) `/dev/nvme0n1p1` e `/dev/nvme0n1p2`

**27.** Qual arquivo de dispositivo fornece uma sequência sem fim de bytes zero, usada por exemplo com o `dd` para criar arquivos preenchidos?

- A) `/dev/null`
- B) `/dev/tty`
- C) `/dev/random`
- D) `/dev/sda`
- E) `/dev/zero`

**28.** Um programa precisa guardar arquivos temporários que devem **sobreviver a uma reinicialização**. Segundo o FHS, qual diretório usar?

- A) `/tmp`
- B) `/run`
- C) `/var/tmp`
- D) `/dev/shm`
- E) `/proc`

**29.** Na saída do `free`, qual coluna estima a memória que novos programas ainda podem usar **sem recorrer ao swap**?

- A) `total`
- B) `used`
- C) `free`
- D) `shared`
- E) `available`

**30.** O `top` mostra `load average: 0.50, 1.20, 2.00`. O que significam os três números?

- A) A carga média do sistema no último minuto, nos últimos 5 e nos últimos 15 minutos
- B) O uso de CPU de três processos
- C) A memória usada em GiB em três momentos
- D) O número de usuários conectados em cada terminal
- E) A temperatura de três núcleos

**31.** Qual comando consulta o DNS e mostra o endereço IP de um nome, **sem** testar se a máquina responde?

- A) `ping`
- B) `ip route`
- C) `ss`
- D) `traceroute`
- E) `host`

**32.** A saída de `ip addr show` tem a linha `inet 192.168.1.20/24`. Quantos endereços de host utilizáveis existem nessa rede?

- A) 24
- B) 256
- C) 255
- D) 254
- E) 65534

**33. [lacuna]** Qual comando lista os dispositivos conectados ao barramento PCI, como placas de vídeo e de rede? Escreva só o comando, sem parâmetros: ______

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** **(escolha duas)** A usuária `ana` está no grupo `sudo`. Quais comandos abrem para ela um shell de root pedindo **a senha dela**?

- A) `su -`
- B) `sudo -i`
- C) `su ana`
- D) `sudo su -`
- E) `passwd root`

**35.** O arquivo `relatorio.txt` pertence a `ana` e ao grupo `dev`, com permissão `640`. O usuário `bob`, que está no grupo `dev`, executa `echo x >> relatorio.txt`. O que acontece?

- A) O texto é acrescentado, porque `bob` está no grupo `dev`
- B) O conteúdo é substituído por `x`
- C) O comando falha com *Permission denied*, porque o grupo só tem leitura
- D) O texto é acrescentado, porque o `>>` não exige escrita
- E) O arquivo passa a pertencer a `bob`

**36.** **(escolha duas)** O diretório `/home/bob/troca` tem `drwxrwxrwt` e pertence a `bob`. A usuária `ana` criou nele o arquivo `a.txt`. Além do root, quem pode apagar `a.txt`?

- A) `ana`, a dona do arquivo
- B) `bob`, o dono do diretório
- C) `carol`, que está no grupo `bob`
- D) Qualquer usuário, porque todos têm `w` no diretório
- E) Ninguém além do root

**37.** O `ls -l /usr/bin/passwd` mostra `-rwsr-xr-x 1 root root`. Por que esse arquivo tem o `s`?

- A) Para que só o root possa executá-lo
- B) Para que o comando rode com o UID efetivo do root, e o usuário comum consiga gravar a senha nova no `/etc/shadow`
- C) Para que o arquivo não possa ser apagado
- D) Para que os arquivos criados herdem o grupo `root`
- E) Para impedir que o comando seja copiado

**38.** Qual é a notação octal completa de `-rwsr-s---`?

- A) `4750`
- B) `2750`
- C) `6750`
- D) `6770`
- E) `0750`

**39.** O administrador colocou um arquivo `.vimrc` em `/etc/skel`. Quem recebe esse arquivo?

- A) Todos os usuários, na hora, inclusive os que já existem
- B) Só o root
- C) Os usuários criados a partir de agora com pasta pessoal (`useradd -m`)
- D) Ninguém, até reiniciar o sistema
- E) Os usuários que fizerem login a partir de agora

**40. [lacuna]** Qual comando define ou troca a senha de um usuário? Escreva só o comando, sem caminho e sem parâmetros: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **C** | Cada família tem seu formato: `.deb` (Debian, Ubuntu) e `.rpm` (Red Hat, Fedora, SUSE). Ferramentas de conversão existem, mas não são o caminho normal, e o `apt`/`dpkg` não instalam `.rpm` diretamente |
| 2 | **A e D** | NGINX e Apache HTTPD são servidores web; MariaDB e PostgreSQL, bancos relacionais. Samba e NFS compartilham arquivos; IIS e SQL Server são da Microsoft |
| 3 | **A** | O NFS (*Network File System*) é o compartilhamento nativo entre sistemas Unix e Linux. O Samba é a escolha quando há clientes Windows (protocolo SMB) |
| 4 | **C** | A MIT é permissiva e compatível com a GPL; a GPLv3 é copyleft e exige que o trabalho derivado distribuído siga a GPLv3. Os avisos da MIT continuam obrigatórios |
| 5 | **D** | A OSI publica a Open Source Definition e aprova licenças. A FSF define "software livre" pelas quatro liberdades; as duas listas de licenças se sobrepõem bastante |
| 6 | **E** | O HTTPS cifra o tráfego e confirma que o certificado vale para aquele domínio, mas um site falso também pode ter certificado válido para o **próprio** domínio falso. Por isso o cadeado não garante legitimidade |
| 7 | **`vi`** | Grafia aceita: `vi` ou `vim`. O `nano` não tem modos: digita-se direto |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **A e D** | `..` sobe para `/home/ana`, então `../docs` é `/home/ana/docs`; `~ana` é a pasta pessoal de `ana`. `./docs` seria `/home/ana/projetos/docs`, e `../../docs`, `/home/docs` |
| 9 | **B** | `-l` é a listagem longa, `-t` ordena pela data de modificação (mais recente primeiro) e `-r` inverte a ordem: o mais novo vai para o fim, o que é prático para ver o último arquivo alterado. O recursivo é `-R`, maiúsculo, e o tamanho, `-S` |
| 10 | **E** | Aspas duplas expandem (`10`); aspas simples não expandem (`$x`); a barra invertida protege o `$` seguinte (`$x`). As três partes saem coladas, sem espaço |
| 11 | **D** | O primeiro `mv` move o arquivo para dentro do diretório que já existe. O segundo **renomeia** o diretório, porque `salvos` não existe; o `mv` não precisa de `-r` para diretórios |
| 12 | **A** | Cada pacote costuma ter um subdiretório em `/usr/share/doc`. As páginas de manual ficam em `/usr/share/man` |
| 13 | **C** | O `info` é o formato de documentação do projeto GNU, navegável por nós. O `help` serve só para os comandos internos do Bash |
| 14 | **D** | No Bash, `!!` é expandido para o último comando do histórico. O `!$` seria só o último **argumento** dele, e o `$?`, o código de saída |
| 15 | **E** | `-type d` limita a diretórios e `-iname` ignora maiúsculas e minúsculas. O `-name` diferencia, e o `grep` sobre o `ls -R` também pegaria arquivos |
| 16 | **`OLDPWD`** | Grafia aceita: `OLDPWD`. O `PWD` guarda o diretório atual |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **A e E** | `-x` extrai e `-z` usa o gzip. O GNU tar detecta sozinho a compressão **na leitura**, então `-xf` também extrai. O `-c` criaria (e sobrescreveria o arquivo); o `-t` só lista |
| 18 | **C** | Os redirecionamentos são lidos da esquerda para a direita. O `2>&1` liga o canal 2 ao **lugar atual** do canal 1, que ainda é a tela; só depois o `>` manda o canal 1 para o arquivo. Para juntar os dois no arquivo: `> out.txt 2>&1` (treino V3) |
| 19 | **A** | O primeiro `grep -v` tira as linhas que começam com `#`; o segundo tira as vazias (`^$`: início seguido de fim). O `wc -l` conta o que sobrou |
| 20 | **D** | Sem `-n`, o `sort` compara como **texto**, caractere por caractere: `1` vem antes de `9`, e `10` vem antes de `100`. Com `sort -n`, sairia `9`, `10`, `100` |
| 21 | **C** | O `uniq` só junta linhas iguais **vizinhas**. Como os dois `ana` não estão lado a lado, nada muda. Por isso se usa `sort nomes.txt | uniq` |
| 22 | **B** | Com `-E` (expressão regular estendida), o `|` é "ou". Sem o `-E`, o `|` é um caractere comum, e a A procuraria o texto literal `erro|falha`. Na C, `falha` vira o nome de um arquivo |
| 23 | **D** | Passado como argumento, o script só precisa ser **lido** pelo `bash`. Para rodar como `./backup.sh`, o arquivo precisa de `x`, até com `sudo`. Sem `./`, o shell procura o nome no `PATH` |
| 24 | **B** | Sem argumentos, `$1` é vazio e o `-z` é verdadeiro. O `$0` expande para o nome como foi chamado (`./v.sh`), e o `exit 1` encerra o script antes do `ok`; o `$?` mostra esse 1 |
| 25 | **`#!`** | Grafia aceita: `#!` (o *shebang*) |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **E** | NVMe: controlador (`nvme0`), *namespace* (`n1`) e partição (`p1`). SATA e SCSI usam `sd` com letra; `hd` era o antigo IDE (Exercícios da LPI 4.3) |
| 27 | **E** | O `/dev/zero` devolve zeros na leitura. O `/dev/null` descarta o que recebe e, na leitura, devolve fim de arquivo; o `/dev/random` e o `/dev/urandom` devolvem bytes aleatórios |
| 28 | **C** | O `/tmp` pode ser limpo na inicialização (muitas vezes é montado na memória); o `/var/tmp` guarda temporários que persistem. O `/run` é zerado a cada boot |
| 29 | **E** | O `available` soma a memória livre com o cache que o kernel pode liberar. O `free` mostra só o que não está em uso nenhum, e por isso costuma ser pequeno |
| 30 | **A** | São médias de carga em 1, 5 e 15 minutos. No exemplo, a carga está caindo |
| 31 | **E** | O `host` (e o `dig`) só perguntam ao servidor DNS. O `ping` também resolve o nome, mas o objetivo dele é testar a resposta da máquina |
| 32 | **D** | O `/24` deixa 8 bits para hosts: 256 endereços, menos o da rede (`.0`) e o de broadcast (`.255`): 254 |
| 33 | **`lspci`** | Grafia aceita: `lspci`. Para o barramento USB: `lsusb` |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **B e D** | O `sudo` sempre pede a senha de quem executa; no `sudo su -`, o `su` já roda como root e não pede outra senha. O `su -` sozinho pede a senha do **root** |
| 35 | **C** | `640` dá `r--` ao grupo. Acrescentar com `>>` é escrever, e exige `w` |
| 36 | **A e B** | Com o sticky bit, só apagam a entrada o dono do arquivo, o **dono do diretório** e o root (Exercícios da LPI 5.4). O `w` para todos deixa criar, mas não apagar o que é dos outros |
| 37 | **B** | O SUID faz o programa rodar com os privilégios do **dono do arquivo**. O usuário não pode alterar o `/etc/shadow` diretamente, mas o `passwd`, rodando como root, pode (exercício 5.2 E8 da LPI) |
| 38 | **C** | SUID (4) no dono e SGID (2) no grupo somam 6; `rwx` = 7, `r-x` = 5, `---` = 0. Os `s` minúsculos indicam que dono e grupo têm `x` |
| 39 | **C** | O `/etc/skel` é copiado para a pasta pessoal **no momento em que ela é criada**. Usuários que já existem não são alterados |
| 40 | **`passwd`** | Grafia aceita: `passwd` |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 18 | Ordem do `2>&1` (treino V3; Q18 do simulado 06) |
| 23 | Permissão de execução de scripts (aulas 48 a 55) |
| 24 | `$0` e `exit` em script (reincidência do `$#` e do `$0`) |
| 34 | `su` e `sudo` (Q20 do R4) |
| 36 | Sticky bit e dono do diretório (Exercícios da LPI 5.4) |
| 37 | SUID do `passwd` (exercício 5.2 E8, em branco) |
| 38 | Bits especiais pelo trio (reincidência, 6 vezes) |

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
| Data | 16/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |