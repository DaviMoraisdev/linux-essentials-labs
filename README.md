# Linux Essentials — Laboratórios

Caderno de laboratório da minha preparação para a certificação **LPI Linux Essentials (010-160)**.

Prova em **23/11/2026**. Estudo em ritmo de cerca de 9 horas por semana, com registro diário dos comandos executados e do que foi aprendido.

## Ambiente

VirtualBox com Ubuntu Server 26.04.1 LTS (2 vCPU, 2 GB RAM, LVM estendido para 23 GB), acessado por SSH na porta 2222. Snapshot `limpo` como ponto de restauração, o que permite quebrar o sistema deliberadamente durante os laboratórios.

Containers Docker (Rocky Linux, Debian, Alpine) para comparação entre distribuições e gerenciadores de pacotes.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `labs/` | Diário de estudo. Um arquivo por semana: comandos executados, saídas, correções e o que aprendi |
| `labs/simulados-práticos.lpi/` | Simulados no formato do exame, com gabarito comentado, apuração por tópico e painel de resultados |
| `cheatsheets/` | Referência destilada por tema. Só a forma final correta, sem o processo |
| `scripts/` | Shell scripts escritos durante o estudo |
| `PLANO.md` | Plano de estudos completo, cronograma e registro de aprendizados |
| `SETUP-LAB.md` | Guia de montagem do laboratório |

A distinção entre `labs/` e `cheatsheets/` é deliberada: o primeiro registra **como** o aprendizado aconteceu, incluindo os erros; o segundo registra **o que** ficou, em forma consultável. Na revisão final, o segundo é o que se lê.

## Estratégia até a prova

O cronograma foi revisado três vezes: em 26/09 (curso como atividade principal), em 02/10 (simulado semanal e checkpoints) e em 13/10, quando a prova passou para **23/11**. A estratégia vigente tem três etapas, em ordem fixa:

| Etapa | Período | Foco |
|---|---|---|
| **1 — Dívidas** | 13/10 a 18/10 | Práticas de usuários, grupos e permissões · simulado 02 · autoavaliações das Semanas 5 e 6 · curso fechado em paralelo |
| **2 — Conteúdo restante** | 15/10 a 25/10 | Tópico 4 em três práticas de laboratório: hardware e diretórios, processos e logs, rede |
| **3 — Simulados** | 23/10 a 19/11 | Um simulado completo a cada dois ou três dias, com revisão dirigida só nos erros |
| **Prova** | 23/11 | — |

Depois das dívidas da Etapa 1, o plano só admite conteúdo da prova ainda não estudado e simulados. Itens antigos de registro retroativo e de ambiente saíram do plano em 13/10.

Todos os dias de estudo sem simulado começam com um **aquecimento de 10 minutos**: cinco comandos refeitos de memória, sem consulta. O que travar vira card de revisão. Comando vira reflexo por repetição espaçada, não por tempo acumulado.

## Cronograma

| Semana | Período | Conteúdo | Situação |
|---|---|---|---|
| 0 | até 31/08 | Montagem do laboratório | Concluída |
| 1 | 01–06/09 | Tópico 1 — comunidade, licenças, distribuições e FHS | Concluída |
| 2 | 07–13/09 | Tópico 2 — linha de comando e sistema de ajuda | Concluída |
| 3 | 14–20/09 | Tópico 2 — arquivos, diretórios e links | Concluída |
| 4 | 21–27/09 | Tópico 3 — redirecionamento, filtros, busca e compactação | Concluída · autoavaliação 14 de 20 |
| 5 | 28/09–04/10 | Objetivo 3.3 — shell script | Concluída |
| 6 | 05–11/10 | Simulado diagnóstico · scripts do 3.3 · abertura do Tópico 5 | Concluída · simulado 01: 28 de 40 |
| 7 | 12–18/10 | Tópico 5 em prática · simulado 02 · fechamento do curso | Em andamento |
| 8 | 19–25/10 | Tópico 4 — hardware, processos, logs e rede · simulado 03 | Pendente |
| 9 | 26/10–01/11 | Simulados 04 e 05 · reforço R2 | Pendente |
| 10 | 02–08/11 | Simulados 06, 07 e 08 · gate | Pendente |
| 11 | 09–15/11 | Simulados 09 e 10 | Pendente |
| 12 | 16–22/11 | Revisão leve · simulado final em 19/11 · descanso | Pendente |

## Cobertura por tópico do exame

O exame tem 40 questões distribuídas por peso entre cinco tópicos. A estimativa considera o peso de cada tópico, não o número de semanas.

