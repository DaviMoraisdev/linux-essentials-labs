# Simulado 08 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 19/11/2026 para a **sexta 20/11**. É o **nível 2** do padrão novo: cada questão pede **dois passos**, juntando dois comandos ou dois conceitos (um `cd` com `..` duas vezes, um pipeline de quatro comandos, uma rede `/24` com gateway, um diretório com SGID e um usuário de outro grupo). Conta para o ponto de ajuste de 22/11. Nenhuma questão repete os simulados 02 a 07, os reforços ou os Exercícios da LPI.

Cinco alternativas por questão, **cinco questões de escolher duas** e cinco lacunas. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. Reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **28 acertos firmes** ou mais |

Faça **antes de qualquer outra tarefa do dia**. Anote as respostas em papel antes de abrir o gabarito e **marque cada chute**, mesmo acertando. Nas questões de dois passos, escreva o resultado do primeiro passo na margem antes de seguir.

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

**1.** Um usuário quer sempre as versões mais novas dos programas, sem esperar uma versão maior da distribuição, e aceita mais risco de algo quebrar. Qual modelo de lançamento atende, e qual distribuição o segue?

- A) Versão LTS; Ubuntu LTS
- B) *Rolling release*; Arch Linux
- C) Versão estável; Debian *stable*
- D) *Rolling release*; Red Hat Enterprise Linux
- E) Versão fixa; Arch Linux

**2.** Uma empresa usa internamente um programa sob **GPLv2**, modifica o código e **nunca distribui** a versão alterada para fora. O que a GPLv2 exige dela?

- A) Publicar o código modificado na internet
- B) Enviar as alterações ao autor original
- C) Pagar uma taxa de uso comercial
- D) Trocar a licença para a MIT
- E) Nada quanto ao código: a obrigação de oferecer o fonte nasce na distribuição

**3.** Uma empresa vende suporte, treinamento e consultoria para um programa 100% open source sob GPL. Qual afirmação é correta?

- A) A GPL proíbe qualquer cobrança relacionada ao programa
- B) A empresa precisa comprar uma licença comercial da FSF
- C) Só é permitido cobrar pelo código-fonte
- D) É permitido: a GPL não proíbe cobrar, e esse é um modelo de negócio de serviços
- E) Só o autor original pode vender serviços

**4.** **(escolha duas)** Quais comandos instalam um pacote **resolvendo as dependências automaticamente**?

- A) `dpkg -i pacote.deb`
- B) `apt install pacote`
- C) `rpm -i pacote.rpm`
- D) `tar -xf pacote.tar`
- E) `dnf install pacote`

**5.** Um desenvolvedor quer testar o mesmo programa em ambientes Ubuntu e Fedora no notebook, subindo e descartando cada um em segundos. Não precisa de outro kernel. O que é mais indicado?

- A) Contêineres
- B) Máquinas virtuais com hipervisor
- C) *Dual boot*
- D) Emulação de outra arquitetura
- E) Instalar as duas distribuições em discos separados

**6.** Qual configuração do navegador mais reduz o **rastreamento entre sites** por anunciantes?

- A) Usar sempre sites com HTTPS
- B) Trocar a senha de e-mail com frequência
- C) Limpar o histórico de downloads
- D) Bloquear os cookies de terceiros
- E) Aumentar o tamanho do cache

**7. [lacuna]** Qual é a extensão dos pacotes da família Red Hat, como Fedora e RHEL? Escreva só a extensão, sem o ponto: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O usuário está em `/var/log` e executa `cd ../lib/../tmp` e depois `pwd`. O que aparece?

- A) `/var/log/tmp`
- B) `/var/lib/tmp`
- C) `/tmp`
- D) Um erro, porque não se pode usar `..` duas vezes
- E) `/var/tmp`

**9.** O usuário executa `NOME=ana` (sem `export`) e, em seguida, `bash -c 'echo $NOME'`. O que aparece?

- A) `ana`
- B) `$NOME`
- C) Um erro de variável não definida
- D) Uma linha vazia
- E) `NOME`

**10.** Qual é a saída de `echo 'Usuário: $(whoami)'`?

