# Semana 1 — Comunidade, Open Source, Distribuições e FHS

**Período:** 01 a 07/09/2026
**Objetivos da prova:** 1.1 · 1.2 · 1.3 · 1.4 (Tópico 1, peso 7) + introdução ao FHS (objetivo 2.3)
**Ambiente:** VM `lab-ubuntu` (Ubuntu Server 26.04.1 LTS) via `ssh lab`

> Anotações revisadas em 02/09. Correções marcadas com ⚠️ e explicadas na seção final.

---

## 1. Open Source vs Software Livre

| Conceito | Foco | Organização |
|---|---|---|
| **Open Source** | O **código-fonte**: acesso, contribuição, revisão por muita gente — o que melhora segurança, manutenção e features | **OSI** — Open Source **Initiative** |
| **Free Software** | A **liberdade do usuário** sobre o programa. Não é um argumento técnico, é ético/filosófico | **FSF** — Free Software Foundation |

Na prática, quase todo software livre é open source e vice-versa. A diferença é de ênfase e de filosofia, não de catálogo.

**"Free as in freedom, not free as in beer"** — *free* aqui é liberdade, não preço. Software livre **pode ser vendido**.

### As 4 liberdades do Software Livre (FSF)

Numeradas a partir de zero, como bom projeto de programador:

| # | Liberdade |
|---|---|
| 0 | Executar o programa para qualquer propósito |
| 1 | Estudar e modificar o código-fonte |
| 2 | Redistribuir cópias |
| 3 | Distribuir versões modificadas |

⚠️ **Correção:** software livre não é "liberdade total sem exceções". Licenças copyleft impõem uma condição — quem redistribui tem que manter a mesma licença. A liberdade é do usuário, não do redistribuidor fazer o que quiser.

### Siglas guarda-chuva

- **FOSS** — Free and Open Source Software
- **FLOSS** — Free/Libre and Open Source Software (o "Libre" entra para desfazer a ambiguidade de *free* em inglês)

---

## 2. Tipos de licença

### Copyleft

Quem modifica e **redistribui** precisa manter a mesma licença e disponibilizar o código-fonte. A liberdade se propaga junto com o software.

⚠️ **Correção importante:** copyleft **NÃO proíbe vender**. A GPL permite explicitamente cobrar pelo software. O que ela exige é que, ao distribuir, você entregue o código-fonte e mantenha a licença. A Red Hat construiu uma empresa bilionária vendendo software GPL. O que copyleft impede é **fechar o código** e **mudar a licença**.

### Permissiva

Permite usar, modificar e redistribuir inclusive em produtos **proprietários e fechados**.

⚠️ **Correção:** não é "sem restrições". Praticamente toda licença permissiva exige **manter o aviso de copyright e o texto da licença**. Isso é uma obrigação real — projetos já foram processados por remover atribuição.

### Copyleft fraco (weak copyleft)

Meio-termo: o copyleft vale só para os arquivos originais da biblioteca, não para o programa inteiro que a usa.

- **LGPL** — GNU **Lesser** General Public License. Feita para bibliotecas: permite que um programa proprietário use a biblioteca sem virar GPL.
- **MPL** — Mozilla Public License. Copyleft em nível de **arquivo**.

### Tabela das licenças que caem na prova

| Licença | Tipo | Observação |
|---|---|---|
| **GPL v2** | Copyleft forte | A do kernel Linux |
| **GPL v3** | Copyleft forte | Adiciona cláusulas sobre patentes e "tivoização" |
| **LGPL** | Copyleft fraco | Bibliotecas |
| **MPL** (Mozilla) | Copyleft fraco | ⚠️ **NÃO é permissiva** |
| **BSD / FreeBSD** | Permissiva | Variantes de 2, 3 e 4 cláusulas |
| **MIT** | Permissiva | A mais curta e simples |
| **Apache 2.0** | Permissiva | Inclui concessão explícita de patentes |

### Creative Commons

Família de licenças para **obras criativas** (textos, imagens, música, vídeo) — não para software. Combina módulos:

