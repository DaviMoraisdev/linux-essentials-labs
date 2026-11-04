# Exercícios da LPI — todas as lições do exame 010-160

**Criado em:** 03/11/2026 · **Fonte:** LPI Learning Material, Linux Essentials versão 1.6, em português (o PDF do Projeto) · **Uso:** um bloco por dia na operação prática (`labs/operacao-pratica.md`)

São as **24 lições** do material oficial, com cerca de **205 exercícios** (Guiados e Exploratórios). É o único banco de questões escrito pela própria LPI. Os enunciados e as respostas ficam no PDF; este arquivo diz **o que fazer em cada dia**, onde estão as páginas e onde anotar os erros.

## Como fazer

| Passo | Detalhe |
|---|---|
| 1. Responder | Abra a página dos exercícios no PDF e responda **sem consultar o texto da lição**, por escrito, no caderno |
| 2. Conferir | Só depois abra "Respostas aos Exercícios" (página indicada) e compare |
| 3. Anotar | Na tabela da seção 3, só as **erradas**, com o número (G3, E2) e uma linha sobre o que estava errado |
| 4. Executar | Se o erro for sobre um comando, rode-o na VM antes de seguir |
| Tempo | **25 a 30 minutos** por bloco. Acabou o tempo, acabou o bloco: o que sobrar não vira pendência |
| Exploratórios | Fazem parte do bloco, mas, se o tempo apertar, os Guiados vêm primeiro |

**Ordem.** O Tópico 5 vem primeiro, porque foi o mais fraco no simulado 02 (3 de 7); o Tópico 4 em seguida, enquanto as Práticas 3 a 5 estão frescas; depois os Tópicos 3 e 2; e o Tópico 1, o mais firme, fecha a série. Quando um bloco cai no mesmo dia de um mini-simulado do mesmo tema, um reforça o outro (o 5.1 com o R4, o 4.4 com o R2, o 3.1 com o R1).

**As lições 5.1 a 5.4 já foram feitas em 21/10**, com um guia resolvido. Agora é para responder **sem olhar o guia**: é a medição que faltou naquele dia.

---

## 1. Calendário

| Dia | Lições | Exercícios | Páginas dos exercícios | Páginas das respostas |
|---|---|---|---|---|
| Ter 03/11 | 4.3, lição 1 e 4.3, lição 2 | G4 E2 + G6 E3 | 303 e 305 · 321 e 324 | 308 e 310 · 328 e 332 |
| Qua 04/11 | 5.1 | G5 E7 | 372 e 374 | 377 e 379 |
| Qui 05/11 | 5.2 | G2 E8 | 391 e 393 | 395 e 397 |
| Sex 06/11 | 4.1 e 4.2 | G5 E2 + G3 E1 | 264 e 266 · 283 e 284 | 268 e 270 · 286 e 288 |
| Sáb 07/11 | 5.3 | G6 E5 | 416 e 418 | 420 e 423 |
| Seg 09/11 | 4.4 | G4 E5 | 349 e 350 | 352 e 353 |
| Ter 10/11 | 5.4 | G5 E5 | 434 e 435 | 439 e 440 |
| Qua 11/11 | 3.1 | G5 E4 | 183 e 184 | 187 e 189 |
| Qui 12/11 | 2.1, lição 1 | G3 E3 | 82 e 84 | 86 e 87 |
| Sex 13/11 | 2.1, lição 2 | G4 E5 | 94 e 95 | 97 e 98 |
| Sáb 14/11 | 2.2 | G6 E5 | 107 e 109 | 111 e 114 |
| Seg 16/11 | 2.3, lição 1 e 2.3, lição 2 | G4 E3 + G2 E3 | 122 e 124 · 139 e 141 | 126 e 129 · 143 e 145 |
| Ter 17/11 | 3.3, lição 1 e 3.3, lição 2 | G3 E4 + G2 E1 | 229 e 231 · 247 e 249 | 234 e 236 · 251 e 253 |
| Qua 18/11 | 2.4 | G7 E5 | 162 e 164 | 167 e 170 |
| Qui 19/11 | 3.2, lição 1 | G7 E5 | 199 e 200 | 202 e 204 |
| Sex 20/11 | 3.2, lição 2 | G6 E3 | 210 e 211 | 213 e 215 |
| Sáb 21/11 | 1.1 | G5 E3 | 8 e 9 | 11 e 13 |
| Seg 23/11 | 1.2 | G7 E4 | 30 e 32 | 34 e 36 |
| Ter 24/11 | 1.4 | G5 E3 | 66 e 68 | 70 e 72 |
| Qua 25/11 | 1.3 | G5 E5 | 48 e 49 | 51 e 52 |

"G5 E3" = 5 Guiados e 3 Exploratórios (contagem aproximada). As páginas são as impressas no rodapé do PDF.

**Terça 03/11:** o 4.3 (lições 1 e 2) é a lista que você montou na Prática 4. Se não saiu hoje, ele vai para a quinta 26/11, o dia leve, e não para outro dia da operação.

---

## 2. As 24 lições

| Lição | Tema | Exercícios | Dia |
|---|---|---|---|
| 1.1 | A evolução do Linux e sistemas operacionais populares | G5 E3 | Sáb 21/11 |
| 1.2 | Principais aplicações open source | G7 E4 | Seg 23/11 |
| 1.3 | Software open source e suas licenças | G5 E5 | Qua 25/11 |
| 1.4 | Habilidades ICT e trabalhando no Linux | G5 E3 | Ter 24/11 |
| 2.1, lição 1 | O básico sobre a linha de comando | G3 E3 | Qui 12/11 |
| 2.1, lição 2 | O básico sobre a linha de comando (variáveis) | G4 E5 | Sex 13/11 |
| 2.2 | Usando a linha de comando para conseguir ajuda | G6 E5 | Sáb 14/11 |
| 2.3, lição 1 | Usando diretórios e listando arquivos | G4 E3 | Seg 16/11 |
| 2.3, lição 2 | Usando diretórios e listando arquivos (caminhos e ocultos) | G2 E3 | Seg 16/11 |
| 2.4 | Criando, movendo e deletando arquivos | G7 E5 | Qua 18/11 |
| 3.1 | Empacotando arquivos na linha de comando | G5 E4 | Qua 11/11 |
| 3.2, lição 1 | Redirecionamento e pipes | G7 E5 | Qui 19/11 |
| 3.2, lição 2 | `grep` e expressões regulares | G6 E3 | Sex 20/11 |
| 3.3, lição 1 | Transformando comandos em scripts | G3 E4 | Ter 17/11 |
| 3.3, lição 2 | Códigos de saída, argumentos e `for` | G2 E1 | Ter 17/11 |
| 4.1 | Escolhendo um sistema operacional | G5 E2 | Sex 06/11 |
| 4.2 | Entendendo o hardware do computador | G3 E1 | Sex 06/11 |
| 4.3, lição 1 | Onde os dados são armazenados: programas, configuração e processos | G4 E2 | Ter 03/11 |
| 4.3, lição 2 | Onde os dados são armazenados: logs e mensagens do sistema | G6 E3 | Ter 03/11 |
| 4.4 | Seu computador na rede | G4 E5 | Seg 09/11 |
| 5.1 | Segurança básica e tipos de usuários | G5 E7 | Qua 04/11 |
| 5.2 | Criando usuários e grupos | G2 E8 | Qui 05/11 |
| 5.3 | Gerenciando permissões e propriedade de arquivos | G6 E5 | Sáb 07/11 |
| 5.4 | Diretórios e arquivos especiais | G5 E5 | Ter 10/11 |

---

## 3. Registro

Só as erradas. "Reincidência" quando o mesmo erro já apareceu em simulado, mini-simulado ou correção numerada; nesse caso, card no Notion.

| Dia | Lição | Acertos | Erradas (número e o que estava errado) | Reincidência? |
|---|---|---|---|---|
| Ter 03/11 | 4.3, lição 1 | de 6 | | |
| Ter 03/11 | 4.3, lição 2 | de 9 | | |
| Qua 04/11 | 5.1 | de 12 | | |
| Qui 05/11 | 5.2 | de 10 | | |
| Sex 06/11 | 4.1 | de 7 | | |
| Sex 06/11 | 4.2 | de 4 | | |
| Sáb 07/11 | 5.3 | de 11 | | |
| Seg 09/11 | 4.4 | de 9 | | |
| Ter 10/11 | 5.4 | de 10 | | |
| Qua 11/11 | 3.1 | de 9 | | |
| Qui 12/11 | 2.1, lição 1 | de 6 | | |
| Sex 13/11 | 2.1, lição 2 | de 9 | | |
| Sáb 14/11 | 2.2 | de 11 | | |
| Seg 16/11 | 2.3, lição 1 | de 7 | | |
| Seg 16/11 | 2.3, lição 2 | de 5 | | |
| Ter 17/11 | 3.3, lição 1 | de 7 | | |
| Ter 17/11 | 3.3, lição 2 | de 3 | | |
| Qua 18/11 | 2.4 | de 12 | | |
| Qui 19/11 | 3.2, lição 1 | de 12 | | |
| Sex 20/11 | 3.2, lição 2 | de 9 | | |
| Sáb 21/11 | 1.1 | de 8 | | |
| Seg 23/11 | 1.2 | de 11 | | |
| Ter 24/11 | 1.4 | de 8 | | |
| Qua 25/11 | 1.3 | de 10 | | |