# Simulado 05 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 04/11/2026 para a **segunda 09/11**, na operação prática. Cinco alternativas por questão, como no exame e nos reforços R3 e R4; quatro questões de escolher duas; cinco lacunas com a instrução que a prova usa. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

Quinze questões retestam reincidências registradas até 04/11 (tabela no fim do gabarito), sempre por um ângulo diferente do da questão em que você errou.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. **Use pelo menos 45** e reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **24 acertos firmes** ou mais |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando.

Nas questões **[lacuna]**, escreva só o que foi pedido: sem caminho (salvo se o enunciado pedir), sem `sudo`, sem opções, sem explicação ao lado. "Licença Copyleft" ou "-x - extract" valem zero na prova.

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

**1.** Uma empresa modifica um programa licenciado sob a GPLv3 e passa a usá-lo **só nos próprios servidores internos**, sem entregar cópia a ninguém. O que a GPLv3 exige dela?

- A) Publicar o código-fonte modificado na internet
- B) Nada: as obrigações da GPL surgem quando o programa é distribuído
- C) Pagar uma taxa à Free Software Foundation
- D) Relicenciar a versão modificada sob a licença MIT
- E) Avisar os autores originais sobre as modificações

**2. (escolha duas)** Quais destes são ambientes de desktop?

- A) GNOME
- B) Wayland
- C) systemd
- D) KDE Plasma
- E) Apache

**3.** Em qual modelo de nuvem o provedor administra o sistema operacional e o ambiente de execução, e o cliente só envia o código da aplicação?

- A) IaaS
- B) SaaS
- C) PaaS
- D) LAN
- E) VPN

**4.** Qual serviço open source permite compartilhar arquivos e impressoras entre um servidor Linux e clientes Windows?

- A) NFS
- B) Apache
- C) Postfix
- D) OpenSSH
- E) Samba

**5.** O que o modo de navegação privada (anônima) de um navegador garante?

- A) Esconde o seu endereço IP do provedor de internet
- B) Criptografa todo o tráfego entre o computador e os sites
- C) Impede a instalação de vírus
- D) Não guarda o histórico, os cookies nem os dados de formulário depois que a janela é fechada
- E) Torna você anônimo para os sites visitados

**6.** Em uma distribuição atual da família Red Hat, qual comando instala um pacote **resolvendo e baixando as dependências**?

- A) `dpkg -i pacote.rpm`
- B) `dnf install pacote`
- C) `rpm -i pacote.rpm`
- D) `apt install pacote`
- E) `zypper install pacote`

**7. [lacuna]** Qual é o sistema operacional do Google para smartphones que usa o kernel Linux? Escreva só o nome, uma palavra: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O usuário está em `/home/davi/docs` e executa `cd ../../..`. O que o `pwd` mostra em seguida?

- A) `/home`
- B) `/home/davi`
- C) `/`
- D) Nada: o comando falha
- E) `/root`

**9.** O comando `type cd` responde `cd is a shell builtin`. Qual comando mostra a ajuda do `cd`?

- A) `man cd`
- B) `whatis cd`
- C) `which cd`
- D) `locate cd`
- E) `help cd`

**10.** A seção **8** do manual é dedicada a:

- A) Comandos do usuário
- B) Comandos de administração do sistema
- C) Formatos de arquivo
- D) Chamadas de sistema
- E) Jogos

**11.** O diretório `a` não existe. Qual linha cria `a/b/c` e, dentro dele, o arquivo vazio `x.txt`?

- A) `mkdir a/b/c ; touch a/b/c/x.txt`
- B) `touch -p a/b/c/x.txt`
- C) `mkdir -r a/b/c && touch a/b/c/x.txt`
- D) `mkdir -p a/b/c && touch a/b/c/x.txt`
- E) `mkdir a b c && touch x.txt`

**12.** Um diretório contém `log1`, `log2`, `log10` e `logA`. Qual é a saída de `ls log?`?

- A) `log1 log2 logA`
- B) `log1 log2`
- C) `log1 log2 log10 logA`
- D) `log10`
- E) `logA`