| Módulo | Significa |
|---|---|
| **BY** | Atribuição obrigatória |
| **SA** | ShareAlike — derivados na mesma licença (é copyleft) |
| **NC** | NonCommercial — uso comercial proibido |
| **ND** | NoDerivatives — não pode modificar |
| **CC0** | Domínio público, sem exigências |

A Wikipédia usa CC BY-SA.

### Categorias de software (não são licenças livres)

| Categoria | O que é |
|---|---|
| **Commercial / Proprietary** | Pago, código fechado |
| **Shareware** | Distribuição livre de uma versão limitada; paga-se para liberar o resto |
| **Freeware** | Gratuito, mas **código fechado** |

⚠️ **Atenção — pega muita gente:** *freeware* ≠ *free software*. Freeware é grátis mas proprietário (ex.: o antigo Adobe Reader). Software livre é sobre liberdade e pode ser pago.

---

## 3. Distribuições Linux

⚠️ **Correção conceitual:** distribuições **não são implementações diferentes do kernel**. Todas usam o **mesmo kernel Linux** (em versões e com patches diferentes). O que muda é tudo em volta.

Uma distribuição é uma **combinação empacotada** de:

```
Kernel Linux
+ GNU Core Utils (ls, cp, grep, bash...)
+ Gerenciador de pacotes (apt, dnf, zypper, apk)
+ Softwares suplementares
+ Scripts, serviços e init system (systemd)
+ Instalador
= uma distribuição
```

### As duas grandes famílias

| Família | Base | Pacotes | Gerenciador |
|---|---|---|---|
| **Debian** | Debian | `.deb` | `apt` / `dpkg` |
| **Red Hat** | RHEL / Fedora | `.rpm` | `dnf` / `rpm` |

(SUSE é `.rpm` com `zypper`; Arch e Alpine seguem caminhos próprios.)

### Família Debian

- **Debian** — mantida pela comunidade, totalmente livre, referência em estabilidade. Serve tanto desktop quanto servidor.
- **Ubuntu** — baseada no Debian, mantida pela **Canonical**. Versões desktop e server. Lança a cada 6 meses; as **LTS** (Long Term Support) saem a cada 2 anos, em abril de anos pares, com 5 anos de suporte (10 com Ubuntu Pro).
- **Linux Mint** — baseada no Ubuntu, foco em desktop e facilidade de uso.
- **Raspberry Pi OS** (antigo Raspbian) — baseada no Debian, para o Raspberry Pi.

### Família Red Hat

- **RHEL** (Red Hat Enterprise Linux) — a maior empresa de Linux corporativo. O software é livre, mas o acesso a binários compilados, atualizações e suporte é vendido por **assinatura**.

  ⚠️ **Correção:** a Red Hat não "vende o código-fonte". O código é aberto por obrigação da GPL. O que ela vende é **assinatura de suporte, certificação e acesso ao canal oficial de atualizações**.

- **Fedora** — ⚠️ **não é derivada do RHEL, é o contrário.** Fedora é o laboratório **upstream**: as novidades aparecem nela primeiro e depois amadurecem para o RHEL. Ciclo rápido, ~6 meses, patrocinada pela Red Hat.

- **CentOS Linux** — era a recompilação gratuita do RHEL, sem marca e sem suporte. **Descontinuada**: a versão 8 encerrou em 2021 e a 7 em junho de 2024.

- **CentOS Stream** — o que existe hoje com esse nome. ⚠️ **Não é a mesma coisa:** é um *preview* contínuo do que vai virar o próximo RHEL, ficando **entre** o Fedora e o RHEL. Não é mais um clone downstream.

- **Rocky Linux** e **AlmaLinux** — os substitutos diretos do antigo CentOS Linux: recompilações gratuitas e 1:1 do RHEL.

- **Scientific Linux** — era baseada no RHEL, para computação científica (física de altas energias, grandes volumes de dados). ⚠️ **Também descontinuada**, em 2021, com o CERN e o Fermilab migrando para AlmaLinux.

### Família SUSE

