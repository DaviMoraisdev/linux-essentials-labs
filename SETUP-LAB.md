# Semana 0 — Montando o laboratório (VirtualBox + Ubuntu Server)

**Tempo estimado:** 2h a 2h30 (a maior parte é download e espera)
**Custo:** R$ 0,00 — tudo gratuito e legal
**Hardware do Davi:** i5-11300H (4 núcleos / 8 threads) · 8 GB RAM · ~200 GB livres em SSD

---

## Parte 1 — Antes de instalar: entendendo o que é uma VM

### O que é, na prática

Uma **máquina virtual** é um computador inteiro simulado por software dentro do seu computador. O VirtualBox é o programa que faz essa simulação — ele se chama **hypervisor**.

O "computador" que ele cria tem processador, memória, disco e placa de rede próprios — só que todos são *fatias emprestadas* dos seus componentes reais:

| Componente da VM | O que é de verdade |
|---|---|
| "Disco rígido de 25 GB" | Um **único arquivo** `.vdi` no seu SSD (`C:\Users\Davi\VirtualBox VMs\...`) |
| "2 GB de RAM" | 2 GB da sua RAM real, **reservados só enquanto a VM está ligada** |
| "2 processadores" | 2 dos seus 8 threads, compartilhados com o Windows |
| "Placa de rede" | Uma placa virtual que sai pela internet do seu Windows |

Para o Ubuntu lá dentro, tudo isso é indistinguível de hardware real. Ele **não sabe** que está numa VM.

### Sim, é um aplicativo comum de desktop

O VirtualBox instala como qualquer programa do Windows: aparece no menu Iniciar, você abre, e vê uma janela com a lista das suas VMs. Você seleciona uma, clica em **Iniciar**, e abre outra janela — que é a tela do computador virtual, ligando do zero, com POST, boot e tela de login.

Fechar a janela do VirtualBox não apaga nada. As VMs ficam salvas como arquivos.

### Ela consome recursos o tempo todo? Não.

Esta é a parte que confunde todo mundo no começo. **Uma VM desligada não consome absolutamente nada de RAM nem de CPU** — só ocupa espaço em disco, exatamente como um arquivo de vídeo parado na sua pasta.

Os 2 GB de RAM que você "dá" para a VM não são retirados do Windows na hora da criação. Eles são reservados **no instante em que você clica em Iniciar** e devolvidos **no instante em que você desliga**.

Você tem três formas de parar uma VM:

| Ação | Analogia | O que acontece | Quando usar |
|---|---|---|---|
| **Desligar (`sudo poweroff`)** | Desligar o PC pelo menu | Sistema encerra direito, RAM é liberada, próximo boot começa do zero | **É o padrão.** Use sempre este. |
| **Salvar estado** (fechar a janela → "Save the machine state") | Hibernar | A RAM inteira é gravada num arquivo em disco e liberada. Ao ligar de novo, você volta exatamente onde parou, com os programas abertos | Quando você quer pausar no meio de um lab e voltar depois |
| **Desligamento forçado** ("Power off the machine") | Puxar o cabo da tomada | Corta na hora, pode corromper arquivos | Só se travar de vez |

Ou seja: você estuda 1h com a VM ligada, dá `sudo poweroff`, e o Windows volta a ter os 8 GB inteiros. Nada roda em segundo plano.

### Snapshot: o recurso que mais importa para você

Um **snapshot** é um ponto de restauração — literalmente um *save point* de videogame. Você tira um snapshot, destrói o sistema todo com um comando errado, clica em "Restore" e em ~10 segundos está de volta ao estado salvo.

Isso muda como você estuda: **você pode quebrar coisas de propósito.** Rodar `chmod 000 /etc`, apagar `/bin`, errar um `rm -rf` — ver o sistema quebrar e entender *por que* quebrou ensina mais rápido do que qualquer aula. Sem snapshot, você teria medo de experimentar. Com snapshot, não há risco nenhum.

Snapshots ocupam disco (guardam as diferenças desde o ponto salvo), mas com 200 GB livres isso é irrelevante para você.

---

## Parte 2 — Decisões de arquitetura para o SEU hardware

### ⚠️ Ponto crítico: 8 GB de RAM + WSL2 + Docker Desktop

