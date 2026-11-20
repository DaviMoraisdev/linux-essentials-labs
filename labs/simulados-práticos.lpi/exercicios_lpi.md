# Exercícios da LPI — todas as lições do exame 010-160

**Criado em:** 03/11/2026 · **Fonte:** LPI Learning Material, Linux Essentials versão 1.6, em português (o PDF do Projeto) · **Uso:** um ou dois blocos por dia na operação prática (`labs/operacao-pratica.md`)

São as **24 lições** do material oficial, com cerca de **205 exercícios** (Guiados e Exploratórios). É o único banco de questões escrito pela própria LPI. Os enunciados e as respostas ficam no PDF; este arquivo diz **o que fazer em cada dia**, onde estão as páginas e onde anotar os erros.

## Como fazer

| Passo | Detalhe |
|---|---|
| 1. Responder | Abra a página dos exercícios no PDF e responda **sem consultar o texto da lição**, por escrito, no caderno |
| 2. Conferir | Só depois abra "Respostas aos Exercícios" (página indicada) e compare |
| 3. Anotar | Na tabela da seção 3, só as **erradas**, com o número (G3, E2) e uma linha sobre o que estava errado |
| 4. Executar | Se o erro for sobre um comando, rode-o na VM antes de seguir |
| Tempo | **25 minutos** por bloco; dois blocos nos dias B. Acabou o tempo, acabou o bloco: o que sobrar não vira pendência |
| Exploratórios | Fazem parte do bloco, mas, se o tempo apertar, os Guiados vêm primeiro |

**Ordem.** O Tópico 5 vem primeiro, porque foi o mais fraco no simulado 02 (3 de 7); o Tópico 4 em seguida, enquanto as Práticas 3 a 5 estão frescas; depois os Tópicos 3 e 2; e o Tópico 1, o mais firme, fecha a série. Quando um bloco cai no mesmo dia de um mini-simulado do mesmo tema, um reforça o outro (o 5.1 com o R4, o 4.4 com o R2, o 3.1 com o R1).

**As lições 5.1 a 5.4 já foram feitas em 21/10**, com um guia resolvido. Agora é para responder **sem olhar o guia**: é a medição que faltou naquele dia.

---

## 1. Calendário

**Refeito em 17/11**, com um simulado por dia: as 11 lições que faltam vão de 17 a 22/11, duas por dia (um ou dois blocos de 25 minutos), e de 22 a 25/11 quatro blocos **refazem as questões que você errou**.

| Dia | Lições | Exercícios (aprox.) | Páginas dos exercícios | Páginas das respostas |
|---|---|---|---|---|
| Sex 06/11 | 4.1 | 7 | 264–266 | 268–270 |
| Seg 09/11 | 5.1 e 5.2 | 12 + 10 | 372–374 · 391–393 | 377–379 · 395–397 |
| Ter 10/11 | 4.2 e 5.3 | 4 + 11 | 283–284 · 416–418 | 286–288 · 420–423 |
| Qua 11/11 | 4.3, lição 1 e 4.3, lição 2 | 6 + 9 | 303–305 · 321–324 | 308–310 · 328–332 |
| Qui 12/11 | 4.4 e 5.4 | 9 + 10 | 349–350 · 434–435 | 352–353 · 439–440 |
| Sex 13/11 | 3.1 e 3.2, lição 1 | 9 + 12 | 183–184 · 199–200 | 187–189 · 202–204 |
| Seg 16/11 | 3.2, lição 2 e 3.3, lição 1 (feito) | 9 + 7 | 210–211 · 229–231 | 213–215 · 234–236 |
| Ter 17/11 | 3.3, lição 2 e 2.1, lição 1 (feito) | 3 + 6 | 247–249 · 82–84 | 251–253 · 86–87 |
| Qui 19/11 | 2.3, lição 1 e 2.3, lição 2 (feito) | 7 + 5 | 122–124 · 139–141 | 126–129 · 143–145 |
| Sex 20/11 | 2.1, lição 2 e 2.2 | 9 + 11 | 94–95 · 107–109 | 97–98 · 111–114 |
| Sáb 21/11 | 2.4 e 1.1 | 12 + 8 | 162–164 · 8–9 | 167–170 · 11–13 |
| Dom 22/11 | 1.2 e 1.3 | 11 + 10 | 30–32 · 48–49 | 34–36 · 51–52 |
| Seg 23/11 | 1.4 | 8 | 66–68 | 70–72 |
| Seg 23/11 | **Revisão: erradas dos Tópicos 5 e 4** | As erradas da seção 3 | — | — |
| Ter 24/11 | **Revisão: erradas do Tópico 3** | As erradas da seção 3 | — | — |
| Qua 25/11 | **Revisão: erradas dos Tópicos 2 e 1 e as reincidências** | As erradas da seção 3 | — | — |

