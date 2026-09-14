# Semana 3 — Arquivos, diretórios e links

Período: 14 a 20/09/2026 (segunda a domingo)
Objetivos da prova: 2.3 (Using Directories and Listing Files) e 2.4 (Creating, Moving and Deleting Files)
Tópico 2, peso 9 de 40 — esta semana fecha os 4 pontos restantes do tópico
Carga prevista: 5 sessões de aproximadamente 1 hora

Esta semana tem uma característica diferente das anteriores: **a Sessão 1 é inteiramente dedicada a quitar dívidas da Semana 2**. Isso é deliberado. As dívidas acumuladas são pequenas individualmente, mas duas delas são medições — sem elas não há como saber se o aprendizado está acontecendo.

---

## Objetivos oficiais cobertos

**2.3 Using Directories and Listing Files** — conhecimentos exigidos:

- Arquivos e diretórios
- Arquivos e diretórios ocultos
- Diretório home
- Caminhos absolutos e relativos
- Termos e utilitários: `ls`, `cd` com suas opções, `.`, `..`, `home`, `~`

**2.4 Creating, Moving and Deleting Files** — conhecimentos exigidos:

- Arquivos e diretórios
- Sensibilidade a maiúsculas e minúsculas
- Globbing e quoting simples
- Termos e utilitários: `mv`, `cp`, `rm`, `touch`, `mkdir`, `rmdir`

Parte deste conteúdo já foi encostada nas semanas anteriores. Esta semana consolida e aprofunda, especialmente em links, arquivos ocultos e as armadilhas de `cp`, `mv` e `rm`.

---

## Rotina de abertura e fechamento

```powershell
lab-up
ssh lab
```

```bash
cd ~/linux-essentials-labs
code .
```

Ao fim de cada sessão:

```bash
git add . && git commit -m "docs: semana 3 - sessao N" && git push
sudo poweroff
```

---

## Sessão 1 — Segunda 14/09 — Quitação de dívidas e autoavaliação

Sessão curta em comandos e alta em valor. Faça na ordem.

### Parte 1 — Autoavaliação da Semana 2 (30 min)

Abra `labs/semana-02.md`, vá até a seção de autoavaliação e responda as 15 questões **sem consultar nada**. Só depois confira o gabarito.

Esta é a dívida mais importante das seis. As outras cinco são experimentos; esta é a **única medição** de quanto do conteúdo das semanas 1 e 2 realmente ficou. Sem ela, entramos na Semana 4 sem saber se a base está sólida.

Registre a nota abaixo e transforme cada erro em card no Notion **hoje**.

Nota: ___ de 15

Erros:

1.
2.
3.

### Parte 2 — Os experimentos pendentes (20 min)

**Código de saída — o `echo $?` colado no comando testado:**

```bash
ls /naoexiste
echo $?          # espera-se 2
ls /
echo $?          # espera-se 0
ls -lh /var /log
echo $?          # espera-se 2
```

**Confirmar o mecanismo do `cd -`:**

```bash
cd /etc
cd /var/log
echo $OLDPWD     # deve mostrar /etc
cd -
pwd
```

**A expansão do asterisco — o experimento que fecha a Semana 2:**

```bash
cd /tmp && mkdir prova-glob && cd prova-glob
touch a.txt b.txt c.txt
echo *.txt       # a.txt b.txt c.txt
ls *.txt         # a.txt b.txt c.txt
echo *.md        # *.md — não casou com nada, o shell devolve o padrão cru
cd ~ && rm -rf /tmp/prova-glob
```

O `echo` mostra **exatamente o que o `ls` recebe**. Quem expande o `*` é o shell, antes de o comando existir.

**O `Permission denied` — a ponte para o Tópico 5:**

```bash
cd /var/log
cp /etc/hostname .
```

Deve falhar. Anote a mensagem exata; ela reaparece na Semana 6.

**O `locate` e o banco de dados indexado:**