Você já roda WSL2 e Docker Desktop. Ambos são, eles mesmos, máquinas virtuais rodando em segundo plano — e o WSL2 tem fama de engolir RAM. Somando Windows (~3 GB) + WSL2 (até 4 GB) + Docker Desktop (~1,5 GB) + navegador (~1,5 GB), seus 8 GB já estão comprometidos **antes** de você ligar qualquer VM.

**Duas providências resolvem isso:**

**1. Limite a RAM do WSL2.** Crie o arquivo `C:\Users\<seu-usuario>\.wslconfig` (no PowerShell: `notepad $env:USERPROFILE\.wslconfig`) com:

```ini
[wsl2]
memory=3GB
processors=4
swap=2GB
```

Depois rode `wsl --shutdown` no PowerShell. Sem isso, o WSL2 pode reservar até metade da sua RAM e só devolver com relutância.

**2. Feche o Docker Desktop antes de ligar a VM.** Não é obrigatório, mas com 8 GB é a diferença entre fluido e travando. Uma VM de Ubuntu Server sem interface gráfica usa só ~300 MB de fato — os 2 GB são folga, não consumo.

### ⚠️ Ponto crítico 2: VirtualBox vs Hyper-V

WSL2 e Docker Desktop ligam a plataforma de virtualização da Microsoft (Hyper-V / VBS) no Windows. Quando ela está ativa, o VirtualBox **não consegue mais acessar o processador diretamente** — ele passa a rodar *em cima* do Hyper-V, num modo mais lento.

Você vai perceber isso por um **ícone de tartaruga verde** no canto inferior da janela da VM. Isso é normal e esperado no seu caso.

**A recomendação é conviver com a tartaruga.** Desativar o Hyper-V quebraria seu WSL2 e seu Docker — que são seu ambiente de trabalho real. E para o que você vai fazer (terminal, comandos, scripts, sem interface gráfica), a lentidão é imperceptível. Ela só incomodaria com VMs gráficas pesadas.

### Quantas VMs? Uma só. (mudança em relação ao plano original)

O plano original previa duas VMs (Ubuntu + Debian). **Com 8 GB, isso é desperdício.** Ajuste:

| Ambiente | Para quê | Custo de RAM |
|---|---|---|
| **1 VM VirtualBox — Ubuntu Server 26.04 LTS** | O laboratório principal: boot real, `systemd`, discos, `/dev`, `/proc`, rede, usuários, permissões, scripts | 2 GB (só ligada) |
| **Containers Docker** (você já tem) | Comparar distros e gerenciadores de pacotes — `apt` vs `dnf` vs `apk` | ~30 MB cada |
| **WSL2 Ubuntu** (você já tem) | Prática rápida do dia a dia, sem ligar nada | já rodando |

Para comparar distros — que é objetivo do Tópico 4 — containers resolvem em segundos e sem custo de RAM:

```bash
docker run -it --rm rockylinux/rockylinux:10 bash   # família RHEL: dnf, rpm
docker run -it --rm debian:13 bash                  # apt, dpkg
docker run -it --rm alpine sh                       # apk, minimalista, sem bash
```

> Guarde a ideia da segunda VM (**Rocky Linux** ou **AlmaLinux**) para quando você atacar o RHCSA. Aí ela faz todo sentido — e será seu laboratório gratuito no lugar dos cursos RH124/RH134.

### Qual distro para a VM principal

**Ubuntu Server 26.04 LTS ("Resolute Raccoon")** — lançado em abril/2026, com suporte até 2036.

Por quê, no seu caso:

- **Server, não Desktop.** Sem interface gráfica você é *obrigado* ao terminal, que é exatamente o que a prova cobra. Além disso, o Desktop pediria 4 GB de RAM e ficaria pesado nos seus 8 GB. Servidor headless usa ~300 MB.
- **Ubuntu**, e não Debian ou Fedora, porque é a mesma família do seu WSL2 — você aproveita o que já sabe e as duas certificações seguintes (RHCSA à parte) e a maior parte do material em português usam Ubuntu.
- Se o curso do Muller usar **24.04 LTS**, pode instalar essa versão sem problema. Nada que cai no Linux Essentials mudou entre as duas.

**Configuração da VM:** 2 GB RAM · 2 vCPUs · disco de 25 GB dinâmico

> "Disco dinâmico" significa que o arquivo `.vdi` começa com ~2 GB e só cresce conforme você usa, até o teto de 25 GB. Você não perde 25 GB do SSD no dia da criação.