As páginas são as impressas no rodapé do PDF.

---

## 2. As 24 lições

| Lição | Tema | Exercícios | Dia |
|---|---|---|---|
| 1.1 | A evolução do Linux e sistemas operacionais populares | G5 E3 | Sáb 21/11 |
| 1.2 | Principais aplicações open source | G7 E4 | Dom 22/11 |
| 1.3 | Software open source e suas licenças | G5 E5 | Dom 22/11 |
| 1.4 | Habilidades ICT e trabalhando no Linux | G5 E3 | Seg 23/11 |
| 2.1, lição 1 | O básico sobre a linha de comando | G3 E3 | Ter 17/11 |
| 2.1, lição 2 | O básico sobre a linha de comando (variáveis) | G4 E5 | Sex 20/11 |
| 2.2 | Usando a linha de comando para conseguir ajuda | G6 E5 | Sex 20/11 |
| 2.3, lição 1 | Usando diretórios e listando arquivos | G4 E3 | Qui 19/11 |
| 2.3, lição 2 | Usando diretórios e listando arquivos (caminhos e ocultos) | G2 E3 | Qui 19/11 |
| 2.4 | Criando, movendo e deletando arquivos | G7 E5 | Sáb 21/11 |
| 3.1 | Empacotando arquivos na linha de comando | G5 E4 | Sex 13/11 |
| 3.2, lição 1 | Redirecionamento e pipes | G7 E5 | Sex 13/11 |
| 3.2, lição 2 | `grep` e expressões regulares | G6 E3 | Seg 16/11 |
| 3.3, lição 1 | Transformando comandos em scripts | G3 E4 | Seg 16/11 |
| 3.3, lição 2 | Códigos de saída, argumentos e `for` | G2 E1 | Ter 17/11 |
| 4.1 | Escolhendo um sistema operacional | G5 E2 | Sex 06/11 |
| 4.2 | Entendendo o hardware do computador | G3 E1 | Ter 10/11 |
| 4.3, lição 1 | Onde os dados são armazenados: programas, configuração e processos | G4 E2 | Qua 11/11 |
| 4.3, lição 2 | Onde os dados são armazenados: logs e mensagens do sistema | G6 E3 | Qua 11/11 |
| 4.4 | Seu computador na rede | G4 E5 | Qui 12/11 |
| 5.1 | Segurança básica e tipos de usuários | G5 E7 | Seg 09/11 |
| 5.2 | Criando usuários e grupos | G2 E8 | Seg 09/11 |
| 5.3 | Gerenciando permissões e propriedade de arquivos | G6 E5 | Ter 10/11 |
| 5.4 | Diretórios e arquivos especiais | G5 E5 | Qui 12/11 |

---

## 3. Registro

Só as erradas. "Reincidência" quando o mesmo erro já apareceu em simulado, mini-simulado ou correção numerada; nesse caso, card no Notion.

