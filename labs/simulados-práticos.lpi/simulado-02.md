# Simulado 02 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 13/10/2026 para o **sábado 17/10**, como uma das dívidas da Etapa 1 (`labs/semana-07.md`).

Este simulado é **mais difícil que o 01**: enunciados com cenário, pegadinhas de comando, quatro questões de escolher duas respostas e cinco questões de preencher a lacuna. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. **Use pelo menos 45** e reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **24 ou mais** (critério do Checkpoint A) |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando.

Nas questões **[lacuna]**, escreva só o que foi pedido: sem caminho, sem flags, sem sublinhado, sem aspas, sem ponto final. Maiúsculas e minúsculas contam.

Nas questões **(escolha duas)**, a questão só conta como certa se as duas respostas estiverem certas.

## Distribuição por tópico

| Tópico | Peso | Questões |
| --- | --- | --- |
| 1. A comunidade Linux e uma carreira em open source | 7 | 1 a 7 |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 8 a 16 |
| 3. O poder da linha de comando | 9 | 17 a 25 |
| 4. O sistema operacional Linux | 8 | 26 a 33 |
| 5. Segurança e permissões de arquivo | 7 | 34 a 40 |

**Atenção ao Tópico 4:** ele só será estudado na Semana 8. As questões dele medem o ponto de partida, não o resultado do estudo. Marque os chutes com cuidado.

---

## Tópico 1 — A comunidade Linux e uma carreira em open source

**1.** Uma empresa modifica um programa licenciado sob a GPLv2 e passa a distribuir o binário modificado aos seus clientes. O que a licença exige dela?

- A) Nada, porque a GPL só se aplica a quem vende o software
- B) Pagar uma taxa de licenciamento à Free Software Foundation
- C) Oferecer aos clientes o código-fonte da versão modificada, sob a mesma licença
- D) Relicenciar o programa sob a licença MIT antes de distribuí-lo

**2.** **(escolha duas)** Quais destas licenças são permissivas, ou seja, permitem incorporar o código em software proprietário sem exigir a abertura do código derivado?

- A) MIT
- B) GPLv3
- C) BSD de duas cláusulas
- D) AGPLv3
- E) GPLv2

**3.** Qual afirmação descreve corretamente como empresas como a Red Hat ganham dinheiro com software livre?

- A) Vendem licenças de uso do kernel Linux, que pertence a elas
- B) Mantêm fechado o código-fonte do RHEL
- C) Cobram pelo download do Fedora
- D) Vendem assinaturas que incluem suporte, atualizações e certificação

**4.** Rocky Linux e AlmaLinux são distribuições criadas para serem compatíveis, binário a binário, com qual distribuição?

- A) Debian
- B) Red Hat Enterprise Linux
- C) openSUSE
- D) Ubuntu

**5.** Uma designer quer um programa de código aberto para retocar fotografias, que são imagens rasterizadas. Qual é o mais indicado?

- A) GIMP
- B) Inkscape
- C) Blender
- D) Audacity

**6.** Qual prática protege melhor as contas de um usuário na internet?

- A) Usar a mesma senha longa em todos os serviços, para não esquecê-la
- B) Trocar a senha toda semana por uma variação da anterior
- C) Guardar as senhas em um arquivo de texto na área de trabalho
- D) Usar um gerenciador de senhas, com uma senha diferente por serviço, e ativar a autenticação em dois fatores

**7. [lacuna]** Nas distribuições da família Debian, o `apt` resolve dependências e baixa pacotes. A ferramenta de baixo nível que de fato instala um arquivo `.deb` é: ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O usuário executa `ls` em sua pasta pessoal e o arquivo `.bashrc` não aparece, embora ele exista. Por quê?

- A) O usuário não tem permissão de leitura sobre a própria pasta pessoal
- B) O `.bashrc` fica em `/etc`, não na pasta pessoal
- C) Arquivos cujo nome começa com ponto são ocultos e só aparecem com `ls -a`
- D) O `ls` só lista diretórios quando é executado sem argumentos

**9.** **(escolha duas)** O usuário `davi` está em `/var/log`. Quais comandos o levam para `/home/davi`?

- A) `cd /`
- B) `cd`
- C) `cd ..`
- D) `cd ~`
- E) `cd /home`

**10.** O usuário está em `/var/log` e quer ir para `/var/tmp` usando um **caminho relativo**. Qual comando faz isso?