**13. (escolha duas)** Quais comandos **copiam** o diretório `projeto`, com tudo dentro, para `/tmp`?

- A) `cp projeto /tmp`
- B) `cp -r projeto /tmp`
- C) `mv projeto /tmp`
- D) `cp -i projeto /tmp`
- E) `cp -R projeto /tmp`

**14.** Qual comando lista também os arquivos ocultos, mas **sem** as entradas `.` e `..`?

- A) `ls -a`
- B) `ls -l`
- C) `ls -A`
- D) `ls -d`
- E) `ls -h`

**15.** O link simbólico `atalho` aponta para `relatorio.txt`. O arquivo original é renomeado para `rel.txt`. O que acontece com `cat atalho`?

- A) Mostra o conteúdo do arquivo normalmente
- B) O `cat` segue o link até `rel.txt` automaticamente
- C) O link é renomeado junto com o arquivo
- D) Mostra o nome `rel.txt`
- E) Dá erro: o link guarda o nome `relatorio.txt`, que não existe mais

**16. [lacuna]** Qual comando procura arquivos pelo nome consultando um banco de dados gerado previamente, sem percorrer o disco na hora da busca? Escreva só o comando, sem caminho e sem parâmetros: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando cria o arquivo `site.tar.bz2` com o conteúdo do diretório `site`?

- A) `tar -czf site.tar.bz2 site`
- B) `tar -xjf site.tar.bz2 site`
- C) `tar -cfj site.tar.bz2 site`
- D) `tar -cjf site.tar.bz2 site`
- E) `tar -tjf site.tar.bz2`

**18. [lacuna]** Qual comando descompacta um arquivo `.bz2`? Escreva só o comando, sem caminho e sem parâmetros: ______

**19.** Qual é o conteúdo de `a.txt` depois da sequência abaixo?

```bash
echo um > a.txt
echo dois >> a.txt
echo tres > a.txt
```

- A) `tres`
- B) `um`, `dois` e `tres`, uma por linha
- C) `dois` e `tres`
- D) `um` e `tres`
- E) Nada: o arquivo fica vazio

**20. (escolha duas)** Quais comandos descartam **toda** a saída de `comando`, a normal e a de erro?

- A) `comando 2>&1 > /dev/null`
- B) `comando 2> /dev/null`
- C) `comando > /dev/null 2>&1`
- D) `comando | /dev/null`
- E) `comando &> /dev/null`

**21.** Qual é a saída do trecho abaixo?

```bash
wc -l << FIM
alfa
beta
gama
FIM
```

- A) `4`
- B) `3`
- C) `0`
- D) Um erro de sintaxe
- E) `FIM`

**22.** Qual comando mostra as linhas de `/etc/passwd` que **não** terminam em `nologin`?

- A) `grep 'nologin$' /etc/passwd`
- B) `grep -c 'nologin$' /etc/passwd`
- C) `grep -n 'nologin' /etc/passwd`
- D) `grep -i 'NOLOGIN$' /etc/passwd`
- E) `grep -v 'nologin$' /etc/passwd`

**23.** Qual comando mostra **quantas linhas diferentes** existem em `nomes.txt`, contando cada repetida uma vez só?

- A) `uniq nomes.txt | wc -l`
- B) `wc -l nomes.txt`
- C) `sort nomes.txt | uniq | wc -l`
- D) `sort -u nomes.txt | wc -c`
- E) `cut -d' ' -f1 nomes.txt | wc -l`

**24.** O script `conta.sh` contém só a linha `echo "Recebi $# argumentos: $@"`. Qual é a saída de `./conta.sh "a b" c`?

- A) `Recebi 3 argumentos: a b c`
- B) `Recebi 2 argumentos: "a b" c`
- C) `Recebi 3 argumentos: a b`
- D) `Recebi 2 argumentos: a b c`
- E) `Recebi 1 argumentos: a b c`

**25.** Qual é a saída de `test -d /etc ; echo $?`?

- A) `0`
- B) `1`
- C) `true`
- D) `/etc`
- E) Nada

