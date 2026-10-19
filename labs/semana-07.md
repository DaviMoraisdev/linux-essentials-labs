# Semana 7 — Pagamento das dívidas, fechamento do curso e nova estratégia até a prova

Período: 12/10 a 18/10/2026 (segunda a domingo)
Objetivos da prova: Tópico 5 (5.1 a 5.4) em prática; curso do Matheus Muller até a aula 72
**Data da prova: segunda-feira, 23/11/2026** (definida em 13/10)
Carga prevista: cerca de 8h30, de terça 13/10 a domingo 18/10
Marco da semana: **Checkpoint A, domingo 18/10**, com as quatro dívidas pagas e o curso fechado

---

## 1. A nova estratégia (13/10)

A prova passou para **23/11**. O plano a partir de hoje tem três etapas, nesta ordem, e nada de fora delas entra na agenda.

| Etapa | Período | O que se faz | Termina quando |
|---|---|---|---|
| **1. Pagar as dívidas** | 13/10 a 18/10 | Prática 1, Prática 2, simulado 02, autoavaliações das Semanas 5 e 6 | As quatro dívidas estiverem registradas (Checkpoint A, 18/10) |
| **2. Conteúdo não estudado** | 15/10 a 25/10 | Curso do Muller até a aula 72 e os laboratórios do Tópico 4, no mesmo formato das práticas anteriores | Curso fechado e Tópico 4 praticado (Checkpoint B, 25/10) |
| **3. Simulados** | 23/10 a 19/11 | Um simulado completo a cada dois ou três dias, com revisão dirigida apenas nos erros | Gate de 08/11 e simulado final de 19/11 |

Regras que valem a partir de agora:

1. **Depois de pagas as dívidas, dívida antiga não volta.** O que não é conteúdo da prova ainda não estudado, nem simulado, sai do plano.
2. **O curso é feito junto com as dívidas, não depois.** As aulas 41 a 72 ocupam os dias de semana; as práticas e o simulado, os dias mais longos.
3. **Erro de simulado se anota e se corrige no Notion**, como desde 06/10. Erro de laboratório e de curso continua com correção numerada; a próxima é a **75**.

---

## 2. Conteúdos ainda não vistos na preparação

Levantamento feito em 13/10 a partir do plano, dos cadernos das Semanas 1 a 6 e do painel de resultados. Os pesos são os oficiais do exame 010-160, versão 1.6.

### 2.1 Curso do Matheus Muller

| Item | Situação |
|---|---|
| Último registro | Aula 40, em 09/10 (checkpoint na **aula 41**) |
| Restante | **Aulas 41 a 72**, 32 aulas |
| Plano | 41 a 57 de quinta 15/10 a sexta 16/10; 58 a 72 no fim de semana 17 e 18/10 |

Se você assistiu a alguma aula depois de 09/10 sem registrar, anote na tabela "Curso — Matheus Muller" (seção 5) e desconte da conta.

### 2.2 Tópico 5 — Segurança e permissões de arquivo (peso 7)

O aquecimento de 07/10 cobriu a conversão entre octal e simbólico e o `chmod` simbólico. Todo o resto do tópico ainda não foi praticado; é o que as Práticas 1 e 2 cobrem.

| Objetivo | Peso | O que falta |
|---|---|---|
| 5.1 Segurança básica e tipos de usuário | 2 | Root, usuários comuns e de sistema; campos de `/etc/passwd`, `/etc/shadow` e `/etc/group`; `id`, `who`, `w`, `last`; `su` contra `sudo` |
| 5.2 Criação de usuários e grupos | 2 | `useradd`, `groupadd`, `passwd`, `usermod -aG`, `userdel`, `groupdel`; `/etc/skel/`; faixas de UID |
| 5.3 Permissões e donos | 2 | Leitura do `ls -l`; `chown` e `chgrp`; SUID, SGID e sticky bit; o `x` em diretórios |
| 5.4 Diretórios e arquivos especiais | 1 | `/tmp` e `/var/tmp` com sticky bit; `ls -d`; `ln -s` com caminho relativo |