- A) `cd ../tmp`
- B) `cd /var/tmp`
- C) `cd ./tmp`
- D) `cd ~/tmp`

**11.** Um diretório contém os arquivos `a1.txt`, `a2.txt`, `ab.txt`, `abc.txt` e `b1.txt`. Qual é a saída de `ls a?.txt`?

- A) `a1.txt a2.txt`
- B) `a1.txt a2.txt b1.txt`
- C) `a1.txt a2.txt ab.txt abc.txt`
- D) `a1.txt a2.txt ab.txt`

**12.** O comando `rmdir dados` falha com a mensagem `Directory not empty`. Qual comando remove o diretório e todo o seu conteúdo?

- A) `rmdir -f dados`
- B) `rm -r dados`
- C) `rm dados`
- D) `mv dados /dev/null`

**13. [lacuna]** Comandos internos do shell, como o `cd`, não têm página de manual própria. O comando interno do Bash que exibe a ajuda desses comandos é: ______

**14.** **(escolha duas)** Quais afirmações sobre o comando `mv` estão corretas?

- A) Renomeia um arquivo quando a origem e o destino estão no mesmo diretório
- B) Mantém uma cópia do arquivo na origem
- C) Exige a opção `-r` para mover diretórios
- D) Só funciona dentro de um mesmo diretório
- E) Move arquivos de um diretório para outro

**15.** Um usuário criou o arquivo `notas.txt` há um minuto e o comando `locate notas.txt` não o encontra. Qual é a causa mais provável?

- A) O `locate` só procura dentro de `/home`
- B) O arquivo é oculto
- C) O `locate` precisa ser executado com `sudo`
- D) O banco de dados consultado pelo `locate` ainda não foi atualizado pelo `updatedb`

**16.** Qual comando exibe a página de manual que descreve o **formato do arquivo** `/etc/passwd`, e não o comando `passwd`?

- A) `man passwd`
- B) `passwd --help`
- C) `man 5 passwd`
- D) `man -k passwd`

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando extrai, no diretório atual, o conteúdo do arquivo `site.tar.bz2`?

- A) `tar -czf site.tar.bz2`
- B) `tar -tjf site.tar.bz2`
- C) `tar -xzf site.tar.bz2`
- D) `tar -xjf site.tar.bz2`

**18.** O comando `tar -cvf -z dados.tar.gz dados/` não produz o arquivo `dados.tar.gz` esperado. Por quê?

- A) O `-f` consome o argumento seguinte: o arquivo criado passou a se chamar `-z`, e `dados.tar.gz` virou um item a incluir, que não existe
- B) A opção `-v` não pode ser combinada com `-c`
- C) Falta a opção `-x`
- D) O `tar` não comprime com gzip; seria preciso rodar o `gzip` depois

**19.** Qual comando grava a saída padrão **e** as mensagens de erro de `find / -name core` no mesmo arquivo `tudo.txt`?

- A) `find / -name core 2>&1 > tudo.txt`
- B) `find / -name core > tudo.txt 2>&1`
- C) `find / -name core 2> tudo.txt`
- D) `find / -name core | tudo.txt`

**20.** Um script contém o trecho abaixo. Qual é o conteúdo de `lista.txt` depois da execução?

```bash
cat << FIM > lista.txt
um
dois
FIM
```

- A) Só a palavra `FIM`
- B) As linhas `um` e `dois`
- C) As linhas `um`, `dois` e `FIM`
- D) Nada: o arquivo fica vazio

**21. [lacuna]** O operador que redireciona **somente** a saída de erro de um comando para um arquivo, sobrescrevendo-o, é: ______

**22.** Qual comando mostra as linhas de `app.log` que **não** contêm a palavra `DEBUG`?

- A) `grep -v DEBUG app.log`
- B) `grep -i DEBUG app.log`
- C) `grep -c DEBUG app.log`
- D) `grep -n DEBUG app.log`

**23.** Qual pipeline mostra os três shells mais usados em `/etc/passwd`, do mais frequente para o menos frequente, com a contagem de cada um?

- A) `cut -d: -f7 /etc/passwd | uniq -c | sort -rn | head -3`
- B) `sort /etc/passwd | head -3`
- C) `cut -d: -f7 /etc/passwd | sort -r | head -3`
- D) `cut -d: -f7 /etc/passwd | sort | uniq -c | sort -rn | head -3`

**24.** O script `s.sh` contém apenas `echo $# $2`. Qual é a saída de `./s.sh a b c`?