- **SLES** (SUSE Linux Enterprise Server) — concorrente direta do RHEL, mesmo modelo de assinatura.
- **openSUSE** — a versão comunitária e gratuita, em dois sabores:
  - **Leap** — releases fixas, estáveis, alinhadas ao SLES
  - **Tumbleweed** — *rolling release*, sempre com os pacotes mais novos

### Outras

- **Alpine Linux** — minimalista, ~5 MB, usa `musl` em vez de `glibc` e `apk` como gerenciador. Padrão no mundo de containers. Ramos: **main** (estável) e **edge** (desenvolvimento).
- **Arch Linux** — *rolling release*, montagem manual, filosofia "faça você mesmo".

### LTS vs Rolling Release

| Modelo | Como funciona | Exemplos |
|---|---|---|
| **Fixed / Point release** | Versões numeradas, congeladas, com suporte de anos | Debian, Ubuntu LTS, RHEL, openSUSE Leap |
| **Rolling release** | Atualização contínua, sem "versões" | Arch, openSUSE Tumbleweed, Gentoo |

Servidor quer previsibilidade → fixed release. Desktop de entusiasta quer novidade → rolling.

---

## 4. Onde o Linux roda

- **Servidores e data centers** — o uso dominante. RHEL, Ubuntu Server, Debian, SLES.
- **Cloud computing** — AWS, Google Cloud, Azure: a infraestrutura roda majoritariamente Linux. **OpenStack** é a plataforma open source de IaaS para montar nuvem privada.
- **Sistemas embarcados** (*embedded systems*) — hardware que já sai de fábrica com o sistema gravado: roteadores, TVs, automóveis, equipamentos industriais.
- **IoT** (Internet of Things) — dispositivos conectados à internet: automação residencial, sensores, wearables.
- **Raspberry Pi** — computador de placa única, barato, muito usado em IoT e educação. Roda Raspberry Pi OS, baseado em Debian.
- **Android** — usa o kernel Linux (com userland própria, não GNU).
- **Supercomputadores** — 100% dos 500 maiores do mundo rodam Linux.

---

## 5. Interfaces gráficas (ambientes desktop)

| Ambiente | Característica | Gerenciador de arquivos |
|---|---|---|
| **GNOME** | Padrão do Ubuntu e Fedora. Interface própria, mais pesado | Nautilus (Files) |
| **KDE Plasma** | Altamente personalizável, visual próximo do Windows | Dolphin |
| **Xfce** | Leve, estável, muito personalizável — equilíbrio popular | Thunar |
| **LXDE / LXQt** | O mais leve, para hardware antigo | PCManFM |
| **Unity** | Da Canonical, usada no Ubuntu de 2011 a 2017 | Nautilus |
| **Cinnamon** | Padrão do Linux Mint, derivado do GNOME | Nemo |

**Correções e detalhes:**

- ⚠️ **Canonical**, não "Kanonical".
- O Unity foi abandonado em **2017**; o Ubuntu **17.10** foi o primeiro a voltar ao GNOME, e o **18.04 LTS** foi o primeiro LTS sem Unity.
- ⚠️ O KDE não foi "baseado no CDE". Foi criado em 1996 por Matthias Ettrich **como alternativa** ao CDE (Common Desktop Environment), que era proprietário e pouco amigável.
- **GNOME** = *GNU Network Object Model Environment* (sigla histórica, hoje em desuso).
- **LXDE** = *Lightweight X11 Desktop Environment*.

### Servidor gráfico

| Sistema | Situação |
|---|---|
| **X11 / X.Org** | O padrão histórico, décadas de compatibilidade |
| **Wayland** | O substituto moderno; já é padrão no Ubuntu e no Fedora |

> Sua VM é **headless** — não tem nenhum desses. É por isso que ela usa ~300 MB de RAM em vez de 2 GB.

---

## 6. Aplicações open source por categoria (objetivo 1.2)

⚠️ Sua anotação dizia "Switch Open Office". O termo é **suíte de escritório** (*office suite*).

### 6.1 Aplicações de desktop