### 2.3 Tópico 4 — O sistema operacional Linux (peso 8)

Nunca estudado como tópico. Foi encostado na prática (LVM e partições na Semana 0, `/proc` e `/dev` na Semana 3, pacotes no curso), por isso a cobertura parte de cerca de 30%. O simulado 01 confirmou as lacunas: `top` (Q28) e o sinal padrão do `kill` (Q29) foram erros chutados.

| Objetivo | Peso | Conteúdo oficial | Onde será praticado |
|---|---|---|---|
| 4.1 Escolhendo um sistema operacional | 1 | Diferenças entre Windows, macOS e Linux; ciclo de vida das distribuições (LTS, estável, beta, rolling release); interface gráfica e linha de comando | Bloco de leitura de quinta 22/10 |
| 4.2 Entendendo o hardware | 2 | Placas-mãe, processadores, fontes, drives ópticos, periféricos; discos e partições, `/dev/sd*`; drivers | Prática 3 |
| 4.3 Onde os dados são armazenados | **3** | Programas e configuração, pacotes e banco de dados de pacotes; processos, memória, mensagens do sistema e logs; `ps`, `top`, `free`, `syslog`, `dmesg`; `/etc/`, `/var/log/`, `/boot/`, `/proc/`, `/dev/`, `/sys/` | Práticas 3 e 4 |
| 4.4 Seu computador na rede | 2 | Internet, rede, roteadores; cliente DNS; configuração de rede; `route`, `ip route show`, `ifconfig`, `ip addr show`, `netstat`, `ss`, `/etc/resolv.conf`, `/etc/hosts`, IPv4, IPv6, `ping`, `host` | Prática 5 |

### 2.4 Resíduos dos tópicos já fechados

Dois pontos, apontados nas dicas recorrentes de 06/10, nunca foram estudados como conceito. Entram no bloco de quinta 22/10 e nos mini-simulados de reforço, sem sessão própria.

| Ponto | Objetivo | Situação |
|---|---|---|
| Here document (`<<` com delimitador) | 3.2 | Usado muitas vezes para criar arquivos, nunca estudado como conceito |
| Questões de preencher a lacuna | Formato do exame | Nunca treinadas; a Q11 do simulado 01 foi respondida com um sublinhado na frente de `PATH` |

### 2.5 Resumo

| Bloco | Tamanho | Peso no exame |
|---|---|---|
| Curso, aulas 41 a 72 | 32 aulas | — |
| Tópico 5 | 4 objetivos, 2 práticas | 7 de 40 |
| Tópico 4 | 4 objetivos, 3 práticas e 1 bloco de leitura | 8 de 40 |
| Here document e lacunas | 1 bloco curto e os reforços R1 e R2 | Transversal |

**Cobertura estimada em 13/10: cerca de 70% do conteúdo da prova** (Tópicos 1, 2 e 3 completos; 4 em 30%; 5 com a conversão de permissões).

---

## 3. Dívidas a pagar nesta semana

São as quatro dívidas que você escolheu pagar para entrar na nova estratégia. Os roteiros das práticas não mudam e continuam no arquivo da Semana 6; este arquivo só traz a agenda e o registro.

| # | Dívida | Roteiro | Quando |
|---|---|---|---|
| 1 | **Prática 1** — usuários e grupos, com 20 min de Exercícios da LPI (lições 5.1 e 5.2) | `labs/semana-06.md`, seção "Prática 1" | **Feita em 13 e 15/10**; faltam os Exercícios da LPI 5.1 e 5.2 (domingo 18/10) |
| 2 | **Prática 2** — permissões, com 20 min de Exercícios da LPI (lições 5.3 e 5.4) e limpeza dos usuários de teste | `labs/semana-06.md`, seção "Prática 2" | **Domingo 18/10** |
| 3 | **Simulado 02** — 40 questões, 60 minutos | `labs/simulados-práticos.lpi/simulado-02.md` | **Sábado 17/10** |
| 4 | **Autoavaliação da Semana 5** (10 questões, shell script) e **Autoavaliação da Semana 6** (10 questões, Tópico 5) | S5: `labs/semana-06.md`, seção "Autoavaliação da Semana 5" · S6: seção 6 deste arquivo | S5: **feita em 13 e 15/10 (9 de 10)** · S6: **quinta 22/10**, primeira atividade |

