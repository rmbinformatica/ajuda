---
title: Desmontando um cluster proxmox
author: "Renato Monteiro Batista"
date: 2025-08-28
category: [sistemas-operacionais, linux]
layout: post
revisao: 2025-08-28
keywords: proxmox, cluster, desmontar, desmanchar, desmembar, quebrar, desfazer, separar, individualizar
description: Solução para desmontar um cluster proxmox e transformar os nós em servidores independentes.
---

Desmontar um cluster Proxmox e transformar os nós em hypervisores independentes exige cuidado, pois o processo é irreversível e pode afetar VMs se não for feito corretamente.

## Etapas para desmanchar um cluster Proxmox

#### Antes de prosseguir

* Faça backup das VMs e containers.
* Certifique-se de que os nós não compartilham armazenamento crítico.
* Execute os comandos localmente em cada nó que será removido.

### 1 - Parar serviços de cluster

Em cada nó que será removido do cluster, pare os serviços relacionados ao cluster:

```bash
systemctl stop pve-cluster
systemctl stop corosync

```

### 2 - Forçar modo local no pmxcfs e finalizar processos

```bash
pmxcfs -l
killall pmxcfs
```

Isso ativa o modo local do sistema de arquivos de configuração, permitindo alterações sem o Corosync.

### 3 - Remover arquivos de configuração do cluster

```bash
rm -rf /etc/corosync/*
rm -f /etc/pve/corosync.conf
rm -f /etc/pve/.members
```

### 4 - Reiniciar serviço

```bash
systemctl start pve-cluster
systemctl start pve-storage
```

{% include gads.html %}

### 5 - Verificar se o nó está fora do cluster

```bash
pvecm status
```

Você deve ver um erro dizendo que o nó não pertence a nenhum cluster — isso é esperado.

## Conclusão

Após esses passos, o nó estará livre do cluster e funcionará como um hypervisor Proxmox independente. Você poderá gerenciar VMs localmente, sem sincronização com outros nós.