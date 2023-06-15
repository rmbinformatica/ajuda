---
description: Solução para carregar a imagem de containers dockers através de mídia offline, sem acesso à conexão de internet.
---

# Usando containers Docker sem internet com docker load e docker save

Neste post vamos abordar a utilização containers Docker em um ambiente sem acesso à internet, usando os comandos docker load e docker save. Esses comandos permitem exportar e importar imagens Docker como arquivos tar, que podem ser transferidos por meio de dispositivos de armazenamento externos, como pendrives.

## Salvando imagens de containers docker com o comando docker save

Primeiramente será necessário exportar a imagem Docker que você quer usar, em um computador onde você precisa ter a imagem em seu repositório local. Ou seja: num computador onde a imagem já foi baixada através da internet ou no computador onde a imagem foi construída a partir do Dockerfile.

O primeiro passo é exportar a imagem Docker que você quer usar em um arquivo tar. Por exemplo, se você quiser exportar a imagem ubuntu:20.04, você pode usar o seguinte comando:

```bash
docker save -o ubuntu.tar ubuntu:20.04
```

Isso vai criar um arquivo chamado `ubuntu.tar` no diretório atual, contendo a imagem `ubuntu:20.04` e todas as suas camadas. Você pode verificar o tamanho do arquivo com o comando ls -lh ubuntu.tar. Dependendo da imagem, o arquivo pode ser bastante grande, então certifique-se de ter espaço suficiente no dispositivo de armazenamento que você vai usar para transferi-lo.

### Comprimindo um arquivo .tar com o gzip usando compressão máxima

Caso a imagem seja muito grande, há também a opção de comprimir com o gzip utilizando a compressão máxima e sem perda de dados do arquivo, para isso utilize o comando a seguir:

```bash
gzip -9 ubuntu.tar
```

Será gerado o arquivo `ubuntu.tar.gz` que ocupará bem menos espaço em disco do que o arquivo original.

### Descompactando uma arquivo gzip

Para descompactar o arquivo gzip no computador de destino onde a imagem será carregada basta executar o comando:

```bash
gunzip ubuntu.tar.gz
```

## Importando a imagem de um container docker salva em disco com o docker load

O passo seguinte é transferir o arquivo contemdo a imagem salva para o computador de destino. Caso a imagem tenha sido comprimida, lembre de realizar a descompressão utilizando o `gunzip`.

De posse do arquivo original da imagem em formato `.tar` você pode importar a imagem Docker do arquivo tar para o repositório local do ambiente sem internet. Para fazê-lo vamos utilizar o comando docker load:

```bash
docker load -i /media/pendrive/ubuntu.tar
```

Isso vai carregar a imagem ubuntu:20.04 e todas as suas camadas para o repositório local do ambiente sem internet.

### Listando as imagens instaladas no repositório local do docker

Você pode verificar se a imagem foi importada com sucesso com o comando docker image. Para isso execute:

```bash
docker image ls
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}