### É tudo gratuito?

Sim, e sem pegadinha:

- **VirtualBox** — software livre (GPL v2), gratuito para qualquer uso.
- **Ubuntu Server** — gratuito, sem registro obrigatório.
- **Extension Pack do VirtualBox** — ⚠️ este tem licença **diferente** (PUEL: só uso pessoal/avaliação). **Você não precisa dele.** Ele serve para USB 3.0, webcam e RDP. Não instale.
- **Guest Additions** — grátis, mas serve para tela cheia e área de transferência em VM *gráfica*. Numa VM server headless, não faz falta. Pule.

---

## Parte 3 — Passo a passo da instalação

### Etapa 1 — Confirmar que a virtualização está ligada (1 min)

Abra o Gerenciador de Tarefas (`Ctrl+Shift+Esc`) → aba **Desempenho** → clique em **CPU**. No painel da direita, procure **Virtualização**. Deve estar **Habilitado**.

Se estiver desabilitado (improvável, já que seu WSL2 funciona), é preciso ligar VT-x na BIOS/UEFI.

### Etapa 2 — Downloads (20–40 min, dependendo da internet)

Deixe os dois baixando em paralelo:

1. **VirtualBox** → https://www.virtualbox.org/wiki/Downloads → *Windows hosts* (~110 MB)
2. **Ubuntu Server 26.04 LTS** → https://ubuntu.com/download/server → botão *Download Ubuntu Server 26.04 LTS* (arquivo `.iso`, ~3 GB)

> Um arquivo `.iso` é a imagem de um DVD de instalação. Você não precisa gravar nada — a VM "insere" esse arquivo como se fosse um disco.

### Etapa 3 — Instalar o VirtualBox (3 min)

Execute o instalador e aceite tudo como está (Next → Next → Install).

- Ele vai avisar que **a rede será reiniciada** por alguns segundos. Normal — ele instala placas de rede virtuais. Aceite.
- Se pedir para instalar dependências (Python), pode aceitar.
- Ao final, **não** baixe o Extension Pack.

### Etapa 4 — Criar a VM (5 min)

No VirtualBox, clique em **Novo** (ou `Ctrl+N`).

**Tela 1 — Nome e Sistema Operacional:**

| Campo | Valor |
|---|---|
| Name | `lab-ubuntu` |
| Folder | deixe o padrão |
| ISO Image | selecione o `.iso` do Ubuntu Server que você baixou |
| Type / Version | preenche sozinho: *Linux / Ubuntu (64-bit)* |
| **☑ Skip Unattended Installation** | **MARQUE ESTA CAIXA** |

> ⚠️ **Marcar "Skip Unattended Installation" é importante.** Sem isso o VirtualBox instala o Ubuntu sozinho, e você perde justamente o processo de instalação — que ensina particionamento, hostname, criação de usuário e configuração de rede, tudo conteúdo do exame.

**Tela 2 — Hardware:**

| Campo | Valor |
|---|---|
| Base Memory | `2048 MB` |
| Processors | `2` |
| Enable EFI | deixe desmarcado |

**Tela 3 — Disco:**

| Campo | Valor |
|---|---|
| Create a Virtual Hard Disk Now | selecionado |
| Tamanho | `25 GB` |
| ☐ Pre-allocate Full Size | **deixe desmarcado** (é o que torna o disco dinâmico) |

Clique em **Finish**.

### Etapa 5 — Configurar a rede para SSH (3 min)

Isso permite você acessar a VM pelo Windows Terminal, em vez de ficar preso na janelinha do VirtualBox. Vale muito a pena — e já treina `ssh`, que cai na prova.

Selecione a VM → **Configurações** → **Rede** → **Adaptador 1**:

- *Conectado a:* **NAT** (já é o padrão)
- Expanda **Avançado** → clique em **Redirecionamento de Portas**
- Clique no **+** e preencha:

| Nome | Protocolo | IP Host | Porta Host | IP Convidado | Porta Convidado |
|---|---|---|---|---|---|
| ssh | TCP | *(vazio)* | `2222` | *(vazio)* | `22` |

OK → OK.

