# Semana 8 — Dívidas da Semana 7, simulado 02 e reforço

Período: 19/10 a 25/10/2026 (segunda a domingo)
Objetivos da prova: Tópico 5 (consolidação) e os erros dos Tópicos 1 a 3 apontados pelo simulado 02
**Data da prova: segunda-feira, 23/11/2026**
Marco da semana: **dívidas fechadas no domingo 25/10, sem exceção**. O Tópico 4, as aulas 41 a 72 e o Checkpoint B foram para a Semana 9 (`labs/semana-09.md`)

**Refeito em 23/10.** O simulado 02 saiu na sexta: **22 de 40, com 17 firmes**, abaixo da meta de 24. Os erros se concentraram em conteúdo já estudado (navegação e ajuda no Tópico 2; contas e permissões no Tópico 5), e quatro deles repetem correções antigas. Por isso o fim de semana ficou só para corrigir esses erros e medir a correção com dois reforços novos, R3 e R4. Conteúdo novo e aulas começam na segunda 26/10.

---

## Calendário da semana

| Dia | Atividade | Tempo |
|---|---|---|
| Ter 20 | Prática 2, blocos 5 e 6 | **feito** |
| Qua 21 | Exercícios da LPI 5.1 a 5.4 resolvidos | **feito** |
| Qui 22 | Cards 60 a 70 no Notion e correções das Práticas 1 e 2 no caderno | **feito** |
| Sex 23 | **Simulado 02**: 22 de 40 | **feito** |
| **Sáb 24** | Autoavaliação da Semana 6 · cards do simulado 02 · ajustes e cards que faltam · cola de permissões | cerca de 2h10 |
| **Dom 25** | **R4** e **R3** · erros dos reforços no Notion | cerca de 1h40 |

---

## Mapa das dívidas até domingo 25/10 (limite)

Só ficou o que é **conteúdo da prova**. Domingo é o limite: o que não fechar até lá **sai do plano**, não passa para a Semana 9.

### Sábado 24/10

| Ordem | Atividade | Tempo | Por que é relevante |
|---|---|---|---|
| 1 | **Autoavaliação da Semana 6**, sem consulta, **antes** dos cards (questões em `labs/semana-07.md`, seção 6) | 30 min | Mede o Tópico 5 antes da correção: as questões 2, 3, 7, 8 e 9 cobrem exatamente os erros 34, 36, 37 e 38 do simulado |
| 2 | **Cards do simulado 02**: 14 erros em conteúdo estudado, com o erro, o certo e o mecanismo já escritos em `simulado-02.md`, seção "O que escrever em cada card" | 50 min | São os erros que derrubaram o simulado. Cinco deles são reincidência |
| 3 | **Ajustes nos cards já anotados**: 65 (`/user` vira `/usr`), 69 (falta o "não") e 70 (o "Mecanismo" certo: `?` casa exatamente um caractere qualquer; `{}` é expansão do shell, não globbing) | 5 min | Card errado ensina errado na revisão final |
| 4 | **Cards 71 a 75** e os dois sem número que restam (`x` em diretório; 4644) | 25 min | Variáveis, aspas, `locate`, `type` e campos do `passwd` são cobrados no exame. O card da Q6 da autoavaliação da Semana 5 (`$#`) foi **absorvido** pelo card da Q24 do simulado 02 |
| 5 | **`cheatsheets/permissoes.md`**, escrito à mão: octal nos dois sentidos, simbólico, SUID/SGID/sticky com `s`/`S` e `t`/`T`, `r`/`w`/`x` em diretório | 20 min | É a cola da revisão final, e permissões foi o tema com menos acertos (2 de 5) |

### Domingo 25/10

