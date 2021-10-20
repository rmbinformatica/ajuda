---
description: Comandos e dicas para configuração de servidores CentOS 7
---

# CentOS 7

## Alterando o timezone do CentOS 7 para o horário brasileiro

```
timedatectl set-timezone America/Recife
```

No exemplo acima definimos o timezone para Recife, para obter uma lista das outras cidades disponíveis na américa execute o comando `timedatectl list-timezones | grep America` e escolha o mais adequado à sua cidade.
