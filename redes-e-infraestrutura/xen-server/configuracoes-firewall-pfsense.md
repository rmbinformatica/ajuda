---
description: >-
  Este artigo descreve as configurações adicionais do necessárias para execução de uma VM pfsense virtualizado no xenserver.
---

# Configurações adicionais de interface de rede para firewall pfsense no xenserevr

Vamos obter uma lista dos uuids das vms existentes no servidor.

```bash
xe vm-list
```

O retorno será similar, contendo as seguintes informações:

{% code title="retorno xe vm-list" %}
```text
uuid ( RO) : [uuid-vm]
name-label ( RW): [vm-name]
power-state ( RO): [vm-power]
```
{% endcode %}

Precisaremos das informações retornadas em **uuid-vm** para a vms que vamos configurar a interface de rede.

Obtendo a lista de identificadores uuid da interface de rede da vm:

```bash
xe vif-list vm-uuid=[uuid-vm]
```

Lembre-se de substituir o _uuid-vm_ pela retornado no comando anterior para a respectiva vm.
Script para reconfiguração da placa de rede:

```bash
export VIFUUID="[uuid-da-interface]"


xe vif-param-set uuid=$VIFUUID other-config:ethtool-gso="off"
xe vif-param-set uuid=$VIFUUID other-config:ethtool-ufo="off"
xe vif-param-set uuid=$VIFUUID other-config:ethtool-tso="off"
xe vif-param-set uuid=$VIFUUID other-config:ethtool-sg="off"
xe vif-param-set uuid=$VIFUUID other-config:ethtool-tx="off"
xe vif-param-set uuid=$VIFUUID other-config:ethtool-rx="off"
```

Repita o último comando para todas as demais interfaces de rede da vm.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}