---

## Tópico 4 — O sistema operacional Linux

**26.** Qual destes sistemas operacionais é **proprietário** e tem base Unix?

- A) Windows
- B) macOS
- C) Debian
- D) Fedora
- E) Android

**27.** O `lscpu` mostra o modelo do processador. De qual arquivo virtual vem essa informação, que também pode ser lida com `cat`?

- A) `/etc/cpuinfo`
- B) `/sys/cpu`
- C) `/dev/cpu`
- D) `/var/log/cpu`
- E) `/proc/cpuinfo`

**28. [lacuna]** Escreva o **caminho completo** do diretório onde, segundo o FHS, ficam os arquivos de log do sistema: ______

**29.** Que sinal o comando `kill -15 2345` envia ao processo?

- A) `SIGKILL`
- B) `SIGINT`
- C) `SIGTERM`
- D) `SIGHUP`
- E) `SIGSTOP`

**30.** Qual comando mostra os processos **continuamente**, com a tela atualizada a cada poucos segundos e ordenável por CPU ou por memória?

- A) `top`
- B) `ps`
- C) `jobs`
- D) `free`
- E) `pstree`

**31.** Uma máquina tem o endereço `192.168.1.50/24`. Qual é o endereço **da rede** a que ela pertence?

- A) `192.168.0.0`
- B) `192.168.1.255`
- C) `255.255.255.0`
- D) `192.168.1.0`
- E) `192.168.1.1`

**32.** O comando `ping servidor01` funciona, mas `host servidor01` responde que o nome não existe. Qual é a explicação mais provável?

- A) O `ping` usa uma rota diferente da do `host`
- B) O nome está no `/etc/hosts`, que a resolução do sistema consulta e o `host` não, porque ele pergunta só ao DNS
- C) Um firewall bloqueia o `host`, mas libera o `ping`
- D) O `ping` não precisa resolver nomes
- E) O `host` só funciona com `sudo`

**33.** Em qual diretório cada processo em execução tem um subdiretório com o número do seu PID?

- A) `/sys`
- B) `/dev`
- C) `/proc`
- D) `/run`
- E) `/var/run`

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Na linha `maria:x:1005:1005:Maria Lima:/home/maria:/bin/zsh` do `/etc/passwd`, qual valor define o programa executado quando `maria` faz login?

- A) `/home/maria`
- B) `x`
- C) `1005`
- D) `Maria Lima`
- E) `/bin/zsh`

**35. [lacuna]** Qual comando, de uma letra só, mostra quem está logado e o que cada usuário está fazendo no momento? ______

**36.** Qual é a notação octal de `rwxrw-r--`?

- A) `764`
- B) `754`
- C) `674`
- D) `766`
- E) `744`

**37.** Um arquivo tem permissão `600`. Qual é a permissão depois de `chmod go+r,u+x arquivo`?

- A) `644`
- B) `755`
- C) `700`
- D) `744`
- E) `640`

**38.** Como aparece no `ls -l` um executável com permissão `4711`?

- A) `-rwS--x--x`
- B) `-rws--x--x`
- C) `-rwx--s--x`
- D) `-rwx--x--t`
- E) `-rws--s--x`

**39.** Qual comando muda, de uma vez, o **dono** do arquivo `arq` para `bob` e o **grupo** para `dev`?

- A) `chgrp bob:dev arq`
- B) `chmod bob:dev arq`
- C) `chown bob:dev arq`
- D) `chown dev:bob arq`
- E) `usermod -g dev bob`

**40. (escolha duas)** Quais informações o comando `id ana` mostra?

- A) O UID de `ana`
- B) O hash da senha de `ana`
- C) O último login de `ana`
- D) Os grupos de `ana`
- E) O shell de login de `ana`

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>

## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **B** | A GPL impõe obrigações a quem **distribui**. Uso interno não é distribuição. (A AGPL é a variante que estende a obrigação ao uso pela rede) |
| 2 | **A e D** | GNOME e KDE Plasma são ambientes de desktop. Wayland é protocolo de servidor gráfico; systemd é o sistema de inicialização; Apache é servidor web |
| 3 | **C** | PaaS (*Platform as a Service*): o provedor cuida do SO e do ambiente. Na IaaS o cliente administra o SO; na SaaS ele só usa o programa pronto |
| 4 | **E** | Samba implementa o protocolo de compartilhamento do Windows (SMB). O NFS compartilha arquivos entre sistemas Unix |
| 5 | **D** | O modo privado só deixa de **guardar** dados localmente. O provedor e os sites continuam vendo o seu tráfego |
| 6 | **B** | `dnf` é o gerenciador de alto nível da família Red Hat e resolve dependências. O `rpm -i` instala só o arquivo, sem resolver dependências. `apt` é Debian; `zypper` é SUSE |
| 7 | **`Android`** | Grafia aceita: `Android` |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **C** | `/home/davi/docs` → `..` = `/home/davi` → `..` = `/home` → `..` = `/` |
| 9 | **E** | Comando interno tem ajuda no `help`. O `man cd` não existe no Ubuntu; `which` e `locate` procuram arquivos |
| 10 | **B** | Seção 1: comandos do usuário; 5: formatos de arquivo; 8: administração do sistema |
| 11 | **D** | O `-p` cria os diretórios intermediários. Na A, o `mkdir` falha porque `a` não existe, e o `touch` falha em seguida |
| 12 | **A** | O `?` casa exatamente **um** caractere qualquer: `1`, `2` e `A`. O `log10` tem dois depois de `log` |
| 13 | **B e E** | `-r` e `-R` copiam recursivamente. Sem eles, o `cp` recusa diretório; o `mv` **move**, não copia |
| 14 | **C** | `-A` (*almost all*) mostra os ocultos sem `.` e `..`; `-a` mostra tudo |
| 15 | **E** | O link simbólico guarda o **nome** do alvo. Renomeado o alvo, o link fica quebrado. Um hard link continuaria funcionando |
| 16 | **`locate`** | Grafia aceita: `locate`. O índice é refeito pelo `updatedb`; o `find` olha o disco na hora |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **D** | `-c` cria, `-j` bzip2, `-f` vem por último e recebe o nome. Na C, o `-f` recebe `j` como nome de arquivo |
| 18 | **`bunzip2`** | Grafia aceita: `bunzip2`. Pares: `gzip`/`gunzip`, `bzip2`/`bunzip2`, `xz`/`unxz` |
| 19 | **A** | O último `>` **sobrescreve** o arquivo; o `>>` anterior não importa mais |
| 20 | **C e E** | `> /dev/null 2>&1`: primeiro a saída vai para o `/dev/null`, depois o erro vai para onde ela está. `&>` faz os dois. Na A, o erro foi para o terminal antes |
| 21 | **B** | O here document entrega três linhas ao `wc -l`; o delimitador `FIM` não entra |
| 22 | **E** | `-v` inverte; `nologin$` casa as linhas que **terminam** em `nologin` |
| 23 | **C** | O `uniq` só junta repetidas **vizinhas**, por isso o `sort` vem antes. Na D, o `wc -c` conta bytes, não linhas |
| 24 | **D** | Entre aspas, `"a b"` é **um** argumento: `$#` = 2. O `$@` imprime `a b c`, porque o `echo` não mostra as aspas |
| 25 | **A** | `test -d` é verdadeiro para diretório: código de saída **0** |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **B** | O macOS é proprietário e tem base Unix (o núcleo Darwin). O Windows é proprietário, mas não é Unix |
| 27 | **E** | O `/proc/cpuinfo` é gerado pelo kernel na hora em que é lido |
| 28 | **`/var/log`** | Grafia aceita: `/var/log` |
| 29 | **C** | `SIGTERM` é o 15, o mesmo que o `kill` envia sem número. `SIGKILL` é o 9; `SIGINT`, o 2 (`Ctrl+C`) |
| 30 | **A** | O `top` é o "filme"; o `ps` é a "foto" |
| 31 | **D** | `/24` = máscara `255.255.255.0`: os três primeiros números são a rede, e o último zerado é o endereço da rede. `.255` é o *broadcast* |
| 32 | **B** | Os programas resolvem nomes pelo sistema, que consulta o `/etc/hosts` antes do DNS. O `host` e o `dig` perguntam só ao DNS (Prática 5, `getent hosts`) |
| 33 | **C** | O `/proc` tem um diretório por PID, com os dados daquele processo |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **E** | O 7º campo é o shell de login. O 6º é a pasta pessoal; o 3º e o 4º, UID e GID |
| 35 | **`w`** | Grafia aceita: `w`. O `who` mostra quem está logado, sem o que cada um faz |
| 36 | **A** | `rwx` 7, `rw-` 6, `r--` 4 |
| 37 | **D** | Dono: 6 + 1 = 7. Grupo: 0 + 4 = 4. Outros: 0 + 4 = 4 |
| 38 | **B** | O `4` é SUID, no `x` do dono; o dono tem `x`, então `s` minúsculo. O resto é `711` |
| 39 | **C** | `chown dono:grupo arquivo`. O `chmod` muda permissões, não dono; a D inverte a ordem |
| 40 | **A e D** | O `id` mostra UID, GID e grupos. O hash está no `/etc/shadow`; o último login, no `last`; o shell, no `/etc/passwd` |

