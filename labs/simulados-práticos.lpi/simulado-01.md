# Simulado 01 — Diagnóstico — resultado de 05/10/2026

**28 de 40 acertos (70%), equivalente a 560 de 800.** Tempo usado: 20 min 31 s (restaram 39:29 dos 60 minutos). As respostas marcadas por você estão preservadas abaixo, na própria prova.

Simulado no formato do exame LPI Linux Essentials 010-160, versão 1.6.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | Não há. É um diagnóstico |

Anote as respostas em papel ou em um arquivo separado antes de abrir o gabarito. Marque as questões em que você **chutou**, mesmo acertando — são elas que informam o plano de estudo, e sem essa marca um acerto por sorte se disfarça de conhecimento.

## Distribuição por tópico

Reproduz o peso oficial do exame.

| Tópico | Peso | Questões |
| --- | --- | --- |
| 1. A comunidade Linux e uma carreira em open source | 7 | 1 a 7 |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 8 a 16 |
| 3. O poder da linha de comando | 9 | 17 a 25 |
| 4. O sistema operacional Linux | 8 | 26 a 33 |
| 5. Segurança e permissões de arquivo | 7 | 34 a 40 |

---

## Tópico 1 — A comunidade Linux e uma carreira em open source

**1.** Qual das licenças a seguir é classificada como copyleft forte?

- A) MIT
- B) Apache 2.0
- [x]  C) GPLv3
- D) BSD de três cláusulas

**2.** Qual afirmação sobre licenças copyleft é correta?

- A) Proíbem a venda do software licenciado
- [x]  B) Exigem que trabalhos derivados sejam distribuídos sob a mesma licença
- C) Impedem a modificação do código-fonte
- D) Aplicam-se apenas a software sem finalidade comercial

**3.** Qual distribuição é mantida pela comunidade e serve como base de desenvolvimento upstream para o Red Hat Enterprise Linux?

- [x]  A) Debian
- B) Fedora
- C) openSUSE
- D) Ubuntu

**4.** Qual par associa corretamente a distribuição ao seu gerenciador de pacotes nativo?

- A) Debian e `rpm`
- B) Fedora e `dpkg`
- [x]  C) Ubuntu e `apt`
- D) Rocky Linux e `apt`

**5.** O sistema operacional Android é construído sobre qual kernel?

- A) BSD
- [x]  B) Linux
- C) Mach
- D) Windows NT

**6.** Ao ativar o modo de navegação privada em um navegador, o que é efetivamente garantido?

- A) Anonimato completo na internet
- B) Que o provedor de acesso não consegue identificar os sites visitados
- [x]  C) Que histórico, cookies e dados de formulário não são gravados no computador local
- D) Que todo o tráfego passa a ser criptografado de ponta a ponta

**7.** Qual tecnologia permite executar vários sistemas operacionais isolados sobre um único hardware físico, cada um com seu próprio kernel?

- [x]  A) Contêineres
- B) Virtualização por hipervisor
- C) `chroot`
- D) Ambiente gráfico

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** Qual comando exibe o diretório de trabalho atual?

- A) `cd`
- [x]  B) `pwd`
- C) `ls -d`
- D) `whereis`

**9.** Um usuário está em `/home/davi/projetos/app`. Qual comando o leva para `/home/davi/projetos`?

- A) `cd -`
- [x]  B) `cd ..`
- C) `cd ~`
- D) `cd /`

**10.** O que o comando `cd -` faz?

- [x]  A) Vai para o diretório pai
- B) Vai para o diretório pessoal do usuário
- C) Volta ao diretório em que o usuário estava antes
- D) Produz erro de sintaxe

**11.** Escreva o nome da variável de ambiente que o shell consulta para localizar o executável de um comando digitado. Responda apenas com o nome da variável, sem o sinal `$`.

`_PATH ___________`

**12.** Qual comando revela se `ls` é um alias, um comando interno do shell ou um programa externo?

- A) `which ls`
- [x]  B) `type ls`
- C) `whereis ls`
- D) `file ls`

**13.** De acordo com o FHS, qual diretório contém os arquivos de configuração do sistema?

- A) `/var`
- [x]  B) `/etc`
- C) `/usr`
- D) `/opt`