| Dia | Lição | Acertos | Erradas (número e o que estava errado) | Reincidência? |
|---|---|---|---|---|
| Sex 06/11 | 4.1 | **7 de 7** | Nenhuma | — |
| Seg 09/11 | 5.1 | **12 de 12** | Nenhuma. Medição a confirmar: a redação é a mesma do guia resolvido de 21/10 | — |
| Seg 09/11 | 5.2 | **9 de 10** | E8 em branco (o SUID do `passwd`). Medição a confirmar, pelo mesmo motivo | Não |
| Ter 10/11 | 4.2 | **4 de 4** | Nenhuma (E1 com a saída de exemplo do PDF, não a da sua VM) | — |
| Ter 10/11 | 5.3 | **9 de 11** | G2: espaço depois da vírgula no `chmod` simbólico; E1 em branco (`chmod 4` e `chmod 44`) | Não |
| Qua 11/11 | 4.3, lição 1 | **6 de 6** | Nenhuma (saídas do `which` copiadas do PDF; na VM são `/usr/...`) | — |
| Qua 11/11 | 4.3, lição 2 | **7 de 9** | G3, itens 2 e 3, pesquisados; E3, item 4 (o pendrive some do `/dev`) | Não |
| Qui 12/11 | 4.4 | **7 de 9** | G1 e G3 sem a linha de comando (a confirmar: podem ter sumido na cópia) | — |
| Qui 12/11 | 5.4 | **10 de 10** | Nenhuma | — |
| Sex 13/11 | 3.1 | **8 de 9** | E4: faltou o `tar -xf` depois do `gunzip` | — |
| Sex 13/11 | 3.2, lição 1 | **7 de 12** | G3, G4, G5 (forma do comando), E2 e E5 | Sim: forma dos comandos |
| Seg 16/11 | 3.2, lição 2 | **8 de 9** | G3: `'^. . .dig'` com espaços entre os pontos | Sim: forma dos comandos |
| Seg 16/11 | 3.3, lição 1 | **6 de 7** | G1: `export PATH= "..."`, com espaço depois do `=` | Sim: forma dos comandos |
| Ter 17/11 | 3.3, lição 2 | **3 de 3** | Nenhuma | — |
| Ter 17/11 | 2.1, lição 1 | **5 de 6** | E1: `game{1. .5}`, com espaço entre os pontos | Sim: forma dos comandos |
| Qui 19/11 | 2.3, lição 1 | **7 de 7** | Nenhuma | — |
| Qui 19/11 | 2.3, lição 2 | **5 de 5** | Nenhuma | — |
| Sex 20/11 | 2.1, lição 2 | de 9 | | |
| Sex 20/11 | 2.2 | de 11 | | |
| Sáb 21/11 | 2.4 | de 12 | | |
| Sáb 21/11 | 1.1 | de 8 | | |
| Dom 22/11 | 1.2 | de 11 | | |
| Dom 22/11 | 1.3 | de 10 | | |
| Seg 23/11 | 1.4 | de 8 | | |
| Seg 23/11 | Revisão: erradas dos Tópicos 5 e 4 |  | | |
| Ter 24/11 | Revisão: erradas do Tópico 3 |  | | |
| Qua 25/11 | Revisão: erradas dos Tópicos 2 e 1 e as reincidências |  | | |

---

## 4. Correções

### 5.1 e 5.2 — segunda 09/11

**Medição.** Várias respostas têm a mesma redação do guia resolvido de 21/10 ("Hash não é criptografia reversível", "Remove o cabeçalho, inclusive o resumo", "Nome do grupo, marcador, GID e lista de membros", "/home pode ficar indisponível"). Se o guia foi consultado, as duas lições contam como feitas, mas **não como acertos firmes** (regra 4 da operação). A checagem fica no M1, na quinta 12/11, com questões dos dois temas. Para 5.3 e 5.4, na terça 10/11, **deixe o guia de 21/10 fechado**: ele também traz as respostas dessas lições.