| Tópico | Peso | Cobertura | Situação |
|---|---|---|---|
| 1. Comunidade Linux e carreira em open source | 7 | 100% | Concluído e revisado |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 100% | Concluído — os quatro objetivos |
| 3. O poder da linha de comando | 9 | 100% | Concluído, com quatro scripts escritos no objetivo 3.3 |
| 4. O sistema operacional Linux | 8 | 30% | Parcial: FHS, LVM, `/proc`, `/dev`, portas e pacotes · práticas na Semana 8 |
| 5. Segurança e permissões de arquivo | 7 | 50% | Usuários e grupos praticados (Prática 1) · permissões na Prática 2 |

**Progresso geral estimado: aproximadamente 75% do conteúdo do exame.**

## Medições

Autoavaliações realizadas ao fim de cada semana, sem consulta, com gabarito conferido apenas depois.

| Semana | Questões | Resultado | Meta |
|---|---|---|---|
| 2 | 15 | 14 | 12 |
| 3 | 20 | 20 | 16 |
| 4 | 20 | 14 | 16 |
| 5 | 10 | 9 | 8 |
| 6 | 10 | a responder em 19/10 | 8 |

A Semana 4 ficou abaixo da meta, e a comparação com as semanas anteriores só é possível com uma ressalva que mudou o método: **as autoavaliações das Semanas 2 e 3 foram respondidas no mesmo dia do último laboratório; a da Semana 4 foi respondida quatro dias depois.** As duas primeiras mediram memória de curto prazo. A terceira mediu retenção.

Os quatro conceitos errados estavam registrados corretamente no próprio caderno, escritos dias antes. Isso caracteriza o problema como retenção, não compreensão, e altera a regra: **da Semana 5 em diante, a autoavaliação de cada semana é respondida na semana seguinte.** Um número menor e honesto vale mais que um número alto e cedo.

| Bloco da Semana 4 | Acertos | Sessão de origem |
|---|---|---|
| Redirecionamento | 5 de 5 | Sessão 1, a mais antiga |
| Filtros e pipes | 3 de 5 | Sessão 2 |
| `grep` e expressões regulares | 2 de 5 | Sessão 3 |
| Compactação | 4 de 5 | Sessão 4, a mais recente |

A concentração no `grep` descarta a hipótese de decaimento por tempo: o bloco mais antigo foi o único perfeito. O aquecimento diário da Semana 5 foi redirecionado para `grep` e `sort`, sem custo de sessão adicional.

**Simulado diagnóstico (05/10):** 28 de 40 (70%), acima do corte de 26, com 23 acertos firmes. O Tópico 3 fechou em 9 de 9; seis dos sete erros com convicção caíram nos Tópicos 1 e 2. A série completa de simulados, com metas e checkpoints, está em `labs/simulados-práticos.lpi/resultados_simulados.md`.

## Prática complementar

**OverTheWire — Bandit.** Wargame de linha de comando acessado por SSH, usado para exercitar navegação, permissões, busca e manipulação de arquivos em situações não guiadas. **Níveis 0 a 9 concluídos.**

**LPI Learning Materials.** Material oficial da LPI, organizado objetivo por objetivo, usado como leitura de reforço.

**Cards de revisão espaçada.** Mantidos em ferramenta externa, alimentados a cada erro identificado nos laboratórios e nas autoavaliações.

## Metodologia

Todo comando é digitado, nunca copiado. Cada sessão termina com o registro do que foi executado e do que foi compreendido.

Os arquivos em `labs/` incluem uma seção de **correções**, com os conceitos que foram anotados de forma incorreta e a explicação do que está certo. O registro dos erros é parte deliberada do método — até aqui são 74 correções registradas ao longo de seis semanas, e a maioria delas revelou imprecisão de compreensão que nenhuma autoavaliação teria detectado sozinha.

A correção 44 é o exemplo mais claro do valor do método: em `find . -type f -name "*.py" -o -name "*.md"`, o `-o` tem precedência menor que o **e** implícito, e o `-type f` vale apenas para o primeiro grupo. O comando roda, não emite aviso nenhum e devolve resultado errado. Nenhuma leitura de material teria exposto isso — só a anotação do raciocínio e a conferência dela.

A correção 50 ensinou algo sobre o próprio método. Ela é a quarta ocorrência do mesmo conceito — o `sort` sem `-n` ordenar em sentido crescente —, já registrado por escrito três vezes. Um conceito que resiste a três registros escritos não é resolvido por um quarto: é resolvido executando os quatro comandos e vendo as quatro saídas lado a lado. **Registrar expõe o erro; executar é o que o corrige.**