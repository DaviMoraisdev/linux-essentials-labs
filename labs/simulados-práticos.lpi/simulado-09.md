# Simulado 09 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 20/11/2026; feito no **sábado 28/11** (data ajustada em 26/11). É o segundo de **nível 2**: cada questão pede dois passos, juntando dois comandos ou dois conceitos. O ponto de ajuste saiu do plano em 26/11. Nenhuma questão repete os simulados 02 a 08, os reforços ou os Exercícios da LPI.

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

**1.** Um professor vai usar um Raspberry Pi em sala. Qual afirmação descreve corretamente o sistema oficial da placa?

- A) Raspberry Pi OS, baseado no Debian, para processadores ARM
- B) Raspberry Pi OS, baseado no Fedora, para processadores x86
- C) Ubuntu Server, que é o único sistema que roda na placa
- D) Android, porque a placa não roda distribuições Linux comuns
- E) Raspberry Pi OS, um sistema proprietário sem kernel Linux

**2.** Um programa **proprietário**, distribuído a clientes, usa por ligação dinâmica uma biblioteca sob **LGPL**, sem modificá-la. O que a licença permite?

- A) Nada: qualquer uso de código LGPL obriga a abrir o programa inteiro
- B) Usar a biblioteca e manter o programa fechado; se a própria biblioteca for alterada, as alterações dela seguem a LGPL
- C) Usar a biblioteca só se o programa for gratuito
- D) Usar a biblioteca só dentro da empresa
- E) Trocar a licença da biblioteca para proprietária

**3.** Uma foto publicada sob **CC BY-SA** vai ser usada no site comercial de uma empresa. O que a licença exige?

- A) Nada, porque Creative Commons é domínio público
- B) Pagar uma taxa ao autor
- C) Usar a foto só em sites sem fins lucrativos
- D) Pedir autorização por escrito ao autor
- E) Dar crédito ao autor e, se a foto for modificada, publicar a versão modificada sob a mesma licença

**4.** **(escolha duas)** Quais destes são **ambientes de desktop** do Linux?

- A) GNOME
- B) Bash
- C) systemd
- D) KDE Plasma
- E) GRUB

**5.** Uma empresa usa e-mail e editor de documentos **pelo navegador**, pagando por usuário, sem instalar nem administrar nenhum servidor. Qual é o modelo de nuvem?

- A) IaaS
- B) PaaS
- C) SaaS
- D) *On-premise*
- E) Virtualização local

**6.** Ana quer mandar a Bruno um arquivo cifrado com GnuPG, de modo que **só Bruno** consiga abri-lo. Com qual chave Ana cifra o arquivo?

- A) Com a chave privada de Ana
- B) Com a chave pública de Ana
- C) Com a chave privada de Bruno
- D) Com a chave pública de Bruno
- E) Com uma senha enviada no mesmo e-mail

**7. [lacuna]** Qual é a sigla da licença GNU feita para **bibliotecas**, que permite o uso por programas proprietários? ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O usuário `davi` está em `/tmp` e executa, nesta ordem, `cd ~/docs`, `cd /etc`, `cd -` e `pwd`. O que o `pwd` mostra?

- A) `/tmp`
- B) `/etc`
- C) `/home/davi/docs`
- D) `/home/davi`
- E) `/etc/docs`

**9.** Um diretório contém `file1.txt`, `fileA.txt`, `file_.txt` e `file10.txt`. Qual é a saída de `ls file[!0-9].txt`?

- A) `file1.txt`
- B) `fileA.txt file_.txt`
- C) `fileA.txt file_.txt file10.txt`
- D) `file1.txt file10.txt`
- E) Nada, porque `!` não é aceito entre colchetes

**10.** Depois de `DIR="Meus Docs"`, o que acontece com `ls $DIR`, sem aspas, se existe um diretório chamado `Meus Docs`?

- A) Lista o conteúdo de `Meus Docs`
- B) Lista o diretório atual
- C) O `ls` procura dois nomes, `Meus` e `Docs`, e reclama que não existem
- D) Mostra o texto `Meus Docs`
- E) Dá erro de sintaxe na atribuição

**11.** O usuário executa `mkdir -p a/b/c` e, em seguida, `rmdir a`. O que acontece?

- A) O `rmdir` apaga `a`, `b` e `c`
- B) O `rmdir` apaga só o `c`
- C) O `rmdir` falha, porque `a` não está vazio
- D) O `rmdir` pede confirmação
- E) O `mkdir -p` falha, porque `a` não existia

**12.** O que acontece ao executar `touch relatorio.txt` quando esse arquivo **já existe** com conteúdo?

