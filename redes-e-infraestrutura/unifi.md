---
description: Informações sobre configuração e gerenciamento de access points Unifi
---

# UniFi

Os access points Unifi podem ser acessados via SSH mediante autenticação de usuário e senha, as credenciais de acesso podem ser obtidas no unifi controller em Settings - Site, dentro da seção Device Authentication. Uma vez estabelecida uma conexão SSH, você pode no próprio dispositivo:

## Realizar upgrade de firmware do unifi usando ssh

Neste caso [encontre o link do arquivo do firmware atualizado conforme o modelo do seu dispositivo,](https://www.ui.com/download/unifi/unifi-ap) de posse do URL realize:

```text
upgrade [url]
```

É comum a ocorrência de erros de validaço de certificado, prefira realizar o download utilizando http em vez de https.

Outra maneira de realizar a atualização de firmware é seguindo as instruções disponíveis na página [UniFi - Changing the Firmware of a UniFi Device](https://help.ubnt.com/hc/en-us/articles/204910064-UniFi-Upgrading-firmware-image-via-SSH).

## Visualizar a configuração atual do unifi usando ssh

```text
info
```

## Alterar o endereço do controller unifi usando ssh

```text
set-inform http://[ip-do-controller]:8080/inform
```





