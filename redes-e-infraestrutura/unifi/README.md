---
description: Informações sobre configuração e gerenciamento de access points Unifi
---

# UniFi

Os access points Ubiquiti Unifi podem ser acessados via SSH mediante autenticação de usuário e senha, as credenciais de acesso podem ser obtidas no unifi controller em Settings - Site, dentro da seção Device Authentication. Uma vez estabelecida uma conexão SSH, você pode no próprio dispositivo:

## Realizar upgrade de firmware do unifi usando ssh

Neste caso [encontre o link do arquivo do firmware atualizado conforme o modelo do seu dispositivo,](https://www.ui.com/download/unifi/unifi-ap) de posse do URL realize:

```
upgrade [url]
```

É comum a ocorrência de erros de validaço de certificado, prefira realizar o download utilizando http em vez de https.

Outra maneira de realizar a atualização de firmware é seguindo as instruções disponíveis na página [UniFi - Changing the Firmware of a UniFi Device](https://help.ubnt.com/hc/en-us/articles/204910064-UniFi-Upgrading-firmware-image-via-SSH).

## Visualizar a configuração atual do unifi usando ssh

```
info
```

## Alterar o endereço do controller unifi usando ssh

```
set-inform http://[ip-do-controller]:8080/inform
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}