**14.** No FHS, o nome do diretório `/usr` é a abreviação de:

- [x]  A) *User*
- B) *Unix System Resources*
- C) *User Services and Resources*
- D) *Universal Storage*

**15.** Qual diretório é um sistema de arquivos virtual que expõe informações sobre os processos em execução?

- [x]  A) `/dev`
- B) `/proc`
- C) `/boot`
- D) `/run`

**16.** Um usuário quer consultar a documentação completa do comando `cp`, incluindo todas as opções. Qual comando usar?

- A) `help cp`
- B) `man cp`
- [x]  C) `cp --manual`
- D) `info -m cp`

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando conta quantas linhas o arquivo `dados.txt` possui?

- A) `wc -w dados.txt`
- [x]  B) `wc -l dados.txt`
- C) `wc -c dados.txt`
- D) `count -l dados.txt`

**18.** O que o comando `ls -l > saida.txt 2>&1` faz?

- A) Grava a saída padrão em `saida.txt` e envia os erros ao terminal
- B) Grava os erros em `saida.txt` e a saída padrão no terminal
- [x]  C) Grava a saída padrão e os erros em `saida.txt`
- D) Cria dois arquivos, `saida.txt` e `1`

**19.** Qual comando extrai o sétimo campo de `/etc/passwd`, usando `:` como delimitador?

- [x]  A) `cut -d':' -f7 /etc/passwd`
- B) `cut -c7 /etc/passwd`
- C) `cut -d7 -f':' /etc/passwd`
- D) `cut -f':' -d7 /etc/passwd`

**20.** No comando `sort -t',' -k3 -n arquivo.csv`, o que a opção `-k3` define?

- A) O separador de campos
- B) As três primeiras linhas do arquivo
- [x]  C) A coluna usada como critério de ordenação
- D) Ordem decrescente

**21.** Um arquivo contém as linhas `a`, `a`, `b`, `c`, `c`, nessa ordem. Qual é a saída de `uniq -u arquivo`?

- A) `a`, `b`, `c`
- B) `a`, `c`
- [x]  C) `b`
- D) `a`, `a`, `b`, `c`, `c`

**22.** Qual comando cria o arquivo compactado `backup.tar.gz` a partir do diretório `dados/`?

- A) `tar -cvf backup.tar.gz dados/`
- [x]  CHUTE - B) `tar -czvf backup.tar.gz dados/`
- C) `tar -xzvf backup.tar.gz dados/`
- D) `gzip -r dados/ backup.tar.gz`

**23.** O que acontece ao executar `gzip relatorio.txt`?

- A) É criado `relatorio.txt.gz` e o original é mantido
- [x]  B) É criado `relatorio.txt.gz` e o original deixa de existir
- C) O arquivo é compactado sem alteração de nome
- D) O comando falha, porque o `gzip` só aceita diretórios

**24.** Na expressão regular `ab*c`, o que o `*` significa?

- A) Qualquer sequência de caracteres
- [x]  B) Zero ou mais ocorrências da letra `b`
- C) Uma ou mais ocorrências da letra `b`
- D) Um único caractere qualquer

**25.** Qual linha deve ser a primeira de um arquivo de script para que o sistema o interprete com o Bash?

- A) `# bash`
- [x]  B) `#!/bin/bash`
- C) `#!bash`
- D) `/bin/bash`

---

## Tópico 4 — O sistema operacional Linux

**26.** Qual comando exibe a versão do kernel em execução?

- [x]  A) `uname -r`
- B) `uptime`
- C) `cat /etc/hostname`
- D) `lsmod`

**27.** Qual arquivo identifica o nome e a versão da distribuição instalada?

- A) `/etc/hostname`
- [x]  B) `/etc/os-release`
- C) `/etc/fstab`
- D) `/proc/cpuinfo`

**28.** Qual comando exibe os processos em execução ordenados por consumo de CPU, atualizando a lista continuamente?

- A) `ps aux`
- B) `top`
- C) `jobs`
- [x]  - CHUTE - D) `free -h`

**29.** Qual sinal o comando `kill` envia por padrão, quando nenhum sinal é especificado?

