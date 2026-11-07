# Operação prática — 05/11 a 26/11/2026

**Prova: segunda-feira, 30/11/2026** · Exame **010-160** · Criado em 26/10/2026

A operação começou na **quinta 05/11**, com o simulado 03 (27 de 40, 20 firmes). **Calendário refeito em 06/11:** o sábado 07/11 fica com o R4 e os Exercícios da LPI da semana, o domingo 08/11 com as aulas 41 a 72 e o que faltar da LPI, e o simulado 05 passou para a segunda 09/11. Daí até a prova, **todos os dias** são de prática. Não há dívida. A única exceção é o fim de semana de 07 e 08/11, que fecha o conteúdo (as aulas 41 a 72) e os Exercícios da LPI atrasados.

Este arquivo substitui os arquivos semanais a partir de 05/11. O registro de cada dia fica na seção 9.

---

## 1. As regras

| # | Regra | Por quê |
|---|---|---|
| 1 | **Nada passa para o dia seguinte.** O que não coube no dia some do plano | O acúmulo de pendências derrubou o rendimento em outubro. Um erro real volta sozinho no próximo simulado, e aí é corrigido com o contexto fresco |
| 2 | **A correção é no mesmo dia**, em no máximo 20 minutos (seção 4) | Corrigir dias depois vira tarefa burocrática, não aprendizado |
| 3 | **Card no Notion só para reincidência**, ou seja, um erro que já aconteceu antes | Quatro das nove correções antigas voltaram a errar no simulado 02. Escrever não fixou; **executar na VM** fixa |
| 4 | **Condição de prova** em todo simulado: cronometrado, sem consulta, marcando cada chute. **Questão pesquisada conta como errada** | A prova não tem consulta. Na dúvida, marque o chute e siga |
| 5 | **Um número para acompanhar: os acertos firmes**, sem chutes e sem pesquisas | O total com chutes engana: 28 no simulado 01 eram só 23 firmes |
| 6 | **O domingo é descanso de verdade** | A retenção se consolida no intervalo, não na repetição sem pausa |

---

## 2. Os dois tipos de dia

**Carga revista em 04/11:** cerca de **2h a 2h15 todos os dias**, seis dias por semana (perto de 13h semanais), em vez de dias leves alternados com dias pesados. Todo dia tem simulado (completo ou mini), treino na VM e Exercícios da LPI.

| Tipo | Sessão | Tempo |
|---|---|---|
| **A — Simulado** | Lacunas (5 min) · **simulado completo**, 40 questões em 60 min · correção (20 min) · **treino na VM** sobre os erros do simulado (25 min) · **1 bloco** dos Exercícios da LPI (25 min) | cerca de 2h15 |
| **B — Reforço** | Lacunas (5 min) · **mini-simulado**, 20 questões em 25 min · correção (10 min) · **treino na VM** (30 min) · **2 blocos** dos Exercícios da LPI (50 min) | cerca de 2h |

**Todo dia tem simulado:** completo nos dias A, mini nos dias B. Os mini-simulados M1 a M6 são escritos por mim **a partir dos seus erros** nos simulados anteriores, e o treino na VM dos dias A é sempre sobre o que você errou no simulado do dia.

**Exercícios da LPI** (`labs/simulados-práticos.lpi/exercicios-lpi.md`): as 24 lições terminam em 20/11; de 21 a 25/11, um bloco por dia **refaz as que você errou**, tópico a tópico.

**Banco de lacunas:** `labs/simulados-práticos.lpi/lacunas.md`. Uma série por dia, na ordem; as erradas voltam três dias depois.

---

## 3. Calendário

**Refeito em 06/11**, a seu pedido. Quinta e sexta foram feitas em parte; o que ficou para trás foi para o fim de semana, e a semana de 09/11 andou um dia:

| Mudança | Antes | Agora |
|---|---|---|
| R4 | Qui 05/11 | **Sáb 07/11** |
| Exercícios da LPI 4.2, 4.3, 5.1 e 5.3 | Qui 05 a sáb 07/11 | **Sáb 07 e dom 08/11** |
| Aulas 41 a 72 | Noites de qui 05 a sáb 07/11 | **Dom 08/11** |
| Simulado 05 | Sáb 07/11 | **Seg 09/11** |
| R2 | Seg 09/11 | Ter 10/11 |
| Simulado 04 | Ter 10/11 | Qua 11/11 |
| M1 | Sex 13/11 | Qui 12/11 |
| Simulado 06 | Qui 12/11 | Sex 13/11 |
| R1 | Qua 11/11 | **Saiu do plano**: os temas dele (permissões, `tar`, redirecionamento, diretórios, lacunas) já aparecem em todo simulado e no banco de lacunas |

De 15/11 em diante, nada mudou.

| Dia | Tipo | Sessão | Treino na VM | Exercícios da LPI | Lacunas |
|---|---|---|---|---|---|
| **Qui 05/11** | A | **Simulado 03** (feito: 27 de 40, 20 firmes) · V5 e V6 (feitos). O R4 e a LPI 4.3 e 5.1 passaram para o sábado 07/11 | V5 e V6 (feitos) | — | Série 03 |
| Sex 06/11 | B | **R3** (feito: 17 de 20) · **bloco curto**: 4.1 e here document (feito) · V1 e V3 (feitos). A LPI 4.2 passou para o sábado 07/11 | V1 e V3 (feitos) | 4.1 (feito) | Série 04 |
| Sáb 07/11 | B | **R4** — contas e permissões (`reforco-r3-r4.md`) · **Exercícios da LPI da semana**, o quanto couber | — | 4.2 e 4.3, lição 1 e 4.3, lição 2 e 5.1 e 5.3 | Série 05 |
| **Dom 08/11** | Conteúdo | **Aulas 41 a 72** (curso fechado) · Exercícios da LPI da semana que não saíram no sábado | — | — | — |
| **Seg 09/11** | A | **Simulado 05** (`simulado-05.md`) | V4 (scripts) e os erros do simulado | 5.2 | Série 06 |
| Ter 10/11 | B | **R2** — permissões, `tar`, redirecionamento, diretórios, processos e rede (`praticas_simulados.md`, seção 8) | V7 (processos e rede) | 4.4 e 5.4 | Série 07 |
| **Qua 11/11** | A | **Simulado 04** (`simulado-04.md`) | Conforme os erros do simulado | 3.1 | Série 08 |
| Qui 12/11 | B | **M1** — os temas mais errados nos simulados 03, 05 e 04 | Conforme o M1 | 2.1, lição 1 e 2.1, lição 2 | Série 09 |
| **Sex 13/11** | A | **Simulado 06** | Conforme os erros do simulado | 2.2 | Série 10 |
| **Sáb 14/11** | A | **Simulado 07** | Conforme os erros do simulado | 2.3, lição 1 e 2.3, lição 2 | Série 11 |
| Dom 15/11 | — | Descanso | — | — | — |
| Seg 16/11 | B | **M2** | Conforme o M2 | 2.4 e 3.2, lição 1 | Série 12 |
| **Ter 17/11** | A | **Simulado 08** — conta para a decisão | Conforme os erros do simulado | 3.2, lição 2 | Série 13 |
| Qua 18/11 | B | **M3** | Conforme o M3 | 3.3, lição 1 e 3.3, lição 2 e 1.1 | Série 14 |
| **Qui 19/11** | A | **Simulado 09** — conta para a decisão | Conforme os erros do simulado | 1.2 | Série 15 |
| Sex 20/11 | B | **M4** (feriado) | Conforme o M4 | 1.3 e 1.4 | Série 16 |
| **Sáb 21/11** | A | **Simulado 10** · **decisão da data** (média de acertos firmes dos simulados 08, 09 e 10) | Conforme os erros do simulado | Revisão: erradas do Tópico 5 | Série 17 |
| Dom 22/11 | — | Descanso | — | — | — |
| **Seg 23/11** | A | **Simulado 11** | Conforme os erros do simulado | Revisão: erradas do Tópico 4 | Série 18 |
| Ter 24/11 | B | **M5** | Conforme o M5 | Revisão: erradas dos Tópicos 3 e 2 | Série 19 |
| **Qua 25/11** | A | **Simulado 12** — o simulado final | Conforme os erros do simulado | Revisão: erradas do Tópico 1 | Série 20 |
| Qui 26/11 | Leve | **M6** — só as reincidências · releitura das colas | Os blocos das reincidências | — | Série 21 |
| Sex 27/11 | — | Descanso antes da prova | — | — | — |
| Sáb 28/11 | — | Descanso antes da prova | — | — | — |
| Dom 29/11 | — | Descanso antes da prova · não estudar na véspera | — | — | — |
| **Seg 30/11** | — | **PROVA — Linux Essentials 010-160** | — | — | — |

**Se a LPI atrasada não sair no fim de semana,** ela entra um bloco por dia na semana de 09/11, junto com os blocos novos: **5.1** na seg 09, **4.3, lição 1** na ter 10, **4.3, lição 2** na qua 11, **4.2** na qui 12 e **5.3** na sex 13. A aula que não couber no domingo vai para a noite de segunda.

**Contas:** 10 simulados completos (03 a 12), 9 mini-simulados (R2, R3, R4 e M1 a M6), as 24 lições da LPI mais cinco blocos de revisão das erradas, treino na VM todos os dias, 21 séries de lacunas e 3 domingos de descanso, além dos três dias antes da prova.

**Se um dia cair**, ele não é reposto. O dia seguinte segue o calendário, e a regra 1 vale aqui também.

---

## 4. Protocolo de correção (no mesmo dia)

Limite: **20 minutos** depois de um simulado, **10** depois de um mini-simulado.

1. Confira o gabarito e preencha a apuração do próprio arquivo: acertos, chutes e **acertos firmes**.
2. Na tabela "Questões erradas" do arquivo, anote **só as erradas e as chutadas**, com uma coluna a mais: **é reincidência?** Ou seja, esse erro já apareceu antes, em simulado, reforço ou correção numerada?
3. Para cada erro, leia o comentário do gabarito. Se o erro for sobre um comando, **rode o comando na VM** antes de seguir.
4. **Se for reincidência:** card no Notion e uma linha na seção 6 deste arquivo.
5. Acabou o tempo, acabou a correção. O que sobrou volta, se for real, no próximo simulado.

Me mande os resultados ao fim do dia, como sempre. Eu reviso, registro e uso os erros para escrever os mini-simulados M1 a M6.

---

## 5. Treinos na VM

Trinta minutos nos dias B. **Preveja a saída antes de cada comando**; a previsão errada é o que ensina. Os comentários com `#` mostram o resultado esperado; tape-os com a mão.

### V1 — Caminhos e navegação

```bash
cd /var/log ; pwd                 # /var/log
cd ../tmp ; pwd                   # /var/tmp
cd - ; pwd                        # /var/log (o anterior, não o pai)
cd ./apt ; pwd                    # /var/log/apt
cd ../.. ; pwd                    # /var
cd ; pwd ; cd ~ ; pwd             # /home/davi nas duas
cd /home ; pwd ; ls               # /home: o diretório que CONTÉM as pastas pessoais
echo ~ ~root                      # /home/davi /root
ls -a ~ | head -5                 # os ocultos começam com ponto
```

### V2 — Ajuda e documentação

```bash
type cd ls echo                   # interno, arquivo (ou alias), interno
help cd | head -5                 # ajuda de comando interno
man -k passwd | head              # busca nas descrições; o mesmo que apropos passwd
whatis passwd                     # mostra as seções em que passwd existe: 1 e 5
man 5 passwd                      # formato do ARQUIVO (q para sair)
ls --help | head -5               # resumo curto do próprio programa
which ls ; type -a ls
sudo updatedb ; locate -n 3 passwd ; find /etc -name passwd
```

### V3 — Redirecionamento, pipes e grep

```bash
ls /etc/hostname /naoexiste > a.txt 2>&1 ; cat a.txt     # as duas linhas no arquivo
ls /etc/hostname /naoexiste 2>&1 > b.txt ; cat b.txt     # erro na TELA; só a saída no arquivo
ls /etc/hostname /naoexiste &> c.txt ; cat c.txt         # as duas
ls /naoexiste 2> /dev/null ; echo $?                     # nada na tela; código 2
grep -v '^#' /etc/ssh/sshd_config | grep -v '^$' | head  # linhas que NÃO são comentário nem vazias
grep -c bash /etc/passwd ; grep -n root /etc/passwd ; grep -i ROOT /etc/passwd
cut -d: -f7 /etc/passwd | sort | uniq -c | sort -rn      # shells, do mais usado ao menos
cat << FIM > d.txt
linha 1
linha 2
FIM
cat d.txt ; wc -l d.txt                                  # o FIM não entra
```

### V4 — Scripts

```bash
cat > p.sh << 'FIM'
#!/bin/bash
echo "nome: $0 | quantidade: $# | primeiro: $1 | segundo: $2 | todos: $@"
if [ $# -ne 2 ]; then
  echo "uso: $0 a b"
  exit 1
fi
echo ok
FIM
chmod +x p.sh
./p.sh um ; echo $?               # mensagem de uso; código 1
./p.sh um dois ; echo $?          # ok; código 0
bash p.sh a b c ; echo $?         # quantidade 3; código 1
[ -f /etc/hosts ] && echo arquivo ; [ -d /etc ] && echo diretorio
for n in 1 2 3 ; do echo "volta $n" ; done
```

### V5 — Permissões

```bash
touch f ; mkdir -p d
for m in 640 750 751 4755 2744 ; do chmod $m f ; stat -c '%a %A' f ; done
for m in 1777 1770 2770 ; do chmod $m d ; stat -c '%a %A' d ; done   # t e T; s no grupo
chmod 754 f ; chmod o+w,g-x f ; stat -c '%a %A' f        # 746
chmod 640 f ; chmod g+w,o+x f ; stat -c '%a %A' f        # 661
chmod 755 f ; chmod u-w,g-r,o= f ; stat -c '%a %A' f     # 510
chmod 775 f ; chmod a-x f ; stat -c '%a %A' f            # 664
chmod 711 d ; ls -ld d                                    # x sem r: atravessa, não lista (o d no chmod é obrigatório)
```

### V6 — Contas e grupos

```bash
head -3 /etc/passwd ; grep davi /etc/passwd      # 7 campos; o x = senha no shadow
sudo grep davi /etc/shadow                       # 9 campos; o hash
grep -E '^(sudo|davi):' /etc/group               # 4 campos; membros secundários no 4º
id ; id root
sudo groupadd dev ; sudo groupadd ops    # se já existirem desde a Prática 2, o aviso pode ser ignorado
sudo useradd -m -s /bin/bash -G dev teste1 ; id teste1
sudo usermod -G ops teste1 ; id teste1           # o dev sumiu: -G sem -a substitui
sudo usermod -aG dev teste1 ; id teste1          # ops e dev
ls -a /etc/skel ; sudo ls -a /home/teste1        # o skel foi copiado
sudo chown teste1:ops f ; ls -l f ; sudo chgrp dev f ; ls -l f
last | head -3 ; who
sudo userdel -r teste1 ; sudo groupdel ops ; sudo groupdel dev
```

### V7 — Tópico 4: processos, hardware e rede

```bash
ps aux | head -5 ; ps -ef | head -3
sleep 300 &                        # [1] e o PID
jobs ; fg                          # traz para o primeiro plano; Ctrl+Z suspende
bg ; jobs ; kill %1 ; jobs         # kill sem número = SIGTERM (15)
sleep 300 & kill -9 $!             # SIGKILL: o processo não consegue tratar
free -h ; uptime
top                                # P ordena por CPU, M por memória, q sai
lsblk ; ls -l /dev/sda*            # b = dispositivo de bloco
lsmod | head -5 ; lspci | head -5
sudo dmesg | tail -5 ; ls /var/log ; ls /boot
head -5 /proc/cpuinfo ; ls /sys/class/net
ip addr show ; ip route show ; ss -tln
cat /etc/resolv.conf ; cat /etc/hosts
host lpi.org ; ping -c 2 8.8.8.8
```

### V8 — `tar`, compressão e links

```bash
sudo apt install -y zip unzip       # se ainda não tiver
mkdir -p proj/sub ; echo a > proj/a.txt
tar -czvf proj.tar.gz proj ; tar -tzf proj.tar.gz
tar -cjf proj.tar.bz2 proj ; tar -cJf proj.tar.xz proj ; ls -l proj.tar.*
mkdir -p x ; tar -xzf proj.tar.gz -C x ; ls -R x
zip -r proj.zip proj ; unzip -l proj.zip
ln -s proj/a.txt link ; ls -l link            # l no início; aponta para proj/a.txt
ln proj/a.txt duro ; ls -li proj/a.txt duro   # mesmo inode; contador 2
```

---

## 6. Lista de reincidências

São os erros que voltaram depois de corrigidos. É a lista que guia os treinos na VM, o M6 e a revisão leve de 25 e 26/11. Uma linha nova entra quando um erro se repete (regra 3).

| Erro | Vezes | O certo | Treino |
|---|---|---|---|
| `cd ..`, `cd -`, `./` e `../` trocados | **7** | `..` é o pai; `-` é o anterior; `.` é o atual | V1 |
| `sort` sem `-n` descrito como invertendo | **5** | As duas formas são crescentes; só o `-r` inverte; `-k` é a coluna | V3 |
| Ordem do `2>&1` | 2 | `> arq 2>&1`: da esquerda para a direita | V3 |
| `grep -v` | 2 | É *invert*; no `grep` não é *verbose* | V3 |
| `/home` tratado como a pasta pessoal | 2 | `/home` contém as pastas; a pessoal é `~` | V1 |
| `$#` | **3** (Q24 do simulado 02; Q6 da autoavaliação da Semana 5; Q16 do R3) | Conta só os argumentos; o `$0` (nome do script) **não entra**: `./args.sh um dois` dá `$#` = 2 | V4 |
| O `x` do `/etc/passwd` | 2 | Só diz que o hash está no `/etc/shadow`; o administrador é o UID 0 | V6 |
| Conversão octal, com e sem bit especial | **3** (Q37 do simulado 01; Q36 do simulado 02; Q36 do simulado 03, `645` no lugar de `4755`) | Bit especial primeiro (SUID 4, SGID 2, sticky 1), depois trio por trio: `rwsr-xr-x` = 4755; `rwxr-x---` = 750 | V5 |
| Herança de variáveis: `export` | **3** (Correções 12 e 71; Q16 do simulado 03) | O `export` marca a variável para os filhos; o `env NOME` tenta executar um comando | V4 |
| `{}` tratado como globbing | 2 | A expansão de chaves cria os nomes sem olhar o disco | — |
| Sinal padrão do `kill` | 2 | `SIGTERM` (15); o `SIGKILL` (9) só com `kill -9` | V7 |
| **Forma das lacunas** (palavra a mais, explicação junto da resposta) | **5** (Q11 do simulado 01; Q7 e Q13 do simulado 02; séries 01 e 02 das lacunas) | Na lacuna, só o pedido: `copyleft`, `-x`, `FSF`. Explicação vai no caderno, nunca na resposta | — |
| Seções do `man` (`man 5` contra `man -k`) | 2 (Q16 do simulado 02; Q7 do R3) | `man 5 arquivo` abre o **formato do arquivo**; `man -k` só **procura** a palavra e lista páginas | V2 |
| `help` para os comandos internos | **3** (Correção 74; Q13 do simulado 02; série 02 das lacunas) | `help cd`; o `man` é para programas, o `type` diz o que é interno | V2 |
| Padrão de globbing sem correspondência | 2 (Semana 3; Q24 do simulado 03) | O Bash entrega o texto literal, como `*.log`; não há erro | V1 |
| `fg` e `bg` | 2 (Correção 78; Q29 do simulado 03) | `fg` traz para o primeiro plano; `bg` continua em segundo; `Ctrl+Z` suspende | V7 |
| `x` em diretório | 2 (Prática 2, bloco 4; Q39 do simulado 03) | `r` lista; `x` atravessa e abre um nome conhecido; `w` cria e apaga | V5 |
| Arquivos de contas (`/etc/shadow`, `/etc/group`) | 2 (Q34 do simulado 02; séries 01 e 02 das lacunas) | `/etc/passwd` contas, `/etc/shadow` hashes, `/etc/group` grupos e membros secundários | V6 |

---

## 7. Metas e decisão da data

| Período | Simulados | Meta de acertos firmes |
|---|---|---|
| Linha de base | 03 (05/11) | **20** (feito) |
| Primeira semana | 05 (09/11) e 04 (11/11) | **24 ou mais** |
| Segunda semana | 06 (13/11), 07 (14/11) e 08 (17/11) | **28 ou mais** |
| Terceira semana | 09 (19/11), 10 (21/11) e 11 (23/11) | **30 ou mais** |
| Final | 12 (25/11) | **30 ou mais** |

**Decisão final, no sábado 21/11**, com a média de acertos firmes dos simulados 08, 09 e 10:

| Média | Decisão |
|---|---|
| **26 ou mais** | Vai em 30/11 |
| **Abaixo de 26** | Remarcar. O exame 010-160 fica disponível até abril de 2027; antes de escolher a nova data, revemos o método com os números na mão |

O corte do exame é de 26 acertos. Com 26 firmes, os chutes ainda somam: a nota real fica acima disso. Confira a janela de remarcação sem custo da Pearson VUE antes de 21/11.

---

## 8. De onde vêm as questões

| Material | Situação |
|---|---|
| Simulado 03 | Pronto (`simulado-03.md`) |
| Simulado 04 | Pronto (`simulado-04.md`, escrito em 04/11), para a quarta 11/11. Substitui o exame final do NDG, que fica como treino extra opcional |
| R2, R3 e R4 | Prontos (`praticas_simulados.md` e `reforco-r3-r4.md`). O R3 foi feito em 06/11; o R1 saiu do plano em 06/11 |
| Simulado 05 | Pronto (`simulado-05.md`, escrito em 04/11), para a segunda 09/11 |
| Simulados 06 a 12 | Escritos por mim, prontos **até três dias antes** de cada um |
| M1 a M6 | Escritos por mim a partir dos erros dos simulados anteriores, prontos na véspera |
| Lacunas | Prontas (`lacunas.md`, 24 séries) |
| Exercícios da LPI | No PDF do material oficial; calendário e registro em `exercicios-lpi.md` |

---

## 9. Registro diário

| Data | Tipo | Sessão | Acertos | Firmes | Lacunas | Exercícios da LPI | Reincidências novas |
|---|---|---|---|---|---|---|---|
| 04/11 | — | Lacunas das séries 01 e 02 | — | — | 1 de 5 e 0 de 5 | — | Forma das lacunas; `help`; arquivos de contas |
| 05/11 | A | Simulado 03 · V5 e V6 | Simulado 03: **27 de 40** | **20** | Série 03: **4 de 5** | — (passaram para 07/11) | Seis, no próprio `simulado-03.md` |
| 06/11 | B | R3 · bloco curto (4.1 e here doc) · V1 e V3 | R3: **17 de 20** | **17** | — | 4.1: **7 de 7** | `$#`; seções do `man` |
| 07/11 | B | R4 · LPI da semana | R4: de 20 | | Série 05: de 5 | 4.2, 4.3 (lições 1 e 2), 5.1 e 5.3 · de | |
| 08/11 | Conteúdo | Aulas 41 a 72 · LPI que faltou | — | — | — | | |
| 09/11 | A | Simulado 05 | de 40 | | Série 06: de 5 | 5.2 · de | |
| 10/11 | B | R2 | de 20 | | Série 07: de 5 | 4.4 e 5.4 · de | |
| 11/11 | A | Simulado 04 | de 40 | | Série 08: de 5 | 3.1 · de | |
| 12/11 | B | M1 | de 20 | | Série 09: de 5 | 2.1 (lições 1 e 2) · de | |
| 13/11 | A | Simulado 06 | de 40 | | Série 10: de 5 | 2.2 · de | |
| 14/11 | A | Simulado 07 | de 40 | | Série 11: de 5 | 2.3 (lições 1 e 2) · de | |
| 16/11 | B | M2 | de 20 | | de 5 | 2.4 e 3.2, lição 1 · de | |
| 17/11 | A | Simulado 08 | de 40 | | de 5 | 3.2, lição 2 · de | |
| 18/11 | B | M3 | de 20 | | de 5 | 3.3 (lições 1 e 2) e 1.1 · de | |
| 19/11 | A | Simulado 09 | de 40 | | de 5 | 1.2 · de | |
| 20/11 | B | M4 · feriado | de 20 | | de 5 | 1.3 e 1.4 · de | |
| 21/11 | A | Simulado 10 · Decisão da data | de 40 | | de 5 | Revisão: erradas do Tópico 5 · de | |
| 23/11 | A | Simulado 11 | de 40 | | de 5 | Revisão: erradas do Tópico 4 · de | |
| 24/11 | B | M5 | de 20 | | de 5 | Revisão: erradas dos Tópicos 3 e 2 · de | |
| 25/11 | A | Simulado 12 (final) | de 40 | | de 5 | Revisão: erradas do Tópico 1 · de | |
| 26/11 | Leve | M6 (reincidências) · Colas | de 20 | | de 5 | — | |

### Treinos na VM — o que saiu diferente do previsto

| Data | Bloco | Observação |
|---|---|---|
| 05/11 | V5 | Todas as conversões bateram, inclusive `2744` → `-rwxr-Sr--` (`S`: SGID sem `x` no grupo) e `1770` → `T`. O roteiro previa `671` para `640` com `g+w,o+x`; o certo, confirmado na VM, é **`661`** (roteiro e gabarito do R4 corrigidos). O `chmod 711 ; ls -ld d` deu *missing operand*: faltou o `d` no `chmod` |
| 05/11 | V6 | `usermod -G ops` tirou o `dev` e o `-aG dev` devolveu: o mecanismo da reincidência, visto na prática. O `/etc/skel` foi copiado para a pasta do `teste1`. **O `last` não existe no Ubuntu 26.04**: foi substituído pelo pacote `wtmpdb` (`sudo apt install wtmpdb` traz o comando). Para a prova, continua valendo: o `last` lê o histórico de logins do `/var/log/wtmp`. O `groupdel ops` falhou porque a `carol`, da Prática 2, ainda existe com o `ops` como grupo primário |
| 06/11 | V1 | Tudo como previsto, inclusive o `cd -`, que imprime o diretório antes do `pwd` (por isso o `/var/log` saiu duas vezes). O `ls /home` mostrou `alice`, `bob` e `carol`, da Prática 2, ainda na VM |
| 06/11 | V3 | O `2>&1 > b.txt` mandou o erro para a **tela** e só a saída para o arquivo: na sua colagem, a primeira linha depois do comando é o erro na tela, e o `cat b.txt` mostrou só o `/etc/hostname`. No primeiro here document, o `FIM` não fechou o bloco: a linha tinha um **espaço depois do `FIM`**, e o delimitador precisa estar sozinho na linha, sem espaço. Por isso o bloco só fechou no segundo `FIM` |

### Bloco curto — 4.1 e here document (06/11)

**Lição 4.1.** As duas tabelas ficaram completas e certas: licença, kernel (Windows NT, XNU/Darwin, Linux), interface padrão e instalação de software nos três sistemas, e as quatro fases do ciclo de vida. A observação final está ótima: **beta e estável** dizem a maturidade, **LTS** diz a duração do suporte e **rolling release** diz o modelo de atualização. São eixos diferentes, e a prova costuma misturá-los. Ajuste de grafia: "mac0S" → **macOS**.

**Exercícios da LPI 4.1:** os 5 Guiados e os 2 Exploratórios respondidos, todos certos. O `uname -r` mostra a versão do kernel, e o `uname -s` no macOS responde `Darwin`.

**Here document:** a tabela dos quatro operadores (`<`, `<<`, `>`, `>>`) está certa. Fica o detalhe do V3: o delimitador fecha o bloco só se estiver **sozinho na linha**, sem espaço antes ou depois.