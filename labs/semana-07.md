# Semana 7 — Tópico 5 em prática: autoavaliação da Semana 5, Práticas 1 e 2

Período: 12/10 a 20/10/2026
Objetivos da prova: Tópico 5 (5.1 a 5.4) em prática
**Data da prova: segunda-feira, 30/11/2026** (movida em 26/10)
Situação: **semana fechada**

---

## Resumo da semana

| Item | Resultado |
|---|---|
| Autoavaliação da Semana 5 (shell script) | **9 de 10**, nove a onze dias depois do Laboratório 2 |
| Prática 1 — usuários e grupos | Feita em 13 e 15/10; Correção 75 |
| Prática 2 — permissões | Feita em 19 e 20/10; correções registradas em 22/10 |
| Curso | Sem avanço (parado na aula 40) |

**Histórico.** A semana foi planejada em 13/10 com a prova em 23/11 e um modelo de dívidas a pagar. Os dias 14, 16, 17 e 18/10 ficaram sem estudo, e a Prática 2 terminou em 20/10. Em 26/10 a estratégia mudou para conteúdo seguido de operação prática diária, e a prova passou para 30/11 (`PLANO.md`, seções 6, 7 e 11).

---

## Calendário

| Dia | Atividade | Tempo |
|---|---|---|
| Ter 13 | Autoavaliação da Semana 5, questões 1 a 7 · Prática 1, blocos 1 e 2 | **feito** |
| Qua 14 | Sem estudo | — |
| Qui 15 | Autoavaliação da Semana 5, questões 8 a 10 · Prática 1, bloco 3 e experimento sem `-m` | **feito** |
| Sex 16 | Sem estudo; a Prática 2 foi para o domingo | — |
| Sáb 17 | Sem estudo; o simulado 02 foi para o sábado 24/10 | — |
| Dom 18 | Sem estudo | — |
| Seg 19 | Prática 2, blocos 1 a 4 e parte do 5 | **feito** |
| Ter 20 | Prática 2, blocos 5 e 6 | **feito** |

---

## Registro das sessões

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

**Reincidência:** o `$#` voltou a errar na Q24 do simulado 02 e está na lista de reincidências da operação prática, com o treino V4.

**Ajustes de forma (sem número):**

1. **Aspas curvas** (`“ ”`) nas respostas 6, 7 e 9. No terminal, só as retas (`"`) funcionam; numa questão de preencher, aspa curva invalida a resposta.
2. **`Crtl` em vez de `Ctrl`** na questão 10. É a segunda vez (já aparecia no caderno da Semana 5).
3. Na questão 10, "o `Esc` volta ao modo em que você digita comandos": o `Esc` volta ao **modo normal** (o de navegação, que o material também chama de modo de comando). Os comandos com `:`, como `:wq`, são digitados no **modo de linha de comando**, que se abre com `:` a partir do normal. Na prova, os nomes que aparecem são **inserção** e **comando** (ou normal).

### Prática 1 — 13 e 15/10 — CONCLUÍDA

**Blocos 1 e 2 anotados em 13/10; bloco 3, experimento sem `-m` e "Para o caderno" em 15/10; respostas que faltavam e correções registradas em 22/10.** Os Exercícios da LPI 5.1 e 5.2 foram feitos em 21/10 (registro em `labs/semana-08.md`).

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

Respostas que faltavam, registradas em 22/10:

1. **De qual arquivo o `last` lê?** Do `/var/log/wtmp`, o registro binário de logins e logouts. (O `who` lê o `/var/run/utmp`, que guarda só as sessões abertas agora.)
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

1. **Os 7 campos do `/etc/passwd`** (registrado em 22/10), na linha `root:x:0:0:root:/root:/bin/bash`:

   | Campo | Valor | Significado |
   |---|---|---|
   | 1 | `root` | Nome de login |
   | 2 | `x` | Marcador: o hash da senha está no `/etc/shadow` |
   | 3 | `0` | UID |
   | 4 | `0` | GID do grupo primário |
   | 5 | `root` | Comentário (GECOS) |
   | 6 | `/root` | Diretório pessoal |
   | 7 | `/bin/bash` | Shell de login |

2. **Por que o `/etc/passwd` é legível por todos e não guarda a senha** (registrado em 22/10): vários programas precisam traduzir UID em nome; por isso a senha foi para o `/etc/shadow`, legível só pelo root e pelo grupo `shadow`, e o `x` do segundo campo indica isso.
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

### Prática 2 — 19 e 20/10 — CONCLUÍDA

**Blocos 1 a 4 em 19/10; blocos 5 e 6 em 20/10; correções dos blocos 1, 2, 4 e 5 registradas em 22/10.** Os Exercícios da LPI 5.3 e 5.4 foram feitos em 21/10 (registro em `labs/semana-08.md`).

#### Bloco 1 — Ler as permissões

Listagem registrada: `/etc/shadow` com `-rw-r-----` (`root shadow`), `/home` com `drwxr-xr-x`, `/tmp` com `drwxrwxrwt` e `/usr/bin/passwd` com `-rwsr-xr-x`. As tabelas de `u`, `g`, `o` e `a` e de `r`, `w` e `x` em arquivo e em diretório estão corretas.

Ajustes:

1. **Corrigido em 22/10. Na linha do `/tmp`, o dono saiu `rwr`.** O certo é `rwx`: `drwxrwxrwt` se lê `d` · `rwx` · `rwx` · `rwt`.
2. **Onde aparecem o `s` e o `t`**, que o roteiro pedia: o `s` do `/usr/bin/passwd` está no lugar do `x` do **dono** (SUID: o programa roda como root, que é quem pode gravar no `/etc/shadow`); o `t` do `/tmp` está no lugar do `x` dos **outros** (sticky bit).
3. A primeira linha da listagem saiu `- rw-r-----`: o `-` do tipo virou marcador de lista no editor. No caderno, coloque a listagem em bloco de código para o `-` não sumir.
4. O `/etc/shadow` passou de 942 para 1129 bytes desde a Prática 1: são as linhas da `alice`, do `bob`, da `carol` e do `teste_sem_nome`.

#### Bloco 2 — `chmod` em octal e simbólico

| Comando, na ordem | Octal | Simbólico | Revisão |
|---|---|---|---|
| `chmod 640 teste` | 640 | `rw-r-----` | Certo |
| `chmod u+x teste` | 740 | `rwxr-----` | Certo |
| `chmod g=rw,o= teste` | 760 | `rwxrw----` | Certo |
| `chmod a-x teste` | 660 | `rw-rw----` | Certo |
| `chmod 4644 teste` | **4644** | `rwSr--r--` | Corrigido em 22/10: no caderno tinha saído **4664**. O simbólico está certo, e ele mostra o erro: `r--` no grupo vale 4, não 6 |
| `chmod u+x teste` | 4744 | `rwsr--r--` | Certo |

A regra do `s` e do `S` está registrada com o mecanismo certo: minúsculo é bit especial com `x`; maiúsculo é bit especial sem `x`. O mesmo vale para `t` e `T`.

#### Bloco 3 — `chown` e `chgrp`

Correto em todos os passos: `chown bob:dev` troca dono e grupo; `chown :ops` troca só o grupo; `chgrp dev` também só o grupo; resultado final `bob` e `dev`. A tabela de quem pode o quê está certa: só o root troca o dono; o dono troca o grupo, para um grupo do qual participa; o dono ou o root usam o `chmod`. A Correção 68 (`chmod` contra `chown`) está resolvida na prática.

#### Bloco 4 — Diretório: o `x` é de atravessar

**Corrigido em 22/10.** As frases do caderno estavam certas, mas a tabela contradizia duas delas. Para 500 e 100 você escreveu que "consegue acessar um arquivo pelo nome", e a tabela marcou `cat pasta/arq` como "Não". O certo é **Sim** nos dois: o `x` basta para atravessar o diretório e abrir um arquivo cujo nome você conhece. Tabela corrigida:

| Modo | `ls pasta` | `cat pasta/arq` | `touch pasta/novo` | `rm pasta/arq` |
|---|---|---|---|---|
| 700 | Sim | Sim | Sim | Sim |
| 600 | Só os nomes, com erros nos detalhes | Não | Não | Não |
| 500 | Sim | **Sim** | Não | Não |
| 300 | Não | Sim | Sim | Sim |
| 100 | Não | **Sim** | Não | Não |

Se a tabela foi preenchida como **previsão** antes de executar, vale registrar assim: "previ Não; o terminal mostrou Sim". Esse é o erro mais útil da prática, porque é o que a prova cobra (Q39 do simulado 01 e Q39 do simulado 03).

As três regras, com o mecanismo:

1. `r` no diretório lista os **nomes**.
2. `x` no diretório permite **atravessar**: entrar com `cd` e abrir o que está dentro, desde que se saiba o nome.
3. Criar, apagar e renomear mexem na **lista de entradas do diretório**, e por isso exigem `w` **e** `x` no diretório. A permissão do próprio arquivo não decide se ele pode ser apagado.

#### Bloco 5 — SGID e sticky bit (em parte)

Você trocou o `chmod g+wxs,o+t` pelo octal, com `sudo chown root:dev /srv/Box` e `3775`. **O caminho está certo**: o diretório nasce com 755; `g+wx` leva a 775; o `s` do grupo soma 2 e o `t` soma 1 no primeiro dígito, e o resultado é **3775**, ou `drwxrwsr-t`. A anotação trazia `sudo 3775 /srv/Box`, sem o `chmod`; corrigido em 22/10 para `sudo chmod 3775 /srv/Box`.

**Resultados registrados em 20/10.** O arquivo `a` nasceu com dono `alice` e grupo **`dev`**: o SGID funcionou. As regras anotadas estão corretas e mais precisas que o roteiro:

| Anotado | Revisão |
|---|---|
| SGID: determina o grupo herdado pelos arquivos novos | Correto |
| Sticky: podem remover ou renomear uma entrada o dono do arquivo, o dono do diretório ou o root; "só quem criou pode apagar" é simplificação | Correto, e é a formulação que a prova usa |
| O sticky não impede alterar o **conteúdo**; isso depende das permissões do próprio arquivo | Correto |
| O `/srv` evita depender da travessia da sua pasta pessoal | Correto |

**Resultado esperado do `sudo -u bob rm /srv/Box/a`:** falha com `rm: cannot remove '/srv/Box/a': Operation not permitted`: o `bob` tem `w` no diretório pelo grupo `dev`, mas não é dono do arquivo nem do diretório. O comando do bloco é `sudo chmod 3775 /srv/Box`.

#### Bloco 6 — Temporários e links

Correto. O link guarda o **texto** `alvo`; esse texto é resolvido a partir do diretório onde o link está, então em `sub/` ele procura `~/lab6/sub/alvo`, que não existe, e o `cat` falha. O `readlink sub/link` devolvendo `alvo` é a prova disso. A tabela de `/tmp`, `/var/tmp` e `/run` está certa, e a resposta também: o `/run` é esvaziado na inicialização; a limpeza do `/tmp` depende da política do sistema; o `/var/tmp` sobrevive a reinícios.

**Com caminho absoluto** (`ln -s ~/lab6/alvo link`), o link continua funcionando depois do `mv`, porque o texto guardado já aponta o lugar certo.

**Limpeza:** se os usuários e grupos de teste ainda estiverem na VM, o treino V6 da operação prática remove os grupos `dev` e `ops` no fim. Para conferir: `getent passwd alice bob carol teste_sem_nome ; getent group dev ops`.

### Correções da semana

A numeração segue a série global. **A próxima é a 76.**

| # | Tema | Origem |
|---|---|---|
| 75 | `/home/alice` é o diretório pessoal (6º campo), não o grupo primário (4º campo) | Prática 1, bloco 3, 15/10 |

---

## Horas da semana

| Dia | Previsto | Real | Observação |
|---|---|---|---|
| Ter 13 | 2h05 | | Autoavaliação S5 (1 a 7) e Prática 1, blocos 1 e 2 |
| Qua 14 | 2h20 | 0 | Sem estudo |
| Qui 15 | 1h | | Autoavaliação S5 (8 a 10) e Prática 1, bloco 3 |
| Sex 16 | 2h10 | 0 | Sem estudo |
| Sáb 17 | 3h10 | 0 | Sem estudo |
| Dom 18 | 3h30 | 0 | Sem estudo |
| Seg 19 | — | | Prática 2, blocos 1 a 4 e parte do 5 |
| Ter 20 | — | | Prática 2, blocos 5 e 6 |

---

## Checklist da semana

- [x] Autoavaliação da Semana 5 respondida e conferida (13 e 15/10): 9 de 10
- [x] Prática 1, blocos 1 a 3 e experimento (13 e 15/10)
- [x] Prática 2, blocos 1 a 6 (19 e 20/10)
- [x] Correções das Práticas 1 e 2 no caderno (22/10)