- A) `4 b`
- B) `3 a`
- C) `3 b`
- D) `a b c`

**25.** Em um script, qual condição é verdadeira quando `/etc/hosts` existe e é um **arquivo regular**?

- A) `[ -d /etc/hosts ]`
- B) `[ -f /etc/hosts ]`
- C) `[ -z /etc/hosts ]`
- D) `[ -x /etc/hosts ]`

---

## Tópico 4 — O sistema operacional Linux

**26.** O que caracteriza uma versão LTS de uma distribuição Linux?

- A) Recebe correções de segurança e de bugs por um período estendido, de vários anos
- B) É atualizada continuamente, sem números de versão
- C) É a versão de testes publicada antes da versão estável
- D) Só pode ser instalada em servidores, sem interface gráfica

**27.** Qual diretório é um sistema de arquivos virtual em que o kernel expõe informações sobre dispositivos, barramentos e drivers, organizadas em uma hierarquia como `class/net` e `block`?

- A) `/proc`
- B) `/sys`
- C) `/dev`
- D) `/boot`

**28.** Em qual diretório ficam, normalmente, a imagem do kernel (`vmlinuz`) e o `initramfs` usados na inicialização?

- A) `/etc`
- B) `/usr/bin`
- C) `/var`
- D) `/boot`

**29. [lacuna]** O comando que exibe as mensagens do buffer do kernel, como as geradas na inicialização ou ao conectar um dispositivo USB, é: ______

**30.** Qual arquivo de dispositivo representa a **segunda partição** do **terceiro disco** SATA do sistema?

- A) `/dev/sdc2`
- B) `/dev/sdb3`
- C) `/dev/sd3b`
- D) `/dev/sdb2`

**31.** Qual arquivo define os servidores DNS que o sistema consulta para resolver nomes?

- A) `/etc/hosts`
- B) `/etc/hostname`
- C) `/etc/resolv.conf`
- D) `/etc/networks`

**32.** **(escolha duas)** Quais destes endereços IPv4 pertencem a faixas privadas?

- A) `8.8.8.8`
- B) `10.20.30.40`
- C) `172.32.0.1`
- D) `172.16.5.4`
- E) `200.1.2.3`

**33.** Um processo de PID 4321 não termina com `kill 4321`. Qual comando o encerra imediatamente, sem permitir que ele trate ou ignore o sinal?

- A) `kill -15 4321`
- B) `kill -9 4321`
- C) `kill -1 4321`
- D) `kill 4321` repetido duas vezes

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Em `/etc/passwd`, a linha `ana:x:1001:1001:Ana Souza:/home/ana:/bin/bash` tem um `x` no segundo campo. O que ele indica?

- A) Que o hash da senha está guardado em `/etc/shadow`
- B) Que a conta está bloqueada
- C) Que a conta não tem senha
- D) Que a usuária tem privilégios de administrador

**35.** O usuário `bob` está nos grupos secundários `dev` e `docker`. O administrador executa `sudo usermod -G ops bob`. Em quais grupos secundários `bob` fica?

- A) `dev`, `docker` e `ops`
- B) `dev` e `docker`
- C) Apenas `ops`
- D) Nenhum: o comando falha sem a opção `-a`

**36.** Qual é a notação octal de `rwxr-x---`?

- A) `755`
- B) `750`
- C) `740`
- D) `570`

**37.** Um arquivo tem permissão `754`. Qual é a permissão depois de `chmod o+w,g-x arquivo`?

- A) `744`
- B) `756`
- C) `766`
- D) `746`

**38.** Como aparece, no `ls -ld`, um diretório com permissão `1777`?

- A) `drwsrwxrwx`
- B) `drwxrwsrwx`
- C) `drwxrwxrwt`
- D) `drwxrwxrwT`

**39.** O diretório `/tmp` tem permissão `drwxrwxrwt` e pertence ao root. A usuária `ana` tenta apagar `/tmp/relatorio`, que pertence a `bob`. O que acontece?

- A) Ela não consegue: com o sticky bit, só o dono do arquivo, o dono do diretório ou o root podem apagá-lo
- B) Ela consegue, porque tem permissão de escrita no diretório
- C) Ela consegue, se estiver no mesmo grupo de `bob`
- D) Ela não consegue, porque o `/tmp` é montado como somente leitura

**40. [lacuna]** O comando que altera **somente o grupo** de um arquivo, sem alterar o dono, é: ______

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>

## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **C** | A GPL é copyleft: quem distribui uma versão modificada precisa oferecer o código-fonte dela aos destinatários, sob a mesma licença. Uso interno, sem distribuição, não gera essa obrigação |
| 2 | **A e C** | MIT e BSD são permissivas. GPLv2, GPLv3 e AGPLv3 são copyleft |
| 3 | **D** | O código é aberto; o produto vendido é a assinatura (suporte, atualizações, certificação). O kernel não pertence a nenhuma empresa |
| 4 | **B** | Rocky e AlmaLinux reconstroem o RHEL. Na cadeia da Correção 62: Fedora, CentOS Stream, RHEL, e então Rocky e AlmaLinux |
| 5 | **A** | GIMP edita imagens rasterizadas. Inkscape é vetorial, Blender é 3D, Audacity é áudio |
| 6 | **D** | Senhas únicas, guardadas em gerenciador, mais o segundo fator. Reaproveitar senha expõe todas as contas quando um serviço vaza |
| 7 | **`dpkg`** | Grafia aceita: `dpkg`. O `apt` usa o `dpkg` por baixo. Na família Red Hat, o par equivalente é `dnf` e `rpm` |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **C** | Nome começando com ponto é a convenção de arquivo oculto. `ls -a` mostra; `ls -A` mostra sem `.` e `..` |
| 9 | **B e D** | `cd` sem argumento e `cd ~` levam à pasta pessoal. `cd /home` leva ao diretório que **contém** as pastas pessoais (Correção 54) |
| 10 | **A** | De `/var/log`, `..` é `/var`, e `../tmp` é `/var/tmp`. A opção B chega ao lugar certo, mas é caminho **absoluto** |
| 11 | **D** | O `?` casa **exatamente um** caractere qualquer, letra ou número (Correção 70). `abc.txt` tem dois caracteres depois do `a`; `b1.txt` não começa com `a` |
| 12 | **B** | O `rmdir` só remove diretório vazio. `rm -r` remove recursivamente. O `rmdir` não tem `-f` |
| 13 | **`help`** | Grafia aceita: `help`. Exemplo: `help cd`. O `type cd` mostra que o `cd` é interno (Correção 74) |
| 14 | **A e E** | O `mv` renomeia e move. Não deixa cópia, não exige `-r` para diretórios (quem exige é o `cp`) e funciona entre diretórios |
| 15 | **D** | O `locate` consulta um índice pronto; o `updatedb` o reconstrói. O `find` olharia o disco na hora e encontraria (Correção 73) |
| 16 | **C** | A seção 5 do manual é a de formatos de arquivo. `man passwd` abre a seção 1, a do comando |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **D** | `-x` extrai, `-j` é bzip2, `-f` indica o arquivo. A opção C usaria gzip num arquivo bzip2. A opção B só lista |
| 18 | **A** | O `-f` recebe o **argumento seguinte** como nome do arquivo (Correção 52). Por isso ele vem por último no grupo: `tar -czvf dados.tar.gz dados/` |
| 19 | **B** | Os redirecionamentos são lidos da esquerda para a direita: primeiro a saída padrão vai para o arquivo, depois o erro vai para onde a saída padrão está. Na opção A, o erro foi duplicado para o terminal antes de a saída padrão ir para o arquivo (Correção 29) |
| 20 | **B** | O here document entrega ao `cat` as linhas até a linha que contém só o delimitador. O delimitador não entra no texto; o `>` grava o resultado no arquivo |
| 21 | **`2>`** | Grafia aceita: `2>`, sem espaço entre o `2` e o `>`. O `2>>` acrescentaria em vez de sobrescrever |
| 22 | **A** | No `grep`, `-v` é *invert* (Correção 49). `-i` ignora maiúsculas, `-c` conta, `-n` numera |
| 23 | **D** | O `uniq` só junta linhas iguais **vizinhas**, por isso o `sort` precisa vir antes dele. A opção A pula esse `sort` e conta errado |
| 24 | **C** | `$#` é o número de argumentos (3), `$2` é o segundo (`b`). O nome do script, `$0`, não entra na contagem |
| 25 | **B** | `-f` testa arquivo regular. `-d` testa diretório, `-z` testa texto vazio, `-x` testa permissão de execução |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **A** | LTS é suporte estendido. A opção B descreve rolling release; a C, uma versão beta |
| 27 | **B** | O `/sys` expõe dispositivos e drivers organizados pelo kernel. O `/proc` é de processos e informações do kernel; o `/dev` traz os arquivos de dispositivo que os programas abrem |
| 28 | **D** | O `/boot` guarda o kernel, o `initramfs` e os arquivos do carregador de inicialização. Na sua VM ele fica em `sda2`, fora do LVM |
| 29 | **`dmesg`** | Grafia aceita: `dmesg`. No Ubuntu recente, ler o buffer pode exigir `sudo`, mas o nome do comando é esse |
| 30 | **A** | `sd` + letra do disco (`a`, `b`, `c` = primeiro, segundo, terceiro) + número da partição |
| 31 | **C** | O `/etc/resolv.conf` lista os servidores DNS. O `/etc/hosts` é uma tabela local de nomes, consultada antes do DNS |
| 32 | **B e D** | As faixas privadas são `10.0.0.0/8`, `172.16.0.0/12` (de `172.16` a `172.31`) e `192.168.0.0/16`. `172.32.0.1` fica fora da faixa |
| 33 | **B** | `kill` sem número envia `SIGTERM` (15), que o processo pode tratar. `SIGKILL` (9) é aplicado pelo kernel e não pode ser tratado nem ignorado |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **A** | O `/etc/passwd` é legível por todos; por isso o hash fica no `/etc/shadow`, legível só pelo root |
| 35 | **C** | Sem o `-a`, o `-G` **substitui** a lista de grupos secundários. O comando não falha: ele faz exatamente o que foi pedido |
| 36 | **B** | `rwx` = 7, `r-x` = 5, `---` = 0 |
| 37 | **D** | Grupo: `r-x` (5) menos `x` = `r--` (4). Outros: `r--` (4) mais `w` = `rw-` (6). Dono inalterado: 7 |
| 38 | **C** | O `1` é o sticky bit, que aparece como `t` no lugar do `x` dos outros. Como os outros têm `x`, o `t` é minúsculo |
| 39 | **A** | O sticky bit restringe a exclusão ao dono do arquivo, ao dono do diretório e ao root, mesmo com `w` no diretório para todos |
| 40 | **`chgrp`** | Grafia aceita: `chgrp`. O `chown :grupo arquivo` também muda só o grupo, mas a pergunta pede o comando feito para isso |

