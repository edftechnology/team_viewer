# Como configurar/instalar o `TeamViewer` no `Linux Ubuntu`

## Resumo

Neste documento estão contidos os principais comandos e configurações para configurar/instalar/usar o `TeamViewer` no `Linux Ubuntu`.

## _Abstract_

_This document contains the main commands and settings to configure/install/use the `TeamViewer` in `Linux Ubuntu`._

## Descrição [2]

`TeamViewer`

O `TeamViewer` é uma popular solução de _software_ de acesso remoto e reuniões online que permite que os usuários acessem computadores e dispositivos remotamente a partir de qualquer lugar do mundo. Ele é amplamente utilizado por indivíduos, empresas e equipes de suporte técnico para fornecer assistência remota, solucionar problemas de computador, realizar apresentações e reuniões virtuais, e colaborar em tempo real. O `TeamViewer` oferece recursos de controle remoto, transferência de arquivos, compartilhamento de tela, bate-papo e videoconferência, tornando-o uma ferramenta versátil para comunicação e colaboração à distância. É compatível com uma variedade de plataformas, incluindo `Windows`, `macOS`, `Linux`, `Android` e `iOS`, e é conhecido por sua segurança e criptografia robusta para proteger as sessões de acesso remoto. O `TeamViewer` é uma escolha popular para aqueles que precisam de uma solução confiável e eficiente para trabalhar e colaborar remotamente.

## 1. Configurar/Instalar/Usar para `Team Viewer` no `Linux Ubuntu` [1]

Para configurar/instalar/usar o `Terminal Linux` do `Linux Ubuntu` siga os passos abaixo:

Vou mostrar como fazer isso para o bash, mas o processo é similar para outros shells.

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```


2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:
    ```bash
    sudo apt clean
    ```
    
    2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:
    ```bash
    sudo apt autoclean
    ```

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:
    ```bash
    sudo apt autoremove -y
    ```

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt update
    ```

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:
    ```bash
    sudo apt --fix-broken install
    ```

    2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:
    ```bash
    sudo apt clean
    ```
    
    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt list --upgradable
    ```

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:
    ```bash
    sudo apt full-upgrade -y
    ```
    

Para configurar/instalar/usar o `TeamViewer` no `Linux Ubuntu` pelo `Terminal Emulator`, siga estas etapas:

1. **Baixe o pacote `DEB` do `TeamViewer`:** Primeiro, você precisa baixar o pacote de instalação do `TeamViewer`. O `TeamViewer` oferece um pacote `DEB` que é compatível com sistemas baseados em `Debian`, como o `Ubuntu`. Você pode baixar o pacote usando o comando `wget`. Abra o `Terminal Emulator` e digite:

    ```bash
    wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb
    ```

2. **Instale o pacote `DEB`:** Após o _download_ do pacote `.deb`, você pode instalá-lo usando o comando `dpkg`. Se ocorrerem problemas de dependência, você pode resolvê-los com o apt. Execute: 

    ```bash
    sudo dpkg -i teamviewer_amd64.deb
    sudo apt install -f
    ```
    
    O comando `dpkg -i` instala o pacote, e o `apt install -f` corrige quaisquer problemas de dependência.

3. **Abra o `TeamViewer`:** Depois que a instalação for concluída, você pode iniciar o `TeamViewer`
através do `Terminal Emulator` ou encontrar o aplicativo no menu de programas.

    Para iniciar pelo `Terminal Emulator`, digite:
    
    ```bash
    teamviewer
    ```

Assegure-se de que está baixando o pacote `TeamViewer` do site oficial para evitar questões de 
segurança. O processo de instalação no `Linux Ubuntu` é bastante direto, mas é sempre importante
garantir que o sistema esteja atualizado antes de instalar novos _softwares_.


### 1.2 Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `TeamViewer` no `Linux Ubuntu` sem precisar digitar linha por
linha, você pode seguir estas etapas:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digite o seguinte comando e pressione `Enter`:

    ```bash
    sudo apt clean
    sudo apt autoclean
    sudo apt autoremove -y
    sudo apt update
    sudo apt --fix-broken install
    sudo apt clean
    sudo apt list --upgradable
    sudo apt full-upgrade -y
    wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb
    sudo dpkg -i teamviewer_amd64.deb
    sudo apt install -f
    teamviewer
    ```

### 1.3 Configurar o Acesso Fácil (Easy Access) e o acesso não supervisionado

O `TeamViewer Classic` suporta **Acesso Fácil (Easy Access)**. Para utilizar esse recurso,
vincule o computador remoto à sua conta e habilite o acesso não supervisionado.

1. **Confirme a versão no computador que será controlado:** Abra o terminal e execute:

    ```bash
    teamviewer --version
    ```

2. **Inicie a configuração de atribuição à sua conta:** Execute o comando abaixo e siga
   as instruções apresentadas:

    ```bash
    sudo teamviewer setup
    ```

3. **Abra o TeamViewer:**

    ```bash
    teamviewer
    ```

4. **Vincule o computador e conceda acesso fácil:** No `TeamViewer`, entre com sua conta
   **Eden Denis** e procure por **Extras → Opções → Segurança** ou, dependendo da versão,
   **Extras → Opções → Geral → Atribuição de conta**. Procure opções como **Atribuir à conta**,
   **Conceder acesso fácil** ou **Grant Easy Access**. Conclua a atribuição à conta e
   ative o acesso fácil.

5. **Conecte-se pelo outro computador:** Entre com a mesma conta e abra
   **Computadores e contatos**. O computador configurado deverá aparecer na lista.
   Com ele ligado, conectado à internet e com o `TeamViewer` em execução, selecione-o
   e clique em **Controle remoto**. Assim, você poderá acessar o computador sem informar
   manualmente o ID `886 771 968` e a senha temporária exibidos no computador remoto.


## 2. Desinstalar o `TeamViewer` do `Linux Ubuntu`

Para desinstalar o `TeamViewer` do `Linux Ubuntu` pelo `Terminal Emulator`, siga estas etapas:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. **Remova o `TeamViewer`**: Use o comando `apt-get` remove para desinstalar o `TeamViewer`. Digite o seguinte comando e pressione Enter:

    ```bash
    sudo apt remove teamviewer -y
    ```

3. **Remova os pacotes não utilizados**: Após a desinstalação, é uma boa prática limpar os pacotes não utilizados que podem ter sido instalados como dependências do `TeamViewer`. Execute o seguinte comando:

    ```bash
    sudo apt autoremove
    ```

4. **Remova arquivos de configuração (opcional)**: Se você quiser remover completamente todos os arquivos de configuração do `TeamViewer`, use o comando `purge`:
    
    ```bash
    sudo apt purge teamviewer -y
    ```

5. **Atualize a lista de pacotes**: Por fim, é uma boa prática atualizar a lista de pacotes para garantir que o sistema esteja em um estado atualizado:
    
    ```bash
    sudo apt update
    ```

Seguindo esses passos, você terá desinstalado o TeamViewer do seu sistema `Linux Ubuntu`.

## Referências

[1] OPENAI.
**Instalar o `teamviewer` no `linux ubuntu` pelo `terminal emulator`.***
Disponível em: <https://chat.openai.com/c/9a96cf1c-939c-494a-a9ed-918fe64f2380> (texto adaptado).
ChatGPT.
Acessado em: 13/12/2023 07:56.

[2] OPENAI.
**Vs code: editor popular.**
Disponível em: <https://chat.openai.com/c/b640a25d-f8e3-4922-8a3b-ed74a2657e42> (texto adaptado).
ChatGPT.
cdAcessado em: 13/12/2023 07:56.