> ⚠️ **Não encontrou "Avançado" nem "Redirecionamento de Portas"?** As versões novas do VirtualBox (7.1+) redesenharam essa janela e escondem esses campos no modo **Básico**. Procure o alternador **Básico / Expert** no canto superior direito da janela de Configurações e mude para **Expert**.
>
> Se ainda assim não aparecer, use a linha de comando — é infalível e independe da versão da interface. Com a **VM desligada**, no PowerShell:
>
> ```powershell
> cd "C:\Program Files\Oracle\VirtualBox"
> .\VBoxManage.exe modifyvm "lab-ubuntu" --natpf1 "ssh,tcp,,2222,,22"
> .\VBoxManage.exe showvminfo "lab-ubuntu" | Select-String "Rule"
> ```
>
> A saída deve conter `NIC 1 Rule(0): name = ssh, protocol = tcp, host port = 2222, guest port = 22`.
>
> O `VBoxManage` é a interface de linha de comando do VirtualBox — tudo que a janela faz, ele faz, e mais. Vale conhecer.

### Etapa 6 — Instalar o Ubuntu Server (20–30 min)

Selecione a VM e clique em **Iniciar**. Ela vai bootar pelo ISO.

> 💡 **Como sair da janela da VM:** quando você clica dentro dela, o mouse e o teclado ficam "capturados". Para liberar, aperte a **tecla Host**, que por padrão é o **Ctrl da direita**.

Siga o instalador (navegação por setas, Tab e Enter — não tem mouse):

| Tela | O que escolher |
|---|---|
| Language | `English` (recomendado — todo o material técnico e as mensagens de erro que você vai pesquisar estão em inglês) |
| Keyboard | Se seu teclado tem a tecla `Ç`: **Portuguese (Brazil)**. Se não tem: **English (US)**. Use o "Identify keyboard" se ficar em dúvida — teclado errado é a causa nº1 de "minha senha não funciona" |
| Type of install | `Ubuntu Server` (não o minimized) |
| Network | Deixe como está — pega IP automático via DHCP |
| Proxy | Deixe em branco → Done |
| Mirror | Deixe o padrão → Done |
| Storage | `Use an entire disk` · deixe **☑ Set up this disk as an LVM group** marcado (é o que servidores reais usam, e você vai querer ver isso no `lsblk`) → Done |
| Confirmação destrutiva | `Continue` — ele vai formatar o **disco virtual**, não o seu SSD |
| Profile | Your name: `Davi` · Server name: `lab-ubuntu` · Username: `davi` · senha: escolha uma **simples e que você lembre** (é um lab isolado) |
| Ubuntu Pro | `Skip for now` |
| SSH Setup | **☑ Install OpenSSH server** — **MARQUE**. É isso que permite o acesso pelo Windows Terminal |
| Featured snaps | **Não marque nada** → Done |

A instalação leva ~10–20 min (ele baixa atualizações no final). Quando aparecer **Reboot Now**, selecione e dê Enter.

Se ele travar pedindo para remover a mídia de instalação, aperte Enter. Se mesmo assim ficar preso, desligue a janela e no VirtualBox vá em **Configurações → Armazenamento**, selecione a unidade óptica e remova o ISO.

### Etapa 7 — Primeiro login e preparação (5 min)

Faça login com `davi` e sua senha.

> 💡 Ao digitar a senha no Linux **nada aparece na tela** — nem asteriscos. Isso é proposital, não é travamento. Digite e dê Enter.

Rode:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y tree tldr htop unzip zip
ip addr          # veja o IP da VM (deve ser 10.0.2.15)
hostname
free -h          # veja quanta RAM ela realmente usa
df -h            # veja o disco
sudo poweroff    # desliga a VM corretamente
```

### Etapa 8 — O snapshot `limpo` (1 min) — não pule

Com a VM **desligada**, no VirtualBox:

1. Selecione `lab-ubuntu`
2. No menu de hambúrguer (☰) ao lado do nome → **Snapshots**
3. Clique em **Tirar** (Take)
4. Nome: `limpo` · Descrição: `Ubuntu Server 26.04 recém-instalado, atualizado, SSH ativo`
5. OK

Pronto. A partir daqui, **nada que você fizer é irreversível.**

### Etapa 9 — Acessar pelo Windows Terminal (2 min)

Ligue a VM. Ela vai bootar até a tela de login — **deixe nessa tela e minimize a janela**, não precisa logar por ali.

Abra o Windows Terminal (PowerShell) e rode:

```powershell
ssh -p 2222 davi@127.0.0.1
```

Na primeira vez ele pergunta sobre a autenticidade do host — digite `yes`. Depois a senha.

Se você caiu num prompt `davi@lab-ubuntu:~$`, **está tudo funcionando.** Você agora tem um servidor Linux de verdade acessível numa aba do seu terminal, ao lado da aba do WSL2.

---

### Etapa 10 — Verificação final: provar que tudo funciona

**A. O teste do snapshot (o mais importante — não pule)**

Um snapshot que você nunca testou não é uma rede de segurança, é uma suposição. Prove que funciona:

```bash
# Com a VM ligada:
touch ~/EU-NAO-DEVERIA-EXISTIR.txt
ls ~
sudo poweroff
```

No VirtualBox: selecione o snapshot `limpo` → **Restaurar** → confirme (pode desmarcar "criar snapshot do estado atual"). Ligue a VM e:

```bash
ls ~
```

Se o arquivo **sumiu**, sua rede de segurança está funcionando e você pode quebrar o que quiser daqui pra frente.

**B. Verificação dentro da VM**

```bash
cat /etc/os-release | head -2   # Ubuntu 26.04 LTS
uname -r                        # versão do kernel
df -h /                         # ~23G, uso baixo
free -h                         # RAM disponível
swapon --show                   # arquivo de swap ativo
systemctl is-active ssh         # deve responder: active
ip addr show | grep "inet "     # deve mostrar 10.0.2.15
tree --version && htop --version && tldr --version
apt list --upgradable 2>/dev/null | tail -n +2 | wc -l   # deve ser 0
```

**C. Verificação no lado Windows (PowerShell)**

```powershell
Get-Content $env:USERPROFILE\.wslconfig          # limite de RAM do WSL2
cd "C:\Program Files\Oracle\VirtualBox"
.\VBoxManage.exe snapshot "lab-ubuntu" list      # deve listar: limpo
.\VBoxManage.exe showvminfo "lab-ubuntu" | Select-String "Rule|Memory size|Number of CPUs"
```

**D. O teste definitivo — SSH**

Com a VM ligada na tela de login (sem logar), no Windows Terminal:

```powershell
ssh -p 2222 davi@127.0.0.1
```

Caiu em `davi@lab-ubuntu:~$`? A Semana 0 está concluída.

---

## Rotina diária — usando a VM pelo PowerShell

### Por que "digitar o comando" dá erro e "colar" funciona

O comando `.\VBoxManage.exe` tem duas partes que precisam estar certas:

- **`.\`** significa literalmente *"o arquivo que está nesta pasta"*. Se você não estiver dentro de `C:\Program Files\Oracle\VirtualBox`, não existe nada com esse nome ali, e o PowerShell reclama.
- Por isso o comando só funciona **depois** do `cd "C:\Program Files\Oracle\VirtualBox"`. Colado, você trouxe o `cd` junto sem perceber.

**A solução definitiva é o PATH.** O PATH é a lista de pastas onde o sistema procura programas quando você digita um nome sem caminho. É por isso que `git`, `ping` e `notepad` funcionam de qualquer lugar: as pastas deles estão no PATH.

Teste primeiro (de qualquer pasta):

```powershell
VBoxManage --version
```

Se responder com um número de versão, já está no PATH e você pode esquecer o `cd` e o `.\` para sempre. Se der "não é reconhecido", adicione:

```powershell
$antigo = [Environment]::GetEnvironmentVariable("Path","User")
[Environment]::SetEnvironmentVariable("Path", "$antigo;C:\Program Files\Oracle\VirtualBox", "User")
```

**Feche e reabra o Windows Terminal** (a mudança só vale para terminais novos) e teste de novo.

> Esse é exatamente o mesmo conceito da variável `$PATH` no Linux, objetivo **2.1** da prova. Rode `echo $PATH` na VM e compare — é a mesma ideia, com `:` no lugar de `;`.

### Melhoria 1 — Apelido para o SSH (`.ssh/config`)

Em vez de decorar `ssh -p 2222 davi@127.0.0.1`, você registra o servidor numa agenda de endereços. Crie o arquivo:

```powershell
notepad $env:USERPROFILE\.ssh\config
```

Conteúdo (a indentação é só estética, mas mantenha):

```
Host lab
    HostName 127.0.0.1
    Port 2222
    User davi