Dois ajustes nos roteiros, por causa da ordem nova:

- **As práticas vêm antes das aulas do Tópico 5.** Para não praticar às cegas, leia antes de cada prática a lição correspondente do PDF oficial (cerca de 15 minutos): lições 5.1 e 5.2 antes da Prática 1, e 5.3 e 5.4 antes da Prática 2. O vídeo, depois, confirma.
- **A autoavaliação da Semana 6 volta ao plano**, a seu pedido. Ela fica na quinta 22/10, quatro dias depois da Prática 2, para medir retenção e não memória de curto prazo (regra de 29/09). O simulado 02, no sábado, não a substitui: ele mede a prova inteira, e ela mede só o Tópico 5, com perguntas abertas.

---

## 4. Calendário da semana

**Replanejado em 15/10 e de novo em 16/10.** A quarta 14/10 e a sexta 16/10 ficaram sem estudo. A Prática 2 passa para o domingo, que fecha todas as dívidas da semana. As aulas de sexta vão para o sábado, para o domingo não passar de 3h30.

| Dia | Atividade | Tempo |
|---|---|---|
| Ter 13 | Autoavaliação da Semana 5, questões 1 a 7 · Prática 1, blocos 1 e 2 | **feito** |
| Qua 14 | Sem estudo | — |
| Qui 15 | Autoavaliação da Semana 5, questões 8 a 10 · Prática 1, bloco 3 e experimento sem `-m` | **feito** |
| Sex 16 | Sem estudo; a Prática 2 foi para o domingo | — |
| **Sáb 17** | **Simulado 02** (60 min, primeira atividade) · apuração (25 min) · **curso, aulas 41 a 58** (2x até o fim do Tópico 5) | cerca de 3h10 |
| **Dom 18** | **Fechamento das dívidas:** leitura das lições 5.3 e 5.4 do PDF (15 min) · **Prática 2 — permissões** (1h) com Exercícios da LPI 5.3 e 5.4 (20 min) e a limpeza · Exercícios da LPI 5.1 e 5.2 e o que faltou da Prática 1: os 7 campos do `/etc/passwd` e o arquivo do `last` (25 min) · **curso, aulas 59 a 72** (fechamento) · **Checkpoint A** (10 min) | cerca de 3h30 |

**Total do fim de semana: cerca de 6h40.** A vantagem da troca: as aulas do Tópico 5 chegam **antes** da Prática 2, e não depois. Se faltar tempo, corte nesta ordem:

| Ordem | Corte | Para onde vai |
|---|---|---|
| 1 | Exploratórios da LPI (mantendo os Guiados) | Saem |
| 2 | Aulas que não couberem no sábado | Domingo, depois da Prática 2 |
| 3 | Aulas que não couberem no domingo | Segunda 19/10 e terça 20/10, 30 minutos antes da prática do dia |

**Não se cortam:** a Prática 2 e o simulado 02.

**A autoavaliação da Semana 6 não cabe no domingo.** Ela mede retenção e precisa de três dias depois da Prática 2 (regra de 29/09); feita no mesmo dia, daria uma nota alta e falsa, como os 20 de 20 da Semana 3. Por isso vai para a **quinta 22/10**, como primeira atividade.

Velocidade do curso: **2x** onde o vídeo repete o que já foi praticado (shell script, Tópico 5 depois das práticas); **1.25x** no Tópico 4, que é conteúdo novo.

---

## 5. Curso — Matheus Muller

| Data | Aulas previstas | Aulas assistidas | Parei na aula | Anotações novas |
|---|---|---|---|---|
| Qui 15/10 | 41 a 49 | | | |
| Sex 16/10 | 50 a 57 | | | |
| Sáb 17/10 | 58 a 64 | | | |
| Dom 18/10 | 65 a 72 | | | |

Regras de sempre: anote só o que o vídeo mostra e você ainda não sabia; em permissões, converta de cabeça antes de o professor mostrar; registre a aula em que parou ao fim de cada dia.

---

## 6. Autoavaliação da Semana 6 — Quinta 22/10

Dez questões sobre o Tópico 5 (objetivos 5.1 a 5.4), respondidas **sem consultar**, quatro dias depois da Prática 2. **Primeira atividade da quinta 22/10**, antes do bloco curto. Escreva as respostas à mão e só depois abra o gabarito.

1. Quais são os três tipos de conta em um sistema Linux? Como o UID ajuda a distingui-los, e onde se confere a partir de qual número começam os usuários comuns na sua VM?
2. Quantos campos tem cada linha do `/etc/passwd`, qual o separador, e o que guardam o **terceiro**, o **sexto** e o **sétimo** campos?
3. Por que o `/etc/passwd` pode ser lido por qualquer usuário e o `/etc/shadow` não? O que o `x` do segundo campo do `/etc/passwd` indica?
4. Explique a diferença entre `su - ana` e `sudo comando`. De quem é a senha pedida em cada caso? O que faz `sudo -i`?
5. Escreva o comando que cria o usuário `carla` com diretório pessoal, shell `/bin/bash` e o grupo secundário `dev`. Qual é o papel do `/etc/skel/` nessa criação?
6. A usuária `ana` está nos grupos secundários `dev` e `docker`. Escreva o comando que a acrescenta ao grupo `ops` sem retirá-la dos outros. O que acontece se o `-a` for esquecido?
7. Converta, nos dois sentidos: (a) `rw-r-----` para octal; (b) `751` para simbólico; (c) `rwsr-xr-x` para octal, com o bit especial.
8. Um arquivo tem permissão `640`. Qual a permissão final, em octal e em símbolos, depois de `chmod u+x,o+r arquivo`?
9. O que fazem o **SUID** em um executável (dê o exemplo do sistema), o **SGID** em um diretório e o **sticky bit** em um diretório? O que significa um `S` maiúsculo no lugar do `x` do dono?
10. O diretório `pasta` tem permissão `500` (`r-x------`) e pertence a você. Dentro dele há o arquivo `arq`, com permissão `644`. Você consegue (a) listar o diretório, (b) ler `arq`, (c) criar `pasta/novo`, (d) apagar `arq`? Justifique a resposta (d).

| Campo | Valor |
|---|---|
| Acertos | de 10 |
| Meta | 8 ou mais |
| Questões erradas | |
| Erros viram | lista das questões erradas aqui; a correção fica no Notion |

<details>
<summary>Gabarito (abra só depois de responder)</summary>

1. **Root** (superusuário, UID **0**), **usuários de sistema** (contas de serviço, como `www-data` e `sshd`, com UID abaixo do primeiro UID de usuário comum e normalmente com shell `nologin`) e **usuários comuns** (pessoas, a partir do `UID_MIN`). O valor está em `/etc/login.defs`: `grep UID_MIN /etc/login.defs`. No Ubuntu é **1000**.
2. **Sete** campos, separados por **dois-pontos**. Terceiro: **UID**. Sexto: **diretório pessoal**. Sétimo: **shell de login**. (A ordem completa: usuário, `x`, UID, GID, comentário, home, shell. O GID é o quarto, que foi o erro da Q35 do simulado 01.)
3. Vários programas comuns precisam traduzir UID em nome de usuário, por isso o `/etc/passwd` é legível por todos (`644`). A senha, por isso mesmo, **não** fica nele: o `x` indica que o hash da senha está no `/etc/shadow`, que só o root (e o grupo `shadow`) consegue ler.
4. `su - ana` troca para a usuária `ana`, com o ambiente de login dela, e pede a **senha da ana**. `sudo comando` executa só aquele comando como root (ou outro usuário), e pede a **sua própria senha**, se você estiver autorizado no `sudoers`. `sudo -i` abre um shell de login do root, com o ambiente do root, usando a sua senha.
5. `sudo useradd -m -s /bin/bash -G dev carla`. O `/etc/skel/` é o modelo: o conteúdo dele (por exemplo, `.bashrc`, `.profile`) é copiado para a nova home criada pelo `-m`.
6. `sudo usermod -aG ops ana`. Sem o `-a`, o `-G` **substitui** a lista de grupos secundários: ela ficaria só em `ops` e perderia `dev` e `docker`.
7. (a) `640`. (b) `rwxr-x--x`. (c) `4755`: o `s` no lugar do `x` do dono indica SUID ligado com `x` presente.
8. `744`, ou seja, `rwxr--r--`. O dono ganha `x` (6 para 7), o grupo fica em 4, os outros ganham `r` (0 para 4).
9. **SUID** em executável: o programa roda com os privilégios do **dono do arquivo**; exemplo, `/usr/bin/passwd`, que pertence ao root e precisa gravar no `/etc/shadow`. **SGID** em diretório: os arquivos criados dentro dele herdam o **grupo do diretório**. **Sticky bit** em diretório: só o **dono do arquivo** (ou o root) pode apagá-lo ou renomeá-lo, mesmo que outros tenham `w` no diretório; exemplo, `/tmp`. **`S` maiúsculo**: o bit especial está ligado, mas o `x` correspondente **não** está.
10. (a) **Sim**, há `r` e `x`. (b) **Sim**, há `x` no diretório e `r` no arquivo. (c) **Não**, falta `w` no diretório. (d) **Não**: apagar um arquivo é alterar a lista de entradas do **diretório**, e isso exige `w` (com `x`) no diretório. A permissão do próprio arquivo não decide.

</details>

---

## 7. Checkpoint A — Domingo 18/10, à noite

Critérios revistos em 13/10 para a nova estratégia. Marque com base no que está registrado nos arquivos, não na sensação.

| # | Critério | Cumprido |
|---|---|---|
| 1 | Práticas 1 e 2 feitas e registradas | |
| 2 | Simulado 02 com **24 ou mais** acertos | |
| 3 | Autoavaliações das Semanas 5 e 6 feitas (meta: 8 de 10 em cada) | Semana 5: **sim, 9 de 10**. Semana 6: na quinta 22/10 |
| 4 | Curso até a aula 72 (ou até a 64, com 65 a 72 marcadas para a segunda 19/10) | |

| Resultado | Condição | Decisão |
|---|---|---|
| **Verde** | Os quatro cumpridos | Segue para a Etapa 2 na segunda 19/10 |
| **Amarelo** | Um critério falhou | Segue; o item vira a primeira atividade da segunda 19/10 |
| **Vermelho** | Dois ou mais falharam, ou simulado 02 abaixo de 20 | A semana de 19/10 abre com as dívidas restantes e o Checkpoint B (25/10) passa a decidir a data |

**Previsão de 16/10: amarelo.** O critério 3 falha no domingo por desenho: a autoavaliação da Semana 6 precisa de três dias depois da Prática 2 e fica para a quinta 22/10. Se mais um critério falhar (Prática 2, simulado 02 ou curso), o resultado passa a vermelho.

Uma autoavaliação abaixo de 8 não reprova o checkpoint: as questões erradas viram o aquecimento da Etapa 2.

---

## 8. Etapa 2 — Laboratórios do Tópico 4 (Semana 8, 19 a 25/10)

Os roteiros das Práticas 3, 4 e 5, do bloco curto, a autoavaliação da Semana 8 e o calendário estão em `labs/semana-08.md`.

---

## 9. Registro das sessões

### Autoavaliação da Semana 5 — 13 e 15/10 — CONCLUÍDA

**Resultado: 9 de 10 acertos firmes. Meta: 8.** Questões 1 a 7 em 13/10 e 8 a 10 em 15/10, nove e onze dias depois do Laboratório 2.

| Q | Situação | Observação |
|---|---|---|
| 1 a 5 | Certas | — |
| 6 | **Respondida com consulta** | O `if` está correto, mas foi pesquisado: não conta como acerto firme |
| 7 | Certa no conceito | No exemplo de texto saiu `[ "$nome" - "Davi" ]`; o operador é `=` |
| 8 | Certa | Completa: `$?`, `exit 0`, `exit 1`, `&&` e `\|\|` |
| 9 | Certa | As duas formas valem: a lista `1 2 3 4 5` e a expansão de chaves `{1..5}`. O gabarito usava `$(seq 1 5)`; vale saber as três, porque a prova pode mostrar qualquer uma |
| 10 | Certa | `i`, `Esc`, `:wq` e `:q!` no `vi`; `Ctrl+O`, `Enter` e `Ctrl+X` no `nano` |

**Leitura.** Retenção boa: onze dias depois do laboratório, o shell script (peso 4, o maior objetivo da prova) segurou nove de dez sem consulta. A única lacuna é escrever o `if` de memória.

**Para o Notion:** questão 6, o `if [ $# -ne 2 ]; then echo "erro"; fi`, escrito de memória até sair sem pensar.

**Ajustes de forma (sem número):**

1. **Aspas curvas** (`“ ”`) nas respostas 6, 7 e 9. No terminal, só as retas (`"`) funcionam; numa questão de preencher, aspa curva invalida a resposta.
2. **`Crtl` em vez de `Ctrl`** na questão 10. É a segunda vez (já aparecia no caderno da Semana 5).
3. Na questão 10, "o `Esc` volta ao modo em que você digita comandos": o `Esc` volta ao **modo normal** (o de navegação, que o material também chama de modo de comando). Os comandos com `:`, como `:wq`, são digitados no **modo de linha de comando**, que se abre com `:` a partir do normal. Na prova, os nomes que aparecem são **inserção** e **comando** (ou normal).

### Prática 1 — 13 e 15/10 — CONCLUÍDA (falta só a parte dos Exercícios da LPI)

**Blocos 1 e 2 anotados em 13/10; bloco 3, experimento sem `-m` e "Para o caderno" em 15/10.** Faltam os 20 minutos de Exercícios da LPI (lições 5.1 e 5.2), remarcados para o domingo 18/10.

**Vocabulário anotado:** UID, GID, grupo primário (registrado no `/etc/passwd`) e grupos secundários. Correto.

#### Bloco 1 — Quem sou eu e quem está logado

| Comando | Resultado registrado |
|---|---|
| `whoami` | `davi`: o usuário efetivo |
| `id` | `uid=1000(davi) gid=1000(davi)`, e os grupos `adm`, `cdrom`, `sudo`, `dip`, `plugdev`, `users` e `lxd` |
| `id root` | UID **0** |
| `who` e `w` | O `who` mostra as sessões (usuário e terminal); o `w` acrescenta o que cada sessão está fazendo: comando atual, tempo ocioso e uso de CPU |
| `last \| head` | Histórico de logins, do mais recente, nas 10 primeiras linhas |
| `sudo whoami` | `root`: o comando roda como root, e o shell volta a ser do `davi` |

Faltam duas respostas do roteiro:

1. **De qual arquivo o `last` lê?** Ainda sem resposta no caderno de 15/10. Do `/var/log/wtmp`, o registro binário de logins e logouts. (O `who` lê o `/var/run/utmp`, que guarda só as sessões abertas agora.)
2. **`su - alice`, `sudo -i` e `sudo su`:** a diferença entre `su` e `sudo` foi respondida em 15/10 ("Para o caderno", abaixo). O detalhe das três formas: o `su - alice` abre um shell de login como `alice` e pede a **senha da alice**; o `sudo -i` abre um shell de login do **root** e pede a **sua** senha; o `sudo su` também vira root com a sua senha, mas sem o ambiente de login do root (o `sudo su -` teria).

#### Bloco 2 — Os arquivos de contas

| Arquivo | Linha lida | O que mostra |
|---|---|---|
| `/etc/passwd` | `root:x:0:0:root:/root:/bin/bash` | 7 campos; as contas `daemon` e `bin` têm shell `/usr/sbin/nologin`, porque são de sistema |
| `/etc/shadow` | `root:*:20563:0:99999:7:::` | 9 campos; hash da senha e prazos |
| `/etc/group` | `root:x:0:` | 4 campos; definição dos grupos e membros |
| `/etc/gshadow` | — | Senha de grupo e administradores do grupo, protegido como o `shadow` |
| `/etc/login.defs` | `UID_MIN 1000` | O primeiro UID de usuário comum, que é o do `davi` |

Permissões registradas: `passwd` e `group` com `-rw-r--r--` (`root root`, legíveis por todos); `shadow` e `gshadow` com `-rw-r-----` (`root shadow`, só root e grupo `shadow` leem).

Ajustes de caderno:

1. **Ainda faltam os 7 campos do `/etc/passwd`, um por um** (o bloco 2 não mudou em 15/10), como o roteiro pede: usuário, `x`, UID, GID, comentário, diretório pessoal e shell de login. É o conteúdo da Q35 do simulado 01, errada por chute.
2. **Falta responder por que o `/etc/passwd` é legível por todos e não guarda a senha:** vários programas precisam traduzir UID em nome; por isso a senha foi para o `/etc/shadow`, e o `x` do segundo campo indica isso.
3. **O `*` no segundo campo do `shadow`** significa que a conta **não tem senha válida**: não dá para entrar com senha. É o caso das contas de sistema. O `20563` é a data da última troca de senha, contada em dias desde 01/01/1970; `0`, `99999` e `7` são o mínimo e o máximo de dias entre trocas e o aviso antes de expirar.
4. **No `/etc/group`, os 4 campos:** nome, `x`, GID e lista de membros. Em `root:x:0:` a lista está vazia.
5. Na listagem do `ls -l`, a primeira linha saiu `rw-r--r--`, sem o `-` do tipo de arquivo. É de cópia, mas na prova o primeiro caractere conta: `-` arquivo, `d` diretório, `l` link.
6. O `#SYS_UID_MIN 101` está comentado (começa com `#`), então vale o padrão do sistema. O `SUB_UID_MIN` é de outro assunto (contêineres sem root) e não cai na prova.

#### Bloco 3 — Criar, alterar e quebrar

| O que foi anotado | Revisão |
|---|---|
| `groupadd` cria o grupo, e os grupos precisam existir antes de aparecer nas opções do `useradd` | Correto. Sem o grupo, o `useradd -G dev` falha com `group 'dev' does not exist` |
| `-m` cria o diretório pessoal; `-s /bin/bash` define o shell de login; `-g ops` define o grupo primário; `-G dev` define os grupos secundários | Correto |
| `passwd` define a senha do usuário; `useradd` cria a conta; `/etc/skel` é o modelo do diretório pessoal | Correto |
| "`/home/alice` e `/home/bob` → grupo primário" | **Errado. Ver Correção 75** |

**A quebra de propósito.** Correto: sem o `-a`, o `usermod -G ops alice` **substituiu** a lista e tirou a `alice` do `dev`; o grupo primário não muda; o `usermod -aG dev alice` devolveu o `dev` mantendo o `ops`. Os GIDs anotados conferem: `dev` é 1001 e `ops` é 1002, porque foram os dois primeiros grupos criados depois do `davi` (1000).

**Os números da VM fecham.** Os usuários receberam UIDs em ordem (`alice` 1001, `bob` 1002, `carol` 1003, `teste_sem_nome` 1004). Os grupos: `dev` 1001, `ops` 1002, `alice` 1003, `bob` 1004 e `teste_sem_nome` 1005. A `carol` **não** ganhou grupo próprio, porque o `-g ops` já deu a ela um grupo primário. É por isso que o `teste_sem_nome` ficou com GID 1005, e não 1004.

**Experimento sem `-m` — registrado.** O `id` mostra a conta criada (`uid=1004`), o `ls -ld /home/teste_sem_nome` responde `No such file or directory`, e mesmo assim o `/etc/passwd` traz `/home/teste_sem_nome` no sexto campo. Conclusão certa, e vale escrever o mecanismo: **o `useradd` grava o caminho do diretório pessoal no `/etc/passwd`, mas só cria a pasta com `-m`**. No Ubuntu, o padrão é não criar (no Red Hat é o contrário). Uma conta assim abre a sessão em `/`, com aviso de que a home não existe. O `adduser`, interativo, cria a home sempre.

**Para o caderno — revisão.** As três respostas estão corretas: `-g` primário e `-G` secundários, com o `-G` sozinho substituindo e o `-aG` acrescentando; o `/etc/skel` como modelo do diretório pessoal; o `su` com a senha do usuário de destino e o `sudo` com a senha de quem o invoca, conforme a política do `sudoers`.

**Atenção para a Prática 2:** o `teste_sem_nome` não está na limpeza original. A limpeza da Prática 2 foi atualizada no caderno da Semana 6 para incluí-lo.

#### Correção 75 — o `/home/alice` é o diretório pessoal, não o grupo primário

A anotação diz "`/home/alice` e `/home/bob` → grupo primário". São coisas de campos diferentes do `/etc/passwd`:

| Campo do `/etc/passwd` | Exemplo da `alice` | O que é |
|---|---|---|
| 4º, GID | `1003` | O **grupo primário**: um grupo com o mesmo nome do usuário (`alice`), criado junto com a conta |
| 6º, diretório pessoal | `/home/alice` | A **pasta** do usuário, criada pelo `-m` com o conteúdo do `/etc/skel` |

Na sua VM: o grupo primário da `alice` é `alice`, o do `bob` é `bob` e o da `carol` é `ops` (por causa do `-g`). Para ver: `id -gn alice ; id -gn carol ; grep '^alice:' /etc/passwd | cut -d: -f4,6`.

### Prática 2 — domingo 18/10

*A preencher.*

### Simulado 02 — sábado 17/10

*A preencher.* Registre também em `labs/simulados-práticos.lpi/resultados_simulados.md`.

### Autoavaliação da Semana 6 — quinta 22/10

*A preencher.* Acertos: de 10. Questões erradas:

### Correções da semana

A numeração segue a série global. **A próxima é a 76.** Erros de simulado e de autoavaliação não geram correção numerada; vão para o Notion.

| # | Tema | Origem |
|---|---|---|
| 75 | `/home/alice` é o diretório pessoal (6º campo), não o grupo primário (4º campo) | Prática 1, bloco 3, 15/10 |

---

## 10. Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Ter 13 | 2h05 | | Autoavaliação S5 (1 a 7) e Prática 1, blocos 1 e 2 |
| Qua 14 | 2h20 | 0 | Sem estudo |
| Qui 15 | 1h | | Autoavaliação S5 (8 a 10) e Prática 1, bloco 3 |
| Sex 16 | 2h10 | 0 | Sem estudo; Prática 2 para o domingo |
| Sáb 17 | 3h10 | | Simulado 02 e aulas 41 a 58 |
| Dom 18 | 3h30 | | Prática 2, Exercícios da LPI 5.1 a 5.4, aulas 59 a 72 e Checkpoint A |

---

## 11. Checklist da semana

- [x] Autoavaliação da Semana 5 respondida e conferida (13 e 15/10): 9 de 10
- [x] Prática 1, blocos 1 a 3 e experimento (13 e 15/10)
- [ ] Exercícios da LPI 5.1 e 5.2 (domingo 18/10)
- [ ] Prática 2, com Exercícios da LPI 5.3 e 5.4 e limpeza dos usuários de teste (domingo 18/10)
- [ ] `cheatsheets/permissoes.md` escrito à mão, nos 10 minutos de registro da Prática 2
- [ ] Curso, aulas 41 a 58 (sábado)
- [ ] Simulado 02 e apuração por tópico e por tema (sábado 17/10)
- [ ] Curso, aulas 59 a 72 (domingo)
- [ ] Autoavaliação da Semana 6 respondida e conferida (quinta 22/10)
- [ ] Checkpoint A preenchido
- [ ] Commits ao fim de cada sessão

---

## Entregável

`labs/semana-07.md` preenchido, `cheatsheets/permissoes.md`, resultado do simulado 02 em `resultados_simulados.md`, as duas autoavaliações conferidas, o curso fechado e o Checkpoint A preenchido.