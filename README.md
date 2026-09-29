# Linux Essentials — Laboratórios

Caderno de laboratório da minha preparação para a certificação **LPI Linux Essentials (010-160)**.

Prova agendada para **09/11/2026**. Estudo em ritmo de 5 a 7 horas por semana, com registro diário dos comandos executados e do que foi aprendido.

## Ambiente

VirtualBox com Ubuntu Server 26.04.1 LTS (2 vCPU, 2 GB RAM, LVM estendido para 23 GB), acessado por SSH na porta 2222. Snapshot `limpo` como ponto de restauração, o que permite quebrar o sistema deliberadamente durante os laboratórios.

Containers Docker (Rocky Linux, Debian, Alpine) para comparação entre distribuições e gerenciadores de pacotes.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `labs/` | Diário de estudo. Um arquivo por semana: comandos executados, saídas, correções e o que aprendi |
| `praticas/` | Simulados no formato do exame, com gabarito comentado e apuração por tópico |
| `cheatsheets/` | Referência destilada por tema. Só a forma final correta, sem o processo |
| `scripts/` | Shell scripts escritos durante o estudo |
| `PLANO.md` | Plano de estudos completo, cronograma e registro de aprendizados |
| `SETUP-LAB.md` | Guia de montagem do laboratório |

A distinção entre `labs/` e `cheatsheets/` é deliberada: o primeiro registra **como** o aprendizado aconteceu, incluindo os erros; o segundo registra **o que** ficou, em forma consultável. Na revisão final, o segundo é o que se lê.

## Estratégia em duas fases

O cronograma foi revisado em 26/09. As quatro primeiras semanas priorizaram prática diária, com cinco sessões de laboratório por semana. Isso acelerou a cobertura dos Tópicos 1, 2 e parte do 3, mas deixou o curso em vídeo para trás.

A partir da Semana 5 o plano inverte a proporção:

| Fase | Semanas | Período | Foco |
|---|---|---|---|
| **1 — Curso** | 5 a 7 | 28/09 a 18/10 | Fechar as 46 aulas restantes · duas práticas por semana |
| **2 — Prática e simulados** | 8 a 10 | 19/10 a 08/11 | Simulados em condição de prova · laboratórios integradores |
| **Prova** | — | 09/11 | — |

### Ritmo semanal da Fase 1

| Dia | Atividade | Tempo |
|---|---|---|
| Segunda | Curso | ~40 min |
| **Terça** | **Laboratório** | 1h |
| Quarta | Curso | ~40 min |
| Quinta | Curso | ~40 min |
| **Sexta** | **Laboratório** | 1h |
| Sábado | Curso ou reposição | ~40 min |
| Domingo | Fechamento e commits | ~30 min |

Todos os dias começam com um **aquecimento de 10 minutos**: cinco comandos refeitos de memória, sem consulta. O que travar vira card de revisão.

A Semana 5 é uma exceção a esse ritmo, por carregar duas pendências da Semana 4. O calendário corrigido está na seção seguinte.

Comando vira reflexo por repetição espaçada, não por tempo acumulado. Duas sessões longas por semana ensinam menos motricidade do que cinco curtas — o aquecimento diário existe para preservar o espaçamento com menos sessões formais.

## Cronograma

| Semana | Período | Conteúdo | Situação |
|---|---|---|---|
| 0 | até 31/08 | Montagem do laboratório | Concluída |
| 1 | 01–06/09 | Tópico 1 — comunidade, licenças, distribuições e FHS | Concluída |
| 2 | 07–13/09 | Tópico 2 — linha de comando e sistema de ajuda | Concluída |
| 3 | 14–20/09 | Tópico 2 — arquivos, diretórios e links | Concluída |
| 4 | 21–27/09 | Tópico 3 — redirecionamento, filtros, busca e compactação | Fechada em 29/09 · autoavaliação 14 de 20 |
| 5 | 28/09–04/10 | Objetivo 3.3 — shell script · simulado diagnóstico | Em andamento |
| 6 | 05–11/10 | Tópico 5 — usuários, grupos e permissões | Pendente |
| 7 | 12–18/10 | Tópico 4 — hardware, processos e rede | Pendente |
| 8 | 19–25/10 | Simulados e revisão dirigida | Pendente |
| 9 | 26/10–01/11 | Simulados e laboratório integrador | Pendente |
| 10 | 02–08/11 | Revisão final | Pendente |

### Semana 5 em detalhe

A segunda-feira 28/09 foi consumida pela Sessão 5 da Semana 4, adiada em três dias. O calendário da semana foi refeito em torno disso: os dois laboratórios saem de terça e sexta para sexta e sábado, e o simulado fecha o domingo. A partir da Semana 6 o ritmo volta ao padrão de terça e sexta.

| Dia | Atividade | Tempo |
|---|---|---|
| Seg 28 | Sessão 5 da Semana 4 — `find` e desafio integrador | concluída |
| Ter 29 | Autoavaliação da Semana 4 — concluída, 14 de 20 · curso, aulas 26 a 31 | 1h10 |
| Qua 30 | Curso, aulas 32 a 37 | 45 min |
| Qui 01/10 | Curso, aulas 38 a 43 | 45 min |
| Sex 02 | Laboratório — fundamentos de shell script | 1h |
| Sáb 03 | Laboratório — os quatro scripts do objetivo 3.3 | 1h |
| Dom 04 | Simulado diagnóstico cronometrado · apuração · commits | 1h35 |

## Cobertura por tópico do exame

O exame tem 40 questões distribuídas por peso entre cinco tópicos. A estimativa considera o peso de cada tópico, não o número de semanas.

| Tópico | Peso | Cobertura | Situação |
|---|---|---|---|
| 1. Comunidade Linux e carreira em open source | 7 | 100% | Concluído e revisado |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 100% | Concluído — os quatro objetivos |
| 3. O poder da linha de comando | 9 | 55% | Objetivos 3.1 e 3.2 concluídos; falta o 3.3 |
| 4. O sistema operacional Linux | 8 | 30% | Parcial: FHS, LVM, `/proc`, `/dev`, portas e pacotes |
| 5. Segurança e permissões de arquivo | 7 | 0% | Não iniciado |

**Progresso geral estimado: aproximadamente 65% do conteúdo do exame.**

Restam seis semanas até a prova, sendo três de conteúdo novo e três de revisão e simulados.

## Medições

Autoavaliações realizadas ao fim de cada semana, sem consulta, com gabarito conferido apenas depois.

| Semana | Questões | Resultado | Meta |
|---|---|---|---|
| 2 | 15 | 14 | 12 |
| 3 | 20 | 20 | 16 |
| 4 | 20 | 14 | 16 |

A Semana 4 ficou abaixo da meta, e a comparação com as semanas anteriores só é possível com uma ressalva que mudou o método: **as autoavaliações das Semanas 2 e 3 foram respondidas no mesmo dia do último laboratório; a da Semana 4 foi respondida quatro dias depois.** As duas primeiras mediram memória de curto prazo. A terceira mediu retenção.

Os quatro conceitos errados estavam registrados corretamente no próprio caderno, escritos dias antes. Isso caracteriza o problema como retenção, não compreensão, e altera a regra: **da Semana 5 em diante, a autoavaliação de cada semana é respondida na semana seguinte.** Um número menor e honesto vale mais que um número alto e cedo.

| Bloco da Semana 4 | Acertos | Sessão de origem |
|---|---|---|
| Redirecionamento | 5 de 5 | Sessão 1, a mais antiga |
| Filtros e pipes | 3 de 5 | Sessão 2 |
| `grep` e expressões regulares | 2 de 5 | Sessão 3 |
| Compactação | 4 de 5 | Sessão 4, a mais recente |

A concentração no `grep` descarta a hipótese de decaimento por tempo: o bloco mais antigo foi o único perfeito. O aquecimento diário da Semana 5 foi redirecionado para `grep` e `sort`, sem custo de sessão adicional.

O simulado diagnóstico de 40 questões cronometradas está escrito e disponível em `praticas/simulado-01-diagnostico.md`, com distribuição de pesos idêntica à do exame e gabarito comentado. Execução prevista para 04/10.

## Prática complementar

**OverTheWire — Bandit.** Wargame de linha de comando acessado por SSH, usado para exercitar navegação, permissões, busca e manipulação de arquivos em situações não guiadas. **Níveis 0 a 9 concluídos.**

**LPI Learning Materials.** Material oficial da LPI, organizado objetivo por objetivo, usado como leitura de reforço.

**Cards de revisão espaçada.** Mantidos em ferramenta externa, alimentados a cada erro identificado nos laboratórios e nas autoavaliações.

## Metodologia

Todo comando é digitado, nunca copiado. Cada sessão termina com o registro do que foi executado e do que foi compreendido.

Os arquivos em `labs/` incluem uma seção de **correções**, com os conceitos que foram anotados de forma incorreta e a explicação do que está certo. O registro dos erros é parte deliberada do método — até aqui são 52 correções registradas ao longo de quatro semanas, e a maioria delas revelou imprecisão de compreensão que nenhuma autoavaliação teria detectado sozinha.

A correção 44 é o exemplo mais claro do valor do método: em `find . -type f -name "*.py" -o -name "*.md"`, o `-o` tem precedência menor que o **e** implícito, e o `-type f` vale apenas para o primeiro grupo. O comando roda, não emite aviso nenhum e devolve resultado errado. Nenhuma leitura de material teria exposto isso — só a anotação do raciocínio e a conferência dela.

A correção 50 ensinou algo sobre o próprio método. Ela é a quarta ocorrência do mesmo conceito — o `sort` sem `-n` ordenar em sentido crescente —, já registrado por escrito três vezes. Um conceito que resiste a três registros escritos não é resolvido por um quarto: é resolvido executando os quatro comandos e vendo as quatro saídas lado a lado. **Registrar expõe o erro; executar é o que o corrige.**