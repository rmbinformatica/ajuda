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

```
xe vm-param-set uuid=[uuid-vm] other-config:auto_poweron=true
```

Lembre-se de substituir o _uuid-vm_ pela retornado no comando anterior para a respectiva vm.

Repita o último comando para todas as demais vms que deseja que sejam inicializadas automaticamente.