| Ordem | Atividade | Tempo | Por que é relevante |
|---|---|---|---|
| 1 | **R4** — contas e permissões, 20 questões, 25 min, e apuração (10 min) | 35 min | Testa se os cards do Tópico 5 fixaram o mecanismo |
| 2 | **R3** — navegação, ajuda e redirecionamento, 20 questões, 25 min, e apuração (10 min) | 35 min | Testa os cards dos Tópicos 1 a 3 |
| 3 | Erros do R3 e do R4 no Notion; reincidência marcada | 20 min | Fecha o ciclo antes do conteúdo novo |

Os reforços estão em `labs/simulados-práticos.lpi/reforco-r3-r4.md`. Meta: **16 de 20 em cada um**.

**Prioridade, se o tempo apertar:** cards do simulado 02, R4, R3, autoavaliação da Semana 6, ajustes nos cards antigos, cards 71 a 75, cola. Corte de trás para a frente.

### Saíram do plano em 23/10

| Item | Motivo |
|---|---|
| Resíduos da Prática 2 (`rm` do `bob`, link absoluto, limpeza com `getent`) | Exercício de laboratório, não de prova. O sticky bit, que era o ponto do `rm`, foi acertado no simulado (Q39) e volta no R4 |
| Erros da primeira tentativa dos Exercícios da LPI 5.1 a 5.4 | Não há registro deles, e o Tópico 5 já tem três medições: simulado 02, autoavaliação da Semana 6 e R4 |

### Foram para a Semana 9

Práticas 3, 4 e 5, bloco curto (4.1 e here document), aulas 41 a 72, simulado 03, R1, R2, autoavaliação da Semana 8 e **Checkpoint B**, agora no domingo 01/11. Roteiros e calendário em `labs/semana-09.md`.

---

## Registro das sessões

### Exercícios da LPI 5.1 a 5.4 — quarta 21/10 — CONCLUÍDOS

Entregue como um guia em PDF com os **43 exercícios resolvidos** (5.1 G1 a G5 e E1 a E7; 5.2 G1 e G2 e E1 a E8; 5.3 G1 a G6 e E1 a E5; 5.4 G1 a G5 e E1 a E5).

**Revisão:** as resoluções estão corretas, inclusive os pontos em que o guia corrige o gabarito do PDF da LPI. Os mais úteis para a prova:

| Exercício | Ponto |
|---|---|
| 5.2 G2 | Grupo primário não aparece na lista de membros do `/etc/group`; `!` no hash é senha bloqueada; `0` na última troca obriga a trocar no próximo login |
| 5.3 G4 | O `s` na posição do grupo é **SGID**, não SUID; e o Linux ignora SUID e SGID em scripts |
| 5.3 G6 | `drwxr-xr-t` = 1755; `----r--r--` = 0044; `drwxr-sr-x` = 2755 |
| 5.3 E2 | Binário executa com `--x`; script precisa de `r`, porque o interpretador lê o arquivo |
| 5.4 E3 | Contador de links 4 = quatro nomes no total, três além do mostrado |
| 5.4 E4 | Symlink relativo resolve a partir do diretório **onde o link está**; o `mv` muda o alvo encontrado |
| 5.4 E5 | O `lrwxrwxrwx` do link não dá acesso: vale a permissão do alvo |

**Ponto de método.** O PDF é um guia resolvido, não o registro das suas respostas. O roteiro pedia responder sem consultar e anotar só as questões erradas. Para o Notion, leve as questões em que a sua **primeira resposta** errou. Se a resolução foi lida antes de responder, registre aqui "estudo, sem medição": a medição do Tópico 5 fica com o simulado 02 (sexta 23/10) e a autoavaliação da Semana 6 (sábado 24/10).

**Saiu do plano em 23/10.** Não há registro da primeira tentativa, e o Tópico 5 já tem medição suficiente: simulado 02 (23/10), autoavaliação da Semana 6 (24/10) e R4 (25/10). Os exercícios ficam como estudo, sem medição.

**Aviso sobre a versão da prova**, que o guia traz e foi conferido no site da LPI em 21/10: a versão atual é a **2.0, exame 010-200**; a **1.6, exame 010-160**, que este plano cobre, fica disponível **até abril de 2027**. Ao agendar na Pearson VUE, escolha o **010-160**.

### Simulado 02 — sexta 23/10 — CONCLUÍDO

**22 de 40 (55%), 17 firmes.** Abaixo da meta (24) e do corte do exame (26). Apuração completa, questões erradas e o texto de cada card em `labs/simulados-práticos.lpi/simulado-02.md`; resumo em `resultados_simulados.md`.

| Tópico | Acertos | Leitura |
|---|---|---|
| 1 | 5 de 7 | Erro de forma na lacuna (Q7, `sudo dpkg`) e um chute (Q5) |
| 2 | **4 de 9** | Caminhos (`./` contra `../`, `/home` contra `~`), `help`, `mv` e seções do `man` |
| 3 | 6 de 9 | Ordem do `2>&1`, `grep -v` e `$#`: os três são reincidência |
| 4 | 4 de 8 | Não estudado; três acertos por chute ou pesquisa |
| 5 | **3 de 7** | `x` do `/etc/passwd`, conversão octal e bits especiais |

**Ponto de método.** Q29 e Q40 foram pesquisadas durante o simulado. No exame não há consulta: daqui em diante, **questão pesquisada conta como errada**. Na dúvida, marque o chute e siga; a pesquisa vem depois, na correção.

### Autoavaliação da Semana 6 — sábado 24/10

*A preencher.* Acertos: de 10.

### Cards no Notion — sábado 24/10

| Grupo | Feito |
|---|---|
| 14 cards do simulado 02 | |
| Ajustes nos cards 65, 69 e 70 | |
| Cards 71 a 75 | |
| Cards sem número: `x` em diretório e 4644 | |

### `cheatsheets/permissoes.md` — sábado 24/10

*A preencher.*

### R4 e R3 — domingo 25/10

*A preencher.* R4: de 20. R3: de 20. Apuração em `reforco-r3-r4.md`.

### Correções da semana

A numeração segue a série global. **A próxima é a 76.** Erros de simulado, reforço e autoavaliação não geram correção numerada; vão para o Notion.

| # | Tema | Origem |
|---|---|---|
| | | |

---

## Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Ter 20 | — | | Prática 2, blocos 5 e 6 |
| Qua 21 | — | | Exercícios da LPI 5.1 a 5.4 |
| Qui 22 | 2h10 | | Cards no Notion e correções no caderno |
| Sex 23 | 1h25 | | Simulado 02 |
| Sáb 24 | 2h10 | | Autoavaliação S6, cards e cola |
| Dom 25 | 1h40 | | R4, R3 e erros no Notion |

---

## Checklist da semana

- [x] Prática 2 terminada, blocos 5 e 6 (terça 20/10)
- [x] Exercícios da LPI 5.1 a 5.4 resolvidos (quarta 21/10)
- [x] Cards 60 a 70 no Notion (quinta 22/10)
- [x] Correções das Práticas 1 e 2 no caderno (quinta 22/10)
- [x] Simulado 02 (sexta 23/10)
- [ ] Autoavaliação da Semana 6 (sábado 24/10)
- [ ] 14 cards do simulado 02 no Notion (sábado 24/10)
- [ ] Ajustes nos cards 65, 69 e 70 (sábado 24/10)
- [ ] Cards 71 a 75, `x` em diretório e 4644 (sábado 24/10)
- [ ] `cheatsheets/permissoes.md` escrito à mão (sábado 24/10)
- [ ] R4 e R3, com apuração (domingo 25/10)
- [ ] Erros dos reforços no Notion (domingo 25/10)
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-08.md` preenchido: simulado 02 registrado, autoavaliação da Semana 6, os cards do Notion em dia, a cola de permissões e os reforços R3 e R4 apurados. Tudo até o domingo 25/10.