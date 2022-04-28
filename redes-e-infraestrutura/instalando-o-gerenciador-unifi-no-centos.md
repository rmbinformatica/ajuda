---
description: Instruções para a instalação do gerenciador Ubiquiti Unifi no CentOS
---

# Instalando o gerenciador Unifi no CentOS

Escolha o método de instalação desejado:

{% tabs %}
{% tab title="Automaticamente" %}
## Script de instalação automática

Disponibilizamos um script de configuração automática disponível no github, no URL:

{% embed url="https://github.com/rmbinformatica/configure_unifi_centos6.9" %}

Caso não possua o git instalado, execute:

```bash
yum -y install git
```

Clone o repositório do git:

```bash
git clone https://github.com/rmbinformatica/configure_unifi_centos6.9.git
```

Atribua permissões de execução e execute o instalador:

```bash
chmod +x configure_unifi_centos6.9/*.sh 
configure_unifi_centos6.9/setup.sh 
```
{% endtab %}

{% tab title="Manualmente" %}
É importante que seu sistema esteja com os pacotes atualizados, execute:

```
yum -y update
```

Instale as ferramentas que serão necessárias:

```
yum -y install nano epel-release java-1.8.0-openjdk unzip wget
```

Até agora as versões que tive acesso do gerenciador unifi sempre tinham dificuldade no envio de e-mail, para superar esse problema recomendo a instalação de algum serviço de e-mail nativo do linux, assim você pode utilizar o e-mail interno do próprio servidor para a função de redefinir a senha.

Instale o banco de dados:

```
yum -y install mongodb-server
```

Baixe o pacote .zip do gerenciador, disponível em: [https://dl.ubnt.com/unifi/5.2.9/UniFi.unix.zip](https://dl.ubnt.com/unifi/5.2.9/UniFi.unix.zip)

Crie um usuário para o gerenciador, exemplo: **ubnt**.

Descompacte o arquivo zip em algum diretório, sugestão **/opt**

Atribua as permissões do usuário criado para o diretório desejado.

Crie o diretório **/data/db** e atribua as permissões pro mongod.

Inicie o serviço do mongodb para que seja criado o banco de dados, em seguida encerre o serviço e desative a inicialização automática pois o próprio gerenciador já inicia o serviço.

Crie um serviço para o gerenciador unifi e coloque na inicialização.

Configure o firewall.

Ficou com dúvidas? Veja nosso script de configuração automática disponível em: [https://github.com/rmbinformatica/configure\_unifi\_centos6.9](https://github.com/rmbinformatica/configure\_unifi\_centos6.9)
{% endtab %}

{% tab title="Docker" %}
Outra maneira de realizar a instalação do gerenciador Unifi no CentOS é por meio do docker. Sendo essa nossa recomendação atual.

Primeiro é necessário instalar e habilitar o serviço docker no linux:

```
yum -y install docker
systemctl enable docker.service
```

Para o docker funcionar com usuários sem permissão de root é necessário a criação do grupo docker e de um usuário que será incluído nesse grupo. Neste exemplo nosso usuário será **dckrmgr**:

```
groupadd docker
useradd dckrmgr
usermod -aG docker dckrmgr
```

Uma vez instalado e configurado o grupo docker, basta iniciar o serviço:

```
systemctl start docker.service
```

Em seguida vamos criar dois diretórios para a persistência dos dados do unifi:

```
mkdir -p unifi/data
mkdir -p unifi/log
```

Testamos e gostamos do container [jacobalberty/unifi](https://hub.docker.com/r/jacobalberty/unifi), sendo nossa recomendação atual para uso. Iniciando o container em modo daemon:

```
docker run --rm -d -p 8080:8080 -p 8443:8443 -p 3478:3478/udp -p 10001:10001/udp -e TZ='America/Recife' -v ~/unifi:/unifi --name unifi jacobalberty/unifi:stable
```

Feito isso basta acessar o unifi controller através do ip da máquina docker, usando https na porta 8443, exemplo:&#x20;

&#x20;**https://\[ip-docker]:8443**

Em caso de dúvidas basta contratar nosso suporte.
{% endtab %}
{% endtabs %}
