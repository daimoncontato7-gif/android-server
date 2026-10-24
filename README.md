# 📱 Transforme um celular Android antigo em um servidor de arquivos (Mini NAS)

♻️ **Dê uma nova vida ao seu celular antigo!** Transforme um dispositivo Android parado em um servidor de arquivos acessível pelo Wi-Fi, permitindo armazenar, transferir e gerenciar seus arquivos diretamente pelo navegador, sem precisar de um computador ou de um servidor dedicado.

Utilizando **Termux + File Browser**, você cria seu próprio mini NAS de forma simples, prática e acessível.

**Celular antigo → Termux → File Browser → Seus arquivos pela rede.**

O projeto automatiza a instalação e a configuração inicial para que você tenha seu próprio servidor de arquivos em poucos minutos.

## 🚀 O que é este projeto?

O `android-nas` é um instalador que transforma um celular Android em um servidor de arquivos para sua rede local.

Com ele, você pode acessar os arquivos do celular pelo navegador de um computador, tablet ou outro smartphone conectado à mesma rede Wi-Fi.

Tudo isso aproveitando um dispositivo que provavelmente estaria esquecido em uma gaveta.

## ✨ Principais recursos

O instalador automatiza as principais etapas da configuração:

- 📂 Configuração do acesso aos arquivos do Android.
- 📦 Instalação das dependências necessárias.
- ⚙️ Detecção automática da arquitetura do dispositivo.
- ⬇️ Download da versão compatível do File Browser.
- 🔧 Instalação e configuração inicial do servidor.
- 👤 Criação de um usuário personalizado.
- 🔐 Definição de senha com no mínimo 12 caracteres.
- 🌐 Escolha da porta de acesso.
- 📡 Detecção automática do endereço IP do celular.
- ▶️ Inicialização do servidor com exibição do endereço de acesso.

O objetivo é simplificar o processo e evitar configurações manuais desnecessárias.

## 🛠️ O que você precisa?

Antes de começar, tenha em mãos:

- Um celular Android.
- Conexão Wi-Fi.
- O aplicativo Termux.
- Um navegador no dispositivo que acessará os arquivos.

**Você não precisa de:**

- ❌ Root.
- ❌ Computador para realizar a instalação.
- ❌ Depuração USB.
- ❌ Hardware dedicado.
- ❌ Modo desenvolvedor.

O celular e o dispositivo que acessará os arquivos precisam estar conectados à mesma rede Wi-Fi para o funcionamento padrão.

## 📥 Instalação

### 1. Instale o Termux

Recomendo utilizar a versão disponível no F-Droid:

🔗 https://f-droid.org/packages/com.termux/

Após instalar, abra o aplicativo.

### 2. Atualize os pacotes e instale o Git

Execute os comandos abaixo no Termux:

```bash
pkg update
pkg install git -y
```

### 3. Baixe o projeto

Clone o repositório oficial:

```bash
git clone https://github.com/daimoncontato7-gif/android-server
```

Entre no diretório do projeto:

```bash
cd android-nas
```

### 4. Execute o instalador

Inicie a instalação com:

```bash
bash install.sh
```

A partir desse momento, o instalador guiará você pelas etapas de configuração.

## 🔐 Configuração de usuário e senha

Durante a instalação, você poderá definir suas próprias credenciais de acesso.

O instalador solicitará:

- Nome de usuário.
- Senha.
- Confirmação da senha.

A senha deverá possuir **no mínimo 12 caracteres**.

Por segurança, os caracteres digitados no campo de senha não serão exibidos no terminal. Isso é normal.

Caso as senhas informadas sejam diferentes, será necessário digitá-las novamente.

## 🌐 Escolha da porta do servidor

Por padrão, o servidor utiliza a porta `8080`.

Durante a instalação, você poderá aceitar a configuração padrão pressionando ENTER ou escolher outra porta disponível.

Exemplo:

```text
Digite a porta [8080]: 8085
```

Nesse caso, o servidor será acessado pelo endereço:

```text
http://IP-DO-CELULAR:8085
```

## 📡 Como acessar seus arquivos

Após a configuração, o instalador detectará o endereço IP local do celular e exibirá o endereço de acesso.

Exemplo:

```text
======================================
       SERVIDOR INICIADO!
======================================

Acesse pelo navegador:

   http://192.168.15.31:8080

Usuário: seu_usuario
```

O endereço acima é apenas ilustrativo. Utilize o IP exibido pelo seu próprio dispositivo.

**Para acessar:**

1. Mantenha o celular e o outro dispositivo conectados à mesma rede Wi-Fi.
2. Copie o endereço informado pelo Termux.
3. Abra o endereço no navegador do computador ou de outro celular.
4. Entre com o usuário e a senha definidos durante a instalação.
5. Comece a gerenciar seus arquivos pela interface do File Browser.

Pronto! Você terá uma interface web para acessar e gerenciar os arquivos disponibilizados pelo servidor.

## ⚙️ Compatibilidade com diferentes arquiteturas

O instalador utiliza o comando `uname -m` para identificar a arquitetura do dispositivo e selecionar o binário correspondente do File Browser.

Arquiteturas consideradas pelo projeto:

| Arquitetura | Identificação |
|---|---|
| `aarch64` | ARM64 |
| `x86_64` | AMD64 |
| `i686` | x86 de 32 bits |
| `armv7l` | ARM de 32 bits |

A maioria dos smartphones Android atuais utiliza ARM64 e normalmente retorna `aarch64`.

Se a arquitetura não for reconhecida pelo script, a instalação será interrompida para evitar uma configuração incompatível.

## 💾 O que você pode fazer com seu Mini NAS?

Depois de configurado, seu celular poderá ser utilizado para:

- 📁 Armazenar e organizar arquivos.
- 🔄 Transferir documentos entre dispositivos.
- 📸 Guardar fotos e vídeos.
- 💾 Criar uma central de arquivos para backups.
- 📄 Acessar documentos pelo navegador.
- 🏠 Compartilhar arquivos na rede local.
- ♻️ Reaproveitar um smartphone antigo.

Tudo isso sem precisar comprar um NAS dedicado para começar.

## 🌍 Acesso pela internet

Por padrão, o projeto foi pensado para funcionar na rede local.

Também é possível planejar o acesso remoto, mas isso exige configurações adicionais de rede e medidas de segurança.

**⚠️ Atenção:** não exponha diretamente a porta do File Browser à internet sem compreender os riscos envolvidos. Para acesso remoto, prefira uma solução segura, como uma VPN, e mantenha o software atualizado.

Uma senha forte é importante, mas não substitui as demais medidas de segurança.

## 🔋 Dicas para manter o servidor funcionando

- Mantenha o celular conectado à energia quando necessário.
- Verifique as configurações de economia de bateria do Android.
- Evite que o sistema encerre o Termux em segundo plano.
- Utilize uma rede Wi-Fi confiável.
- Mantenha cópias adicionais dos arquivos importantes: um único celular não substitui uma estratégia de backup.

## ⭐ Por que usar este projeto?

Porque você não precisa de equipamentos caros para começar a montar sua própria infraestrutura de armazenamento.

Com um celular antigo, o Termux e o File Browser, você pode construir uma solução prática para compartilhar e gerenciar arquivos na sua rede local.

**Tecnologia, reaproveitamento e autonomia em um único projeto.**

## 🔗 Repositório oficial

https://github.com/daimoncontato7-gif/android-server

Se o projeto foi útil para você, considere deixar uma ⭐ estrela no repositório para apoiar o desenvolvimento.

**Desenvolvido por daimoncontato7**
