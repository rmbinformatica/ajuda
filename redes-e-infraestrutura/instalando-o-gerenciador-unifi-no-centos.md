---
description: Instruções para a instalação do gerenciador Ubiquiti Unifi no CentOS
---

# Instalando o gerenciador Unifi no CentOS

Escolha o método de instalação desejado:

{% tabs %}
{% tab title="Automaticamente" %}
## Script de instalação automática

Disponibilizamos um script de configuração automática disponível no github, no URL:

{% embed url="https://github.com/rmbinformatica/configure\_unifi\_centos6.9" %}

Caso não possua o git instalado, execute:

```text
yum -y install git
```

Clone o repositório do git:

```text
git clone https://github.com/rmbinformatica/configure_unifi_centos6.9.git
```

Atribua permissões de execução e execute o instalador:

```text
chmod +x configure_unifi_centos6.9/*.sh 
configure_unifi_centos6.9/setup.sh 
```
{% endtab %}

{% tab title="Manualmente" %}
É importante que seu sistema esteja com os pacotes atualizados, execute:

```text
yum -y update
```

Instale as ferramentas que serão necessárias:

```text
yum -y install nano epel-release java-1.8.0-openjdk unzip wget
```

Até agora as versões que tive acesso do gerenciador unifi sempre tinham dificuldade no envio de e-mail, para superar esse problema recomendo a instalação de algum serviço de e-mail nativo do linux, assim você pode utilizar o e-mail interno do próprio servidor para a função de redefinir a senha.

Instale o banco de dados:

```text
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

Ficou com dúvidas? Veja nosso script de configuração automática disponível em: [https://github.com/rmbinformatica/configure\_unifi\_centos6.9](https://github.com/rmbinformatica/configure_unifi_centos6.9)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Elaborado por [Renato Monteiro Batista](http://renatomonteiro.tk) para o [manual de instruções técnicas](https://doc.rmbinformatica.com.br/ajuda) da [RMB Informática](http://rmbinformatica.com).
{% endhint %}