| Categoria | Softwares | Observações |
|---|---|---|
| **Suíte de escritório** | LibreOffice (Writer, Calc, Impress, Draw), Apache OpenOffice | LibreOffice é um **fork** do OpenOffice.org, feito em 2010 pela The Document Foundation. Hoje é o mais ativo dos dois |
| **Navegador** | Firefox (Mozilla), Chromium | |
| **Navegador de terminal** | `links`, `lynx`, `w3m` | Acessam a web em modo texto, sem interface gráfica |
| **Cliente de e-mail** | Thunderbird (Mozilla), Evolution | Cliente = *MUA* (Mail User Agent). Fala IMAP e POP3 com o servidor; o Thunderbird também faz calendário e newsgroups |
| **Edição de imagem (raster)** | **GIMP** — GNU Image Manipulation Program | Equivalente ao Photoshop. Trabalha com pixels |
| **Edição vetorial** | Inkscape | Equivalente ao Illustrator. Trabalha com curvas |
| **3D** | Blender | Modelagem, animação, renderização e também edição de vídeo |
| **Áudio e vídeo** | VLC, Rhythmbox, Audacious, Clementine, Audacity (edição) | |

> ⚠️ **Fork não é cópia.** Um *fork* é uma **derivação** que passa a seguir seu próprio caminho, com equipe e decisões próprias. O LibreOffice divergiu tanto do OpenOffice que hoje são projetos diferentes, não duas versões do mesmo. Cópia seria um clone que acompanha o original — como o antigo CentOS era do RHEL.

### 6.2 Aplicações de servidor e suas portas

Serviços de rede escutam em **portas** TCP ou UDP. Saber as principais é objetivo direto da prova.

| Serviço | Função | Porta | Software |
|---|---|---|---|
| **HTTP** | Servidor web | **80** | Apache HTTP Server, nginx |
| **HTTPS** | Servidor web com TLS | **443** | Apache, nginx |
| **SSH** | Acesso remoto **criptografado** | **22** | OpenSSH (`sshd`) |
| **Telnet** | Acesso remoto **sem criptografia** | **23** | telnetd |
| **SMTP** | **Envio** de e-mail | **25** | Postfix, Sendmail, Exim |
| **POP3** | **Recebimento** de e-mail (baixa e apaga) | **110** | Dovecot |
| **IMAP** | **Recebimento** de e-mail (mantém no servidor) | **143** | Dovecot |
| **DNS** | Traduz **nomes → IPs** | **53** | BIND, dnsmasq, unbound |
| **DHCP** | Distribui IPs automaticamente | **67/68** | ISC DHCP, dnsmasq |
| **FTP** | Transferência de arquivos | **21** | vsftpd, ProFTPD |
| **NFS** | Network File System — compartilhamento entre Unix/Linux | **2049** | nfs-kernel-server |
| **SMB/CIFS** | Compartilhamento compatível com **Windows** | **139 / 445** | Samba |
| **MySQL / MariaDB** | Banco de dados relacional | **3306** | MySQL, MariaDB |
| **PostgreSQL** | Banco de dados relacional | **5432** | PostgreSQL |
| **LDAP** | Diretório de usuários | **389** | OpenLDAP |
| **IPP** | Impressão | **631** | **CUPS** — Common Unix Printing System |

Também open source, sem porta fixa padrão: **ownCloud** e **Nextcloud** (nuvem privada, rodam sobre HTTP/HTTPS).

**Correções desta seção:**

- ⚠️ **`ssh` e `sshd` não são a mesma coisa.** O `ssh` é o **cliente** (o que você digita); o `sshd` é o **daemon**, o servidor que fica escutando na porta 22. O sufixo **`d` significa daemon** e se repete em vários serviços: `httpd`, `named`, `crond`, `sshd`. Você já viu isso na prática — na VM, `systemctl is-active ssh.socket` consulta o lado servidor.
- ⚠️ **Telnet não foi feito para "testar portas".** Ele é um protocolo de **login remoto sem criptografia**, de 1969 — tudo, inclusive a senha, trafega em texto puro. Está **obsoleto e foi substituído pelo SSH**. Usar `telnet host porta` para testar se um serviço responde é um uso lateral e improvisado (hoje se usa `nc` ou `ss`). A prova cobra o contraste **Telnet inseguro × SSH criptografado**.
- **DNS** faz a resolução de **nome → IP** (e o caminho inverso, chamado *reverse lookup*). Sua anotação dizia "conversão dos IPs", que inverte a direção.