- [x]  CHUTE - A) `SIGKILL` (9)
- B) `SIGTERM` (15)
- C) `SIGHUP` (1)
- D) `SIGSTOP` (19)

**30.** Qual comando exibe os endereços IP configurados nas interfaces de rede do sistema?

- [x]  A) `ip addr`
- B) `ping`
- C) `route add`
- D) `dig`

**31.** No diretório `/dev`, o que o arquivo `sda` representa?

- A) Um subdiretório de dispositivos de armazenamento
- [x]  B) O primeiro disco do tipo SATA ou SCSI reconhecido pelo sistema
- C) A primeira partição do primeiro disco
- D) Um pseudo-terminal

**32.** Qual comando instala o pacote `htop` em uma distribuição baseada em Debian?

- A) `yum install htop`
- [x]  B) `apt install htop`
- C) `rpm -i htop`
- D) `dnf install htop`

**33.** Segundo o FHS, em qual diretório ficam os arquivos de log do sistema?

- [x]  CHUTE A) `/var/log`
- B) `/etc/log`
- C) `/usr/log`
- D) `/tmp/log`

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** Em sistemas Linux modernos, qual arquivo armazena as senhas criptografadas dos usuários?

- A) `/etc/passwd`
- [x]  -CHUTE B) `/etc/shadow`
- C) `/etc/group`
- D) `/etc/sudoers`

**35.** Em cada linha de `/etc/passwd`, o que o último campo indica?

- A) A senha do usuário
- B) O shell de login
- C) O diretório pessoal
- [x]  CHUTE D) O grupo primário

**36.** Um arquivo tem as permissões `rwxr-xr--`. O que isso significa?

- [x]  CHUTE A) Dono: ler, escrever e executar. Grupo: ler e executar. Outros: ler
- B) Dono: ler, escrever e executar. Grupo: ler. Outros: ler e executar
- C) Dono: ler e executar. Grupo: ler, escrever e executar. Outros: ler
- D) Dono: ler e escrever. Grupo: ler e executar. Outros: nenhuma

**37.** Qual é a notação octal equivalente às permissões `rw-r--r--`?

- A) 755
- B) 644
- [x]  CHUTE C) 664
- D) 600

**38.** Qual comando altera o dono para `davi` e o grupo para `financeiro` no arquivo `relatorio.txt`?

- [x]  A) `chmod davi:financeiro relatorio.txt`
- B) `chown davi:financeiro relatorio.txt`
- C) `chgrp davi financeiro relatorio.txt`
- D) `usermod -o davi -g financeiro relatorio.txt`

**39.** Em um **diretório**, o que a permissão de execução (`x`) concede?

- A) O direito de executar os arquivos contidos nele
- [x]  CHUTE B) O direito de entrar no diretório e acessar seu conteúdo pelo nome
- C) O direito de listar os nomes dos arquivos contidos nele
- D) O direito de criar novos arquivos dentro dele

**40.** Um usuário comum cria um arquivo e ele recebe as permissões `rw-r--r--`. Qual mecanismo determinou que o bit de escrita não fosse concedido ao grupo e aos outros?

- A) O `chmod` padrão do sistema
- B) A `umask`
- [x]  CHUTE C) O conteúdo de `/etc/shadow`
- D) O *sticky bit*

---

# Gabarito

Confira apenas depois de responder todas as 40.

## Tópico 1

**1 — C.** A GPLv3 é copyleft forte: o código derivado precisa ser distribuído sob a mesma licença. MIT, Apache 2.0 e BSD são permissivas — permitem que o derivado seja fechado. A MPL é copyleft **fraco**, um meio-termo que não aparece aqui.

**2 — B.** Copyleft é a obrigação de propagar a licença aos derivados. Atenção às armadilhas: copyleft **não proíbe a venda** — a GPL autoriza cobrar pela distribuição de forma explícita; e **não impede a modificação** — ela a garante.

**3 — B.** O Fedora é upstream do RHEL: o que amadurece no Fedora desce para o RHEL, e não o contrário. O CentOS Stream fica entre os dois. Debian, openSUSE e Ubuntu pertencem a outras linhagens.

