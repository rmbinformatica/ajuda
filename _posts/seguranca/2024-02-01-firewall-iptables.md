---
title: Firewall iptables
author: "Renato Monteiro Batista"
date: 2024-02-01
category: seguranca
layout: post
keywords: bash, scripts, shell, linux, iptables
description: Alguns exemplos de comandos iptables para configurar um firewall
revisao: 2024-02-01
---

## Como usar o iptables

### Listar todas as regras

```bash
iptables -L
```

### Limpar todas as regras

```bash
iptables -F
```

### Bloquear uma porta

```bash
iptables -A INPUT -p tcp --dport 22 -j DROP
```

### Liberar uma porta

```bash
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

### Bloquear um IP

```bash
iptables -A INPUT -s <ip> -j DROP
```

### Liberar um IP

```bash
iptables -A INPUT -s <ip> -j ACCEPT
```

### Bloquear um range de IPs

```bash
iptables -A INPUT -s <ip>/24 -j DROP
```

### Liberar um range de IPs

```bash
iptables -A INPUT -s <ip>/24 -j ACCEPT
```

### Bloquear um protocolo

```bash
iptables -A INPUT -p tcp -j DROP
```

### Liberar um protocolo

```bash
iptables -A INPUT -p tcp -j ACCEPT
```

### Bloquear um range de portas

```bash
iptables -A INPUT -p tcp --dport 1:1024 -j DROP
```

### Liberar um range de portas

```bash
# Liberar as portas de 30000 a 31000
iptables -A INPUT -p tcp --dport 30000:31000 -j ACCEPT
## Outra forma
iptables -A INPUT -p tcp --match multiport --dports 30000:31000 -j ACCEPT
```

### Atuar como gateway de internet mascarando os ips internos

```bash
sysctl -w net.ipv4.ip_forward=1
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
```

### Abrir uma porta especifica e redirecionar esse trafego para outra maquina

```bash
sysctl -w net.ipv4.ip_forward=1
iptables -t nat -A PREROUTING -p tcp --dport <porta-local> -j DNAT --to-destination <host-destino>:<porta-destino>
iptables -t nat -A POSTROUTING -j MASQUERADE
```

### Bloquear um range de IPs e liberar um IP específico

```bash
iptables -A INPUT -s <ip> -j ACCEPT
iptables -A INPUT -s <ip>/24 -j DROP
```