- A) Só a data de modificação (e de acesso) é atualizada; o conteúdo fica igual
- B) O arquivo é duplicado como `relatorio.txt.1`
- C) O conteúdo é apagado
- D) O `touch` dá erro, porque o arquivo existe
- E) O arquivo passa a ter permissão de execução

**13.** Qual comando mostra a ajuda do comando **interno** `cd`?

- A) `man cd`
- B) `info cd`
- C) `cd --manual`
- D) `whatis cd`
- E) `help cd`

**14.** Onde o Bash guarda o histórico de comandos do usuário entre uma sessão e outra?

- A) `/var/log/bash.log`
- B) `/etc/bash.bashrc`
- C) `~/.bash_history`
- D) `~/.profile`
- E) Em lugar nenhum: o histórico some ao fechar o terminal

**15.** **(escolha duas)** Quais comandos encontram os arquivos terminados em `.conf` em **todo** o `/etc`, inclusive nos subdiretórios?

- A) `find /etc -name "*.conf"`
- B) `ls /etc/*.conf`
- C) `find /etc -iname "*.CONF"`
- D) `grep -r .conf /etc`
- E) `find /etc -type d -name "*.conf"`

**16. [lacuna]** Qual opção do `ls` lista o conteúdo dos subdiretórios, recursivamente? Escreva só a opção, com o hífen: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando cria o pacote `apt.tar.xz`, **comprimido com xz**, com o conteúdo de `/etc/apt`?

- A) `tar -cjf apt.tar.xz /etc/apt`
- B) `tar -xJf apt.tar.xz /etc/apt`
- C) `tar -czf apt.tar.xz /etc/apt`
- D) `tar -cJf apt.tar.xz /etc/apt`
- E) `tar -cJf /etc/apt apt.tar.xz`

**18.** Um colega usa Windows e precisa abrir o pacote sem instalar nada. Qual comando cria um pacote do diretório `docs`, com todo o conteúdo, no formato mais adequado?

- A) `zip docs.zip docs`
- B) `zip -r docs.zip docs`
- C) `tar -cf docs.zip docs`
- D) `gzip -r docs`
- E) `unzip -r docs.zip docs`

**19.** O que mostra `who | cut -d' ' -f1 | sort -u | wc -l`?

- A) O número de sessões abertas
- B) O número de **usuários diferentes** conectados
- C) Os nomes dos usuários conectados
- D) O número de terminais disponíveis
- E) O número de linhas do `/etc/passwd`

**20.** **(escolha duas)** Quais comandos mostram **quantas linhas** de `app.log` contêm a palavra `erro`?

- A) `grep -c erro app.log`
- B) `grep -v erro app.log | wc -l`
- C) `wc -l app.log`
- D) `grep erro app.log | wc -l`
- E) `grep -n erro app.log`

**21.** O que acontece com o arquivo `nomes.txt` depois de `sort nomes.txt > nomes.txt`?

- A) Fica ordenado
- B) Fica igual
- C) O shell recusa o comando
- D) Fica com o conteúdo duplicado
- E) Fica **vazio**

**22.** Qual é a diferença entre as saídas de `wc -l relatorio.txt` e `wc -l < relatorio.txt`?

- A) Nenhuma
- B) A segunda dá erro
- C) A primeira conta palavras; a segunda, linhas
- D) A primeira mostra o número e o nome do arquivo; a segunda, só o número
- E) A primeira mostra só o número; a segunda, o número e o nome

**23.** O script `s.sh` está abaixo. Qual é a saída de `./s.sh ana root`?

```bash
#!/bin/bash
nome=$1
if [ "$nome" = "root" ]; then
  echo admin
else
  echo comum
fi
echo "fim $#"
```

- A) `admin` e `fim 2`
- B) `comum` e `fim 2`
- C) `comum` e `fim 3`
- D) `admin` e `fim 1`
- E) `comum`, `admin` e `fim 2`

**24.** O que mostra `ls /naoexiste && echo ok || echo falhou`?

- A) Só `ok`
- B) A mensagem de erro do `ls` e depois `falhou`
- C) `ok` e `falhou`
- D) Só a mensagem de erro
- E) Só `falhou`, sem mensagem de erro

**25. [lacuna]** Qual opção do `tail` continua mostrando as linhas novas à medida que o arquivo cresce? Escreva só a opção, com o hífen: ______

---

## Tópico 4 — O sistema operacional Linux

**26.** Qual arquivo de `/proc` mostra a **versão do kernel** em execução, junto com o compilador usado?

