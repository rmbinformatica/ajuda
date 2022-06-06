---
description: >-
  Este artigo descreve o procedimento de criar um pendrive de instalação do
  MacOS
---

# Criando um pendrive de instalação do macOS

Para realizar uma instalação limpa de um sistema operacional é necessário inicializar o boot com um pendrive de instalação desse sistema operacional, descreverei nesse artigo como criar um pendrive do sistema macOS a partir do El Capitan.

## Download do instalador

O primeiro passo para criação do pendrive, é necessário baixar o instalador do MacOS, isso pode ser feito diretamente usando o app store.

* [macOs High Sierra](macappstores://apps.apple.com/br/app/macos-high-sierra/id1246284741?mt=12)
* [macOs Mojave](macappstores://apps.apple.com/br/app/macos-mojave/id1398502828?mt=12)
* [macOs Catalina](macappstores://apps.apple.com/br/app/macos-catalina/id1466841314?mt=12)
* [macOs Big Sur](macappstores://apps.apple.com/br/app/macos-big-sur/id1526878132?mt=12)

### Versões mais antigas

Nas versões mais antigas esse método de criação do pendrive não é compatível, sendo necessário montar o disco `InstallOS.dmg` ou `InstallMacOSX.dmg`. Monte/abra a imagem de disco. Depois, abra o instalador `.pkg` dentro da imagem do disco, são elas:

* [macOS Sierra](http://updates-http.cdn-apple.com/2019/cert/061-39476-20191023-48f365f4-0015-4c41-9f44-39d3d2aca067/InstallOS.dmg)
* [OS X El Capitan](http://updates-http.cdn-apple.com/2019/cert/061-41424-20191024-218af9ec-cf50-4516-9011-228c78eda3d2/InstallMacOSX.dmg)
* [OS X Yosemite](http://updates-http.cdn-apple.com/2019/cert/061-41343-20191023-02465f92-3ab5-4c92-bfe2-b725447a070d/InstallMacOSX.dmg)

## Gravando a instalação no pendrive

Renomeie o pendrive para facilitar a identificação do mesmo, isso pode ser feito no finder. Neste exemplo renomeei o pendrive para **instalador**.

Em seguida execute o **createinstallmedia** que fica dentro de _Contents_/_Resources_ do instalador. Execute via terminal:

```bash
sudo /Applications/Install\ OS\ X\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/instalador --applicationpath /Applications/Install\ OS\ X\ Mojave.app --nointeraction
```

Para facilitar a localização do instalador digite o caminho _/Applications/Install_ e pressione a tecla _\[TAB]_ que o terminal completará o nome do caminho do instalador. Lembre de substituir o **/Volumes/instalador** pelo nome que você usou ao renomear o pendrive.

Informe a senha de administrador da máquina, se for solicitado.

Aguarde a conclusão do processo

```
Erasing Disk: 0%… 10%… 20%… 30%…100%…
Copying installer files to disk…
Copy complete.
Making disk bootable…
Copying boot files…
Copy complete.
Done.
```

## Realizando o boot pelo pendrive de instalação

Reinicie o computador, com o pendrive conectado, e mantenha a tecla _**Option**_ pressionada.

Ao ser perguntado sobre qual o disco que deseja utilizar na inicialização escolha o disco de instalação do MacOS.

[Verifique os requisitos de hardware para instalação do macOS](requisitos-de-hardware-para-instalacao-do-macos.md).