```

Salve. Agora `ssh lab` faz tudo. É um arquivo padrão do OpenSSH — o mesmo formato funciona no Linux, em `~/.ssh/config`, e é assim que se guardam dezenas de servidores com apelido.

### Melhoria 2 — Atalhos permanentes (`$PROFILE`)

`$PROFILE` é um script que o PowerShell executa **toda vez que abre**. É o equivalente do `.bashrc` do Linux: o que você define ali passa a existir em todo terminal novo.

```powershell
if (!(Test-Path $PROFILE)) { New-Item -Path $PROFILE -Type File -Force }
notepad $PROFILE
```

Cole:

```powershell
function lab-up     { VBoxManage startvm "lab-ubuntu" --type headless }
function lab-down   { VBoxManage controlvm "lab-ubuntu" acpipowerbutton }
function lab-status { VBoxManage list runningvms }
```

Salve, **feche e reabra o terminal**.

> Se ao abrir aparecer um erro vermelho sobre "execução de scripts desabilitada", rode uma vez:
> `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`

### A rotina, do início ao fim

```powershell
lab-up          # liga a VM sem janela (headless)
                # espere ~25 segundos
lab-status      # confirma que está rodando
ssh lab         # entra
```

Você estuda dentro da sessão SSH. Ao terminar:

```bash
exit            # sai do SSH (a VM continua ligada)
```

```powershell
lab-down        # desliga a VM
lab-status      # deve não listar mais nada
```

Ou, mais simples, desligue de dentro da própria VM com `sudo poweroff` — a conexão cai sozinha e a VM se apaga. As duas formas são equivalentes.

**Quando você ainda precisa abrir o VirtualBox:** para criar e restaurar snapshots, e se a VM não bootar e você precisar ver a tela de erro. No dia a dia, não.

---

## Checklist da Semana 0

- [ ] `.wslconfig` criado limitando o WSL2 a 3 GB
- [ ] Virtualização confirmada como Habilitada no Gerenciador de Tarefas
- [ ] VirtualBox instalado (sem Extension Pack)
- [ ] VM `lab-ubuntu` criada: 2 GB RAM, 2 vCPU, disco 25 GB dinâmico
- [ ] Redirecionamento de porta 2222 → 22 configurado
- [ ] Ubuntu Server 26.04 LTS instalado com OpenSSH server
- [ ] `sudo apt update && upgrade` executado
- [ ] **Snapshot `limpo` criado**
- [ ] SSH funcionando pelo Windows Terminal
- [ ] Containers de teste rodados (`rockylinux`, `debian`, `alpine`)
- [ ] Repositório `linux-essentials-labs` criado no GitHub *(próximo passo)*

---

## Problemas comuns

| Sintoma | Causa / solução |
|---|---|
| Ícone de **tartaruga verde** na barra da VM | Normal no seu caso — VirtualBox rodando sobre o Hyper-V por causa do WSL2. Não é defeito, não atrapalha labs de terminal. |
| Erro `VT-x is not available` | Virtualização desligada na BIOS, ou algum outro hypervisor travando o acesso. Confirme no Gerenciador de Tarefas. |
| VM extremamente lenta, Windows travando | RAM acabou. Feche o Docker Desktop e rode `wsl --shutdown` antes de ligar a VM. |
| Só aparece opção de sistema 32-bit ao criar a VM | Virtualização desabilitada na BIOS. |
| `ssh: connect to host 127.0.0.1 port 2222: Connection refused` | A VM não terminou de bootar, ou o OpenSSH não foi instalado. Logue pela janela do VirtualBox e rode `sudo apt install -y openssh-server && sudo systemctl enable --now ssh`. |
| Senha "errada" no primeiro login | Layout de teclado diferente do escolhido na instalação. Teste digitando a senha no campo de usuário para ver o que sai. |
| Mouse/teclado presos na janela da VM | Aperte o **Ctrl da direita** (tecla Host). |

---

## Fontes

- [VirtualBox — Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Ubuntu — Download Server](https://ubuntu.com/download/server)
- [Canonical — Ubuntu 26.04 LTS "Resolute Raccoon"](https://canonical.com/blog/canonical-releases-ubuntu-26-04-lts-resolute-raccoon)
- [Ubuntu — Ciclo de releases](https://ubuntu.com/about/release-cycle)
- [Fórum VirtualBox — coexistência com WSL2/Hyper-V](https://forums.virtualbox.org/viewtopic.php?t=112602)