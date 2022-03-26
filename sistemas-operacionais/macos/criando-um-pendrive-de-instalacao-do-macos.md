---
description: >-
  Este artigo descreve o procedimento de criar um pendrive de instalação do
  MacOS
---

# Criando um pendrive de instalação do MacOS

Para realizar uma instalação limpa de um sistema operacional é necessário inicializar o boot com um [pendrive](https://amzn.to/3LzEIEP) de instalação desse sistema operacional, descreverei nesse artigo como criar um pendrive do sistema MacOS a partir do El Capitan.

## Download do instalador

O primeiro passo para criação do [pendrive](https://amzn.to/3LzEIEP), é necessário baixar o instalador do MacOS, isso pode ser feito diretamente usando o app store.

* [MacOs Mojave](https://apps.apple.com/br/app/macos-mojave/id1398502828?mt=12)

## Gravando a instalação no pendrive

Renomeie o [pendrive](https://amzn.to/3LzEIEP) para facilitar a identificação do mesmo, isso pode ser feito no finder. Neste exemplo renomeei o [pendrive](https://amzn.to/3LzEIEP) para **instalador**.

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

## Realizando o boot pelo [pendrive](https://amzn.to/3LzEIEP) de instalação

Reinicie o computador, com o [pendrive](https://amzn.to/3LzEIEP) conectado, e mantenha a tecla _**Option**_ pressionada.

Ao ser perguntado sobre qual o disco que deseja utilizar na inicialização escolha o disco de instalação do MacOS.

[Encontre agora as melhores ofertas de pendrive na amazon](https://amzn.to/3LzEIEP).
