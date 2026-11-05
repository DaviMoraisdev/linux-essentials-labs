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

**Refeito em 04/11**, com mais exercícios por semana: **dois blocos nos dias B** e um nos dias A. As 24 lições terminam em 20/11. De 21 a 25/11, cada bloco **refaz as questões que você errou**, tópico a tópico, sem olhar a resposta antes.

| Dia | Lições | Exercícios (aprox.) | Páginas dos exercícios | Páginas das respostas |
|---|---|---|---|---|
| Qui 05/11 | 4.3, lição 1 e 4.3, lição 2 e 5.1 | 6 + 9 + 12 | 303–305 · 321–324 · 372–374 | 308–310 · 328–332 · 377–379 |
| Sex 06/11 | 4.1 e 4.2 | 7 + 4 | 264–266 · 283–284 | 268–270 · 286–288 |
| Sáb 07/11 | 5.3 | 11 | 416–418 | 420–423 |
| Seg 09/11 | 5.2 e 4.4 | 10 + 9 | 391–393 · 349–350 | 395–397 · 352–353 |
| Ter 10/11 | 5.4 | 10 | 434–435 | 439–440 |
| Qua 11/11 | 3.1 e 2.1, lição 1 | 9 + 6 | 183–184 · 82–84 | 187–189 · 86–87 |
| Qui 12/11 | 2.1, lição 2 | 9 | 94–95 | 97–98 |
| Sex 13/11 | 2.2 e 2.3, lição 1 | 11 + 7 | 107–109 · 122–124 | 111–114 · 126–129 |
| Sáb 14/11 | 2.3, lição 2 | 5 | 139–141 | 143–145 |
| Seg 16/11 | 2.4 e 3.2, lição 1 | 12 + 12 | 162–164 · 199–200 | 167–170 · 202–204 |
| Ter 17/11 | 3.2, lição 2 | 9 | 210–211 | 213–215 |
| Qua 18/11 | 3.3, lição 1 e 3.3, lição 2 e 1.1 | 7 + 3 + 8 | 229–231 · 247–249 · 8–9 | 234–236 · 251–253 · 11–13 |
| Qui 19/11 | 1.2 | 11 | 30–32 | 34–36 |
| Sex 20/11 | 1.3 e 1.4 | 10 + 8 | 48–49 · 66–68 | 51–52 · 70–72 |
| Sáb 21/11 | **Revisão: erradas do Tópico 5** | As erradas da seção 3 | — | — |
| Seg 23/11 | **Revisão: erradas do Tópico 4** | As erradas da seção 3 | — | — |
| Ter 24/11 | **Revisão: erradas dos Tópicos 3 e 2** | As erradas da seção 3 | — | — |
| Qua 25/11 | **Revisão: erradas do Tópico 1** | As erradas da seção 3 | — | — |

As páginas são as impressas no rodapé do PDF.

---

## 2. As 24 lições

| Lição | Tema | Exercícios | Dia |
|---|---|---|---|
| 1.1 | A evolução do Linux e sistemas operacionais populares | G5 E3 | Qua 18/11 |
| 1.2 | Principais aplicações open source | G7 E4 | Qui 19/11 |
| 1.3 | Software open source e suas licenças | G5 E5 | Sex 20/11 |
| 1.4 | Habilidades ICT e trabalhando no Linux | G5 E3 | Sex 20/11 |
| 2.1, lição 1 | O básico sobre a linha de comando | G3 E3 | Qua 11/11 |
| 2.1, lição 2 | O básico sobre a linha de comando (variáveis) | G4 E5 | Qui 12/11 |
| 2.2 | Usando a linha de comando para conseguir ajuda | G6 E5 | Sex 13/11 |
| 2.3, lição 1 | Usando diretórios e listando arquivos | G4 E3 | Sex 13/11 |
| 2.3, lição 2 | Usando diretórios e listando arquivos (caminhos e ocultos) | G2 E3 | Sáb 14/11 |
| 2.4 | Criando, movendo e deletando arquivos | G7 E5 | Seg 16/11 |
| 3.1 | Empacotando arquivos na linha de comando | G5 E4 | Qua 11/11 |
| 3.2, lição 1 | Redirecionamento e pipes | G7 E5 | Seg 16/11 |
| 3.2, lição 2 | `grep` e expressões regulares | G6 E3 | Ter 17/11 |
| 3.3, lição 1 | Transformando comandos em scripts | G3 E4 | Qua 18/11 |
| 3.3, lição 2 | Códigos de saída, argumentos e `for` | G2 E1 | Qua 18/11 |
| 4.1 | Escolhendo um sistema operacional | G5 E2 | Sex 06/11 |
| 4.2 | Entendendo o hardware do computador | G3 E1 | Sex 06/11 |
| 4.3, lição 1 | Onde os dados são armazenados: programas, configuração e processos | G4 E2 | Qui 05/11 |
| 4.3, lição 2 | Onde os dados são armazenados: logs e mensagens do sistema | G6 E3 | Qui 05/11 |
| 4.4 | Seu computador na rede | G4 E5 | Seg 09/11 |
| 5.1 | Segurança básica e tipos de usuários | G5 E7 | Qui 05/11 |
| 5.2 | Criando usuários e grupos | G2 E8 | Seg 09/11 |
| 5.3 | Gerenciando permissões e propriedade de arquivos | G6 E5 | Sáb 07/11 |
| 5.4 | Diretórios e arquivos especiais | G5 E5 | Ter 10/11 |

---

## 3. Registro

Só as erradas. "Reincidência" quando o mesmo erro já apareceu em simulado, mini-simulado ou correção numerada; nesse caso, card no Notion.

| Dia | Lição | Acertos | Erradas (número e o que estava errado) | Reincidência? |
|---|---|---|---|---|
| Qui 05/11 | 4.3, lição 1 | de 6 | | |
| Qui 05/11 | 4.3, lição 2 | de 9 | | |
| Qui 05/11 | 5.1 | de 12 | | |
| Sex 06/11 | 4.1 | de 7 | | |
| Sex 06/11 | 4.2 | de 4 | | |
| Sáb 07/11 | 5.3 | de 11 | | |
| Seg 09/11 | 5.2 | de 10 | | |
| Seg 09/11 | 4.4 | de 9 | | |
| Ter 10/11 | 5.4 | de 10 | | |
| Qua 11/11 | 3.1 | de 9 | | |
| Qua 11/11 | 2.1, lição 1 | de 6 | | |
| Qui 12/11 | 2.1, lição 2 | de 9 | | |
| Sex 13/11 | 2.2 | de 11 | | |
| Sex 13/11 | 2.3, lição 1 | de 7 | | |
| Sáb 14/11 | 2.3, lição 2 | de 5 | | |
| Seg 16/11 | 2.4 | de 12 | | |
| Seg 16/11 | 3.2, lição 1 | de 12 | | |
| Ter 17/11 | 3.2, lição 2 | de 9 | | |
| Qua 18/11 | 3.3, lição 1 | de 7 | | |
| Qua 18/11 | 3.3, lição 2 | de 3 | | |
| Qua 18/11 | 1.1 | de 8 | | |
| Qui 19/11 | 1.2 | de 11 | | |
| Sex 20/11 | 1.3 | de 10 | | |
| Sex 20/11 | 1.4 | de 8 | | |
| Sáb 21/11 | Revisão: erradas do Tópico 5 | | | |
| Seg 23/11 | Revisão: erradas do Tópico 4 | | | |
| Ter 24/11 | Revisão: erradas dos Tópicos 3 e 2 | | | |
| Qua 25/11 | Revisão: erradas do Tópico 1 | | | |