## Tabela de temas

Os temas são os das dicas recorrentes (`praticas_simulados.md`, seção 2.1). Uma questão pode contar em um tema e em um tópico ao mesmo tempo.

| Tema | Mínimo | Questões | Total |
|---|---|---|---|
| Permissões | 4 | 36, 37, 38, 39, 40 | 5 |
| `tar` e compressão | 2 | 17, 18 | 2 |
| Redirecionamento (com `<<`) | 3 | 19, 20, 21 | 3 |
| Diretórios virtuais e `/var` | 3 | 27, 28, 30 | 3 |
| Preencher a lacuna | 5 | 7, 13, 21, 29, 40 | 5 |

## Questões que retestam correções antigas

São da retaguarda: não se estudam de novo, mas o simulado diz se o erro voltou.

| Q | Correção |
|---|---|
| 4 | 62 (cadeia Red Hat) |
| 9 | 54 (`~` contra `/home`) |
| 11 | 70 (`?` casa um caractere qualquer) |
| 15 | 73 (`locate` e `updatedb`) |
| 18 | 52 (o `-f` do `tar`) |
| 19 | 29 (ordem do `2>&1`) |
| 22 | 49 (`grep -v`) |
| 34 | Q35 do simulado 01 (campos do `/etc/passwd`) |
| 35 | Prática 1, bloco 3 (`usermod` sem `-a`) |

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
| Permissões | 5 | |
| `tar` e compressão | 2 | |
| Redirecionamento | 3 | |
| Diretórios virtuais | 3 | |
| Lacunas | 5 | |

## Registro

| Campo | Valor |
| --- | --- |
| Data | 17/10/2026 |
| Tempo gasto | |
| Minutos usados na segunda passada | |
| Acertos | de 40 |
| Percentual e escala LPI | |
| Questões marcadas como chute | |
| Chutes acertados e chutes errados | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

Só as erradas e as chutadas. A correção vai para o Notion, com as suas palavras.

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Corrigida no Notion |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |

**Comparação com o simulado 01 (28 de 40, 23 firmes):** o que errava e agora acerta, o que continua errando, o que apareceu de novo.