**Lição 5.1 (12 de 12).**

| Exercício | Observação |
| --- | --- |
| G4 | Certo: `w`. Faltou citar onde está a **contagem**: na primeira linha do `w` (por exemplo, `2 users`) |
| G5 | Grafia: o diretório inicial é `/home/emma` (estava "/hpme/emma") |
| E1 | Faltou a segunda metade, o que **falta** em cada um: o `who` não mostra a atividade nem a carga; o `w` não mostra as sessões encerradas; o `last` não mostra o que o usuário está fazendo agora |
| E4 | Certo. Atalho para a prova: `id usuario` ou `groups usuario` mostram todos os grupos de uma vez, inclusive o principal |

**Lição 5.2 (9 de 10).**

| Exercício | Observação |
| --- | --- |
| E1 | Incompleto. Com `CREATE_HOME` e `USERGROUPS_ENAB` em `yes`, o `useradd -m dave` também **cria o grupo `dave`** (em `/etc/group` e `/etc/gshadow`) e **copia o `/etc/skel`** para `/home/dave` |
| E2 | Certo, mas responda a pergunta antes do comando: **não consegue**, porque a conta nasce sem senha (`!` no `/etc/shadow`); o `sudo passwd dave` resolve |
| E3 | Certo. O grupo `dave` não tem membros listados (`dave:x:1006:`): o grupo principal não aparece no quarto campo. O UID 1005 e o GID 1006 ficaram diferentes provavelmente porque o GID 1005 já estava em uso (talvez o grupo `ops`, que ficou da Prática 2); `getent group 1005` confirma |
| E5 | O resultado está certo; anote também o comando: `sudo useradd -m -u 1035 -g sys_admin -G web_admin,db_admin carol` |
| E7 | Grafia das permissões: `-rw-r--r--` e `-rw-r-----`, sempre com 10 caracteres |
| E8 | **Em branco.** O `s` no trio do dono é o **SUID**: o `passwd` roda com o UID efetivo do dono, o root, e por isso um usuário comum consegue gravar a própria senha nova no `/etc/shadow`, que ele não pode ler nem alterar diretamente |

### 4.2 e 5.3 — terça 10/11

**Lição 4.2 (4 de 4).**

| Exercício | Observação |
| --- | --- |
| G2 | Certo. A ressalva sobre a GPU faz sentido: os editores atuais usam a GPU para reproduzir e renderizar o vídeo, então ela pesa, sim, quando o programa tem aceleração por GPU |
| G3 | Certo: `/dev/sdc3` (terceiro disco, `c`; terceira partição, `3`) |
| E1 | A tabela descreve a saída de exemplo do PDF (`mmcblk0`, um cartão SD de Raspberry Pi), não a da sua VM. Rode `lsblk -f` na `lab-ubuntu`: o disco deve aparecer como `sda` ou `vda`, com as partições `sda1`, `sda2` e assim por diante. Grafia: é `mmcblk0` (estava "mmclk0") |

**Lição 5.3 (9 de 11).**

| Exercício | Observação |
| --- | --- |
| G2 | **Errado pela forma.** `chmod u+x, go-wx emptyfile` falha: o espaço depois da vírgula separa os argumentos, e o `chmod` responde `invalid mode: 'u+x,'`. O certo é `chmod u+x,go-wx emptyfile`, tudo junto. A prova cobra exatamente esse tipo de detalhe |
| G4 | Certo, e com a correção do gabarito do PDF (o grupo `root` não é o usuário root; o Linux ignora SUID e SGID em scripts). **Para a prova**, se a pergunta for só sobre o bit: SGID faz o programa rodar com o **GID efetivo do grupo dono** (aqui, `root`), nunca com o UID 0. Grafia: o arquivo é `test.sh` (estava "teste.sh") |
| G6 | As quatro conversões certas: 1755, 0044, 0664 e 2755 |
| E1 | **Em branco.** O `chmod` completa com **zeros à esquerda**: `chmod 4` vale `0004` e dá `-------r--` (só os outros leem); `chmod 44` vale `0044` e dá `----r--r--`. Os dígitos que faltam são sempre os da esquerda (bit especial, dono, grupo, nessa ordem) |
| E4 | Certo: `s` minúsculo tem o bit e o `x`; `S` maiúsculo tem o bit sem o `x` |
| E5 | Certo: `chgrp users Box` e `chmod 3770 Box` dão `drwxrws--T`. O 3 é SGID (2) mais sticky (1), e o `T` maiúsculo aparece porque os outros não têm `x` |