**4 — C.** Debian e Ubuntu usam `dpkg` na camada baixa e `apt` na camada alta. Fedora e Rocky Linux usam `rpm` e `dnf`.

**5 — B.** O Android usa o kernel Linux. É o exemplo mais citado de Linux embarcado, e a prova cobra isso.

**6 — C.** O modo privado atua **apenas no computador local**: não guarda histórico, cookies nem dados de formulário. Provedor, empregador, administrador da rede e o próprio site continuam vendo o tráfego.

**7 — B.** Cada máquina virtual tem seu próprio kernel; o hipervisor divide o hardware entre elas. Contêineres **compartilham** o kernel do hospedeiro — é justamente a diferença que a prova explora.

## Tópico 2

**8 — B.** `pwd`, de *print working directory*.

**9 — B.** O `..` é o diretório pai. Não confunda com `cd -`, que volta ao diretório **anterior** na história da sessão, e com `cd ~`, que vai para o diretório pessoal.

**10 — C.** `cd -` alterna entre o diretório atual e o último em que você estava. Útil para ir e voltar entre dois pontos distantes.

**11 — `PATH`.** O shell percorre os diretórios listados em `PATH`, na ordem, e executa o primeiro executável com aquele nome que encontrar.

**12 — B.** O `type` informa a **natureza** do comando: alias, built-in, função ou arquivo externo. O `which` procura apenas por arquivos executáveis no `PATH` e não sabe nada sobre aliases.

**13 — B.** `/etc` guarda a configuração do sistema, em texto. `/var` guarda dados variáveis, `/usr` os programas e bibliotecas, `/opt` software de terceiros.

**14 — B.** *Unix System Resources*. A tradução intuitiva para "arquivos de usuário" é errada: os arquivos pessoais ficam em `/home`.

**15 — B.** `/proc` é um sistema de arquivos virtual, gerado em memória pelo kernel, com um diretório numerado por PID. `/dev` expõe dispositivos, também virtual, mas não processos.

**16 — B.** `man cp` traz a página de manual completa. O `help` só funciona com comandos internos do shell, e `cp` é um programa externo.

## Tópico 3

**17 — B.** `-l` de *lines*. `-w` conta palavras, `-c` conta bytes.

**18 — C.** A leitura é da esquerda para a direita: `> saida.txt` faz o fluxo 1 apontar para o arquivo; `2>&1` faz o fluxo 2 ir **para onde o fluxo 1 está indo naquele momento**, ou seja, o mesmo arquivo. Se a ordem fosse invertida, `2>&1 > saida.txt`, o erro ficaria no terminal.

**19 — A.** `-d` define o delimitador e `-f` o campo. A alternativa B usa `-c`, que conta posições de caractere, não campos.

**20 — C.** O `k` vem de *key*. Quem separa as colunas é o `-t`. Quem inverte a ordem é o `-r`.

**21 — C.** O `uniq -u` mostra **somente** as linhas que nunca se repetiram. `a` e `c` aparecem duas vezes cada e são eliminadas por inteiro. Compare: `uniq` devolveria `a b c`, e `uniq -d` devolveria `a c`.

**22 — B.** `-c` cria, `-z` aciona o `gzip`, `-v` mostra o progresso, `-f` indica o nome do arquivo e vem por último, porque o argumento seguinte é consumido por ele. A alternativa A criaria um arquivo com extensão `.gz` sem nenhuma compressão.

**23 — B.** O `gzip` **substitui** o original. Para preservá-lo, `gzip -k`, de *keep*.

**24 — B.** Em expressão regular, o `*` se aplica ao **elemento imediatamente anterior** — aqui, a letra `b`. O padrão casa `ac`, `abc`, `abbc` e assim por diante. "Qualquer sequência de caracteres" é o significado do `*` no **globbing**, contexto diferente.

**25 — B.** A sequência `#!`, chamada *shebang*, precisa ser os dois primeiros caracteres do arquivo, seguida do caminho absoluto do interpretador.

## Tópico 4

**26 — A.** `uname -r`, de *release*. `uname -a` traz tudo.

**27 — B.** `/etc/os-release` é o arquivo padronizado com `NAME`, `VERSION` e `ID`. O `/etc/hostname` guarda apenas o nome da máquina.

