---
title: Docker comandos
author: "Renato Monteiro Batista"
date: 2023-06-17
category: [redes-e-infraestrutura, docker]
layout: post
revisao: 2023-11-19
keywords: docker, comandos, guia rápido
description: Guia de referência de comandos do docker
---

## Executando o Hello World

```bash
docker run hello-world
```

Incluir a mensagem que é retornada pelo hello-world.

## Trabalhando com imagens

A imagem é como se fosse um script contendo todas as instruções para criação de um container. A imagem é automaticamente baixada do docker hub/docker store como se fosse um git.

### Listando imagens baixadas

```bash
docker image ls
```

### Removendo imagens

```bash
docker rmi <nomeDaImagem>
```
ou
```bash
docker image rm <idDaImagem>
```

### Baixando uma imagem

```bash
docker pull <nomeDaImagem>
```

## Imagens oficiais

As imagens oficiais geralmente não precedem do nome de um usuário. Exemplo `ubuntu` `node` `centos`, etc.
Já as imagens criadas pelos usuários precedem do *nomeDoUsuario\nomeDaImagem*, exemplo `renatomb/exemplo`.

{% include gads.html %}

## Executando containers

Cada vez que for executado o comando `docker run` será criado um novo container baseado na imagem e será executado.

### Mostrando os containers em execução

Será mostrada uma tabela contendo todos os containers que estão atualmente em execução.

```bash
docker ps
```

#### Mostrando todos os containers que já foram criados

Serão mostrados todos os containers criados, mesmo os que já pararam a execução

```bash
docker ps -a
```

### Mostrando somente os IDs dos containers em execução

```bash
docker ps -q
```

### Trabalhando com um terminal interativo

Nesse caso, basta acrescentar a flag *-it* que será iniciado o terminal dentro daquele container

```bash
docker run -it ubuntu
```

### Executar um container em segundo plano sem bloquear o terminal

```bash
docker run -d <nomeDaImagem>
```

### Definindo um working directory

```bash
docker run -w <workingDir>
```

### Executar um comando ao iniciar um container

```bash
docker run <imagem> <comando>
```

### Iniciando um contaier

```bash
docker start <id>
```

Os *id* podem ser vistos através do `docker ps`

### Passando alguma variável de ambiente para o container

Nesse caso usamos o parâmetro *-e VARIAVEL="Conteudo"*
Ex.:
```bash
docker run -e AUTOR="Fulano" <imagem>
```

### Parando um container

```bash
docker stop <id>
```

O docker stop aguarda alguns segundos antes de finalizar o container, isso pode ser evitado fazendo acrescentando a flag *-t* tempo.

```bash
docker stop -t 0 <id>
```

#### Parando todos os containers em execução

```bash
docker stop -t 0 $(docker ps -q)
```

### Reconectando com um container ativo

```bash
docker start -a -i <id>
```

## Removendo um container

```bash
docker rm <id>
```

Para remover um container forçando a parada caso esteja em execução, basta incluir a flag *-f*.

```bash
docker rm -f <id>
```

### Remover todos os containers inativos

```bash
docker container prune
```

### Atribuindo um nome amigável a um container

Para isso basta usar o parâmetro *--name* nome. Nesse caso pode passar a se referenciar ao container pelo *nome*>* em vez do *id*.

```bash
docker run -d --name <nome> <imagem>
```

### Inspecionando detalhes de um container

```bash
docker inspect <id>
```

{% include gads.html %}

## Layered Filesystem

Toda imagem docker é dividida em camadas. Com isso algumas camadas podem ser compartilhadas entre diferentes imagens.

Todas as camadas das imagens são somente para leitura. Quando criamos um container ele cria uma camada acima delas que é de escrita e leitura.

## Background e com Mapeamento de portas

```bash
docker run -d -P <imagem>
```

A flag *-P* faz com que o docker mapeie portas aleatórias da máquina para as portas necessárias do container.

*NOTA: Se estiver usando a docker toolbox que cria uma máquina virtualbox, para identificar o ip da máquina virtual execute:*

```bash
docker-machine ip
```

### Listando portas mapeadas em um container

```bash
docker port <id>
```

### Especificando as portas que deseja mapear

Para especificar as portas que se deseja mapear usamos o parâmetro *-p portaLocal:portaContainer*

```bash
docker run -d -p 12345:80 <imagem>
```

Nesse caso a porta 80 do container estará disponível para acesso através da porta 12345 da máquina local.

## Persistência de dados e armazenamento local

Os containers, assim como seus dados, são voláteis. De modo que sempre que forem removidos todos os dados serão removidos também.

Para persistir os dados é necessário armazená-los no Docker host, sendo necessário mapear um path local dentro de um path do container.

Para fazer isso usamos o parâmetro *-v "pathLocal:pathRemoto"*

```bash
docker run -v "<pathLocal>:<pathRemoto>" <imagem>
```

NOTA: *Se não for especificado o caminho local, o docker irá atribuir um caminho. Para visualizar o caminho atribuído verificar com o `docker inspect`.*

{% include gads.html %}

## Construindo imagens

Para criar uma imagem, é necessário criar um arquivo chamado *Dockerfile*. Quando for necessário construir várias imagens, é necessário usar *nomeDaImagem.Dockerfile*.

### Estrutura do Dockerfile

#### FROM

Especifica a imagem de base. Padrão *imagem:versao*.

#### MAINTAINER

Nome do autor.

#### COPY

Copiar o que for indicado para dentro daquela imagem. Para copiar todos os arquivos pode-se usar o parâmetro **.**
Ex.:
```text
COPY . /var/www
```

#### RUN

Comando que será executado quando a imagem estiver sendo construída.

#### ENTRYPOINT

Comando que será executado assim que carregar o container.

#### EXPOSE

Porta que será exposta pelo container.

#### WORKDIR

Assim que o container for carregado, ele vai iniciar no path especificado.

#### ENV

Definição de variáveis de ambiente. Padrão bash: *VARIAVEL=Valor*.

NOTA: *É possível referenciar uma variável de ambiente em outras partes do Dockerfile, bastando para isso inclui-la no formato $VARIAVEL*

### Construindo a imagem a partir do Dockerfile

```bash
docker build -f <arquivo.Dockerfile> -t <usuarioDockerHub>\<nomeDoProjeto>
```

Se não for especificado o parâmetro -f será considerado o nome de arquivo padrão *Dockerfile*.

### Subindo a imagem pro DockerHub

Antes de ser enviar a imagem para o DockerHub, é necessário fazer o login com as credenciais previamente registradas no site.

```bash
docker login
```

Para enviar uma imagem, basta executar:

```bash
docker push <usuarioDockerHub>\<nomeDoProjeto>
```

{% include gads.html %}

## Comunicação entre containers

Por padrão o docker cria uma rede virtual  *Default* onde todos os containers estão conectados.
Mas para eles se comunicarem seria necessário saber qual o endereço IP que cada container está sendo executado.
Em containers linux é possível saber o ip atual através do comando `hostname -i`.

Porém é importante ressaltar que toda vez  subir um novo container será atribuído um novo ip gerenciado pelo docker. Mas a rede *Default* não permite que sejam atribuídos hostnames aos containers. Nesse caso é necessário criar uma rede virtual dentro do docker.

### Criando uma rede

```bash
docker network create --driver bridge <nomeDaRede>
```

### Listar todas as redes criadas

```bash
docker network ls
```

### Atribuindo um container numa rede

Ao executar um container com o run, incluir o parâmetro *--network nomeDaRede*.

Ex.:

```bash
docker run -it --name centinho --network redevirtual centos
```

Onde o nome da instância do container seria *centinho*, o nome da rede virtual onde ele se conectará será *redevirtual* e a imagem será *centos*.

{% include gads.html %}

## Transferindo containers entre máquinas distintas

### Salvando a imagem de um container num arquivo .tar

```bash
docker save -o <caminhoArquivoTar> <nomeDaImagem>
```

### Importando a imagem salva de um arquivo .tar

```bash
docker load -i <caminhoArquivoTar>
```

## Forçando o composer a usar uma imagem local

Em alguns cenários, como indisponibilidade de internet, pode ser necessário instruir o composer a usar uma imagem existente localmente.

Nesse caso basta utilizar como `image` no arquivo `docker-compose.yml` o nome de uma imagem que seja equivalente a alguma tag existente.

### Criando uma tag a partir de uma imagem existente

```bash
docker tag <idDaImagem> <nomeLocal>
```

## Veja também

* [Repositório de docker-compose criado por Renato Monteiro Batista no GitHub](https://github.com/renatomb/compose)