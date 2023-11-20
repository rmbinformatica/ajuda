---
title: Configurações adicionais de interface de rede para Firewall PfSense no XenSerevr
author: "Renato Monteiro Batista"
date: 2020-03-18
category: [redes-e-infraestrutura, xen-server]
layout: post
revisao: 2023-11-19
keywords: xen, xen server, vm, virtual machine, pfsense, firewall, interface, rede, network, configuração, config, xenserver
description: Este artigo descreve as configurações adicionais do necessárias para execução de uma VM pfsense virtualizado no xenserver.
---

Vamos obter uma lista dos uuids das vms existentes no servidor.

```bash
xe vm-list
```

O retorno será similar, contendo as seguintes informações:

```text
uuid ( RO) : [uuid-vm]
name-label ( RW): [vm-name]
power-state ( RO): [vm-power]
```

Precisaremos das informações retornadas em **uuid-vm** para a vms que vamos configurar a interface de rede.

Obtendo a lista de identificadores uuid da interface de rede da vm:

```bash
xe vif-list vm-uuid=[uuid-vm]
```

Lembre-se de substituir o **uuid-vm** pela retornado no comando anterior para a respectiva vm.
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
