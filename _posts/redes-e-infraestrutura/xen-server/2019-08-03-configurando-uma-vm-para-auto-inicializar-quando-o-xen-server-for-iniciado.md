---
title: Configurando uma VM para auto-inicializar quando o XEN server for iniciado
author: "Renato Monteiro Batista"
date: 2019-08-03
category: [redes-e-infraestrutura, xen-server]
layout: post
revisao: 2023-11-19
keywords: xen, xen server, vm, virtual machine, auto inicializar, auto poweron
description: >-
  Este artigo descreve o procedimento para fazer uma VM iniciar automaticamente
  quando o XEN for iniciado.
---

Conecte no XEN usando o ssh ou vá para o console do servidor através do xencenter.

Obtenha uma lista de pool existentes no servidor:

```bash
xe pool-list
```

Será retornada uma lista de pool conforme o exemplo:

```text
uuid ( RO) : [uuid-pool]
name-label ( RW): [pool-name]
name-description ( RW): [pool-desc]
master ( RO): [uuid-xs]
default-SR ( RW): [uuid-sr]
```

Precisaremos da informação retornada em **uuid-pool**, agora vamos configurar esse pool para ligar automaticamente na inicialização:

```bash
xe pool-param-set uuid=[uuid-pool] other-config:auto_poweron=true
```

Lembre-se de substituir o **uuid-pool** pelo que foi retornado no primeiro comando.

Agora vamos obter uma lista dos uuids das vms existentes no servidor.

```bash
xe vm-list
```

O retorno será similar, contendo as seguintes informações:

```text
uuid ( RO) : [uuid-vm]
name-label ( RW): [vm-name]
power-state ( RO): [vm-power]
```

Precisaremos das informações retornadas em **uuid-vm** para todas as vms que vamos configurar para auto-inicializar. Substitua a informação no comando abaixo:

```bash
xe vm-param-set uuid=[uuid-vm] other-config:auto_poweron=true
```

Lembre-se de substituir o **uuid-vm** pela retornado no comando anterior para a respectiva vm.

Repita o último comando para todas as demais vms que deseja que sejam inicializadas automaticamente.