**28 — B.** O `top` atualiza continuamente. O `ps aux` produz um retrato estático de um instante.

**29 — B.** O padrão é `SIGTERM` (15), que **pede** ao processo que termine, permitindo que ele salve o estado e feche arquivos. O `SIGKILL` (9) é enviado com `kill -9` e encerra sem negociação — é o último recurso, não o primeiro.

**30 — A.** `ip addr`, ou `ip a`. O `ifconfig` é a forma antiga, ausente em instalações recentes.

**31 — B.** `sda` é o disco inteiro; as partições são `sda1`, `sda2` e assim por diante. Discos NVMe seguem outro padrão: `nvme0n1`, com partições `nvme0n1p1`.

**32 — B.** `apt` é a família Debian. `yum`, `dnf` e `rpm` pertencem à família Red Hat.

**33 — A.** `/var/log`. O `/var` guarda dados que crescem com o uso do sistema, e log é o exemplo canônico.

## Tópico 5

**34 — B.** O `/etc/shadow` guarda os hashes e só é legível pelo `root`. O `/etc/passwd` é legível por todos e hoje traz um `x` no campo da senha, indicando que o hash está no `shadow`.

**35 — B.** A ordem dos sete campos é: nome, senha, UID, GID, comentário, diretório pessoal e **shell de login**. É o campo alterado por `usermod -s` e por `chsh`.

**36 — A.** Os nove caracteres formam três grupos de três, na ordem dono, grupo, outros:

```
rwx      r-x      r--
dono    grupo    outros
```

**37 — B.** `r` vale 4, `w` vale 2, `x` vale 1. `rw-` é 6, `r--` é 4, `r--` é 4. Resultado: 644. A opção 755 corresponde a `rwxr-xr-x`, o padrão de diretórios e executáveis.

**38 — B.** O `chown` aceita `dono:grupo` em uma só chamada. O `chmod` trata de permissões, não de propriedade; o `chgrp` só altera o grupo.

**39 — B.** Em um diretório, os três bits têm significados que não são intuitivos:

| Bit | Em um diretório concede |
| --- | --- |
| `r` | Listar os nomes das entradas |
| `w` | Criar, remover e renomear entradas |
| `x` | Entrar no diretório e acessar as entradas pelo nome |

Sem o `x` não se pode nem entrar, mesmo com `r`. E com `x` sem `r` é possível acessar um arquivo cujo nome você já conheça, sem poder listar o conteúdo — configuração usada de propósito em diretórios semipúblicos.

**40 — B.** A `umask` é uma máscara que **retira** permissões das permissões máximas padrão. Para arquivos comuns o padrão é 666, e uma `umask` de 022 remove o bit de escrita de grupo e outros, resultando em 644.

---

# Apuração

Preencha depois de conferir o gabarito.

| Tópico | Peso | Questões | Acertos | Chutes acertados |
| --- | --- | --- | --- | --- |
| 1. Comunidade e open source | 7 | 7 | 5 | 0 |
| 2. Encontrando seu caminho | 9 | 9 | 5 | 0 |
| 3. Poder da linha de comando | 9 | 9 | 9 | 1 |
| 4. Sistema operacional | 8 | 8 | 6 | 1 |
| 5. Segurança e permissões | 7 | 7 | 3 | 3 |
| **Total** | **40** | **40** | **28** | **5** |

## Como ler o resultado

O número total importa menos que a distribuição. Três leituras possíveis:

**Erros concentrados nos Tópicos 4 e 5.** É o resultado esperado neste momento: o Tópico 5 não foi estudado e o Tópico 4 está parcial. O plano está funcionando, e a Semana 6 e a Semana 7 endereçam exatamente esses tópicos.

**Erros nos Tópicos 1, 2 ou 3.** Estes estão fechados no cronograma, e as autoavaliações deram 14 de 15 e 20 de 20. Um erro aqui significa que a autoavaliação da semana mediu o que você acabou de estudar, não o que ficou. Erro nesses tópicos é sinal para revisar, não para seguir adiante.