**Medição.** A resposta do G4 segue a mesma correção do gabarito que está no guia resolvido de 21/10. Se o guia foi consultado nesta lição, ela conta como feita, mas não como acertos firmes. O M1, na quinta 12/11, traz questões de 5.1, 5.2 e 5.3 para medir de novo.

### 4.3, lições 1 e 2 — quarta 11/11

**Lição 4.3, lição 1 (6 de 6).**

| Exercício | Observação |
| --- | --- |
| G1 | Certo na classificação. Os caminhos (`/sbin/swapon`, `/bin/kill`, `/bin/ps`) são os do PDF. Na sua VM, com o `/usr` unificado, o `which` mostra `/usr/sbin/swapon`, `/usr/bin/kill` e `/usr/bin/ps`; o `/bin` e o `/sbin` são links para `/usr/bin` e `/usr/sbin`. Detalhe de prova: o `kill` também é **comando interno** do Bash; o `which` mostra o programa em disco, e o `type kill` diz `kill is a shell builtin` |
| G2 | Certo. Grafia: `~/.profile`, sem espaço |
| G3 | Certo: 4 é a versão, 15 a revisão principal, 0 a secundária e 50 o patch |
| E1 | Certo: `/dev/hd*` para IDE e `/dev/nvme*` para NVMe. Grafia: a primeira partição é `/dev/nvme0n1p1` (estava "nvmen1p1") |
| E2 | Certo. Grafia: o campo é `Shmem` (estava "Shemem") |

**Lição 4.3, lição 2 (7 de 9).**

| Exercício | Observação |
| --- | --- |
| G1 | Certo: `top` da carol (PID 887), `/proc/887` e o `systemd` com PID 1, o primeiro a iniciar |
| G2 | Certo: `last` para o `wtmp`, `lastb` (com `sudo`) para o `btmp` e `journalctl` para o journal. Para um arquivo de journal específico: `journalctl --file <caminho>` |
| G3 | **Itens 2 e 3 marcados como pesquisados**, então contam como erro (regra 4). Ótimo ter marcado. A forma simples que a prova espera: `grep sd /var/log/kern.log` e `grep "session opened" /var/log/auth.log \| tail -1`; o `grep` lê o arquivo direto, sem o `cat`. O item 1 está certo: `last \| grep reboot \| head -1` (o `last` já lista do mais recente para o mais antigo) |
| G4 | Certo: `dmesg` e `journalctl -k` |
| G5 | Certo nas quatro mensagens |
| G6 | Certo: `journalctl -u` com o nome da unidade |
| E1 | Certo: `k` e o PID 444 (sinal 15, o padrão), `m` para as barras, `M` para ordenar por memória, `W` para salvar e `~/.config/procps/toprc`. Grafia: sem espaço depois de `~/.` |
| E2 | Certo: o `exec` troca o programa e **mantém o PID** |
| E3 | **Item 4 errado.** Depois de remover o pendrive, o `ls /dev/sd*` **não mostra mais** o `/dev/sdb` nem o `/dev/sdb1`: os arquivos de dispositivo são criados e removidos na hora pelo `udev`. Se o `/dev/sdb1` continuou aparecendo, o pendrive ainda estava conectado à VM |

