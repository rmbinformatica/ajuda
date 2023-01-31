---
description: >-
  Este artigo descreve o processo para configuração de outra unidade de disco em
  um Xen Server já instalado. Todos os comandos devem ser executados no console.
---

# Adicionando outro Disco Local como novo Storage Repository no Xen Server

Obtenha o UUID do host através do comando, é a sequência de letras e números que aparece após `UUID (RO)`

```bash
xe host-list
```

De posse do número do UUIID do host copiado, vamos executar o comando:

```bash
xe sr-create host-uuid=[uuid_host] content-type=user type=lvmohba device-config:device=[/dev/sdX] shared=false name-label="[nome_repositorio]"
```

_Caso seja exibida uma mensagem de erro,_ pode ser necessário desmontar o Local Storage atual antes de adicionar o novo. Para isso seguimos a mesma lógica dos passos anteriores no sentido de obter o `UUID` do storage e substituir no comando seguinte, execute:

```bash
xe pbd-list
xe pbd-unplug uuid=[uuid_storage]
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}