---
description: >-
  Esse artigo descreve a solução para o problema de compatibilidade de conexão
  SSH com servidores que só suportam o algoritmo ssh-dss.
---

# Como se conectar a um servidor SSH utilizando o algoritmo ssh-dss

## Descrição do problema

Em alguns servidores e storages antigos ao tentar se conectar com o servidor ssh é apresentada a mensagem de erro:

**`Unable to negotiate with xxx.xxx.xxx.xxx port 22: no matching host key type found. Their offer: ssh-dss`**

Isso é causado pois o cliente de ssh está utilizando um algoritmo que não é compatível com o oferecido pelo servidor

## Solução

Para resolver esse problema é necessário configurar o cliente ssh para se conectar utilizando o algoritmo ssh-dss, para fazer isso basta utilizar o comando a seguir:

```bash
ssh -oHostKeyAlgorithms=+ssh-dss [usuario]@[servidor]
```

Substituindo _\[usuario]_ pelo respectivo login e _\[servidor]_ pelo endereço do host do servidor.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}