**Medição.** O G3 marcado como "pesquisado" é exatamente o registro que a operação precisa. Com isso, as lições sem marca contam como firmes. Se nas lições 5.1, 5.2 e 5.3 você não consultou o guia de 21/10, diga e eu tiro a observação de "medição a confirmar".

### 4.4 e 5.4 — quinta 12/11

**Lição 4.4 (7 de 9).**

| Exercício | Observação |
| --- | --- |
| G1 | **Faltam os comandos.** A resposta explica o `ip addr add` e cita "o último comando", mas as linhas não vieram. São: `sudo ip addr add 192.168.10.10/24 dev ens33` e `sudo ip addr add 2001:0:0:abcd:0:8a2e:0370:7334/64 dev ens33`; para conferir, `ip addr show ens33`. Se no seu caderno os comandos estão lá e só sumiram ao copiar (como já aconteceu com o Notion), a lição vira 8 de 9 |
| G2 | Certo: `192.168.10.1`, `172.16.57.47` e `10.100.49.162` são privados (faixas `10.0.0.0/8`, `172.16.0.0/12` e `192.168.0.0/16`) |
| G3 | **Falta a linha.** A explicação está certa (o IP vem primeiro), mas a resposta pedida é a própria linha: `192.168.0.15 example.com`. Mesmo caso do G1: se ela estava num bloco de código, confirme |
| G4 | Certo: rota padrão IPv6 pelo gateway `2001:db8:0:abcd::1` |
| E1 | Certo: TXT, PTR, CNAME e MX. Para a prova, junte os outros dois: **A** (nome para IPv4) e **AAAA** (nome para IPv6) |
| E2 | Certo: a *bridge* liga interfaces na camada de enlace, como um switch |
| E3 | Certo: `ss -u`. Sem `-a` ou `-l`, o `ss` mostra só os sockets estabelecidos |
| E4 | Certo: `ss -s` |
| E5 | Certo: 4 TCP e 7 UDP, total 11 |

**Lição 5.4 (10 de 10).** Os cinco Guiados e os cinco Exploratórios certos (a pergunta do `ls -lah` conta como os Exploratórios 3, 4 e 5). Destaques: o hard link como "outro nome para o mesmo inode", o `Invalid cross-device link` e o `ls -li` para comparar inodes. No E1, a resposta cobre as duas leituras do enunciado, o que está ótimo: com `ln -s recipes.txt rezepte.txt`, apagar `receitas.txt` não afeta o link simbólico.

### 3.1 e 3.2, lição 1 — sexta 13/11

**Lição 3.1 (8 de 9).**

| Exercício | Observação |
| --- | --- |
| G1 a G5 | Certos. Destaque para o G3 (`gunzip`, `tar -rf`, `gzip`: o `tar` não acrescenta dentro de um pacote comprimido) e o G4 (`-P`, `--absolute-names`) |
| E1 | Certo: `--wildcards`, com o padrão entre aspas. Grafia: GNU tar |
| E2 | Certo: o gzip, o bzip2 e o xz conferem a integridade ao descomprimir (também dá para testar antes com `gzip -t`); para comparar com o original, `cmp` |
| E3 | Certo: sobrescreve. Com `-k` (`--keep-old-files`), o `tar` não sobrescreve |
| E4 | **Incompleto.** O `gunzip archive.tgz` só tira a compressão e deixa `archive.tar`; falta extrair: `tar -xf archive.tar`. Em uma linha: `gunzip -c archive.tgz \| tar -xf -` (ou `zcat archive.tgz \| tar -xf -`) |

**Lição 3.2, lição 1 (7 de 12).** Os acertos (G1, G2, G6, G7, E1, E3 e E4) mostram que o raciocínio do redirecionamento está certo. Os cinco erros são todos de **montagem do comando**: o tipo de detalhe que a prova cobra nas alternativas.

| Exercício | Observação |
| --- | --- |
| G3 | **Errado.** `tail -n 10 /etc/passwd > ~/Documents` tenta gravar **no diretório**, e o shell responde `Is a directory`. O destino precisa ser um arquivo: `tail -n 10 /etc/passwd > ~/Documents/ultimas.txt` |
| G4 | **Errado pela forma.** `~/contents` não existe: o arquivo é `~/contents.txt`. Certo: `wc -w < ~/contents.txt >> ~/field2.txt` |
| G5 | **Errado pela forma.** `head -5 n /etc/passwd` faz o `head` procurar um arquivo chamado `n`. Certo: `head -n 5 /etc/passwd \| sort -r` (ou `head -5`, sem o `n`) |
| E1 | Certo na ideia. Grafia: o destino pedido é `field1.txt`. Atenção: no `ls -l` as colunas são separadas por **vários** espaços, por isso o `-f 2` com `-d ' '` pode pegar campos vazios; o E5 resolve isso com `tr -s ' '` |
| E2 | **Errado.** A resposta é de outro exercício. O pedido era tirar os hífens com `tr` e redirecionamento de **entrada**: `tr -d '-' < ~/contents.txt` |
| E5 | **Errado.** Faltou o `cut`, e o `-f 9` foi parar no `tr`, que não tem essa opção. Certo: `tr -s ' ' < ~/contents.txt \| cut -d ' ' -f 9 \| sort -fr`, com **dois pipes** (ou `cat ~/contents.txt \| tr -s ' ' \| cut -d ' ' -f 9 \| sort -fr`, com três). A pergunta "quantos pipes" ficou sem resposta |

Aspas: o caderno tem aspas curvas (`‘test’`) nos comandos. No terminal, só as retas: `'test'`.

**Treino na VM (domingo 15/11).** Rode os cinco comandos corrigidos (G3, G4, G5, E2 e E5) na `lab-ubuntu`, de memória, a partir de um `ls -l > ~/contents.txt`. É o bloco de VM do domingo.

### 3.2, lição 2 e 3.3, lição 1 — segunda 16/11

**Lição 3.2, lição 2 (8 de 9).**

| Exercício | Observação |
| --- | --- |
| G1, G2, G4, G5 e G6 | Certos, com as explicações das classes `[...]`, do `-v`, do `+`, do `\|` com `-E` e do `?` com `-c`. O G6 (`grep -cE '^c?ati'`) é exatamente o tipo de detalhe da prova |
| G3 | **Errado pela forma.** No caderno está `'^. . .dig'`, com espaço entre os pontos: assim o `grep` exige espaços de verdade na linha e não acha nada. O certo é `'^...dig'`, os três pontos juntos. Se o espaço foi só formatação do Notion (ele às vezes troca `...` por `. . .`), me avise que a lição vira 9 de 9. O mesmo vale para o E3 (`'^....rwx'`) |
| E1 | Certo nos cinco grupos (`pot$`, `arc\|cap\|zoo`, `[0-9]th.+`, `^[A-Z]a.*i+`). No grupo B, escreva `p+` (com `-E`) ou `pp*`: o `p++` funciona no GNU grep, mas é uma repetição dobrada que a prova não usa |
| E2 | Certo: `sed`, com o exemplo `s/cat/dog/g` |
| E3 | Certo na ideia: filtrar a saída do `tr` com o `grep` |

**Lição 3.3, lição 1 (6 de 7).**