- A) `Usuário: davi`
- B) `Usuário: $(whoami)`
- C) `Usuário: whoami`
- D) `Usuário:`
- E) Um erro de sintaxe

**11.** O diretório `proj` contém `a.txt`, `b.txt` e `.env`. Depois de `rm proj/*`, o que sobra dentro de `proj`?

- A) Nada
- B) `.env`
- C) `a.txt` e `b.txt`
- D) `a.txt`, `b.txt` e `.env`
- E) O próprio diretório é apagado

**12.** No diretório atual há três arquivos `.txt`, e **não existe** `backup`. O que acontece com `cp *.txt backup`?

- A) O `cp` cria o diretório `backup` e copia os três arquivos
- B) Os três arquivos são juntados em um arquivo chamado `backup`
- C) Só o primeiro `.txt` é copiado, com o nome `backup`
- D) O `cp` responde que o destino `backup` não é um diretório, e nada é copiado
- E) O `cp` pede confirmação para criar o diretório

**13.** O usuário cria o arquivo `relatorio-final.odt` e, logo em seguida, executa `locate relatorio-final.odt`, que não mostra nada. Por quê?

- A) O `locate` só procura em `/usr`
- B) O banco de dados do `locate` ainda não foi atualizado pelo `updatedb`
- C) O `locate` não aceita nomes com hífen
- D) O arquivo é oculto
- E) O `locate` exige o caminho completo

**14.** Depois de `alias ll='ls -l'`, o que o comando `type ll` informa?

- A) Que `ll` é um alias para `ls -l`
- B) Que `ll` é um programa em `/usr/bin`
- C) Que `ll` não foi encontrado
- D) Que `ll` é um comando interno do shell
- E) O conteúdo do diretório em formato longo

**15.** **(escolha duas)** Quais comandos mostram o **valor** da variável `HOME`?

- A) `echo $HOME`
- B) `echo HOME`
- C) `printenv HOME`
- D) `env $HOME`
- E) `set HOME`

**16. [lacuna]** Qual opção do `rm` apaga um diretório com todo o seu conteúdo? Escreva só a opção, com o hífen e uma letra: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando **lista** o conteúdo de `backup.tar.bz2`, sem extrair?

- A) `tar -tzf backup.tar.bz2`
- B) `tar -xjf backup.tar.bz2`
- C) `tar -tJf backup.tar.bz2`
- D) `tar -cjf backup.tar.bz2`
- E) `tar -tjf backup.tar.bz2`

**18.** O arquivo `acessos.log` tem um endereço IP por linha. Qual comando mostra os **três IPs que mais aparecem**, com a contagem?

- A) `uniq -c acessos.log | sort -nr | head -3`
- B) `sort acessos.log | uniq -c | sort -nr | head -3`
- C) `sort acessos.log | uniq | head -3`
- D) `sort -nr acessos.log | uniq -c | head -3`
- E) `cat acessos.log | uniq -c | head -3`

**19.** Qual comando procura `PermitRootLogin` em **todos os arquivos** dentro de `/etc/ssh`, inclusive nos subdiretórios?

- A) `grep -v PermitRootLogin /etc/ssh`
- B) `grep -c PermitRootLogin /etc/ssh`
- C) `find /etc/ssh -name PermitRootLogin`
- D) `grep -i PermitRootLogin /etc/ssh`
- E) `grep -r PermitRootLogin /etc/ssh`

**20.** Qual comando **acrescenta** a saída e as mensagens de erro de `./backup.sh` ao final de `log.txt`, sem apagar o que já está nele?

- A) `./backup.sh 2>&1 >> log.txt`
- B) `./backup.sh > log.txt 2>&1`
- C) `./backup.sh >> log.txt 2>&1`
- D) `./backup.sh &> log.txt`
- E) `./backup.sh >> log.txt 2> log.txt`

**21.** **(escolha duas)** Quais comandos listam os **shells** usados no `/etc/passwd`, cada um uma única vez?

