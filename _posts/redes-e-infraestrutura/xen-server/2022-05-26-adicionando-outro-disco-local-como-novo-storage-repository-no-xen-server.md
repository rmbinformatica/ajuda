---
title: Adicionando outro Disco Local como novo Storage Repository no Xen Server
author: "Renato Monteiro Batista"
date: 2022-05-26
category: [redes-e-infraestrutura, xen-server]
layout: post
revisao: 2023-11-19
keywords: xen, xen server, vm, virtual machine, storage, disco, local, lvm, lvmohba, configuração, config, xenserver
description: Este artigo descreve o processo para configuração de outra unidade de disco em um Xen Server já instalado. Todos os comandos devem ser executados no console.
---

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