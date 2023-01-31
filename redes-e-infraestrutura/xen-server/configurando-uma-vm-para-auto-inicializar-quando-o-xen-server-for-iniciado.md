---
description: >-
  Este artigo descreve o procedimento para fazer uma VM iniciar automaticamente
  quando o XEN for iniciado.
---

# Configurando uma VM para auto-inicializar quando o XEN server for iniciado

Conecte no XEN usando o ssh ou vá para o console do servidor através do xencenter.

Obtenha uma lista de pool existentes no servidor:

```bash
xe pool-list
```

Será retornada uma lista de pool conforme o exemplo:

{% code title="resultado do xe pool-list" %}
```
uuid ( RO) : [uuid-pool]
name-label ( RW): [pool-name]
name-description ( RW): [pool-desc]
master ( RO): [uuid-xs]
default-SR ( RW): [uuid-sr]
```
{% endcode %}

Precisaremos da informação retornada em **uuid-pool**, agora vamos configurar esse pool para ligar automaticamente na inicialização:

```bash
xe pool-param-set uuid=[uuid-pool] other-config:auto_poweron=true
```

Lembre-se de substituir o _uuid-pool_ pelo que foi retornado no primeiro comando.

Agora vamos obter uma lista dos uuids das vms existentes no servidor.

```bash
xe vm-list
```

O retorno será similar, contendo as seguintes informações:

{% code title="retorno xe vm-list" %}
```
uuid ( RO) : [uuid-vm]
name-label ( RW): [vm-name]
power-state ( RO): [vm-power]
```
{% endcode %}

Precisaremos das informações retornadas em **uuid-vm** para todas as vms que vamos configurar para auto-inicializar. Substitua a informação no comando abaixo:

```bash
xe vm-param-set uuid=[uuid-vm] other-config:auto_poweron=true
```

Lembre-se de substituir o _uuid-vm_ pela retornado no comando anterior para a respectiva vm.

Repita o último comando para todas as demais vms que deseja que sejam inicializadas automaticamente.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}