- A) `cut -d: -f7 /etc/passwd | sort -u`
- B) `cut -d: -f6 /etc/passwd | sort -u`
- C) `cut -f7 /etc/passwd | sort -u`
- D) `cut -d: -f7 /etc/passwd | uniq | sort`
- E) `cut -d: -f7 /etc/passwd | sort | uniq`

**22.** Qual comando mostra **só a quinta linha** de `dados.txt`?

- A) `head -n 5 dados.txt`
- B) `tail -n 5 dados.txt | head -n 1`
- C) `head -n 5 dados.txt | tail -n 1`
- D) `tail -n 1 dados.txt | head -n 5`
- E) `head -n 1 dados.txt | tail -n 5`

**23.** O script `soma.sh` está abaixo. Qual é a saída de `./soma.sh 2 3 5`?

```bash
#!/bin/bash
total=0
for n in "$@"; do
  total=$((total + n))
done
echo "$# números, soma $total"
```

- A) `3 números, soma 10`
- B) `4 números, soma 10`
- C) `3 números, soma 235`
- D) `$# números, soma $total`
- E) `3 números, soma 0`

**24.** O script `t.sh` está abaixo. Qual é a saída de `./t.sh /etc/passwd`?

```bash
#!/bin/bash
if [ -d "$1" ]; then
  echo dir
elif [ -f "$1" ]; then
  echo arq
else
  echo nada
fi
```

- A) `dir`
- B) `nada`
- C) `dir` e `arq`
- D) `arq`
- E) `/etc/passwd`

**25. [lacuna]** Qual opção do `sort` ordena os números pelo **valor**, e não como texto? Escreva só a opção, com o hífen: ______

---

## Tópico 4 — O sistema operacional Linux

**26.** O processo de PID 1234 está travado. Onde ficam as informações dele, e qual sinal **pede** o encerramento normal, deixando o programa fechar arquivos antes de sair?

- A) `/proc/1234`, com `SIGTERM` (15)
- B) `/sys/1234`, com `SIGKILL` (9)
- C) `/proc/1234`, com `SIGKILL` (9)
- D) `/dev/1234`, com `SIGTERM` (15)
- E) `/var/run/1234`, com `SIGINT` (2)

**27.** Qual comando envia `SIGKILL` a **todos** os processos chamados `firefox`?

- A) `kill -9 firefox`
- B) `killall -9 firefox`
- C) `kill -15 firefox`
- D) `killall firefox`
- E) `top -9 firefox`

**28.** O usuário executou `sleep 300 &` e `jobs` mostrou `[1]+ Running sleep 300 &`. Qual sequência traz o trabalho para o primeiro plano e o interrompe?

- A) `bg %1` e depois `Ctrl+Z`
- B) `fg %1` e depois `Ctrl+Z`
- C) `fg %1` e depois `Ctrl+C`
- D) `jobs -9` e depois `Enter`
- E) `kill %0`

**29.** O `free -h` mostra o swap com `used 1.8Gi` de 2.0Gi e a coluna `available` da memória com só 150Mi. O que isso indica?

- A) Que o disco está cheio
- B) Que o sistema está sem memória RAM suficiente e recorre ao swap, o que deixa tudo mais lento
- C) Que o swap está desativado
- D) Que o kernel está com defeito
- E) Que o cache precisa ser apagado à mão

**30.** O `ping 8.8.8.8` funciona, mas `ping google.com` responde *Temporary failure in name resolution*. Onde está o problema mais provável, e o que conferir primeiro?

- A) Na resolução de nomes; conferir os servidores DNS em `/etc/resolv.conf`
- B) No roteador; reiniciar o roteador
- C) No cabo de rede; trocar o cabo
- D) No firewall do Google; esperar
- E) Na placa de rede; rodar `ip link`

**31.** Qual comando mostra se algum serviço está **escutando** na porta TCP 22?

- A) `ss -uln | grep ':22'`
- B) `ip addr | grep 22`
- C) `ss -tln | grep ':22'`
- D) `ping -p 22 localhost`
- E) `netstat -r | grep 22`

**32.** **(escolha duas)** Uma máquina tem o IP `192.168.0.25/24` e o gateway `192.168.0.1`. Para quais destinos os pacotes **precisam passar pelo gateway**?