### 6.3 Métodos de desenvolvimento

Os dois modelos vêm do ensaio **"The Cathedral and the Bazaar"**, de Eric S. Raymond (1997) — texto fundador da cultura open source.

| Modelo | Como funciona | Exemplo histórico |
|---|---|---|
| **Cathedral** (catedral) | O código é desenvolvido por um grupo restrito e só é publicado nas **releases**. Entre uma versão e outra, o público não vê nada | Projeto GNU / Emacs, na época do ensaio |
| **Bazaar** (bazar) | Desenvolvimento **aberto e contínuo**: qualquer um vê o código a qualquer momento, propõe mudanças e reporta bugs | Kernel Linux |

A frase-síntese do ensaio: *"given enough eyeballs, all bugs are shallow"* — com olhos suficientes, todo bug é raso. É o argumento central a favor do modelo bazar.

### 6.4 Linguagens de programação

| Tipo | Como executa | Exemplos |
|---|---|---|
| **Compiladas** | Um **compilador** traduz o código-fonte para código de máquina (binário) **antes** da execução. O resultado roda direto no processador | C, C++, Go, Rust |
| **Interpretadas** | Um **interpretador** lê e executa o código-fonte **na hora**, linha a linha. Não há binário gerado | Python, Perl, PHP, Ruby, Shell script, JavaScript |
| **Híbridas (bytecode)** | Compiladas para um formato intermediário, executado por uma máquina virtual | Java (JVM), C# (.NET) |

**Trade-offs reais:**

| Aspecto | Compilada | Interpretada |
|---|---|---|
| **Velocidade de execução** | Mais rápida (código de máquina nativo) | Mais lenta (tradução em tempo de execução) |
| **Portabilidade** | O binário serve só para uma arquitetura/SO — precisa recompilar | O mesmo arquivo roda em qualquer lugar que tenha o interpretador |
| **Dependência** | Nenhuma na máquina do usuário | Exige o interpretador instalado |
| **Ciclo de desenvolvimento** | Mais lento: editar → compilar → testar | Mais rápido: editar → rodar |
| **Erros** | Muitos aparecem na compilação | Só aparecem na execução |

> ⚠️ **Correção:** sua anotação dizia que linguagens compiladas "tendem a ser menores devido às bibliotecas que pesam bastante". **Tamanho não é uma diferença confiável entre os dois modelos** — um binário C com *static linking* pode ser bem maior que o script Python equivalente. As diferenças que valem são as da tabela acima: velocidade de execução × portabilidade e velocidade de desenvolvimento.

Para a prova, as linguagens citadas nos objetivos são: **C, Java, JavaScript, Perl, PHP, Python e Shell script**.

---

## 7. FHS — Filesystem Hierarchy Standard (objetivo 2.3)

Padrão que define onde cada tipo de arquivo mora numa distribuição Linux. Adotado por praticamente todas.

| Diretório | Conteúdo |
|---|---|
| `/` | Raiz — tudo pendura daqui |
| `/bin` | *Binaries* — comandos essenciais para todos os usuários (`ls`, `cp`, `cat`) |
| `/sbin` | *System binaries* — comandos de **administração**, geralmente só úteis ao root (`fdisk`, `iptables`) |
| `/boot` | Kernel, initramfs e o gerenciador de boot (GRUB) |
| `/dev` | *Devices* — arquivos que representam dispositivos: discos, terminais, periféricos |
| `/etc` | Arquivos de **configuração** do sistema e dos programas instalados |
| `/home` | Diretórios pessoais dos usuários comuns |
| `/root` | O diretório pessoal **do usuário root** (não confundir com `/`) |
| `/lib`, `/lib64` | Bibliotecas compartilhadas essenciais |
| `/media` | Ponto de montagem **automático** de mídia removível (pendrive, CD) |
| `/mnt` | Ponto de montagem **manual e temporário** |
| `/opt` | *Optional* — software de terceiros instalado fora do gerenciador de pacotes |
| `/proc` | Pseudo-sistema de arquivos: informações sobre **processos** e sobre o kernel |
| `/sys` | Pseudo-sistema de arquivos: dispositivos, drivers, módulos e energia |
| `/run` | Dados de execução criados **desde o último boot** (em RAM, some ao desligar) |
| `/tmp` | Arquivos temporários de qualquer usuário |
| `/usr` | **Unix System Resources** — programas, bibliotecas e documentação instalados no sistema |
| `/var` | *Variable* — dados que mudam de tamanho durante a operação: logs, filas, caches, bancos |
| `/srv` | Dados servidos por serviços do sistema (ex.: site de um servidor web) |

