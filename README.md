# Linux Essentials — Laboratórios

Caderno de laboratório da minha preparação para a certificação **LPI Linux Essentials (010-160)**.

Prova agendada para **09/11/2026**. Estudo em ritmo de 5 a 7 horas por semana, com registro diário dos comandos executados e do que foi aprendido.

## Ambiente

VirtualBox com Ubuntu Server 26.04.1 LTS (2 vCPU, 2 GB RAM, LVM estendido para 23 GB), acessado por SSH na porta 2222. Snapshot `limpo` como ponto de restauração, o que permite quebrar o sistema deliberadamente durante os laboratórios.

Containers Docker (Rocky Linux, Debian, Alpine) para comparação entre distribuições e gerenciadores de pacotes.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `labs/` | Um arquivo por semana: comandos executados, saídas, correções e o que aprendi |
| `cheatsheets/` | Referências rápidas por tema (permissões, arquivos, rede) |
| `scripts/` | Shell scripts escritos durante o estudo |
| `PLANO.md` | Plano de estudos completo, cronograma e registro de aprendizados |
| `SETUP-LAB.md` | Guia de montagem do laboratório |

## Cronograma

A ordem das semanas acompanha a sequência do curso utilizado, que inicia pelo Tópico 1.

| Semana | Período | Conteúdo | Situação |
|---|---|---|---|
| 0 | 25–31/08 | Montagem do laboratório | Concluída |
| 1 | 01–07/09 | Tópico 1 — Comunidade, licenças, distribuições e FHS | Concluída |
| 2 | 08–14/09 | Tópico 2 — Linha de comando e sistema de ajuda | Em andamento |
| 3 | 15–21/09 | Tópico 2 — Arquivos, diretórios e links | Pendente |
| 4 | 22–28/09 | Tópico 3 — Compactação, filtros e busca | Pendente |
| 5 | 29/09–05/10 | Tópico 3 — Shell scripting | Pendente |
| 6 | 06–12/10 | Tópico 5 — Usuários, grupos e permissões | Pendente |
| 7 | 13–19/10 | Tópico 4 — Hardware, processos e rede | Pendente |
| 8 | 20–26/10 | Revisão geral e simulado diagnóstico | Pendente |
| 9 | 27/10–02/11 | Simulados e laboratório integrador | Pendente |
| 10 | 03–09/11 | Revisão final e prova | Pendente |

## Cobertura por tópico do exame

O exame tem 40 questões distribuídas por peso entre cinco tópicos. A estimativa abaixo considera o peso de cada tópico, não o número de semanas.

| Tópico | Peso | Cobertura | Situação |
|---|---|---|---|
| 1. Comunidade Linux e carreira em open source | 7 | 100% | Concluído e revisado |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 30% | Em andamento |
| 3. O poder da linha de comando | 9 | 5% | Contato inicial com pipes e redirecionamento |
| 4. O sistema operacional Linux | 8 | 15% | FHS, particionamento e portas vistos de forma parcial |
| 5. Segurança e permissões de arquivo | 7 | 0% | Não iniciado |

**Progresso geral estimado: aproximadamente 28% do conteúdo do exame.**

O número é maior que a fração de semanas concluídas porque o Tópico 1, já encerrado, é integralmente teórico, e porque a montagem do laboratório antecipou conteúdo dos Tópicos 2 e 4 — particionamento, LVM, `lsblk`, NAT, portas e SSH foram exercitados na prática antes de serem estudados formalmente.

Restam aproximadamente 8 semanas até a prova, sendo 5 de conteúdo novo e 3 de revisão e simulados.

## Prática complementar

**OverTheWire — Bandit.** Wargame de linha de comando acessado por SSH, usado para exercitar navegação, permissões, busca e manipulação de arquivos em situações não guiadas.

| Níveis | Situação |
|---|---|
| 0 a 4 | Concluídos |
| 5 | Em andamento |
| 6 a 20 | Pendentes |

**LPI Learning Materials.** Material oficial da LPI, organizado objetivo por objetivo, usado como leitura de reforço.

**Cards de revisão espaçada.** Mantidos em ferramenta externa, alimentados a cada erro identificado nos laboratórios e nas revisões.

## Metodologia

Divisão de aproximadamente 40% do tempo em vídeo e 60% em prática no terminal. Todo comando é digitado, nunca copiado, e cada sessão termina com o registro do que foi executado e do que foi compreendido.

Antes de cada sessão nova, três comandos da sessão anterior são refeitos de memória, sem consulta. Os que falham viram cards de revisão.

Os arquivos em `labs/` incluem uma seção de correções, com os conceitos que foram anotados de forma incorreta e a explicação do que está certo. O registro dos erros é parte deliberada do método.