**Acertos por chute.** É a métrica mais honesta do simulado, e a que só você pode registrar. Uma questão acertada por eliminação, sem saber a resposta, conta como erro para efeito de estudo. A coluna existe para isso.

## Registro

| Campo | Valor |
| --- | --- |
| Data | 05/10/2026 |
| Tempo gasto | 20 min 31 s (restaram 39:29) |
| Acertos | **28** de 40 |
| Percentual | **70%** |
| Equivalente na escala LPI | 28 × 20 = **560 de 800**, acima do corte de 500 (26 acertos) |
| Questões marcadas como chute | **10**: 22, 28, 29, 33, 34, 35, 36, 37, 39 e 40. Cinco acertadas (22, 33, 34, 36, 39) e cinco erradas (28, 29, 35, 37, 40) |

A conversão é aproximada: o exame real usa pontuação de 200 a 800, com corte em 500. Vinte pontos por questão é uma aproximação linear suficiente para acompanhar a evolução.

---

# Correção por questão

| Q | Tópico | Sua resposta | Gabarito | Resultado | Chute |
| --- | --- | --- | --- | --- | --- |
| 1 | 1 | C | C | Certo |  |
| 2 | 1 | B | B | Certo |  |
| 3 | 1 | A | B | **Errado** |  |
| 4 | 1 | C | C | Certo |  |
| 5 | 1 | B | B | Certo |  |
| 6 | 1 | C | C | Certo |  |
| 7 | 1 | A | B | **Errado** |  |
| 8 | 2 | B | B | Certo |  |
| 9 | 2 | B | B | Certo |  |
| 10 | 2 | A | C | **Errado** |  |
| 11 | 2 | PATH | PATH | Certo |  |
| 12 | 2 | B | B | Certo |  |
| 13 | 2 | B | B | Certo |  |
| 14 | 2 | A | B | **Errado** |  |
| 15 | 2 | A | B | **Errado** |  |
| 16 | 2 | C | B | **Errado** |  |
| 17 | 3 | B | B | Certo |  |
| 18 | 3 | C | C | Certo |  |
| 19 | 3 | A | A | Certo |  |
| 20 | 3 | C | C | Certo |  |
| 21 | 3 | C | C | Certo |  |
| 22 | 3 | B | B | Certo | Sim |
| 23 | 3 | B | B | Certo |  |
| 24 | 3 | B | B | Certo |  |
| 25 | 3 | B | B | Certo |  |
| 26 | 4 | A | A | Certo |  |
| 27 | 4 | B | B | Certo |  |
| 28 | 4 | D | B | **Errado** | Sim |
| 29 | 4 | A | B | **Errado** | Sim |
| 30 | 4 | A | A | Certo |  |
| 31 | 4 | B | B | Certo |  |
| 32 | 4 | B | B | Certo |  |
| 33 | 4 | A | A | Certo | Sim |
| 34 | 5 | B | B | Certo | Sim |
| 35 | 5 | D | B | **Errado** | Sim |
| 36 | 5 | A | A | Certo | Sim |
| 37 | 5 | C | B | **Errado** | Sim |
| 38 | 5 | A | B | **Errado** |  |
| 39 | 5 | B | B | Certo | Sim |
| 40 | 5 | C | B | **Errado** | Sim |

**Erros com convicção (sem marca de chute):** 3, 7, 10, 14, 15, 16 e 38. São os que viram correção com mecanismo (62 a 68, no arquivo da Semana 6).

**Erros marcados como chute:** 28, 29, 35, 37 e 40. Todos nos Tópicos 4 e 5, ainda não estudados. Definem a ênfase das Semanas 6 e 7.

**Acertos por chute:** 22, 33, 34, 36 e 39. Contam como erro para efeito de estudo. Acertos firmes: **23 de 40 (57,5%)**.

**Retestes das correções antigas:** as questões 18, 20, 21 e 24 foram acertadas sem chute, e as correções 29, 33/34/50, 36 e a de regex contra globbing se sustentaram. A 22 (Correção 52, `-f` do `tar` por último) foi acertada **por chute** e não está confirmada.

**Observação sobre a 11:** a resposta foi `PATH`. No campo de preenchimento do exame real, escreva só a palavra, sem sublinhado ou outro caractere.