- A) `192.168.0.200`
- B) `8.8.8.8`
- C) `127.0.0.1`
- D) `192.168.0.50`
- E) `10.0.0.5`

**33. [lacuna]** Escreva o **caminho completo** do arquivo que lista os servidores DNS consultados pelo sistema, nas linhas `nameserver`: ______

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** O diretório `/srv/time` tem `drwxrwx---`, pertence ao root e ao grupo `dev`, **sem** sticky bit. A usuária `ana` (grupo `dev`) criou nele `ana.txt`, com `-rw-r--r--`. O usuário `bob`, também do grupo `dev`, consegue apagar `ana.txt`?

- A) Não, porque o arquivo é de `ana`
- B) Não, porque o arquivo não tem `w` para o grupo
- C) Sim, porque tem `w` no diretório e não há sticky bit
- D) Só se usar `sudo`
- E) Só se `ana` estiver desconectada

**35.** O arquivo `rel.txt` está como `-rw-r--r-- ana ana`. Qual dupla de comandos faz os membros do grupo `dev` poderem **editá-lo**, sem trocar o dono?

- A) `chown dev rel.txt` e `chmod g+w rel.txt`
- B) `chmod g+w rel.txt` apenas
- C) `chgrp dev rel.txt` e `chmod o+w rel.txt`
- D) `usermod -aG dev ana` e `chmod o+w rel.txt`
- E) `chgrp dev rel.txt` e `chmod g+w rel.txt`

**36.** O diretório `/srv/proj` pertence ao grupo `dev` e tem permissão `2775`. A usuária `ana`, cujo grupo primário é `ana`, cria nele `nota.txt`. Qual é o grupo de `nota.txt`?

- A) `dev`
- B) `root`
- C) `ana`
- D) `users`
- E) O grupo do processo do shell, `ana`, porque o SGID só vale para executáveis

**37.** Qual é a diferença entre `su` e `su -`?

- A) Nenhuma
- B) O `su -` abre um shell de login, com o ambiente do usuário de destino (`HOME`, `PATH`, diretório inicial)
- C) O `su -` não pede senha
- D) O `su` só funciona para o root
- E) O `su -` usa a senha do usuário atual

**38.** **(escolha duas)** O arquivo `script.sh` está com `-rw-r--r--`. Quais comandos o deixam com `-rwxr--r--`?

- A) `chmod u+x script.sh`
- B) `chmod +x script.sh`
- C) `chmod 755 script.sh`
- D) `chmod 744 script.sh`
- E) `chmod a+x script.sh`

**39.** Qual comando mostra **quem está logado agora** e **o que cada um está executando**, com o tempo ocioso?

- A) `w`
- B) `last`
- C) `who`
- D) `id`
- E) `whoami`