**Correções da seção:**

- ⚠️ **`/usr` NÃO é "coisas do usuário".** Significa **Unix System Resources**. Contém `/usr/bin`, `/usr/lib`, `/usr/share` — o software do sistema. Os arquivos pessoais ficam em `/home`. Essa confusão é clássica e cai na prova.
- ⚠️ **`/proc` é sobre processos**, não "hardware do arquivo". Cada processo em execução tem uma pasta com seu PID lá dentro. Também expõe info do kernel (`/proc/cpuinfo`, `/proc/meminfo`).
- ⚠️ **`/run` e `/tmp` são diferentes.** `/run` é dado de runtime dos serviços desde o boot, sempre em RAM. `/tmp` é rascunho de qualquer usuário e pode sobreviver entre reinicializações, dependendo da configuração.
- ⚠️ **`/sbin`** é *system binaries* — binários de administração. Não "sistema de arquivos".

### Verificar na VM

```bash
ls /
ls /etc | head -20
ls /bin | wc -l
cat /proc/cpuinfo | head
cat /proc/meminfo | head -3
ls -l /bin
df -h
```

O último `ls -l /bin` mostra algo curioso: em distribuições modernas, `/bin` é um **link simbólico** para `/usr/bin`. Isso se chama */usr merge* — a separação histórica entre `/bin` e `/usr/bin` deixou de fazer sentido e foi unificada. Vale saber que existe, mas a prova cobra o modelo clássico da tabela.

---

## 8. Comandos praticados

| Comando | O que faz |
|---|---|
| `sudo su` | Vira root (⚠️ ver correção abaixo) |
| `cd /` | Vai para a raiz do sistema |
| `cd ..` | Vai para o diretório **pai** |
| `cd` (sozinho) | Vai para a home do usuário |
| `ls` | Lista o conteúdo do diretório atual |

**Correções:**

- ⚠️ **`cd ..` vai para o diretório PAI, não para o "anterior".** Quem volta ao diretório anterior é o **`cd -`**. São coisas diferentes e a prova diferencia:
  ```bash
  cd /var/log
  cd /etc
  cd ..     # → /  (o pai de /etc)
  cd -      # → /etc (o anterior)
  ```
- ⚠️ **`ls` lista o conteúdo do diretório atual**, arquivos e pastas — não "o que contém em cada um". Para ver o conteúdo dos subdiretórios, é `ls -R` (recursivo).
- ⚠️ **`sudo su` funciona, mas não é a forma recomendada.** O preferível é `sudo -i` (shell de login como root) ou `sudo su -`. Sem o `-`, você vira root mas mantém as variáveis de ambiente do seu usuário, o que causa comportamentos estranhos. Melhor ainda: usar `sudo comando` para cada ação, sem virar root.

---

## 9. Resumo das correções desta revisão

| # | O que estava | O que é | Por que importa |
|---|---|---|---|
| 1 | Copyleft "não permite vender" | Copyleft **permite vender**; exige código aberto e mesma licença | Erro conceitual que a prova cobra diretamente |
| 2 | Mozilla listada como permissiva | MPL é **copyleft fraco** | Questão de classificação de licenças |
| 3 | `/usr` = "coisas do usuário" | `/usr` = **Unix System Resources** (software do sistema) | Confusão clássica de FHS |
| 4 | `cd ..` = "diretório anterior" | `cd ..` = **pai**; `cd -` = anterior | Diferença que cai em questão prática |
| 5 | Distro = "implementação do kernel" | Distro = **empacotamento** em torno do mesmo kernel | Definição fundamental do Tópico 1 |
| 6 | Fedora como derivada do RHEL | Fedora é **upstream** do RHEL | Relação invertida |
| 7 | CentOS = "RHEL de graça" | CentOS Linux acabou; **Stream** é upstream, não clone | Situação mudou em 2021/2024 |
| 8 | Free Software = "liberdade sem exceções" | São as **4 liberdades**; copyleft impõe condição ao redistribuir | Base filosófica do objetivo 1.3 |
| 9 | "Kanonical" / "Switch Office" | **Canonical** / **suíte** de escritório | Grafia dos nomes cai em questão |
| 10 | Telnet "para testar portas" | Telnet = login remoto **sem criptografia**, obsoleto, substituído pelo SSH | O contraste Telnet × SSH é questão clássica |
| 11 | "SSH pode ser chamado de SSHD" | `ssh` = **cliente**; `sshd` = **daemon/servidor**. O `d` final significa daemon | Distinção cliente/servidor cai na prova |
| 12 | DNS "converte os IPs" | DNS resolve **nome → IP** (e o reverso) | Direção invertida |
| 13 | Fork = "cópia" | Fork = **derivação** que segue caminho próprio | LibreOffice × OpenOffice |
| 14 | Compiladas "tendem a ser menores" | Tamanho não distingue; o que distingue é **velocidade × portabilidade** | Comparação errada leva a resposta errada |
| 15 | Interpretadas "compilam e executam" | O interpretador **executa direto**, sem gerar binário | Definição do objetivo 1.2 |
| 16 | Bandit 3 e 4 resolvidos com `find` + `cat` em tudo | Nível 3 é `ls -a` (arquivo oculto); nível 4 é `file ./*` (identificar tipo) | Ver seção 11 |

---

## 10. Cards de revisão (Notion)

Perguntas prioritárias desta semana, já no meu sistema de cards:

**Licenças e filosofia**
- Copyleft permite vender? → Sim. Exige código aberto e mesma licença.
- Freeware é software livre? → Não. É gratuito mas proprietário.
- MPL é permissiva ou copyleft? → Copyleft fraco (por arquivo).
- LGPL serve para quê? → Bibliotecas usadas por programas não-GPL.
- Quais as 4 liberdades? → 0 executar, 1 estudar/modificar, 2 redistribuir, 3 distribuir modificado.
- OSI e FSF representam o quê? → Open Source Initiative (código) e Free Software Foundation (liberdade).

**Distribuições**
- Fedora vem do RHEL ou o RHEL vem do Fedora? → Fedora é upstream do RHEL.
- O que substituiu o CentOS Linux? → Rocky Linux e AlmaLinux.

**FHS e comandos**
- O que significa `/usr`? → Unix System Resources.
- Diferença entre `/media` e `/mnt`? → Automático vs manual/temporário.
- Diferença entre `cd ..` e `cd -`? → Pai vs anterior.
- Qual comando identifica o tipo de um arquivo? → `file`.
- Como listar arquivos ocultos? → `ls -a`.

**Portas e serviços**
- SSH, Telnet, HTTP, HTTPS, SMTP, POP3, IMAP, DNS → 22, 23, 80, 443, 25, 110, 143, 53
- Samba, NFS, MySQL, CUPS → 139/445, 2049, 3306, 631
- Diferença entre `ssh` e `sshd`? → Cliente e daemon (servidor).
- Por que o Telnet foi abandonado? → Trafega tudo em texto puro, sem criptografia.

**Desenvolvimento**
- Cathedral vs Bazaar? → Código fechado até a release vs aberto continuamente.
- Compilada vs interpretada? → Binário nativo (rápido, não portável) vs execução direta do fonte (portável, exige interpretador).

---

## 11. Registro do Bandit

Progresso e comandos usados em cada nível. Formato de conexão:

```bash
ssh bandit<N>@bandit.labs.overthewire.org -p 2220
```