```bash
sudo apt install -y plocate
sudo updatedb
locate hostname | head

touch ~/arquivo-recem-criado.txt
locate arquivo-recem-criado     # não encontra
sudo updatedb
locate arquivo-recem-criado     # agora encontra
rm ~/arquivo-recem-criado.txt
```

Esse é o melhor jeito de sentir a diferença entre `locate` e `find`: o `locate` só enxerga o que existia na última indexação.

**Documentação dos pacotes:**

```bash
ls /usr/share/doc | head -20
ls /usr/share/doc/tar/
```

### Registro da sessão

```bash

```

---

## Sessão 2 — Terça 15/09 — Criar, copiar, mover e remover (objetivo 2.4)

### Curso

Muller: seções sobre manipulação de arquivos e diretórios. **Esta semana o curso volta ao roteiro** — ver observação ao final do documento.

### Laboratório

**Criação:**

```bash
cd ~ && mkdir -p lab3 && cd lab3

touch arquivo1.txt
touch arquivo2.txt arquivo3.txt      # vários de uma vez
ls -l

mkdir pasta1
mkdir -p projeto/src/componentes     # cria toda a cadeia
mkdir a b c                          # vários diretórios
ls -l
```

O `touch` tem uma segunda função além de criar: se o arquivo já existe, ele **atualiza a data de modificação**. Comprove:

```bash
ls -l arquivo1.txt
touch arquivo1.txt
ls -l arquivo1.txt      # o horário mudou
```

**Cópia:**

```bash
cp arquivo1.txt copia1.txt
cp arquivo1.txt pasta1/
cp -r projeto projeto-backup         # -r é obrigatório para diretórios
ls -l
```

Tente copiar um diretório sem o `-r` e leia o erro:

```bash
cp projeto outro-projeto             # falha: -r not specified
```

**Movimentação e renomeação:**

```bash
mv copia1.txt renomeado.txt          # renomear
mv renomeado.txt pasta1/             # mover
mv pasta1/renomeado.txt .            # trazer de volta
ls -l
```

O `mv` faz as duas coisas porque renomear **é** mover para o mesmo diretório com outro nome. Não existe comando `rename` separado no básico do Linux.

**A armadilha silenciosa do `cp` e do `mv`:**

```bash
echo "conteudo original" > importante.txt
echo "conteudo novo" > outro.txt
cat importante.txt

cp outro.txt importante.txt          # sobrescreve SEM PERGUNTAR
cat importante.txt                   # o original foi perdido
```

Nenhum aviso, nenhuma confirmação. Por isso existe o `-i` (*interactive*):

```bash
cp -i outro.txt importante.txt       # agora pergunta antes
mv -i outro.txt importante.txt
```

Em servidores de produção é comum ter `alias cp='cp -i'` no `~/.bashrc` justamente por causa disso.

**Remoção:**

```bash
rm arquivo2.txt
rm -i arquivo3.txt                   # pergunta antes
rmdir a                              # só funciona em diretório VAZIO
rmdir projeto                        # falha: Directory not empty
rm -r projeto-backup                 # remove diretório com conteúdo
```

O `rmdir` existir separadamente é uma proteção: ele se recusa a apagar um diretório que tenha qualquer coisa dentro.

**Sobre o `rm -rf`:** o `-f` (*force*) suprime confirmações e erros. Combinado com `-r`, apaga tudo em silêncio. Não há lixeira no terminal — o que o `rm` apaga não volta. Teste destrutivo **apenas** com o snapshot `limpo` disponível:

```bash
# Em uma VM com snapshot. NUNCA em uma máquina real.
sudo rm -rf /  --no-preserve-root
```

Não é necessário rodar. Saber por que essa linha destrói o sistema já é o aprendizado.

**Sensibilidade a maiúsculas — conteúdo direto de prova:**

```bash
touch Arquivo.txt arquivo.txt ARQUIVO.txt
ls
```

Três arquivos distintos. O Linux é **case sensitive**, ao contrário do Windows. É a causa mais comum de erro em quem vem do Windows: `cd Documentos` e `cd documentos` são caminhos diferentes.

### Registro da sessão

```bash

```

### O que aprendi

- `touch` além de criar:
- Por que `cp -r` é necessário:
- O risco de `cp` e `mv` sem `-i`:
- `rmdir` e `rm -r`, diferença:
- Case sensitivity, com meu exemplo:

---

## Sessão 3 — Quarta 16/09 — Links simbólicos e hard links

### Laboratório

```bash
cd ~/lab3
echo "conteudo original" > original.txt

ln original.txt hardlink.txt         # hard link
ln -s original.txt simbolico.txt     # link simbólico (soft link)

ls -l
```

Leia a saída com atenção. O link simbólico aparece com `l` no início das permissões e uma seta apontando para o destino. O hard link é indistinguível de um arquivo comum.

```bash
ls -li                               # -i mostra o número de inode
```

O **inode** é o identificador real do arquivo no sistema de arquivos. Repare:

| Arquivo | Inode | Interpretação |
|---|---|---|
| `original.txt` | X | O arquivo |
| `hardlink.txt` | **X, o mesmo** | Outro nome para o **mesmo** arquivo |
| `simbolico.txt` | Y, diferente | Um arquivo separado que **contém o caminho** do original |

**O teste que revela a diferença:**

```bash
cat hardlink.txt
cat simbolico.txt

rm original.txt

cat hardlink.txt      # continua funcionando
cat simbolico.txt     # quebra: No such file or directory
ls -l                 # o link simbólico aparece quebrado
```

O hard link sobrevive porque é um nome apontando direto para o inode — o dado só é liberado quando o último nome desaparece. O link simbólico morre porque guardava apenas um caminho de texto, e o caminho deixou de existir.

| | Hard link | Link simbólico |
|---|---|---|
| Aponta para | O inode (o dado) | Um caminho (texto) |
| Sobrevive à remoção do original | Sim | Não |
| Funciona entre partições diferentes | Não | Sim |
| Funciona com diretórios | Não | Sim |
| Criado com | `ln` | `ln -s` |

Você já viu um link simbólico real no sistema, na Semana 1:

```bash
ls -l /bin
```

O `/bin` é um link simbólico para `/usr/bin`. Foi por isso que `ls /bin | wc -l` devolveu 1114.

### Arquivos ocultos

```bash
cd ~
ls
ls -a
ls -la
```

Arquivos que começam com `.` são ocultos. Não é um atributo especial — é apenas uma convenção do `ls`, que os omite por padrão.

```bash
ls -a ~ | head -20
cat ~/.bashrc | head -20
```

Repare que quase tudo que é configuração pessoal começa com ponto: `.bashrc`, `.ssh`, `.gitconfig`, `.bash_history`.

```bash
touch .oculto.txt
ls
ls -a
mv .oculto.txt visivel.txt    # deixar de ser oculto é só renomear
ls
```

### Registro da sessão

```bash

```

### O que aprendi

| | Hard link | Link simbólico |
|---|---|---|
| Aponta para | | |
| Sobrevive à remoção do original | | |
| Funciona entre partições | | |
| Funciona com diretórios | | |

- O que é um inode:
- Por que arquivos de configuração começam com ponto:

---

## Sessão 4 — Quinta 17/09 — FHS aprofundado e navegação avançada (objetivo 2.3)

### Laboratório

Na Semana 1 o FHS foi estudado em tabela. Agora ele é percorrido.

```bash
ls /
ls -l /                       # repare quais são links simbólicos
```

**Percorra e responda, para cada um, o que encontrou:**

```bash
ls /etc | wc -l
ls /etc/ssh
cat /etc/os-release
cat /etc/hostname

ls /var/log | head
sudo tail -5 /var/log/syslog

ls /usr/bin | wc -l
ls /usr/share/doc | wc -l

ls /home
ls -a ~

ls /tmp
ls /proc | head
cat /proc/uptime
cat /proc/version

ls /dev | head -20
ls -l /dev/null
```

O `/dev/null` merece atenção: é um arquivo especial que **descarta** tudo que recebe. Aparece o tempo todo em scripts:

```bash
ls /naoexiste 2> /dev/null     # silencia a mensagem de erro
echo $?                        # o código de saída continua sendo 2
```

**Opções do `ls` que ainda não foram exercitadas:**

```bash
ls -lS /usr/bin | head         # ordena por tamanho
ls -lt /var/log | head         # ordena por data de modificação
ls -ltr /var/log | head        # inverte a ordem: mais antigo primeiro
ls -ld /etc                    # informações do DIRETÓRIO, não do conteúdo
ls -R ~/lab3                   # recursivo
ls -1 /etc | head              # um por linha
```

O `-d` é o mais sutil e o mais cobrado: sem ele, `ls -l /etc` lista **o que está dentro**; com ele, lista **o diretório em si**.

### Registro da sessão

```bash

```

### O que aprendi

- O que faz `/dev/null`:
- Diferença entre `ls -l /etc` e `ls -ld /etc`:
- Três diretórios do FHS que eu não sabia o conteúdo e agora sei:

---

## Sessão 5 — Sexta 18/09 — Recuperação do curso e autoavaliação

### Parte 1 — Curso do Muller (40 min)

Assista, em 1.25x, as seções correspondentes aos Tópicos 2.3 e 2.4. Se houver acúmulo das semanas anteriores, priorize o que ainda não foi visto sobre manipulação de arquivos.

Anote apenas o que **divergir** do que você já praticou. Se o vídeo só confirmar o que o laboratório ensinou, não copie nada — siga em frente.

### Parte 2 — Autoavaliação da Semana 3 (20 min)

Responda sem consultar.

1. Qual comando cria a cadeia `a/b/c` de uma vez só?
2. Por que `cp pasta destino` falha e o que corrige isso?
3. O que acontece se você rodar `cp novo.txt existente.txt` e o destino já existir?
4. Qual a diferença entre `rmdir` e `rm -r`?
5. `Arquivo.txt` e `arquivo.txt` podem coexistir no mesmo diretório? Por quê?
6. Qual comando renomeia um arquivo?
7. Você apaga o arquivo original. O hard link continua funcionando? E o link simbólico?
8. Qual dos dois tipos de link funciona entre partições diferentes?
9. O que é um inode?
10. Como listar arquivos ocultos?
11. O que `ls -ld /etc` mostra a mais — ou a menos — que `ls -l /etc`?
12. Para que serve `/dev/null`?
13. Qual opção do `ls` ordena por tamanho? E por data, do mais antigo para o mais recente?
14. O que o `touch` faz com um arquivo que já existe?
15. Qual flag do `cp`, `mv` e `rm` pede confirmação antes de sobrescrever ou apagar?

<details>
<summary>Gabarito</summary>

1. `mkdir -p a/b/c`
2. Falha porque a origem é um diretório. Corrige-se com `cp -r`.
3. O destino é sobrescrito silenciosamente, sem aviso. O `-i` pede confirmação.
4. `rmdir` só remove diretórios vazios; `rm -r` remove o diretório e todo o conteúdo.
5. Sim. O Linux é case sensitive: maiúsculas e minúsculas são caracteres diferentes.
6. `mv`. Renomear é mover para o mesmo lugar com outro nome.
7. O hard link continua funcionando; o link simbólico quebra.
8. Apenas o link simbólico.
9. O identificador real do arquivo no sistema de arquivos. O nome é só um rótulo que aponta para ele.
10. `ls -a`
11. `ls -l /etc` mostra o conteúdo do diretório; `ls -ld /etc` mostra as informações do próprio diretório.
12. Descarta tudo que recebe. Usado para silenciar saídas e mensagens de erro.
13. `ls -lS` ordena por tamanho; `ls -ltr` ordena por data, do mais antigo primeiro.
14. Atualiza a data de modificação.
15. `-i`, de *interactive*.

</details>

Nota: ___ de 15

Meta: 12 de 15.

### Limpeza

```bash
cd ~ && rm -rf lab3
```

---

## Bandit — níveis 6 a 8

Encaixe no sábado ou distribua 15 minutos por sessão.

| Nível | O que treina |
|---|---|
| 6 → 7 | `find` com `-user` e `-group`, busca a partir da raiz, tratamento de erros de permissão |
| 7 → 8 | `grep` em arquivo grande |
| 8 → 9 | `sort` e `uniq -u` combinados por pipe |

O nível 6 tem uma particularidade útil: a busca a partir de `/` gera centenas de mensagens de `Permission denied`. Descartá-las é o uso prático do `2>/dev/null` que você viu na Sessão 4.

Registro:

```bash

```

---

## Checklist da semana

- [ ] Sessão 1 — dívidas e autoavaliação da Semana 2
- [ ] Sessão 2 — criar, copiar, mover e remover
- [ ] Sessão 3 — links e arquivos ocultos
- [ ] Sessão 4 — FHS aprofundado e opções do `ls`
- [ ] Sessão 5 — curso do Muller e autoavaliação da Semana 3
- [ ] Bandit níveis 6 a 8
- [ ] Cards do Notion atualizados
- [ ] Autoavaliação da Semana 2 com 12 acertos ou mais
- [ ] Autoavaliação da Semana 3 com 12 acertos ou mais
- [ ] Commits ao fim de cada sessão

---

## Dívidas da Semana 2 — lista consolidada

| # | Dívida | Onde foi absorvida |
|---|---|---|
| 1 | Autoavaliação da Semana 2 (15 questões) | Sessão 1, Parte 1 |
| 2 | `echo $?` imediatamente após o comando testado | Sessão 1, Parte 2 |
| 3 | `echo $OLDPWD` e o mecanismo do `cd -` | Sessão 1, Parte 2 |
| 4 | Experimento `echo *.txt` versus `ls *.txt` | Sessão 1, Parte 2 |
| 5 | Experimento do `Permission denied` em `/var/log` | Sessão 1, Parte 2 |
| 6 | Instalar e testar `locate` com `updatedb` | Sessão 1, Parte 2 |
| 7 | Navegar em `/usr/share/doc/` | Sessão 1, Parte 2 |
| 8 | Avanço no curso do Muller | Sessão 5, Parte 1 |

---

## Observação sobre o curso

A Semana 2 foi cumprida **inteiramente pela prática**, sem avanço no curso, e o resultado foi bom: as anotações saíram corretas, com apenas duas imprecisões conceituais reais em cinco sessões.

Isso funcionou porque os objetivos 2.1 e 2.2 são operacionais — o laboratório ensina o que eles cobram. O mesmo vale, em boa medida, para esta semana.

A partir da **Semana 4** o cenário muda. O Tópico 3 traz redirecionamento, encadeamento e shell script, e o Tópico 4 traz hardware, processos e rede. São conteúdos em que o vídeo entrega o modelo mental e o laboratório apenas confirma. Chegar na Semana 4 com o curso atrasado é o principal risco identificado até aqui.

Por isso a Sessão 5 desta semana reserva tempo explícito para recuperação.

---

## Cola rápida

```
Criar          touch  mkdir  mkdir -p  mkdir a b c
Copiar         cp  cp -r  cp -i
Mover          mv  mv -i                 (mv também renomeia)
Remover        rm  rm -i  rm -r  rmdir   (rmdir só em diretório vazio)
Links          ln (hard)  ln -s (simbólico)  ls -li (inodes)
Ocultos        ls -a  ls -la             (arquivos iniciados por ponto)
Listagem       ls -l  -a  -h  -t  -S  -r  -R  -d  -1  -i
Especiais      /dev/null   2>/dev/null
Case           Arquivo.txt ≠ arquivo.txt
```