- A) `/proc/version`
- B) `/proc/meminfo`
- C) `/proc/cpuinfo`
- D) `/proc/kernel`
- E) `/proc/uptime`

**27.** Qual comando mostra **só** a versão (o *release*) do kernel, como `6.8.0-45-generic`?

- A) `uname -a`
- B) `uname -s`
- C) `uname -r`
- D) `uname -m`
- E) `lsmod`

**28.** Na lista de processos do `top`, um processo aparece com o estado `Z`. O que isso significa?

- A) Que está em execução
- B) Que está dormindo
- C) Que está parado por `Ctrl+Z`
- D) Que é um processo do kernel
- E) Que é um processo zumbi: terminou, mas o pai ainda não leu o código de saída

**29.** O usuário executa `ps aux | grep sshd` e vê duas linhas, embora só exista um processo do `sshd`. De onde vem a segunda?

- A) De um `sshd` duplicado por erro
- B) Do próprio `grep sshd`, que também tem `sshd` na linha de comando
- C) Do `ps`, que se lista duas vezes
- D) De uma conexão SSH aberta por outro usuário
- E) Do `systemd`

**30.** Em um servidor **Red Hat Enterprise Linux** com o `rsyslog`, onde ficam, por padrão, as mensagens gerais do sistema?

- A) `/var/log/syslog`
- B) `/etc/rsyslog.conf`
- C) `/var/log/kern.log`
- D) `/var/log/messages`
- E) `/var/log/auth.log`

**31.** **(escolha duas)** Quais endereços representam **a própria máquina** (*loopback*)?

- A) `127.0.0.1`
- B) `192.168.0.1`
- C) `0.0.0.0`
- D) `::1`
- E) `255.255.255.255`

**32.** Uma máquina alcança os computadores da rede local, mas não a internet, e o `ip route` não mostra nenhuma linha começando com `default`. O que falta?

- A) Um servidor DNS
- B) A rota padrão (o gateway)
- C) Um endereço IPv6
- D) O arquivo `/etc/hosts`
- E) Uma porta aberta no `ss`

**33. [lacuna]** Qual comando mostra os sockets de rede, como as portas em escuta, e substitui o antigo `netstat`? Escreva só o comando: ______

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Por que é recomendado usar o `sudo` em vez de trabalhar logado direto como root?

- A) Porque o `sudo` dá privilégio só ao comando que precisa e registra quem executou o quê
- B) Porque o root não consegue instalar programas
- C) Porque o `sudo` é mais rápido
- D) Porque o `sudo` não pede senha
- E) Porque o root não tem pasta pessoal

**35.** **(escolha duas)** O `/etc/passwd` tem a linha `sshd:x:110:65534::/run/sshd:/usr/sbin/nologin`. O que se conclui?

- A) É uma conta de sistema, usada por um serviço
- B) A conta não abre um shell interativo
- C) A conta é administradora
- D) A senha está guardada no `/etc/passwd`
- E) A pasta pessoal fica em `/home`

**36.** O diretório `dados` tem `drwxr--r--` e pertence ao root. O que um usuário comum consegue fazer nele?

- A) Entrar com `cd` e ler os arquivos
- B) Criar arquivos
- C) Nada, nem ver os nomes
- D) Ver os nomes dos arquivos com `ls`, mas não entrar nem abrir os arquivos
- E) Apagar arquivos

**37.** Qual comando faz `www-data` virar **dono e grupo** de `/srv/site` e de **tudo** o que está dentro?

- A) `chown www-data /srv/site`
- B) `chmod -R www-data /srv/site`
- C) `chgrp -R www-data /srv/site`
- D) `chown -r www-data:www-data /srv/site`
- E) `chown -R www-data:www-data /srv/site`

**38.** Um arquivo tem permissão `750`. Qual é a permissão depois de `chmod o+rx,g-x arquivo`?

- A) `755`
- B) `745`
- C) `754`
- D) `740`
- E) `705`

**39.** O comando `id ana` mostra `uid=1001(ana) gid=1001(ana) groups=1001(ana),27(sudo)`. O que se conclui?

- A) `ana` é o root
- B) O grupo primário de `ana` é `sudo`
- C) `ana` é uma conta de sistema
- D) `ana` pertence ao grupo `sudo` e, no Ubuntu, pode usar o `sudo`
- E) `ana` não tem grupo primário

**40. [lacuna]** Qual comando altera os dados de uma conta que **já existe**, como os grupos secundários ou o shell? Escreva só o comando: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>


## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **A** | Dois fatos juntos: o Raspberry Pi OS (antigo Raspbian) deriva do **Debian**, por isso usa `apt` e `.deb`, e a placa usa processadores **ARM**, não x86 |
| 2 | **B** | A LGPL (*Lesser* GPL) foi feita para bibliotecas: deixa programas de qualquer licença usá-las, mas mantém o copyleft na **biblioteca**. Com a GPL comum, o programa que a incorpora também teria de ser GPL |
| 3 | **E** | **BY** exige atribuição; **SA** (*ShareAlike*) exige que as derivadas sigam a mesma licença. O uso comercial só seria proibido com **NC** |
| 4 | **A e D** | GNOME e KDE Plasma são ambientes gráficos completos (painéis, gerenciador de arquivos, configurações). O Bash é um shell, o systemd é o sistema de inicialização e o GRUB é o carregador de inicialização |
| 5 | **C** | No SaaS o cliente usa o programa pronto; o provedor cuida de tudo por baixo. No IaaS, o cliente administra o sistema da máquina virtual; no PaaS, só sobe o próprio código |
| 6 | **D** | Cifra-se com a chave **pública do destinatário**; só a chave **privada** dele decifra. A chave privada do remetente serve para **assinar**, provando quem enviou |
| 7 | **`LGPL`** | Grafia aceita: `LGPL` (*GNU Lesser General Public License*) |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **C** | O `cd -` volta ao diretório **anterior**, que é `/home/davi/docs` (de onde ele saiu para ir ao `/etc`), e não ao `/tmp`. Ele só lembra o último |
| 9 | **B** | Os colchetes casam **um** caractere, e o `!` nega a lista: qualquer caractere que não seja dígito. `file10.txt` tem dois caracteres entre `file` e `.txt`, então fica de fora |
| 10 | **C** | Sem aspas, o shell divide o valor nos espaços e entrega **dois** argumentos ao `ls`. Com `ls "$DIR"`, o nome vai inteiro. Por isso se usam aspas duplas em volta de variáveis com caminhos |
| 11 | **C** | O `rmdir` só apaga diretórios **vazios**. Para apagar a árvore inteira: `rmdir -p a/b/c` (de dentro para fora) ou `rm -r a`. O `-p` do `mkdir` cria os pais que faltam |
| 12 | **A** | O `touch` cria o arquivo vazio se ele não existe e, se existe, só atualiza as datas. Quem apaga o conteúdo é o `>` (`> relatorio.txt`) |
| 13 | **E** | O `help` documenta os comandos internos do Bash (`cd`, `export`, `alias`, `jobs`...). Como o `cd` não é um programa em disco, ele normalmente não tem página de manual própria |
| 14 | **C** | O histórico da sessão fica na memória e é gravado em `~/.bash_history` ao sair. O `~/.profile` e o `/etc/bash.bashrc` são arquivos de configuração do shell |
| 15 | **A e C** | O `find` desce pelos subdiretórios; o `-iname` ignora maiúsculas, então `*.CONF` também casa `.conf`. O `ls /etc/*.conf` olha só o primeiro nível; o `grep -r` procura **dentro** dos arquivos; o `-type d` só acharia diretórios |
| 16 | **`-R`** | Grafia aceita: `-R`, maiúsculo. O `-r` minúsculo inverte a ordem |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **D** | `-c` cria, `-J` (maiúsculo) é o xz, `-f` vem seguido do nome do pacote. O `-j` é bzip2 e o `-z`, gzip: o nome `.tar.xz` não muda o compressor. Na E, pacote e origem estão trocados |
| 18 | **B** | O `.zip` abre nativamente no Windows. Para entrar nos subdiretórios, o `zip` precisa de `-r`; sem ele, guarda só a entrada do diretório, vazia. O `gzip -r` comprime arquivo por arquivo, sem empacotar |
| 19 | **B** | O `cut` pega o primeiro campo (o nome), o `sort -u` deixa cada nome uma vez só, e o `wc -l` conta. Sem o `sort -u`, contaria as sessões, e o mesmo usuário pode ter várias |
| 20 | **A e D** | O `grep -c` conta as linhas que casam; o `wc -l` conta as linhas que o `grep` entregou: são duas formas do mesmo número. O `-v` contaria as que **não** têm `erro`; o `-n` só numera as linhas |
| 21 | **E** | O shell prepara os redirecionamentos **antes** de rodar o comando: o `>` zera o `nomes.txt`, e o `sort` lê um arquivo já vazio. O jeito certo é gravar em outro arquivo ou usar `sort -o nomes.txt nomes.txt` |
| 22 | **D** | Com `<`, quem abre o arquivo é o **shell**, e o `wc` lê pela entrada padrão, sem saber o nome. Útil em scripts, quando se quer só o número |
| 23 | **B** | O `$1` é o **primeiro** argumento, `ana`, então o teste é falso e sai `comum`. O `root` é o `$2`, que o script não usa. O `$#` vale 2 |
| 24 | **B** | O `&&` só roda se o anterior der certo, e o `||` só roda se o anterior falhar. O `ls` falha (e mostra o erro), o `echo ok` é pulado, e o `echo falhou` roda |
| 25 | **`-f`** | Grafia aceita: `-f` (*follow*). Muito usada em logs: `tail -f /var/log/syslog` |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **A** | O `/proc/version` traz a versão e os dados da compilação. O mesmo número aparece em `uname -r` |
| 27 | **C** | `-r` é o *release*. O `-s` mostra o nome do kernel (`Linux`), o `-m`, a arquitetura (`x86_64`), e o `-a`, tudo junto (bloco curto de 06/11) |
| 28 | **E** | Os estados mais comuns são `R` (executando), `S` (dormindo), `T` (parado) e `Z` (zumbi). O zumbi não usa CPU nem memória; só ocupa uma entrada na tabela de processos |
| 29 | **B** | O `grep` roda ao mesmo tempo que o `ps` e aparece na lista com `sshd` nos argumentos. Por isso existe o `pgrep sshd`, que não se inclui |
| 30 | **D** | Depende da família: Red Hat e derivadas usam `/var/log/messages`; Debian e Ubuntu, `/var/log/syslog`. O `/etc/rsyslog.conf` é a configuração, não o log |
| 31 | **A e D** | `127.0.0.1` no IPv4 e `::1` no IPv6. O `0.0.0.0`, num serviço em escuta, quer dizer "todas as interfaces"; o `255.255.255.255` é broadcast |
| 32 | **B** | Sem a rota `default`, a máquina não sabe para onde mandar o que não é da rede local. O DNS seria o problema se o IP de fora respondesse e o nome não (Q30 do simulado 08) |
| 33 | **`ss`** | Grafia aceita: `ss`. `ss -tln` mostra as portas TCP em escuta |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **A** | Com o `sudo`, o usuário trabalha sem privilégio e só eleva o comando necessário, e cada uso fica registrado em log com o nome de quem executou. Como root, qualquer erro tem efeito no sistema inteiro |
| 35 | **A e B** | O UID 110, abaixo de 1000, e o shell `nologin` indicam conta de serviço sem login interativo. O `x` indica que o hash está no `/etc/shadow`; administrador é só o UID 0 |
| 36 | **D** | É o caso contrário do `--x`: o `r` deixa **listar os nomes**, mas sem `x` não se atravessa o diretório, então não dá para `cd` nem abrir o que está dentro |
| 37 | **E** | `dono:grupo` muda os dois, e o `-R` (maiúsculo) desce pelo conteúdo. O `-r` minúsculo não é a opção recursiva do `chown`; o `chgrp` só mudaria o grupo |
| 38 | **B** | Trio a trio: o dono continua `rwx` (7); o grupo perde o `x`: `r--` (4); os outros ganham `r-x` (5). Resultado: `745` |
| 39 | **D** | O `gid=` mostra o grupo **primário** (`ana`); o `groups=` lista todos, e o `sudo` aparece como grupo secundário. No Ubuntu, quem está no grupo `sudo` pode usar o comando |
| 40 | **`usermod`** | Grafia aceita: `usermod`. Com `-aG grupo`, acrescenta um grupo secundário sem tirar os outros |

## Questões que retestam erros

| Q | Erro de origem |
|---|---|
| 2 | GPL, LGPL e AGPL (Q1 do simulado 04; Q2 do simulado 08) |
| 8 | `cd -` e o diretório anterior (treino V1) |
| 10 | Aspas em variáveis com espaço |
| 13 | `help` e comandos internos |
| 21 | Ordem dos redirecionamentos: o shell prepara antes do comando (reincidência) |
| 23 | `$1` e `$#` (reincidência, 3 vezes) |
| 24 | Código de saída e `&&` / `||` (Q24 do simulado 07) |
| 27 | `uname -r` (bloco curto de 06/11) |
| 32 | Gateway e rota padrão (Q32 do simulado 08) |
| 36 | `r` sem `x` em diretório (reincidência, 3 vezes, pelo lado contrário) |
| 38 | Forma do `chmod` simbólico com vírgula e conversão octal |
| 39 | `id` e grupos primário e secundário |

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
| Data | 28/11/2026 |
| Tempo gasto | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |