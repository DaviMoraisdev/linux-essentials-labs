# Simulado 04 — LPI Linux Essentials (010-160)

Simulado no formato do exame, versão 1.6. Escrito em 04/11/2026 para a **terça 10/11**, na operação prática. Substitui o exame final de prática do NDG, que estava previsto nesse lugar, para não depender de acesso à plataforma. Se você tiver acesso ao NDG, o exame final de lá vira um treino extra opcional, fora do calendário.

Cinco alternativas por questão, três questões de escolher duas e cinco lacunas com a instrução que a prova usa. As questões são escritas sobre os objetivos oficiais; não são questões reais do exame. Nenhuma repete os simulados 02, 03 e 05.

## Regras

| Item | Valor |
| --- | --- |
| Questões | 40 |
| Tempo | 60 minutos, cronometrados. **Use pelo menos 45** e reserve os últimos 15 para uma segunda passada nas marcadas |
| Consulta | Nenhuma. Sem terminal, sem caderno, sem internet. **Questão pesquisada conta como errada** |
| Aprovação no exame real | 500 de 800 pontos, aproximadamente 65% — 26 acertos |
| Meta deste simulado | **24 acertos firmes** ou mais |

Anote as respostas em papel antes de abrir o gabarito. **Marque cada chute**, mesmo acertando.

Nas questões **[lacuna]**, escreva só o que foi pedido: sem caminho (salvo se o enunciado pedir), sem `sudo`, sem opções, sem explicação ao lado.

Nas questões **(escolha duas)**, a questão só conta como certa se as duas respostas estiverem certas.

## Distribuição por tópico

| Tópico | Peso | Questões |
| --- | --- | --- |
| 1. A comunidade Linux e uma carreira em open source | 7 | 1 a 7 |
| 2. Encontrando seu caminho em um sistema Linux | 9 | 8 a 16 |
| 3. O poder da linha de comando | 9 | 17 a 25 |
| 4. O sistema operacional Linux | 8 | 26 a 33 |
| 5. Segurança e permissões de arquivo | 7 | 34 a 40 |

---

## Tópico 1 — A comunidade Linux e uma carreira em open source

**1.** Uma empresa oferece um programa open source modificado **como serviço web**, sem distribuir cópias. Qual licença a obrigaria a oferecer o código-fonte modificado aos usuários do serviço?

- A) MIT
- B) AGPL
- C) BSD
- D) Apache 2.0
- E) GPLv2

**2.** O Ubuntu é derivado de qual distribuição?

- A) Fedora
- B) Slackware
- C) Arch Linux
- D) Debian
- E) openSUSE

**3. (escolha duas)** Quais linguagens são tipicamente **interpretadas**, executadas sem um passo de compilação separado?

- A) Python
- B) C
- C) Perl
- D) Go
- E) Rust

**4.** Qual tecnologia isola aplicações **compartilhando o kernel do hospedeiro**, sem um sistema operacional completo para cada instância?

- A) Hipervisor
- B) Emulação
- C) *Dual boot*
- D) Máquina virtual
- E) Contêineres

**5.** Qual ferramenta open source criptografa e assina arquivos e e-mails usando pares de chaves pública e privada?

- A) `gzip`
- B) `md5sum`
- C) GnuPG
- D) `passwd`
- E) `tar`

**6.** Uma empresa publica o núcleo do produto como open source e vende recursos adicionais proprietários. Como se chama esse modelo de negócio?

- A) *Open core*
- B) *Freeware*
- C) *Shareware*
- D) Copyleft
- E) Domínio público

**7. [lacuna]** Qual é a sigla de três letras da família de licenças permissivas criada na Universidade da Califórnia, em Berkeley, com variantes de 2 e 3 cláusulas? ______

---

## Tópico 2 — Encontrando seu caminho em um sistema Linux

**8.** O usuário está em `/usr/share/man` e executa `ls ../doc`. Qual diretório é listado?

- A) `/usr/doc`
- B) `/usr/share/doc`
- C) `/usr/share/man/doc`
- D) `/doc`
- E) `/home/usuario/doc`

**9.** O usuário está em `/etc`, executa `cd /var/log` e, em seguida, `cd -`. Onde ele fica?

- A) `/var`
- B) `/`
- C) Na pasta pessoal
- D) `/var/log`
- E) `/etc`

**10.** Qual opção do `ls` ordena a listagem pela data de modificação, dos mais recentes para os mais antigos?

- A) `-S`
- B) `-r`
- C) `-R`
- D) `-t`
- E) `-h`

**11.** Um diretório contém `a.txt`, `b.txt`, `c.txt` e `ab.txt`. Qual é a saída de `ls [ab].txt`?

- A) `a.txt b.txt c.txt`
- B) `ab.txt`
- C) `a.txt b.txt`
- D) `a.txt b.txt ab.txt`
- E) Nada: não há arquivo com esse nome

**12.** Qual opção do `rm` pede confirmação antes de apagar cada arquivo?

- A) `-i`
- B) `-f`
- C) `-r`
- D) `-v`
- E) `-d`

**13. (escolha duas)** Quais comandos listam as variáveis **de ambiente** do shell atual?

- A) `echo`
- B) `env`
- C) `unset`
- D) `printenv`
- E) `type`

**14.** Qual comando mostra, em uma linha, a descrição curta de um comando pelo **nome exato**, consultando o banco de dados do manual?

- A) `apropos`
- B) `info`
- C) `help`
- D) `type`
- E) `whatis`

**15.** Qual afirmação sobre **hard links** está correta?

- A) Guardam o caminho do arquivo de destino, como os links simbólicos
- B) Podem apontar para diretórios livremente
- C) Apontam para o mesmo inode e continuam funcionando se o nome original for apagado
- D) Podem ligar arquivos em sistemas de arquivos diferentes
- E) Aparecem com a letra `l` no início do `ls -l`

**16. [lacuna]** Qual comando cria links, simbólicos ou físicos? Escreva só o comando, sem caminho e sem parâmetros: ______

---

## Tópico 3 — O poder da linha de comando

**17.** Qual comando extrai `backup.tar.gz` **dentro** do diretório `/tmp/restaura`?

- A) `tar -czf backup.tar.gz -C /tmp/restaura`
- B) `tar -xzf /tmp/restaura backup.tar.gz`
- C) `tar -tzf backup.tar.gz -C /tmp/restaura`
- D) `tar -xzf backup.tar.gz -C /tmp/restaura`
- E) `tar -xf -C backup.tar.gz /tmp/restaura`

**18. [lacuna]** Qual comando compacta um arquivo no formato `.gz`? Escreva só o comando, sem caminho e sem parâmetros: ______

**19.** O que faz `sort < nomes.txt > ordenado.txt`?

- A) Grava `nomes.txt` em `ordenado.txt` sem ordenar
- B) Lê `nomes.txt` pela entrada padrão e grava o resultado ordenado em `ordenado.txt`
- C) Ordena `ordenado.txt` e grava o resultado em `nomes.txt`
- D) Dá erro: não se pode usar `<` e `>` no mesmo comando
- E) Acrescenta o conteúdo ordenado ao final de `nomes.txt`

**20.** Qual comando mostra a saída na tela e, **ao mesmo tempo**, a grava em um arquivo?

- A) `cat`
- B) `more`
- C) `less`
- D) `echo`
- E) `tee`

**21.** Qual operador **acrescenta** só as mensagens de erro ao final de `erros.log`, sem apagar o que já está nele?

- A) `2>>`
- B) `2>`
- C) `>>`
- D) `&>`
- E) `1>>`

**22.** Qual comando mostra as linhas de `/etc/passwd` que **começam** com `root`?

- A) `grep 'root$' /etc/passwd`
- B) `grep -v 'root' /etc/passwd`
- C) `grep '^root' /etc/passwd`
- D) `grep -c 'root' /etc/passwd`
- E) `grep '*root' /etc/passwd`

**23.** Qual comando mostra as **cinco primeiras** linhas de `dados.csv`?

- A) `tail -n 5 dados.csv`
- B) `head -n 5 dados.csv`
- C) `cat -5 dados.csv`
- D) `less -5 dados.csv`
- E) `wc -l 5 dados.csv`

**24.** Qual é a saída do trecho abaixo?

```bash
x=5
if [ $x -gt 3 ]; then
  echo maior
else
  echo menor
fi
```

- A) `menor`
- B) `5`
- C) Um erro de sintaxe
- D) `maior`
- E) `maior` e `menor`

**25.** Qual é a saída de `nome=Davi ; echo '$nome'`?

- A) `$nome`
- B) `Davi`
- C) `nome`
- D) Uma linha vazia
- E) Um erro de sintaxe

---

## Tópico 4 — O sistema operacional Linux

**26.** Em que fase do ciclo de vida uma versão ainda está em testes, antes de ser considerada estável?

- A) LTS
- B) Estável
- C) Beta
- D) Fim de vida
- E) *Rolling release*

**27.** No `ls -l /dev/sda`, a primeira letra é `b`. O que ela indica?

- A) Um arquivo binário executável
- B) Um link simbólico
- C) Um diretório
- D) Um dispositivo de caractere
- E) Um dispositivo de bloco

**28. [lacuna]** Escreva o **caminho completo** do sistema de arquivos virtual em que o kernel organiza dispositivos, barramentos e drivers, com subdiretórios como `class/net`: ______

**29.** Qual comando lista os processos de **todos os usuários**, inclusive os que não têm terminal, no estilo BSD?

- A) `ps`
- B) `ps aux`
- C) `ps -p 1`
- D) `ps -t`
- E) `jobs`

**30.** Um script longo foi iniciado em primeiro plano. Qual sequência o faz continuar rodando, mas em **segundo plano**, sem interrompê-lo?

- A) `Ctrl+C` e depois `bg`
- B) `fg`
- C) `jobs`
- D) `Ctrl+Z` e depois `bg`
- E) `kill -9 %1`

**31.** Qual comando mostra os endereços IP das interfaces na ferramenta **atual**, que substituiu o `ifconfig`?

- A) `ip addr show`
- B) `route -n`
- C) `ss -tln`
- D) `ping`
- E) `host`

**32.** Qual afirmação sobre o IPv6 está correta?

- A) Usa 32 bits, escritos em decimal
- B) Usa 64 bits, escritos em hexadecimal
- C) Não tem endereços privados ou locais
- D) O `::` pode aparecer várias vezes no mesmo endereço
- E) Usa 128 bits, escritos em hexadecimal

**33.** Em um Ubuntu com o `rsyslog`, qual arquivo registra as mensagens de autenticação, como logins por SSH e uso do `sudo`?

- A) `/var/log/syslog`
- B) `/var/log/kern.log`
- C) `/var/log/auth.log`
- D) `/var/log/dpkg.log`
- E) `/etc/auth.log`

---

## Tópico 5 — Segurança e permissões de arquivo

**34.** No `/etc/shadow`, o que indica um `!` no início do segundo campo?

- A) Que a conta não tem senha
- B) Que a senha está bloqueada
- C) Que a conta é de administrador
- D) Que a senha expirou hoje
- E) Que o hash está no `/etc/passwd`

**35. [lacuna]** Qual comando troca o usuário atual por outro, abrindo um shell dele e pedindo a senha **da conta de destino**? Escreva só o comando: ______

**36.** Qual é a forma simbólica da permissão `640`?

- A) `rw-r--r--`
- B) `rwxr-----`
- C) `r--rw----`
- D) `rw-r-----`
- E) `rw-rw----`

**37.** Um arquivo tem permissão `777`. Qual é a permissão depois de `chmod o=,g=rx arquivo`?

- A) `750`
- B) `755`
- C) `705`
- D) `770`
- E) `570`

**38.** Como aparece no `ls -ld` um diretório com permissão `2775`?

- A) `drwsrwxr-x`
- B) `drwxrwxr-t`
- C) `drwxrwSr-x`
- D) `drwxrwxrwx`
- E) `drwxrwsr-x`

**39.** Qual é a permissão **mínima** que os "outros" precisam ter em um diretório para entrar nele com `cd`, mesmo sem poder listar o conteúdo?

- A) `r--`
- B) `-w-`
- C) `--x`
- D) `rw-`
- E) Nenhuma: o `cd` não depende de permissão

**40. (escolha duas)** Quais arquivos são alterados quando o administrador executa `useradd -m carlos`?

- A) `/etc/hosts`
- B) `/etc/passwd`
- C) `/etc/resolv.conf`
- D) `/etc/shadow`
- E) `/etc/fstab`

---

# Gabarito

**Não abra antes de responder as 40 questões.**

<details>
<summary>Gabarito comentado</summary>

## Tópico 1

| Q | Resposta | Comentário |
|---|---|---|
| 1 | **B** | A AGPL estende o copyleft ao uso **pela rede**: quem oferece o programa modificado como serviço precisa oferecer o código. A GPL só obriga quem distribui cópias |
| 2 | **D** | O Ubuntu é baseado no Debian e usa o mesmo formato de pacote (`.deb`) |
| 3 | **A e C** | Python e Perl são interpretadas. C, Go e Rust são compiladas para código de máquina |
| 4 | **E** | Contêineres compartilham o kernel do hospedeiro. Máquinas virtuais, com hipervisor, têm cada uma o seu kernel (Correção 63) |
| 5 | **C** | GnuPG (`gpg`) implementa o OpenPGP. O `md5sum` só calcula um resumo; o `gzip` comprime |
| 6 | **A** | *Open core*: o núcleo aberto, os extras pagos. Copyleft é tipo de licença, não modelo de negócio |
| 7 | **`BSD`** | Grafia aceita: `BSD` |

## Tópico 2

| Q | Resposta | Comentário |
|---|---|---|
| 8 | **B** | `..` de `/usr/share/man` é `/usr/share`; `../doc` é `/usr/share/doc` |
| 9 | **E** | `cd -` volta ao diretório **anterior**, o de antes do último `cd`: `/etc`. Não é o pai (Correções 53 e 64) |
| 10 | **D** | `-t` ordena por tempo; `-S` por tamanho; `-r` inverte; `-R` é recursivo |
| 11 | **C** | `[ab]` casa **um** caractere, `a` ou `b`. `ab.txt` tem dois antes do ponto |
| 12 | **A** | `-i` (*interactive*) pergunta; `-f` força sem perguntar |
| 13 | **B e D** | `env` e `printenv` listam as variáveis de ambiente (as exportadas). O `set` listaria também as locais |
| 14 | **E** | `whatis` busca pelo nome exato; `apropos` (o mesmo que `man -k`) busca a palavra nas descrições |
| 15 | **C** | Hard link é outro nome para o mesmo inode: o conteúdo existe enquanto houver um nome. Não cruza sistemas de arquivos nem aponta para diretórios (Correção 27) |
| 16 | **`ln`** | Grafia aceita: `ln`. Com `-s`, simbólico; sem, físico |

## Tópico 3

| Q | Resposta | Comentário |
|---|---|---|
| 17 | **D** | `-x` extrai, `-z` gzip, `-f` com o nome, e `-C` muda para o diretório de destino antes de extrair |
| 18 | **`gzip`** | Grafia aceita: `gzip` |
| 19 | **B** | O `<` entrega o arquivo à entrada padrão do `sort` (quem abre o arquivo é o shell); o `>` grava a saída em outro arquivo |
| 20 | **E** | O `tee` copia a entrada para a tela **e** para o arquivo: `comando \| tee saida.txt` |
| 21 | **A** | `2>>` acrescenta só o erro; `2>` sobrescreveria; `>>` acrescentaria a saída normal |
| 22 | **C** | `^` ancora o início da linha; `$` ancora o fim |
| 23 | **B** | `head` mostra o começo; `tail`, o fim. Sem `-n`, os dois mostram 10 linhas |
| 24 | **D** | `-gt` é *greater than*: 5 > 3 é verdadeiro |
| 25 | **A** | Aspas **simples** não expandem variáveis; com aspas duplas, sairia `Davi` (Correção 72) |

## Tópico 4

| Q | Resposta | Comentário |
|---|---|---|
| 26 | **C** | Beta é a fase de testes. LTS é a versão estável com suporte estendido; *rolling release* não tem versões fixas |
| 27 | **E** | `b` = dispositivo de bloco (discos, partições); `c` = de caractere (`/dev/tty`, `/dev/null`); `l` = link; `d` = diretório |
| 28 | **`/sys`** | Grafia aceita: `/sys`. O `/proc` é de processos; o `/dev`, dos arquivos de dispositivo |
| 29 | **B** | `a` = de todos os usuários, `u` = formato com o dono, `x` = inclusive sem terminal |
| 30 | **D** | O `Ctrl+Z` suspende (`SIGTSTP`) e devolve o prompt; o `bg` o faz continuar em segundo plano. O `Ctrl+C` encerraria (Correção 78) |
| 31 | **A** | `ip addr show` substitui o `ifconfig`; `ip route show` substitui o `route`; `ss` substitui o `netstat` |
| 32 | **E** | IPv6: 128 bits, em hexadecimal; o `::` aparece **uma vez** por endereço; `fe80::` é link-local |
| 33 | **C** | No Debian e no Ubuntu, autenticação vai para o `/var/log/auth.log`; no Red Hat, para o `/var/log/secure` |

## Tópico 5

| Q | Resposta | Comentário |
|---|---|---|
| 34 | **B** | `!` ou `*` no campo do hash: senha bloqueada, sem login por senha (Exercícios da LPI 5.2) |
| 35 | **`su`** | Grafia aceita: `su`. O `sudo` pede a senha de quem executa; o `su`, a da conta de destino |
| 36 | **D** | 6 = `rw-`, 4 = `r--`, 0 = `---` |
| 37 | **A** | `o=` zera os outros; `g=rx` define o grupo como 5; o dono continua 7 |
| 38 | **E** | O `2` é SGID e aparece no `x` do **grupo**; o grupo tem `x` (7), então `s` minúsculo |
| 39 | **C** | Em diretório, `x` permite entrar e atravessar; `r` permite listar; `w`, criar e apagar |
| 40 | **B e D** | O `useradd` grava a conta no `/etc/passwd` e no `/etc/shadow` (e o grupo pessoal no `/etc/group`). Os outros arquivos não têm relação com contas |

## Tabela de temas

| Tema | Mínimo | Questões | Total |
|---|---|---|---|
| Permissões | 4 | 36, 37, 38, 39 | 4 |
| `tar` e compressão | 2 | 17, 18 | 2 |
| Redirecionamento | 3 | 19, 20, 21 | 3 |
| Diretórios virtuais e `/var` | 3 | 27, 28, 33 | 3 |
| Preencher a lacuna | 5 | 7, 16, 18, 28, 35 | 5 |

## Questões que retestam erros antigos

| Q | Erro de origem |
|---|---|
| 4 | Contêineres contra hipervisor (Correção 63, Q7 do simulado 01) |
| 9 | `cd -` contra `cd ..` (Correções 53 e 64) |
| 15 | Hard link (Correção 27) |
| 25 | Aspas simples e duplas (Correção 72) |
| 30 | Primeiro e segundo plano (Correção 78) |
| 34 | `/etc/shadow` (Q34 do simulado 02; série 01 das lacunas) |
| 36 e 37 | Conversão octal e simbólica (Q36 e Q37 do simulado 02) |
| 38 | `s` no grupo (Q38 do simulado 02) |
| 39 | `x` em diretório (Prática 2) |

</details>

---

# Apuração

Preencha depois de conferir o gabarito.

| Tópico | Peso | Questões | Acertos | Chutes acertados |
| --- | --- | --- | --- | --- |
| 1. Comunidade e open source | 7 | 1 a 7 | | |
| 2. Encontrando seu caminho | 9 | 8 a 16 | | |
| 3. Poder da linha de comando | 9 | 17 a 25 | | |
| 4. Sistema operacional | 8 | 26 a 33 | | |
| 5. Segurança e permissões | 7 | 34 a 40 | | |
| **Total** | **40** | | | |

| Tema | Questões | Acertos |
| --- | --- | --- |
| Permissões | 4 | |
| `tar` e compressão | 2 | |
| Redirecionamento | 3 | |
| Diretórios virtuais | 3 | |
| Lacunas | 5 | |

## Registro

| Campo | Valor |
| --- | --- |
| Data | 10/11/2026 |
| Tempo gasto | |
| Minutos usados na segunda passada | |
| Acertos | de 40 |
| Questões marcadas como chute | |
| Chutes acertados e chutes errados | |
| Acertos firmes | |
| Erros de forma nas lacunas | |

## Questões erradas

Só as erradas e as chutadas, no mesmo dia, seguindo o protocolo de correção da operação prática (`labs/operacao-pratica.md`, seção 4). Card no Notion só para reincidência.

| Q | Tópico | Tema | Você marcou | Gabarito | Convicção ou chute | Reincidência? |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |