---
description: >-
  Este artigo descreve um conjunto de comandos úteis para utilização no terminal
  do mac. Alguns comandos descritos podem servir também para sistemas linux.
---

# Comandos úteis no terminal

## Mostrar a tabela de rotas do Mac OS

No linux seria equivalente ao resultado do comando `route -n`

```bash
netstat -rn
```

## Adicionando uma rota manualmente no Mac OS

```bash
sudo route -n add -net [rede_destino/CIDR] [gateway]
```

## Alterar o hostname da máquina

```bash
sudo scutil --set HostName [novo_nome]
```

## Verificar o hash MD5 ou SHA de um arquivo

```bash
md5 [nome_arquivo]
shasum [nome_arquivo]
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}