**40. [lacuna]** Qual comando de baixo nível cria uma conta de usuário, recebendo opções como `-m` e `-G`? Escreva só o comando, sem caminho e sem parâmetros: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **B** | No *rolling release* os pacotes são atualizados continuamente, sem versões maiores; o Arch Linux é o exemplo clássico (o openSUSE Tumbleweed também). LTS e as enterprise priorizam estabilidade |
| 2 | **E** | As obrigações da GPL valem ao **distribuir**. Uso e modificação internos não exigem publicar nada. É a diferença para a AGPL, que também alcança quem oferece o programa como serviço em rede (Q1 do simulado 04) |
| 3 | **D** | Software livre não é sinônimo de grátis. Vender suporte e serviços em volta de um programa open source é um modelo comum (é o da Red Hat, por exemplo) |
| 4 | **B e E** | `apt` e `dnf` são de alto nível: baixam o pacote e as dependências do repositório. `dpkg` e `rpm` são de baixo nível: instalam só o arquivo dado e reclamam se faltar dependência |
| 5 | **A** | Contêineres sobem em segundos porque **compartilham o kernel** do hospedeiro e só isolam a aplicação e as bibliotecas. A máquina virtual seria a escolha se precisasse de outro kernel, como um Windows (reincidência: contêiner e máquina virtual) |
| 6 | **D** | Os cookies de terceiros, gravados por domínios diferentes do site visitado, são o mecanismo principal de rastreamento entre sites. O HTTPS cifra a conexão, mas não impede o rastreamento |
| 7 | **`rpm`** | Grafia aceita: `rpm`. A família Debian usa `deb` |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **E** | Passo a passo: `..` sobe para `/var`; `lib` entra em `/var/lib`; `..` volta para `/var`; `tmp` entra em `/var/tmp` |
| 9 | **D** | O `bash -c` abre um **processo filho**. Sem `export`, a variável fica só no shell atual, e o filho não a conhece. Com `export NOME=ana`, sairia `ana` (lacuna da série 11). As aspas simples só impedem o shell **atual** de expandir; quem expande é o filho |
| 10 | **B** | Dentro de aspas simples, nada é expandido, nem variável nem substituição de comando. Com aspas duplas, `$(whoami)` seria trocado pelo nome do usuário |
| 11 | **B** | O `*` não casa nomes que começam com ponto, então o `.env` escapa. O diretório continua existindo, porque o `rm` sem `-r` só apaga arquivos |
| 12 | **D** | Com mais de uma origem, o último argumento precisa ser um diretório que já existe. O `cp` não cria diretórios; antes seria preciso `mkdir backup` |
| 13 | **B** | O `locate` não varre o disco: consulta um banco gerado periodicamente pelo `updatedb`. Para achar na hora, use `find` ou rode `sudo updatedb` antes |
| 14 | **A** | O `type` diz como o shell interpreta o nome: alias, comando interno (*builtin*), função ou programa em disco. O `which` não enxergaria o alias |
| 15 | **A e C** | `echo $HOME` expande a variável; `printenv HOME` recebe o **nome**, sem `$`. `env $HOME` tentaria executar `/home/davi` como comando, e `set HOME` mudaria os parâmetros posicionais |
| 16 | **`-r`** | Grafia aceita: `-r` (também `-R`). O `rmdir` só apaga diretórios vazios |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **E** | Dois detalhes: `-t` lista (`-x` extrairia, `-c` criaria) e `-j` é o bzip2 (`-z` é gzip; `-J`, xz) |
| 18 | **B** | Primeiro `sort`, para deixar os iguais vizinhos; depois `uniq -c`, que conta cada grupo; depois `sort -nr`, que ordena pela contagem, do maior para o menor; por fim `head -3`. Sem o primeiro `sort`, o `uniq` conta errado (Q21 do simulado 07) |
| 19 | **E** | O `-r` faz o `grep` descer pelos diretórios e mostra o nome de cada arquivo junto da linha. Sem `-r`, o `grep` reclama que `/etc/ssh` é um diretório. O `find -name` procura nomes de arquivo, não conteúdo |
| 20 | **C** | `>>` acrescenta o canal 1, e o `2>&1` **depois** dele manda o canal 2 para o mesmo lugar. A A inverte a ordem (o erro vai para a tela); a B e a D sobrescrevem; a E abre o arquivo duas vezes, e as saídas se atropelam |
| 21 | **A e E** | O shell é o **sétimo** campo, separado por `:`. O `sort -u` e o par `sort | uniq` tiram as repetições; o `uniq` antes do `sort` deixa repetidos os que não estavam vizinhos. O sexto campo é a pasta pessoal |
| 22 | **C** | O `head -n 5` entrega as linhas 1 a 5, e o `tail -n 1` pega a última delas: a quinta. A B pega a quinta **a contar do fim** |
| 23 | **A** | O `"$@"` percorre os três argumentos, e o `$((...))` faz a conta: 2 + 3 + 5 = 10. O `$#` conta só os argumentos, sem o `$0`: 3 |
| 24 | **D** | O `-d` é falso (o `/etc/passwd` não é diretório) e o `-f` é verdadeiro (é um arquivo comum). O `elif` só é testado porque o primeiro teste falhou |
| 25 | **`-n`** | Grafia aceita: `-n`. Com `-r` junto (`-nr`), do maior para o menor |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **A** | Cada processo tem um diretório em `/proc` com o número do PID. O `SIGTERM` é o pedido educado, padrão do `kill`; o `SIGKILL` encerra à força, sem dar chance de o programa se organizar |
| 27 | **B** | O `killall` (e o `pkill`) trabalham pelo **nome**; o `kill` precisa do **PID**. Sem `-9`, o `killall` mandaria o `SIGTERM`, o padrão |
| 28 | **C** | O `fg` traz para o primeiro plano, e o `Ctrl+C` envia o `SIGINT`, que interrompe. O `Ctrl+Z` só **suspende**; o `bg` mantém em segundo plano |
| 29 | **B** | Swap quase cheio e `available` baixo significam pressão de memória: o kernel está tirando páginas da RAM para o disco. A solução é fechar programas ou ter mais RAM |
| 30 | **A** | Se o IP responde, a conexão e a rota estão boas. O que falha é a tradução do nome em IP: o DNS. O `/etc/resolv.conf` diz quais servidores o sistema consulta |
| 31 | **C** | `-t` TCP, `-l` em escuta, `-n` números em vez de nomes; o `grep` filtra a porta. O `-u` seria UDP, e o `netstat -r` mostra a tabela de rotas |
| 32 | **B e E** | Com `/24`, a rede local vai de `192.168.0.0` a `192.168.0.255`, e esses destinos são alcançados direto. `8.8.8.8` e `10.0.0.5` estão fora dela e saem pelo gateway. O `127.0.0.1` é a própria máquina |
| 33 | **`/etc/resolv.conf`** | Grafia aceita: `/etc/resolv.conf` (sem o "e" de *resolve*) |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **C** | Apagar é mexer na **lista de nomes do diretório**, e quem decide é o `w` do diretório, não a permissão do arquivo. Por isso existe o sticky bit: com ele (`drwxrwx--T`), só o dono do arquivo, o dono do diretório e o root apagariam |
| 35 | **E** | Dois passos: o `chgrp` põe o arquivo no grupo `dev`, e o `chmod g+w` dá escrita ao grupo. O `chown dev` trocaria o **dono**; só o `chmod g+w` daria escrita ao grupo `ana`; o `o+w` abriria para todos |
| 36 | **A** | O `2` é o SGID. Em **diretório**, ele faz os arquivos criados lá dentro herdarem o grupo do diretório. É assim que se monta pasta compartilhada de equipe (reincidência dos bits especiais, agora pela função) |
| 37 | **B** | Com o `-` (ou `-l`), o `su` simula um login completo. Sem ele, troca de usuário mas mantém boa parte do ambiente e o diretório atual |
| 38 | **A e D** | Só o dono ganha `x`: `u+x` ou `744`. O `+x` sem letra e o `a+x` dão `x` a todos, e o `755` também |
| 39 | **A** | O `w` mostra as sessões, o comando em execução (coluna `WHAT`) e o resumo do sistema. O `who` mostra só quem está logado; o `last`, o histórico (aulas 59 a 63) |
| 40 | **`useradd`** | Grafia aceita: `useradd`. O `adduser` é o assistente interativo do Debian e do Ubuntu |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 2 | GPL e AGPL (Q1 do simulado 04) |
| 5 | Contêiner e máquina virtual (reincidência, 3 vezes; agora pelo lado do contêiner) |
| 9 | `export` e processo filho |
| 18 | `uniq` sem `sort` (Q21 do simulado 07) |
| 20 | Ordem do `2>&1` (reincidência, 3 vezes) |
| 23 | `$#` sem o `$0` (reincidência, 3 vezes) |
| 27 | `kill` pelo PID e `killall` pelo nome |
| 34 | Apagar depende do `w` do diretório (sticky bit, LPI 5.4) |
| 35 | Comandos de arquivo contra comandos de conta (reincidência, 3 vezes) |
| 36 | SGID, agora pela função em diretório (reincidência, 6 vezes) |
| 38 | Forma do `chmod` simbólico (aulas 59 a 63) |

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
| Data | 20/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |