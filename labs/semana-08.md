# Semana 8 — Prática 2, Exercícios da LPI e simulado 02

Período: 19/10 a 25/10/2026 (segunda a domingo)
Objetivos da prova: Tópico 5 (5.3 e 5.4) em prática e o simulado 02
**Data da prova: segunda-feira, 30/11/2026** (movida em 26/10)
Situação: **semana fechada em 26/10**

---

## Resumo da semana

| Dia | Atividade | Resultado |
|---|---|---|
| Seg 19 e ter 20 | Prática 2 — permissões, blocos 1 a 6 | Feita (registro em `labs/semana-07.md`) |
| Qua 21 | Exercícios da LPI 5.1 a 5.4 | 43 exercícios resolvidos |
| Qui 22 | Correções das Práticas 1 e 2 no caderno · cards 60 a 70 no Notion | Feito |
| Sex 23 | **Simulado 02** | **22 de 40, 17 firmes** |

**Fechamento (26/10).** A estratégia mudou: o modelo de pendências saiu do plano. O que estava previsto para o fim de semana 24 e 25/10 não fica pendente. Os reforços R3 e R4 entraram no calendário da operação prática (02 e 04/11), e as correções do simulado 02 ficam no próprio `simulado-02.md` como referência. Daqui em diante: `labs/semana-09.md` (conteúdo, de 26 a 30/10) e `labs/operacao-pratica.md` (de 31/10 até a prova).

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

**Medição:** os exercícios ficaram como estudo, sem medição, porque não há registro da primeira tentativa. O Tópico 5 foi medido pelo simulado 02.

**Aviso sobre a versão da prova**, que o guia traz e foi conferido no site da LPI em 21/10: a versão atual é a **2.0, exame 010-200**; a **1.6, exame 010-160**, que este plano cobre, fica disponível **até abril de 2027**. Ao agendar na Pearson VUE, escolha o **010-160**.

### Simulado 02 — sexta 23/10 — CONCLUÍDO

**22 de 40 (55%), 17 firmes.** Abaixo da meta (24) e do corte do exame (26). Apuração completa, questões erradas e a correção de cada uma em `labs/simulados-práticos.lpi/simulado-02.md`; resumo em `resultados_simulados.md`. Os cinco erros reincidentes (Q9, Q19, Q22, Q24 e Q34) entraram na lista de reincidências da operação prática (`labs/operacao-pratica.md`, seção 6), cada um com o seu treino na VM.

| Tópico | Acertos | Leitura |
|---|---|---|
| 1 | 5 de 7 | Erro de forma na lacuna (Q7, `sudo dpkg`) e um chute (Q5) |
| 2 | **4 de 9** | Caminhos (`./` contra `../`, `/home` contra `~`), `help`, `mv` e seções do `man` |
| 3 | 6 de 9 | Ordem do `2>&1`, `grep -v` e `$#`: os três são reincidência |
| 4 | 4 de 8 | Não estudado; três acertos por chute ou pesquisa |
| 5 | **3 de 7** | `x` do `/etc/passwd`, conversão octal e bits especiais |

**Ponto de método.** Q29 e Q40 foram pesquisadas durante o simulado. No exame não há consulta: daqui em diante, **questão pesquisada conta como errada**. Na dúvida, marque o chute e siga; a pesquisa vem depois, na correção.

### Correções da semana

Nenhuma correção numerada nesta semana. A próxima é a **76**.

---

## Horas da semana

| Dia | Real | Observação |
|---|---|---|
| Seg 19 e ter 20 | | Prática 2 |
| Qua 21 | | Exercícios da LPI 5.1 a 5.4 |
| Qui 22 | | Correções no caderno e cards no Notion |
| Sex 23 | | Simulado 02 |

---

## Checklist da semana

- [x] Prática 2 terminada, blocos 1 a 6 (segunda 19 e terça 20/10)
- [x] Exercícios da LPI 5.1 a 5.4 resolvidos (quarta 21/10)
- [x] Correções das Práticas 1 e 2 no caderno (quinta 22/10)
- [x] Cards 60 a 70 no Notion (quinta 22/10)
- [x] Simulado 02 (sexta 23/10)