| Nível | Desafio | Comando que resolveu | Status |
|---|---|---|---|
| 0 → 1 | Senha num arquivo `readme` | `ls` · `cat readme` | ✅ |
| 1 → 2 | Arquivo chamado `-` | `cat ./-` | ✅ |
| 2 → 3 | Nome de arquivo com espaços | `cat './--spaces in this filename--'` | ✅ |
| 3 → 4 | Arquivo oculto em `inhere/` | `cd inhere` · `ls -a` · `cat ./...Hiding-From-You` | ✅ |
| 4 → 5 | Único arquivo legível entre 10 | `file ./*` · `cat ./-file07` | ✅ |
| 5 → 6 | Arquivo com tamanho e propriedades específicas | em andamento | 🔄 |

### O que cada nível ensinou

**Nível 1 — o arquivo `-`.** `cat -` não funciona porque, para o `cat`, o `-` sozinho significa **"leia da entrada padrão"** em vez de "leia um arquivo com esse nome". O terminal fica parado esperando você digitar. Duas saídas:

```bash
cat ./-          # o "./" força a interpretação como caminho
cat < -          # redireciona o arquivo para a entrada
```

**Nível 2 — espaços no nome.** O shell separa argumentos por espaço, então um nome com espaços vira vários argumentos. Três formas de resolver:

```bash
cat './--spaces in this filename--'      # aspas simples
cat ./--spaces\ in\ this\ filename--     # escape com barra invertida
cat ./--sp<Tab>                          # Tab completion escapa sozinho
```

O Tab completion é o mais prático e é o que se usa no dia a dia. Ele escapa automaticamente espaços e caracteres especiais.

> Repare que o `./` reapareceu. Sempre que um nome começa com `-`, o comando tenta lê-lo como opção. O `./` desfaz a ambiguidade. Alternativa universal: `cat -- "-arquivo"` — o `--` marca "acabaram as opções".

**Nível 3 — arquivo oculto.** ⚠️ Aqui a ferramenta certa não era o `find`. Arquivos que começam com `.` são **ocultos** e o `ls` comum não os mostra:

```bash
ls          # não mostra nada
ls -a       # mostra ...Hiding-From-You
```

O `-a` vem de *all*. O `find` também funcionou, mas é matar mosca com canhão — e na prova o que se pergunta é o `ls -a`.

**Nível 4 — identificar o tipo do arquivo.** ⚠️ Você abriu todos com `cat` até achar. Funciona, mas o desafio existe para ensinar o comando **`file`**:

```bash
file ./*
```

Ele lê os primeiros bytes de cada arquivo (os *magic numbers*) e diz o que é: `ASCII text`, `data`, `ELF executable`, `PNG image`. Num diretório com 10 arquivos, resolve em um comando. Cat em arquivo binário, além de não ajudar, bagunça o terminal — se acontecer, o conserto é `reset`.

**Nível 5 — dica sem entregar a resposta.** O desafio pede um arquivo com três características simultâneas: legível por humano, **1033 bytes**, e **não executável**. O `find` aceita filtros para exatamente isso:

```bash
man find
# procure por: -size, -type, -readable, -executable
```

O `!` nega uma condição. Tamanho em bytes se escreve com o sufixo `c`. Monte o comando você mesmo — é o objetivo 3.2 da prova e vale mais que a senha.

---

## Checklist da semana

- [x] Tópico 1 — comunidade, open source e licenças
- [x] Tópico 1 — distribuições e aplicações do Linux
- [x] Tópico 1 — interfaces gráficas
- [x] Tópico 1 — aplicações de servidor e portas
- [x] Tópico 1 — métodos de desenvolvimento e linguagens
- [x] FHS — visão geral dos diretórios
- [x] Prática de navegação na VM (`cd`, `ls`, `cat`, `find`, `free -h`)
- [x] Bandit níveis 0 a 4 concluídos
- [x] Cards de revisão criados no Notion
- [ ] Bandit nível 5 → 6
- [ ] Verificar os diretórios do FHS na própria VM (`ls /`, `cat /proc/cpuinfo`, `ls -l /bin`)
- [ ] Refazer os níveis 3 e 4 do Bandit usando `ls -a` e `file`