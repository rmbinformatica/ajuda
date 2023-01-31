---
description: Comandos e dicas para configuração de servidores CentOS
---

# CentOS Linux

## Alterando o timezone do CentOS 7 para o horário brasileiro

```bash
timedatectl set-timezone America/Recife
```

No exemplo acima definimos o timezone para Recife, para obter uma lista das outras cidades disponíveis na américa execute o comando `timedatectl list-timezones | grep America` e escolha o mais adequado à sua cidade.

## Corrigindo a URL de download dos pacotes do CentOS

Em virtude da mudança do CentOS para a versão Stream, as versões anteriores não estão conseguindo realizar download de pacotes apresentando a mensagem de erro abaixo:

> Erro: Failed to download metadata for repo 'AppStream': Cannot prepare internal mirrorlist: No URLs in mirrorlist.

Uma solução para a correção desse problema é atualizar a lista de url dos repositórios para o arquivo (vault) do CentOS, mas antes de prosseguir vamos realizar um backup da lista atual:

```bash
tar -cf old_CentOS_repos.tar /etc/yum.repos.d/*.repo
gzip -9 old_CentOS_repos.tar
```

Feito o backup vamos atualizar as URLs dos repositórios para o vault:

```bash
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
```

### Migrando o CentOS para o CentOS Stream

{% hint style="info" %}
Antes de prosseguir com a migração é recomendado que realize o backup de tudo que for importante no servidor (dados, arquivos de configuração, etc).
{% endhint %}

Caso deseje migrara o seu CentOS para a versão Stream, utilize o script abaixo:

```bash
dnf install centos-release-stream
dnf swap centos-{linux,stream}-repos
dnf distro-sync
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}