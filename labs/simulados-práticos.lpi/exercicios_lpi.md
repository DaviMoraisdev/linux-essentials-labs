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

**Refeito em 08/11**, com a carga maior: **duas ou três lições por dia**, de 09 a 18/11, incluindo os domingos 15 e 22. As cinco lições atrasadas (4.2, 4.3 nas duas lições, 5.1 e 5.3) entraram de 09 a 11/11, junto com as outras do mesmo tópico. De 19 a 25/11, cada bloco **refaz as questões que você errou**, tópico a tópico, e o que errar de novo na revisão volta em 24 e 25/11.

| Dia | Lições | Exercícios (aprox.) | Páginas dos exercícios | Páginas das respostas |
|---|---|---|---|---|
| Sex 06/11 | 4.1 | 7 | 264–266 | 268–270 |
| Seg 09/11 | 5.1 e 5.2 | 12 + 10 | 372–374 · 391–393 | 377–379 · 395–397 |
| Ter 10/11 | 4.2 e 5.3 | 4 + 11 | 283–284 · 416–418 | 286–288 · 420–423 |
| Qua 11/11 | 4.3, lição 1 e 4.3, lição 2 | 6 + 9 | 303–305 · 321–324 | 308–310 · 328–332 |
| Qui 12/11 | 4.4 e 3.1 e 5.4 | 9 + 9 + 10 | 349–350 · 183–184 · 434–435 | 352–353 · 187–189 · 439–440 |
| Sex 13/11 | 3.2, lição 1 e 3.2, lição 2 | 12 + 9 | 199–200 · 210–211 | 202–204 · 213–215 |
| Sáb 14/11 | 3.3, lição 1 e 3.3, lição 2 e 2.1, lição 1 | 7 + 3 + 6 | 229–231 · 247–249 · 82–84 | 234–236 · 251–253 · 86–87 |
| Dom 15/11 | 2.1, lição 2 e 2.2 | 9 + 11 | 94–95 · 107–109 | 97–98 · 111–114 |
| Seg 16/11 | 2.3, lição 1 e 2.3, lição 2 e 2.4 | 7 + 5 + 12 | 122–124 · 139–141 · 162–164 | 126–129 · 143–145 · 167–170 |
| Ter 17/11 | 1.1 e 1.2 | 8 + 11 | 8–9 · 30–32 | 11–13 · 34–36 |
| Qua 18/11 | 1.3 e 1.4 | 10 + 8 | 48–49 · 66–68 | 51–52 · 70–72 |
| Qui 19/11 | **Revisão: erradas do Tópico 5** | As erradas da seção 3 | — | — |
| Sex 20/11 | **Revisão: erradas do Tópico 4** | As erradas da seção 3 | — | — |
| Sáb 21/11 | **Revisão: erradas do Tópico 3** | As erradas da seção 3 | — | — |
| Dom 22/11 | **Revisão: erradas do Tópico 2** | As erradas da seção 3 | — | — |
| Seg 23/11 | **Revisão: erradas do Tópico 1** | As erradas da seção 3 | — | — |
| Ter 24/11 | **Revisão: as que errou de novo na revisão** | As erradas da seção 3 | — | — |
| Qua 25/11 | **Revisão: as reincidências da LPI** | As erradas da seção 3 | — | — |

As páginas são as impressas no rodapé do PDF.

---

## 2. As 24 lições

| Lição | Tema | Exercícios | Dia |
|---|---|---|---|
| 1.1 | A evolução do Linux e sistemas operacionais populares | G5 E3 | Ter 17/11 |
| 1.2 | Principais aplicações open source | G7 E4 | Ter 17/11 |
| 1.3 | Software open source e suas licenças | G5 E5 | Qua 18/11 |
| 1.4 | Habilidades ICT e trabalhando no Linux | G5 E3 | Qua 18/11 |
| 2.1, lição 1 | O básico sobre a linha de comando | G3 E3 | Sáb 14/11 |
| 2.1, lição 2 | O básico sobre a linha de comando (variáveis) | G4 E5 | Dom 15/11 |
| 2.2 | Usando a linha de comando para conseguir ajuda | G6 E5 | Dom 15/11 |
| 2.3, lição 1 | Usando diretórios e listando arquivos | G4 E3 | Seg 16/11 |
| 2.3, lição 2 | Usando diretórios e listando arquivos (caminhos e ocultos) | G2 E3 | Seg 16/11 |
| 2.4 | Criando, movendo e deletando arquivos | G7 E5 | Seg 16/11 |
| 3.1 | Empacotando arquivos na linha de comando | G5 E4 | Qui 12/11 |
| 3.2, lição 1 | Redirecionamento e pipes | G7 E5 | Sex 13/11 |
| 3.2, lição 2 | `grep` e expressões regulares | G6 E3 | Sex 13/11 |
| 3.3, lição 1 | Transformando comandos em scripts | G3 E4 | Sáb 14/11 |
| 3.3, lição 2 | Códigos de saída, argumentos e `for` | G2 E1 | Sáb 14/11 |
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
| Qua 11/11 | 4.3, lição 1 | de 6 |  |  |
| Qua 11/11 | 4.3, lição 2 | de 9 |  |  |
| Qui 12/11 | 4.4 | de 9 |  |  |
| Qui 12/11 | 3.1 | de 9 |  |  |
| Qui 12/11 | 5.4 | de 10 |  |  |
| Sex 13/11 | 3.2, lição 1 | de 12 |  |  |
| Sex 13/11 | 3.2, lição 2 | de 9 |  |  |
| Sáb 14/11 | 3.3, lição 1 | de 7 |  |  |
| Sáb 14/11 | 3.3, lição 2 | de 3 |  |  |
| Sáb 14/11 | 2.1, lição 1 | de 6 |  |  |
| Dom 15/11 | 2.1, lição 2 | de 9 |  |  |
| Dom 15/11 | 2.2 | de 11 |  |  |
| Seg 16/11 | 2.3, lição 1 | de 7 |  |  |
| Seg 16/11 | 2.3, lição 2 | de 5 |  |  |
| Seg 16/11 | 2.4 | de 12 |  |  |
| Ter 17/11 | 1.1 | de 8 |  |  |
| Ter 17/11 | 1.2 | de 11 |  |  |
| Qua 18/11 | 1.3 | de 10 |  |  |
| Qua 18/11 | 1.4 | de 8 |  |  |
| Qui 19/11 | Revisão: erradas do Tópico 5 | | | |
| Sex 20/11 | Revisão: erradas do Tópico 4 | | | |
| Sáb 21/11 | Revisão: erradas do Tópico 3 | | | |
| Dom 22/11 | Revisão: erradas do Tópico 2 | | | |
| Seg 23/11 | Revisão: erradas do Tópico 1 | | | |
| Ter 24/11 | Revisão: as que errou de novo na revisão | | | |
| Qua 25/11 | Revisão: as reincidências da LPI | | | |

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