| Exercício | Observação |
| --- | --- |
| G1 | **Errado pela forma.** `export PATH= "$PATH:$HOME/scripts"` tem um espaço depois do `=`. O shell lê dois argumentos: `PATH=` (que **esvazia** o `PATH`) e `"$PATH:..."`, que não é um nome válido. O certo é sem espaço: `export PATH="$PATH:$HOME/scripts"`. A explicação (o `PATH=~/scripts` substituiu a lista inteira) está certa. É o mesmo erro do `chmod u+x, go-wx` da 5.3: espaço muda o significado |
| G2 | Certo nas regras (`#!`, `=` sem espaço, espaços dentro do `[ ]`, aspas duplas, `fi`). Para fixar, escreva as linhas corrigidas na VM: `#!/bin/bash`, `fruit1=Apples`, `fruit2=Oranges`, `elif [ $1 -gt $2 ]`, `echo "$fruit1 win!"`, `echo "$fruit2 win!"` e `fi` |
| G3 | Certo nas três execuções, inclusive o `$#` valendo 2. Grafia: a saída usa as variáveis, então é `Apples and Oranges`, com maiúsculas |
| E1 | Certo: `[ "$#" -eq 2 ]` e a ordem invertida dos argumentos |
| E2 | Certo, e com um ótimo exemplo: `[ "01" == "1" ]` é falso e `[ "01" -eq "1" ]` é verdadeiro |
| E3 | Certo: `env \| grep '^PWD='` |
| E4 | Certo: compara com `"$PWD"` e testa o número de argumentos |

### 3.3, lição 2 e 2.1, lição 1 — terça 17/11

**Lição 3.3, lição 2 (3 de 3).** O G1 está perfeito: os três códigos de saída (1, 2 e 0) e o porquê de cada um, inclusive o `grep` devolvendo 1 quando não acha nada. O G2 identifica o `$1` como o diretório. O E1 funciona e trata o texto `texto` antes de comparar; o `[[ ... =~ ... ]]` vai além da prova, mas está certo.

**Lição 2.1, lição 1 (5 de 6).**

| Exercício | Observação |
| --- | --- |
| G1 a G3 | Certos, inclusive o `ls -l -a` sem argumento (usa o diretório atual) e as aspas duplas que expandem o `$USER` em um só argumento |
| E1 | **Errado pela forma.** No caderno está `touch game{1. .5}`, com espaço entre os pontos: assim o Bash não reconhece a sequência e cria um arquivo chamado `game{1.` e outro chamado `.5}`. O certo é `touch game{1..5}`, os dois pontos juntos. É a segunda vez que os pontos aparecem separados (a primeira foi o `'^. . .dig'` da 3.2). Confira na VM se é assim que você digita ou se é o Notion que separa |
| E2 | Certo: `rm game[1-5]` (também vale `rm game*` ou `rm game?`) |
| E3 | Certo: pipe e arquivo intermediário. A terceira forma é a substituição de comando: `echo "Hoje: $(date)"` |

### 2.3, lições 1 e 2 — quinta 19/11

**Lição 2.3, lição 1 (7 de 7).** Os quatro Guiados e os três Exploratórios certos, inclusive o rastreamento do G4 (`cd ../../systemd/user` e `cd ..` terminam em `/etc/systemd`) e o E3 com o `--` para proteger o nome com barra invertida. Grafias: `rules.d` e `udev.conf`. No E2, o Tab completa um **diretório** com uma barra no fim: `cd this\ is\ a\ test/`.

**Lição 2.3, lição 2 (5 de 5).** Certos. Grafia: é `~michael/Music`. No G2 A, a primeira linha do `ls -lrS` é um dos diretórios de `4.0K`, porque o `-S` ordena todas as entradas, inclusive diretórios; o primeiro **arquivo comum** é o `scary.jpg`, como você escreveu.

**Os pontos e hífens separados.** No E3 apareceu `- -` no lugar de `--`, como já tinha aparecido `. . .` no lugar de `...` (LPI 3.2, lição 2) e `{1. .5}` no lugar de `{1..5}` (LPI 2.1, lição 1). Parece ser para o Notion não transformar `--` em travessão e `...` em reticências. Se for isso, as duas lições sobem para 9 de 9 e 6 de 6, e esses três casos saem da reincidência de forma. Uma saída simples: no Notion, escreva os comandos dentro de crase (`` `{1..5}` ``) ou num bloco de código, que ele não altera.