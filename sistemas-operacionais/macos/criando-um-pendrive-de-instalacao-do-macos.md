---
description: >-
  Este artigo descreve o procedimento de criar um pendrive de instalação do
  MacOS
---

# Criando um pendrive de instalação do macOS

Para realizar uma instalação limpa de um sistema operacional é necessário inicializar o boot com um pendrive de instalação desse sistema operacional, descreverei nesse artigo como criar um pendrive do sistema macOS a partir do El Capitan.

## Download do instalador

O primeiro passo para criação do pendrive, é necessário baixar o instalador do MacOS, isso pode ser feito diretamente usando o app store.

* [macOs Big Sur 11](macappstores://apps.apple.com/br/app/macos-big-sur/id1526878132?mt=12)
* [macOs Catalina 10.15](macappstores://apps.apple.com/br/app/macos-catalina/id1466841314?mt=12)
* [macOs Mojave 10.14](macappstores://apps.apple.com/br/app/macos-mojave/id1398502828?mt=12)
* [macOs High Sierra 10.13](macappstores://apps.apple.com/br/app/macos-high-sierra/id1246284741?mt=12)

### Versões mais antigas

Nas versões mais antigas esse método de criação do pendrive não é compatível, sendo necessário montar o disco `InstallOS.dmg` ou `InstallMacOSX.dmg`. Monte/abra a imagem de disco. Depois, abra o instalador `.pkg` dentro da imagem do disco, são elas:

* [macOS Sierra 10.12](http://updates-http.cdn-apple.com/2019/cert/061-39476-20191023-48f365f4-0015-4c41-9f44-39d3d2aca067/InstallOS.dmg) (SHA1: 9ba989d30e3548341fc8f5847e856709cb5c67c2)
* [OS X El Capitan 10.11](http://updates-http.cdn-apple.com/2019/cert/061-41424-20191024-218af9ec-cf50-4516-9011-228c78eda3d2/InstallMacOSX.dmg) (SHA1: 21e45136e34c6f805e0f1977e38d6ff029a9a1e2)
* [OS X Yosemite 10.10](http://updates-http.cdn-apple.com/2019/cert/061-41343-20191023-02465f92-3ab5-4c92-bfe2-b725447a070d/InstallMacOSX.dmg) (SHA1: c542681961cc7fafb9c15bfd4af152a3a57f07fa)

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
