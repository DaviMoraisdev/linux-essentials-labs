# Fontes de simulados e questões — 010-160

Levantamento feito em 28/09/2026, com foco em material gratuito e legítimo.

## Recomendadas

### 1. NDG Linux Essentials, via Cisco Networking Academy

A melhor opção gratuita disponível. É o curso oficial reconhecido pela LPI como material preparatório, e o motivo de estar em primeiro lugar não é o conteúdo em vídeo: são as **avaliações**.

| Recurso | Detalhe |
|---|---|
| Quizzes por módulo | Um por capítulo, com correção comentada |
| Exame final de prática | Formato e distribuição de pesos do exame real |
| Laboratórios no navegador | Terminal embutido, sem necessidade de VM |
| Custo | Gratuito, com cadastro na Networking Academy |

Para o seu caso o uso indicado é cirúrgico: **ignorar as aulas e fazer só os quizzes e o exame final.** As aulas cobrem o que o curso do Muller já cobre; os quizzes cobrem o que falta.

- Curso: [netacad.com/courses/os-it/ndg-linux-essentials](https://www.netacad.com/courses/os-it/ndg-linux-essentials)
- Página do provedor: [netdevgroup.com — Linux Essentials](https://www.netdevgroup.com/online/courses/open-source/linux-essentials)

### 2. LPI Learning Materials — o PDF que você já tem

O material oficial da LPI traz **questões de revisão ao final de cada objetivo**, além de exercícios guiados e exercícios exploratórios. Você já tem o arquivo no Projeto: `LPI-Learning-Material-010-160-pt.pdf`.

Este é o material mais alinhado ao exame que existe, porque é escrito pela mesma organização que o redige. As questões não são um simulado cronometrado, e por isso servem para outra função: **verificar objetivo por objetivo** depois de cada laboratório.

### 3. EDUSUM — questões de amostra

Conjunto gratuito de questões no formato do exame, com gabarito. O volume é limitado, mas a redação imita bem o estilo da LPI: enunciados curtos, uma resposta correta e distratores plausíveis.

- [edusum.com — LPI Linux Essentials sample questions](https://www.edusum.com/lpi/lpi-linux-essentials-010-160-certification-sample-questions)

### 4. Howtonetwork — prática gratuita

Simulado gratuito de acesso direto, sem cadastro. Menor e mais simples que os anteriores, útil como aquecimento de dez minutos.

- [howtonetwork.com — Linux LPI Essentials practice exam](https://www.howtonetwork.com/free/linux-lpi-essentials-practice-exam/)

### 5. Os simulados deste repositório

Escritos sob medida, com distribuição de pesos idêntica à do exame e gabarito comentado. A vantagem sobre os anteriores é que as questões atacam **os pontos em que você já errou** — as 48 correções registradas nos cadernos viram questões.

| Arquivo | Conteúdo | Situação |
|---|---|---|
| `simulado-01-diagnostico.md` | 40 questões, todos os tópicos | Pronto |
| `simulado-02-*.md` | 40 questões, ênfase nos Tópicos 4 e 5 | Semana 8 |
| `simulado-03-*.md` | 40 questões, revisão geral | Semana 9 |

## Sobre os sites de dumps

A busca por "simulado 010-160" devolve muitos sites que anunciam "questões reais do exame": ITExams, Marks4Sure, Pass4Success, P2PExams, CertsHero e semelhantes. Eles não estão nesta lista, por três razões concretas.

**Primeira: violam o acordo que você assina antes do exame.** Ao iniciar a prova, o candidato aceita um termo de confidencialidade. A LPI pode revogar certificações obtidas com uso de material vazado, e ela já fez isso.

**Segunda: o conteúdo é frequentemente errado.** As questões são reconstruídas de memória por terceiros, e os gabaritos vêm de votação em fórum. Uma resposta errada memorizada é pior que uma lacuna reconhecida — a lacuna você estuda, o erro memorizado você defende.

**Terceira, e a que mais importa para você:** decorar pares de pergunta e resposta não produz o que a sua preparação está produzindo. O seu diferencial nestas quatro semanas foram as 48 correções — cada uma nasceu de um erro de compreensão que nenhuma memorização teria exposto. Dump é o caminho oposto desse método.

## Ordem de uso sugerida

| Momento | O que usar |
|---|---|
| Semana 5 | `simulado-01-diagnostico.md` deste repositório, cronometrado |
| Semanas 6 e 7 | Quizzes do NDG por módulo, ao fim de cada tópico estudado |
| Semana 8 | Exame final de prática do NDG, cronometrado, e `simulado-02` |
| Semana 9 | `simulado-03` e repetição dos simulados anteriores, só das questões erradas |
| Semana 10 | Questões de revisão do PDF oficial da LPI, objetivo por objetivo |

Uma regra para as Semanas 8 a 10: **refazer um simulado inteiro é desperdício.** Refaça apenas as questões erradas e as marcadas como chute. O acerto que você já teve duas vezes não ensina nada na terceira.