## Tabela de temas

| Tema | Mínimo | Questões | Total |
|---|---|---|---|
| Permissões | 4 | 36, 37, 38, 39 | 4 |
| `tar` e compressão | 2 | 17, 18 | 2 |
| Redirecionamento (com `<<`) | 3 | 19, 20, 21 | 3 |
| Diretórios virtuais e `/var` | 3 | 27, 28, 33 | 3 |
| Preencher a lacuna | 5 | 7, 16, 18, 28, 35 | 5 |

## Questões que retestam reincidências

| Q | Reincidência de origem |
|---|---|
| 6 | `dpkg`/`rpm` e os gerenciadores (Q7 do simulado 02) |
| 8 | `cd ..` e caminhos relativos (Correções 53 e 64; Q10 do simulado 02) |
| 9 | `help` para comandos internos (Correção 74; Q13 do simulado 02; série 02 das lacunas) |
| 10 | Seções do `man` (Q16 do simulado 02) |
| 13 | `cp -r` contra `mv` (Q14 do simulado 02) |
| 20 | Ordem do `2>&1` (Correção 29; Q19 do simulado 02) |
| 22 | `grep -v` (Correção 49; Q22 do simulado 02) |
| 24 | `$#` (Q6 da autoavaliação da Semana 5; Q24 do simulado 02) |
| 29 | Sinais do `kill` (Q29 do simulado 01; Q33 do simulado 02) |
| 30 | `top` (Q28 do simulado 01; série 02 das lacunas) |
| 34 | Campos do `/etc/passwd` (Q35 do simulado 01; Q34 do simulado 02) |
| 36 | Conversão octal (Q37 do simulado 01; Q36 do simulado 02) |
| 37 | `chmod` simbólico (Q37 do simulado 02) |
| 38 | `s` e `S` (Q38 do simulado 02) |
| 39 | `chown` contra `chmod` (Q38 do simulado 01) |

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

| Tema | Questões | Acertos |
| --- | --- | --- |
| Permissões | 4 | |
| `tar` e compressão | 2 | |
| Redirecionamento | 3 | |
| Diretórios virtuais | 3 | |
| Lacunas | 5 | |

## Registro

| Campo | Valor |
| --- | --- |
| Data | 09/11/2026 |
| Tempo gasto | |
| Minutos usados na segunda passada | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Chutes acertados e chutes errados | |
| Acertos firmes | |
| Erros de forma nas lacunas | |
| Reincidências que voltaram (das 15 da tabela) | |

## Questões erradas

Só as erradas e as chutadas, no mesmo dia, seguindo o protocolo de correção da operação prática (`labs/operacao-pratica.md`, seção 4). Card no Notion só para reincidência.

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |