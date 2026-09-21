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

## Sessão 1 — Segunda 14/09 — Quitação de dívidas e autoavaliação — CONCLUÍDA

Sessão curta em comandos e alta em valor. Faça na ordem.

### Parte 1 — Autoavaliação da Semana 2 (30 min)

Abra `labs/semana-02.md`, vá até a seção de autoavaliação e responda as 15 questões **sem consultar nada**. Só depois confira o gabarito.

Esta é a dívida mais importante das seis. As outras cinco são experimentos; esta é a **única medição** de quanto do conteúdo das semanas 1 e 2 realmente ficou. Sem ela, entramos na Semana 4 sem saber se a base está sólida.

**Resultado: 14 de 15.** Meta era 12.

Acertos: questões 1 a 8 e 10 a 15. As respostas sobre `which` versus `type`, sobre a expansão do asterisco pelo shell e sobre o `?` casar exatamente um caractere vieram completas e com a justificativa correta.

**Erro único — questão 9: o que o `export` faz que a atribuição simples não faz.**

Resposta dada: "cria uma variável do shell".
Correto: a atribuição simples **já cria** a variável de shell. O `export` acrescenta uma coisa só — **marca a variável para ser herdada pelos processos filhos**, o que a torna variável de ambiente.

Card criado no Notion: *"O que `export` faz? → Marca a variável para ser herdada pelos processos filhos. A atribuição simples já cria a variável, mas ela fica só no shell atual."*

Este conceito estava correto nas anotações da Sessão 4 da Semana 2, com diagrama e tudo. Errar sob condição de prova, sem consulta, é precisamente o tipo de lacuna que só a autoavaliação revela.

**Observação — questão 3.** O caminho absoluto foi `/home/davi/documentos/arquivo.txt` e o relativo `documentos/arquivos.txt`. O conceito está certo, mas os nomes divergem no plural, então não apontam para o mesmo arquivo. Não conta como erro, mas vale atenção: em questão de preenchimento, um caractere a mais invalida a resposta.

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

> **Este é o único experimento que não foi concluído.** O comando executado foi `cp /etc/hostname`, sem o ponto final, e o erro obtido foi outro:
>
> ```
> cp: missing destination file operand after '/etc/hostname'
> ```
>
> Isso é **erro de sintaxe**, não de permissão. O `cp` exige **dois operandos**: origem e destino. Sem o destino, ele nem chega a tentar escrever — falha antes, na checagem dos argumentos.
>
> O ponto no fim do comando **é o destino**. Ele significa "o diretório atual", que naquele momento é `/var/log`. Com ele, o `cp` tenta de fato criar o arquivo e aí sim esbarra na permissão:
>
> ```
> cp: cannot create regular file './hostname': Permission denied
> ```
>
> Refazer, com o ponto:
>
> ```bash
> cd /var/log
> cp /etc/hostname .
> echo $?
> ```
>
> Vale observar a diferença entre os dois códigos de saída e entre as duas mensagens. Uma diz "você escreveu o comando errado"; a outra diz "o comando está certo, mas você não tem direito de fazer isso". Distinguir as duas é o que separa depurar de adivinhar.

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

**Código de saída.** Confirmado nos três casos: `ls /naoexiste` retorna 2; `ls /` retorna 0; `ls -lh /var /log` retorna 2, porque o `/var` existe mas o `/log` não — basta um argumento falhar para o código ser diferente de zero.

**Mecanismo do `cd -`.** Confirmado. O shell guarda o diretório anterior em `$OLDPWD`; o `cd -` é um atalho para `cd $OLDPWD`. Saindo de `/etc` para `/var/log`, o `$OLDPWD` passou a valer `/etc`, e o `cd -` voltou para lá.

**Expansão do asterisco.** Confirmado. Com `a.txt`, `b.txt` e `c.txt` no diretório, tanto `echo *.txt` quanto `ls *.txt` produzem a mesma lista — porque o `ls` recebe exatamente o que o `echo` mostrou. Já `echo *.md` devolveu `*.md` literalmente: sem nenhum arquivo correspondente, o shell não expande e entrega o padrão cru ao comando.

**`locate` e banco indexado.** Confirmado o ciclo completo: o arquivo recém-criado não aparece na busca, `sudo updatedb` reindexa, e a busca seguinte encontra `/home/davi/arquivo-recem-criado.txt`. É a diferença prática entre consultar um índice e percorrer o sistema de arquivos.

**Documentação dos pacotes.** `/usr/share/doc` listou os pacotes instalados em ordem alfabética. Em `/usr/share/doc/tar/` apareceram `AUTHORS`, `README.Debian`, `changelog.Debian.gz`, `NEWS.gz`, `THANKS.gz` e `copyright` — arquivos que não estão na man page.

Repare que vários terminam em `.gz`: estão comprimidos. Para ler sem descomprimir:

```bash
zcat /usr/share/doc/tar/changelog.Debian.gz | head
zless /usr/share/doc/tar/NEWS.gz
```

Os comandos `zcat`, `zless` e `zgrep` operam direto sobre arquivos `gzip`. Conteúdo do objetivo 3.1, na Semana 4.

**`Permission denied`.** Não concluído — ver observação acima. Pendente para a Sessão 2.

### Pendente

- [x] Refazer `cp /etc/hostname .` em `/var/log`, **com o ponto**, e registrar a mensagem de permissão

---

## Sessão 2 — Terça 15/09 — Criar, copiar, mover e remover (objetivo 2.4) — CONCLUÍDA

### Curso — Gerenciamento de pacotes .deb (15/09)

Retomada do curso. O conteúdo desta aula vai além do exigido pelo Linux Essentials, que cobra apenas o reconhecimento das famílias de pacotes e dos gerenciadores. A profundidade de `dpkg` e `apt-get` aqui é material de **LPIC-1** e será reaproveitada no RHCSA, no equivalente `rpm`/`dnf`.

**Duas formas de instalar software**

| Forma | Como | Resolve dependências |
|---|---|---|
| Repositórios oficiais da distribuição | `apt install pacote` | Sim, automaticamente |
| Pacote `.deb` local, baixado do site do fabricante | `dpkg -i pacote.deb` | **Não** |

**Comandos do `apt`**

| Comando | Função |
|---|---|
| `apt update` | Atualiza o **índice local** de pacotes a partir dos repositórios |
| `apt upgrade` | Atualiza os pacotes instalados |
| `apt full-upgrade` / `apt-get dist-upgrade` | Atualiza resolvendo dependências que exijam instalar ou remover pacotes |
| `apt search palavra` | Pesquisa no cache por palavra-chave |
| `apt install pacote` | Instala |
| `apt remove pacote` | Remove o programa, mantendo as configurações |
| `apt remove --purge` / `apt purge` | Remove o programa **e** os arquivos de configuração |
| `apt autoremove` | Remove bibliotecas órfãs, que nenhum pacote instalado usa mais |

**Comandos do `dpkg`**

| Comando | Função |
|---|---|
| `dpkg -l` / `dpkg --get-selections` | Lista os pacotes instalados |
| `dpkg -i pacote.deb` | Instala um pacote local |
| `dpkg --remove pacote` | Remove, mantendo configurações e dependências |
| `dpkg --purge pacote` | Remove também as configurações |

O ponto central: **o `dpkg` não resolve dependências.** Ele instala exatamente o arquivo que você apontou, e falha se faltar alguma biblioteca. Quem conserta é o `apt`:

```bash
sudo apt-get -f install        # -f de --fix-broken
```

**Onde ficam os repositórios**

```bash
cd /etc/apt
ls
ls sources.list.d/
```

**Correção 17 — o `sources.list` não é mais o arquivo principal.** No Ubuntu 26.04, a configuração dos repositórios migrou para o formato **deb822**, em `/etc/apt/sources.list.d/ubuntu.sources`. O arquivo `/etc/apt/sources.list` ainda existe por compatibilidade, mas costuma estar vazio ou apenas com um comentário apontando para o novo local. Confirme no seu sistema:

```bash
cat /etc/apt/sources.list
cat /etc/apt/sources.list.d/ubuntu.sources
```

O segundo mostra os quatro repositórios que você já viu na Semana 0: `resolute`, `resolute-updates`, `resolute-security` e `resolute-backports`.

**Correção 18 — `apt upgrade` não "exclui o kernel".** A anotação registra que o `apt upgrade` atualiza tudo "com exceção do kernel". Isso é uma simplificação difundida, mas não é a regra real.

O que de fato distingue os comandos é **se podem instalar ou remover pacotes**:

| Comando | Instala pacotes novos | Remove pacotes |
|---|---|---|
| `apt-get upgrade` | Não | Não |
| `apt upgrade` | Sim | Não |
| `apt full-upgrade` / `apt-get dist-upgrade` | Sim | Sim |

O kernel entra nessa história por consequência: cada versão nova do kernel é um **pacote novo** (`linux-image-7.0.0-15`, e não uma atualização do `linux-image-7.0.0-14`). Como o `apt-get upgrade` se recusa a instalar pacotes novos, ele acaba deixando o kernel para trás — e foi daí que nasceu a regra decorada. Já o `apt upgrade`, que você usou na Semana 0, instala o kernel normalmente.

É por isso que aqueles quatro pacotes ficaram como `Not Upgrading` naquela ocasião: não era o kernel, eram pacotes cuja atualização exigia mexer em outros.

**Correção 19 — `dist-upgrade` não significa "atualizar a distribuição".** A anotação diz que `apt-get dist-upgrade` é "upgrade de distribuição de kernel". O nome engana. O `dist-upgrade` é um **upgrade inteligente**: ele resolve mudanças de dependência instalando e removendo pacotes conforme necessário, dentro da **mesma versão** da distribuição.

Quem troca a versão do sistema — de 26.04 para 26.10, por exemplo — é outro comando:

```bash
sudo do-release-upgrade
```

Confundir os dois é erro comum e potencialmente caro em servidor.

**Correção 20 — sintaxe.** A anotação registra `apt-get —dist upgrade`. O correto é `apt-get dist-upgrade`, sem hífens e com hífen entre as palavras. E "atualização de cache do apt → update apt" está com a ordem invertida: é `apt update`.

**Correção 21 — `apt update` não atualiza os repositórios.** Ele atualiza o **índice local** do seu sistema, baixando dos repositórios a lista do que existe e em que versão. Os repositórios são servidores remotos e não mudam por ação sua. A distinção importa: `apt update` não instala nem atualiza nada — só sincroniza o catálogo.

**Acréscimo — a forma moderna de instalar um `.deb` local**

O roteiro `dpkg -i` seguido de `apt-get -f install` funciona, mas hoje existe um caminho direto que resolve dependências de primeira:

```bash
sudo apt install ./code.deb
```

O `./` é obrigatório. Sem ele, o `apt` procuraria nos repositórios um pacote **chamado** `code.deb`, em vez de ler o arquivo. É a mesma lógica do `cat ./-` do Bandit nível 1.

**Roteiro de instalação praticado**

```bash
sudo apt update
sudo apt upgrade
# baixar o .deb, por exemplo de https://code.visualstudio.com/
sudo dpkg -i code.deb
sudo apt-get -f install          # se faltarem dependências
dpkg -l | grep -i code           # confirmar
```

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

Laboratório executado por completo, sem erros de interpretação.

**Criação.** O `touch` e o `mkdir` aceitam vários argumentos e criam vários itens de uma vez. O `-p` do `mkdir` cria toda a cadeia de diretórios-pai do caminho.

Leitura do primeiro caractere na saída do `ls -l`:

| Início | Tipo |
|---|---|
| `-rw-rw-r--` | Arquivo comum |
| `drwxrwxr-x` | Diretório |
| `lrwxrwxrwx` | Link simbólico (Sessão 3) |

Esse primeiro caractere é o tipo do arquivo, e os nove seguintes são as permissões em três grupos. Conteúdo do Tópico 5, Semana 6 — mas já visível aqui.

**Cópia.** O `-r` de *recursive* é obrigatório para diretórios, porque um diretório pode conter subdiretórios e arquivos que também precisam ser copiados. Sem ele:

```
cp: -r not specified; omitting directory 'projeto'
```

**Diferença entre `cp` e `mv`:** o `cp` duplica e mantém o original; o `mv` desloca ou renomeia, e o original deixa de existir no lugar antigo.

**Movimentação.** O `mv` faz renomear e mover porque renomear é mover para o mesmo diretório com outro nome. O `.` como destino significa "o diretório atual" — o mesmo `.` da tabela de símbolos da Semana 2.

**A sobrescrita silenciosa.** Confirmada: o `cp` substituiu `importante.txt` sem qualquer aviso, e o conteúdo original se perdeu. Com `-i` (*interactive*), aparece a confirmação:

```
cp: overwrite 'importante.txt'?
```

| Comando | Se o destino já existir |
|---|---|
| `cp arquivo destino` | Sobrescreve sem perguntar |
| `cp -i arquivo destino` | Pergunta antes |
| `mv arquivo destino` | Substitui sem perguntar |
| `mv -i arquivo destino` | Pergunta antes |

Observação registrada e correta: com o `cp`, o arquivo de origem continua existindo; com o `mv`, ele desaparece do local original.

**Remoção.**

```
rmdir: failed to remove 'projeto': Directory not empty
```

O `rmdir` só apaga diretórios vazios — é uma proteção deliberada. Para remover com conteúdo, `rm -r`. E `rm -ri` pede confirmação item por item durante a remoção recursiva.

**Case sensitivity.** `Arquivo.txt`, `arquivo.txt` e `ARQUIVO.txt` coexistem como três arquivos distintos. O Linux diferencia maiúsculas de minúsculas em nomes de arquivos e diretórios.

### Dívida quitada — o `Permission denied`

Refeito com o ponto, e agora com o erro correto:

```
cp: cannot create regular file './hostname': Permission denied
```

Compare com o erro da tentativa anterior, sem o ponto:

```
cp: missing destination file operand after '/etc/hostname'
```

A primeira mensagem diz que o comando está incompleto; a segunda diz que o comando está certo mas o usuário não tem direito de escrever em `/var/log`. Esse diretório pertence ao `root`, e é essa a porta de entrada do Tópico 5.

### O que aprendi

- **`touch` além de criar:** atualiza os timestamps de um arquivo que já existe.
- **Por que `cp -r` é necessário:** diretórios podem conter outros itens, e o `-r` manda copiar recursivamente todo o conteúdo.
- **O risco de `cp` e `mv` sem `-i`:** ambos sobrescrevem o destino em silêncio, sem aviso e sem possibilidade de desfazer.
- **`rmdir` e `rm -r`:** o `rmdir` só remove diretórios vazios; o `rm -r` remove o diretório e tudo que houver dentro.
- **Case sensitivity:** `Arquivo.txt` e `arquivo.txt` são arquivos diferentes no Linux.

---

## Sessão 3 — Quarta 16/09 — Links simbólicos e hard links — CONCLUÍDA

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

Sessão executada por completo. Nenhuma correção necessária.

**Saída observada do `ls -li`:**

```
262338 -rw-rw-r-- 2 davi davi 18 Sep 17 02:08 original.txt
262338 -rw-rw-r-- 2 davi davi 18 Sep 17 02:08 hardlink.txt
270559 lrwxrwxrwx 1 davi davi 12 Sep 17 02:08 simbolico.txt -> original.txt
```

`original.txt` e `hardlink.txt` compartilham o inode **262338**. O `simbolico.txt` tem inode próprio, **270559**, e traz a seta apontando para o destino.

**O que é um inode.** A identidade real do arquivo no sistema de arquivos. O nome é apenas uma referência para essa estrutura, que guarda:

- Permissões
- Proprietário e grupo
- Tamanho
- Datas
- Localização dos dados no disco

Repare no que o inode **não** guarda: o nome do arquivo. O nome vive no diretório, como uma entrada que aponta para um inode. É exatamente por isso que dois nomes podem apontar para o mesmo arquivo.

**Por que o `rm` não apaga os dados.** Registro correto na anotação: o `rm original.txt` remove a **referência** ao inode, não o conteúdo. Os dados só são liberados quando o último nome desaparece. É daí que vem o termo técnico para o `rm` em C: a chamada de sistema se chama `unlink`.

**O teste confirmado:**

| Comando após `rm original.txt` | Resultado |
|---|---|
| `cat hardlink.txt` | Funciona — o inode continua com um nome apontando para ele |
| `cat simbolico.txt` | Quebra — guardava só um caminho, e o caminho sumiu |

### Dois detalhes que a saída revela

**A coluna do número — a contagem de links.**

```
-rw-rw-r-- 2 davi davi 18 ... original.txt
           ↑
```

Esse `2` é o **número de hard links apontando para o inode**. Ele valia `1` antes de você criar o hard link, e passou a `2` no momento em que o `ln` rodou. Depois do `rm original.txt`, volta a `1`.

É a contagem que o sistema usa para saber quando liberar o espaço em disco: só quando ela chega a zero. Comprove:

```bash
cd ~/lab3
echo teste > conta.txt
ls -l conta.txt          # coluna: 1
ln conta.txt segundo
ls -l conta.txt          # coluna: 2
ln conta.txt terceiro
ls -l conta.txt          # coluna: 3
rm segundo terceiro
ls -l conta.txt          # coluna: 1
```

Diretórios sempre começam com contagem `2`, porque o próprio `.` de dentro deles é um segundo nome para o mesmo inode. Cada subdiretório criado aumenta em um, por causa do `..` que ele contém. Verifique com `ls -ld` em qualquer diretório.

**O tamanho do link simbólico.**

```
lrwxrwxrwx 1 davi davi 12 ... simbolico.txt -> original.txt
                       ↑
```

`12` bytes. E `original.txt` tem exatamente **12 caracteres**. Não é coincidência: o conteúdo de um link simbólico **é o caminho de destino em texto**, e nada mais. O tamanho do link é o comprimento da string que ele guarda.

```bash
ln -s /um/caminho/bem/mais/longo/ainda alvo-longo
ls -l alvo-longo      # o tamanho acompanha o comprimento do caminho
rm alvo-longo
```

Isso explica de uma vez por que o link simbólico funciona entre partições — ele guarda texto, não uma referência a inode, e inodes só fazem sentido dentro do mesmo sistema de arquivos.

### O que aprendi

| | Hard link | Link simbólico |
|---|---|---|
| Aponta para | O inode (o dado) | Um caminho em texto |
| Sobrevive à remoção do original | Sim | Não |
| Funciona entre partições | Não | Sim |
| Funciona com diretórios | Não | Sim |
| Criado com | `ln` | `ln -s` |
| Tem inode próprio | Não | Sim |
| Primeiro caractere no `ls -l` | `-` | `l` |

### Arquivos ocultos

- [ ] Registrar as observações desta parte — os comandos constam do roteiro, mas as anotações da sessão não trazem o resultado

```bash
cd ~
ls
ls -a
ls -a ~ | head -20
cat ~/.bashrc | head -20

touch .oculto.txt
ls                            # não aparece
ls -a                         # aparece
mv .oculto.txt visivel.txt    # deixar de ser oculto é só renomear
ls
rm visivel.txt
```

Ponto a observar: o "oculto" não é um atributo do arquivo, como no Windows. É apenas uma convenção — o `ls` omite, por padrão, tudo que começa com ponto. Renomear já resolve, e nenhuma permissão muda no processo.

---

## Sessão 4 — Quinta 17/09 — FHS aprofundado e navegação avançada (objetivo 2.3) — CONCLUÍDA

### Curso — Gerenciamento de pacotes .rpm e yum (17/09)

Família Red Hat. É o contraponto direto da aula anterior sobre `.deb`.

**Equivalências entre as duas famílias**

| Função | Debian / Ubuntu | Red Hat |
|---|---|---|
| Ferramenta de baixo nível, pacote local | `dpkg` | `rpm` |
| Ferramenta de alto nível, com repositórios | `apt` | `yum` / `dnf` |
| Extensão do pacote | `.deb` | `.rpm` |
| Onde ficam os repositórios | `/etc/apt/sources.list.d/` | `/etc/yum.repos.d/` |
| Formato do arquivo de repositório | `.sources` (deb822) | `.repo` |

**Comandos do `rpm`**

| Comando | Função |
|---|---|
| `rpm -qa` | Lista todos os pacotes instalados (*query all*) |
| `rpm -qi pacote` | Informações detalhadas do pacote (*query info*) |
| `rpm -qR pacote` | Lista as dependências do pacote (*query requires*) |
| `rpm -i pacote.rpm` | Instala |
| `rpm -ivh pacote.rpm` | Instala com saída detalhada e barra de progresso |
| `rpm -e pacote` | Remove (*erase*) |

**Comandos do `yum`**

| Comando | Função |
|---|---|
| `yum update` | Atualiza o sistema **e** o cache de metadados |
| `yum search palavra` | Pesquisa pacotes |
| `yum install pacote` | Instala, resolvendo dependências |
| `yum install -y pacote` | O `-y` responde sim a todas as confirmações |
| `yum check-update` | Verifica se há atualizações disponíveis, sem instalar |
| `yum deplist pacote` | Lista as dependências do pacote |
| `yum remove pacote` | Remove, mantendo as bibliotecas |
| `yum clean packages` | Limpa os arquivos `.rpm` baixados do cache |

**Roteiro praticado**

```bash
yum update
yum install httpd -y          # servidor web Apache
yum install code.rpm          # resolve dependências
yum remove code
rpm -i code.rpm               # reinstala pela via de baixo nível
```

**Correção 22 — as flags do `rpm -ivh`.** A anotação atribui a barra de progresso ao `-ih` e os detalhes ao `-ihv`. Cada letra faz uma coisa, e a ordem entre elas não importa:

| Flag | Significa | Efeito |
|---|---|---|
| `-i` | *install* | Instala |
| `-v` | *verbose* | Saída detalhada |
| `-h` | *hash* | Barra de progresso feita de `#` |

A combinação canônica, que você vai ver em toda documentação, é `rpm -ivh`.

**Correção 23 — `yum check-install` não existe.** O comando é **`yum check-update`**, e ele verifica se há atualizações disponíveis **sem instalar nada**. É o equivalente aproximado do `apt list --upgradable`.

**Correção 24 — `yum clean packages` não remove pacotes órfãos.** Ele limpa os arquivos `.rpm` que foram **baixados para o cache** durante instalações, liberando espaço em `/var/cache`. Não mexe em nada instalado.

O equivalente real do `apt autoremove` é:

```bash
dnf autoremove
```

Confundir "limpar cache" com "remover pacotes órfãos" leva a achar que o sistema foi limpo quando não foi.

**Acréscimo importante — `yum` foi substituído por `dnf`.** O curso ensina o `yum`, que era a ferramenta do CentOS 7. A partir do RHEL 8, Fedora 22 e derivados — incluindo **Rocky Linux e AlmaLinux**, que são o que você vai usar no RHCSA — a ferramenta é o **`dnf`**, e o `yum` virou apenas um link simbólico apontando para ele.

```bash
# Em um container Rocky, verifique:
docker run -it --rm rockylinux/rockylinux:10 bash
ls -l /usr/bin/yum
dnf --version
```

Os comandos são quase idênticos, então o aprendizado se transfere. Vale apenas escrever `dnf` daqui em diante, porque é o que aparece na documentação atual e nas provas da Red Hat.

**Diferença de desenho entre as duas famílias que vale notar.** No Debian, atualizar exige dois passos separados: `apt update` sincroniza o índice, `apt upgrade` atualiza os pacotes. No Red Hat, `yum update` faz as duas coisas de uma vez. Confundir isso é fonte comum de erro para quem transita entre as famílias.

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

**Links simbólicos na raiz.** Quatro encontrados, todos apontando para dentro de `/usr`:

```
lrwxrwxrwx 1 root root 7 Apr 20 08:46 bin   -> usr/bin
lrwxrwxrwx 1 root root 7 Apr 20 08:46 lib   -> usr/lib
lrwxrwxrwx 1 root root 9 Apr 20 08:46 lib64 -> usr/lib64
lrwxrwxrwx 1 root root 8 Apr 20 08:46 sbin  -> usr/sbin
```

Isso é o **`/usr` merge**, mencionado na Semana 1 e agora visto de fato. Repare que os tamanhos são 7, 7, 9 e 8 bytes — exatamente o comprimento de `usr/bin`, `usr/lib`, `usr/lib64` e `usr/sbin`. É a mesma lição de ontem sobre o tamanho do link simbólico ser o comprimento do caminho que ele guarda.

**Inventário do sistema**

| Comando | Resultado |
|---|---|
| `ls /etc \| wc -l` | 197 itens de configuração |
| `ls /usr/bin \| wc -l` | 1117 executáveis |
| `ls /usr/share/doc \| wc -l` | 721 pacotes com documentação |
| `ls /home` | `davi` — um único usuário comum |
| `cat /etc/hostname` | `lab-ubuntu` |

Detalhe que fecha um ciclo: na Semana 2, `ls /bin | wc -l` devolveu **1114**. Agora `/usr/bin` devolve **1117**. Não é contradição — `/bin` **é** `/usr/bin`, e os três executáveis a mais são o `plocate`, o `tealdeer` e o `updatedb` instalados desde então.

**`/proc` — o sistema de arquivos do kernel**

```bash
ls /proc | head
```

Os números listados são **PIDs** de processos em execução. Cada processo ganha um diretório com seu identificador, contendo informações sobre ele. É por isso que `/proc` é chamado de pseudo-sistema de arquivos: nada disso existe em disco, é o kernel expondo seu próprio estado em forma de arquivos.

```
cat /proc/uptime    →  4450.55 8668.18
```

Leitura correta na anotação. O primeiro número é o tempo de máquina ligada em segundos; o segundo é o tempo ocioso **somado entre os processadores**. O segundo ser quase o dobro do primeiro faz sentido: a VM tem 2 vCPUs, e ambas ficaram quase sempre paradas.

```
cat /proc/version   →  Linux version 7.0.0-30-generic ...
```

**`/dev/null` e os arquivos de dispositivo**

```
crw-rw-rw- 1 root root 1, 3 Sep 17 12:35 /dev/null
```

Dois detalhes nessa linha valem atenção:

O primeiro caractere é **`c`**, de *character device* — dispositivo de caractere, que trabalha byte a byte. É o terceiro tipo que você encontra, depois do `-` de arquivo comum e do `l` de link simbólico. Discos aparecem como **`b`**, de *block device*:

```bash
ls -l /dev/sda
```

E onde normalmente estaria o tamanho, há **`1, 3`**. Esses são os números **major** e **minor** do dispositivo: o major identifica o driver que responde por ele, o minor identifica qual dispositivo específico dentro daquele driver. Arquivos de dispositivo não têm conteúdo, então não têm tamanho — o que o `ls -l` mostra ali é a identificação do dispositivo.

**Opções do `ls`**

| Opção | Efeito |
|---|---|
| `-S` | Ordena por tamanho, maior primeiro |
| `-t` | Ordena por data de modificação, mais recente primeiro |
| `-r` | Inverte a ordem escolhida — `-ltr` traz o mais antigo primeiro |
| `-d` | Mostra o **diretório em si**, não o conteúdo |
| `-R` | Recursivo, entra nos subdiretórios |
| `-1` | Um item por linha |

### Observações e correções

**Correção 25 — o `head` corta a listagem, não os arquivos.** A anotação diz que `ls /var/log | head` mostra "as 10 primeiras linhas dos arquivos de logs". Ele mostra as **10 primeiras entradas da listagem** do diretório. O `head` recebe a saída do `ls`, que são nomes de arquivos — ele nunca abre nenhum deles.

Para ver o conteúdo de um log, é preciso apontar para o arquivo:

```bash
head /var/log/syslog        # 10 primeiras linhas DO ARQUIVO
ls /var/log | head          # 10 primeiros NOMES do diretório
```

**Correção 26 — `2> dev/null` não funcionaria.** A anotação registra `ls /naoexiste 2> dev/null`, sem a barra inicial. Escrito assim, o shell tentaria criar um arquivo `null` dentro de um diretório `dev` no diretório atual — que não existe — e o redirecionamento falharia.

O correto é **`2> /dev/null`**, com caminho absoluto. É a mesma distinção entre caminho absoluto e relativo da Semana 2, agora aparecendo num contexto novo.

**Achado — há um arquivo indesejado na sua home.** A saída do `ls -a ~` traz:

```
'sudo apt upgrade -y'
```

Esse é um **arquivo** cujo nome é literalmente `sudo apt upgrade -y`. Ele foi criado por acidente, provavelmente por um redirecionamento (`>`) digitado antes do comando. As aspas simples no `ls` são o próprio shell avisando que o nome contém espaços.

É um exemplo involuntário e perfeito do tema da Semana 2: nomes com espaço precisam de aspas. Para remover:

```bash
cd ~
ls -l 'sudo apt upgrade -y'     # confirme que está vazio antes
rm 'sudo apt upgrade -y'
```

Se as aspas incomodarem, o Tab completion resolve: digite `rm sudo` e aperte Tab — ele completa e escapa os espaços sozinho.

### O que aprendi

- **`/dev/null`:** descarta tudo aquilo que recebe.
- **`ls -l /etc` e `ls -ld /etc`:** o primeiro lista o conteúdo do diretório; o segundo mostra as informações do diretório em si.
- **Diretórios do FHS explorados:** `/var/log` (arquivos de log do sistema e dos programas), `/etc` (configuração do sistema e dos programas instalados), `/proc` (estado do kernel e dos processos, gerado em tempo real) e `/dev` (arquivos que representam dispositivos).

---

## Sessão 5 — Sábado 19/09 — Autoavaliação — CONCLUÍDA

### Parte 1 — Curso do Muller

**Não realizada nesta sessão.** Não caracteriza atraso: o curso teve duas aulas nesta semana, em 15/09 (pacotes `.deb`) e 17/09 (pacotes `.rpm` e `yum`), ambas registradas nas Sessões 2 e 4.

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

**Inodes e links — aprofundamento**

16. Na saída `-rw-rw-r-- 2 davi davi 18 out original.txt`, o que significa o número `2`?
17. Um link simbólico para `original.txt` aparece com 12 bytes de tamanho. Por quê?
18. Por que um hard link não funciona entre partições diferentes, mas um link simbólico funciona?

**Gerenciamento de pacotes — conteúdo do curso**

19. Qual a diferença entre `apt update` e `apt upgrade`?
20. O `dpkg -i pacote.deb` falhou por dependências. Quais são as duas formas de resolver?

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
16. A contagem de hard links apontando para aquele inode. Vale 1 num arquivo comum e sobe a cada hard link criado. O espaço em disco só é liberado quando ela chega a zero.
17. Porque o conteúdo de um link simbólico é o caminho de destino em texto, e `original.txt` tem 12 caracteres. O tamanho do link é o comprimento da string que ele guarda.
18. O hard link aponta para um inode, e a numeração de inodes só é válida dentro do mesmo sistema de arquivos. O link simbólico guarda um caminho em texto, que é interpretado na hora do acesso e pode apontar para qualquer lugar.
19. O `apt update` sincroniza o índice local de pacotes com os repositórios, sem instalar nada. O `apt upgrade` usa esse índice para efetivamente atualizar os pacotes instalados.
20. Instalar com `dpkg -i` e depois corrigir com `sudo apt-get -f install`; ou, de forma direta, usar `sudo apt install ./pacote.deb`, que resolve as dependências desde o início. O `./` é obrigatório nessa segunda forma.

</details>

### Resultado — 20 de 20

**Realizada em 19/09.** Todas as vinte respostas corretas, contra a meta de 16.

Duas justificativas, porém, precisam de correção. A primeira é significativa.

**Correção 27 — um hard link NÃO é uma cópia.**

Na questão 7, a resposta foi certa, mas o motivo não:

> O hardlink continua funcionando porque **é uma cópia do arquivo original com outro nome**

Um hard link não é cópia. É um **segundo nome apontando para o mesmo inode** — existe um único conjunto de dados no disco, com dois rótulos. A diferença é verificável:

```bash
cd ~ && mkdir -p teste-link && cd teste-link
echo "linha um" > arquivo.txt
ln arquivo.txt link.txt
cp arquivo.txt copia.txt

echo "linha dois" >> arquivo.txt

cat link.txt      # tem as duas linhas — é o mesmo arquivo
cat copia.txt     # tem só a primeira — é outro arquivo
ls -li            # arquivo.txt e link.txt compartilham o inode; copia.txt tem o seu

cd ~ && rm -rf teste-link
```

Se hard link fosse cópia, ocuparia o dobro do espaço em disco e as edições não se propagariam. Nenhuma das duas coisas acontece.

Vale notar que este conceito estava **correto** nas suas anotações da Sessão 3, com diagrama inclusive: *"hardlink.txt não é uma cópia de original.txt — os dois nomes passam a apontar para o mesmo conteúdo físico"*. É o segundo caso, depois do `export`, em que a compreensão existe na anotação mas escorrega sob condição de prova.

O risco concreto: se a prova perguntar **"o que é um hard link?"** em vez de "ele continua funcionando?", a alternativa "uma cópia do arquivo" está entre as distratoras clássicas.

Card para o Notion: *"Hard link é cópia? → Não. É outro nome para o mesmo inode. Um único dado no disco, dois rótulos. Editar por um nome altera o que o outro mostra."*

**Correção 28 — `apt-get -f install` não força nada.**

Na questão 20: *"`sudo apt-get -f install` para forçar a instalação"*.

O `-f` é abreviação de **`--fix-broken`**. Ele não força coisa alguma — ele **conserta** o estado quebrado do sistema de pacotes, resolvendo e instalando as dependências que faltavam. É uma operação de reparo, não de imposição.

A distinção importa porque o `apt` tem opções que realmente forçam, como `--force-yes` e `--allow-downgrades`, e essas sim são perigosas em servidor. Trocar os conceitos leva a usar a ferramenta errada quando algo dá problema de verdade.

### Observações menores

Na questão 3, a resposta *"o conteúdo se reescreve"* está certa mas incompleta. O que a prova cobra é o **silêncio**: não há aviso, confirmação nem possibilidade de desfazer. Esse é o ponto.

Na questão 18, faltou a razão de fundo: a numeração de inodes **só é válida dentro do mesmo sistema de arquivos**. É por isso que um hard link não atravessa partições — o número que ele guarda não significa nada do outro lado.

---

## Fechamento da Semana 3

**Concluída em 19/09, um dia antes do prazo.** Todas as cinco sessões cumpridas.

**Objetivos cobertos:** 2.3 (Using Directories and Listing Files) e 2.4 (Creating, Moving and Deleting Files). Com isso, **o Tópico 2 está completo** — os quatro objetivos, somando 9 dos 40 pontos da prova.

**Realizado:**

- Oito dívidas da Semana 2, todas quitadas até 15/09
- Autoavaliação da Semana 2: 14 de 15
- Criação, cópia, movimentação e remoção, incluindo as armadilhas de sobrescrita silenciosa
- Hard links, links simbólicos e inodes, com o teste de remoção do original
- FHS percorrido na prática: `/etc`, `/var/log`, `/usr`, `/proc`, `/dev`, `/tmp`
- Opções avançadas do `ls`: `-S`, `-t`, `-r`, `-d`, `-R`, `-1`, `-i`
- Curso: gerenciamento de pacotes nas duas famílias, Debian e Red Hat
- Autoavaliação da Semana 3: 20 de 20

**Correções registradas na semana:** 12, numeradas de 17 a 28. Duas foram conceituais de fato — o hard link como cópia e o `-f` como força. As demais foram imprecisão de redação ou conteúdo desatualizado do curso.

**Pendências transferidas para a Semana 4:**

- Bandit níveis 6 a 9, realocados de propósito: eles exercitam `find`, `grep`, `sort` e `uniq`, que são o conteúdo do objetivo 3.2
- Registro das observações sobre arquivos ocultos, da Sessão 3
- Simulado diagnóstico completo, de 40 questões

### Limpeza

```bash
cd ~ && rm -rf lab3
```

---

## Bandit — níveis 6 a 8

Encaixe no sábado ou distribua 15 minutos por sessão.

**Reprogramado para a Semana 4.** Os níveis 6 a 9 exercitam `find` com filtros de usuário e grupo, `grep`, `sort` e `uniq` — todos conteúdo do objetivo 3.2, que é justamente o tema da Semana 4. Fazê-los agora seria treinar comandos antes de estudá-los; fazê-los na semana que vem alinha prática e teoria.

| Nível | O que treina |
|---|---|
| 6 → 7 | `find` com `-user` e `-group`, busca a partir da raiz, descarte de erros com `2>/dev/null` |
| 7 → 8 | `grep` em arquivo grande |
| 8 → 9 | `sort` e `uniq -u` combinados por pipe |

O nível 6 tem uma particularidade útil: a busca a partir de `/` gera centenas de mensagens de `Permission denied`. Descartá-las é o uso prático do `2>/dev/null` que você viu na Sessão 4.

Registro:

```bash

```

---

## Checklist da semana

- [x] Sessão 1 — dívidas e autoavaliação da Semana 2 (14/09) — nota 14 de 15
- [x] Sessão 2 — criar, copiar, mover e remover (15/09) — com retomada do curso
- [x] Sessão 3 — links e inodes (16/09) — parte de arquivos ocultos sem registro
- [x] Sessão 4 — FHS aprofundado e opções do `ls` (17/09) — com curso de `.rpm`/`yum`
- [x] Sessão 5 — autoavaliação da Semana 3 (19/09)
- [x] Autoavaliação da Semana 2 — 14 de 15
- [x] Autoavaliação da Semana 3 — 20 de 20
- [ ] Bandit níveis 6 a 9 — reprogramados para a Semana 4, onde o conteúdo casa
- [X] Cards do Notion atualizados

---

## Dívidas da Semana 2 — lista consolidada

| # | Dívida | Onde foi absorvida |
|---|---|---|
| # | Dívida | Situação |
|---|---|---|
| 1 | Autoavaliação da Semana 2 (15 questões) | Quitada em 14/09 — 14 de 15 |
| 2 | `echo $?` imediatamente após o comando testado | Quitada em 14/09 |
| 3 | `echo $OLDPWD` e o mecanismo do `cd -` | Quitada em 14/09 |
| 4 | Experimento `echo *.txt` versus `ls *.txt` | Quitada em 14/09 |
| 5 | Experimento do `Permission denied` em `/var/log` | Quitada em 15/09 |
| 6 | Instalar e testar `locate` com `updatedb` | Quitada em 14/09 |
| 7 | Navegar em `/usr/share/doc/` | Quitada em 14/09 |
| 8 | Avanço no curso do Muller | Quitada em 15/09 — gerenciamento de pacotes |

**Todas as oito dívidas da Semana 2 foram quitadas até 15/09.**

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