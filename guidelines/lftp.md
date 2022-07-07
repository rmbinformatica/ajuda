---
description: >-
  LFTP é um cliente de ftp baseado em linha de comando que permite a elaboração
  de scripts FTP para automatizar tarefas de transferências de arquivos.
---

# LFTP

## Sintaxe da linha de comando

### Executando o LFTP diretamente na linha de comando bash ou utilizando scripts

```bash
lftp [-d] [-e cmd] [-p port] [-u user[,pass]] [site]
```

### Executando um script de comandos do lftp

```
lftp -f script_file
```

## Desabilitando verificação de SSL no LFTP

Para conexão a servidores FTP internos que não possuem SSL configurado é recomendado desativar o suporte SSL do LFTP.

```
set ftp:ssl-allow no
```

## Espelhando diretórios locais e remotos

### Trazendo arquivos do servidor remoto para a pasta local

Este procedimento faz o diretório local ficar com a mesma estrutura e arquivos do servidor remoto.

```
mirror
```

### Enviando arquivos do diretório local para o servidor remoto

Este procedimento faz o diretório do servidor remoto ficar com a mesma estrutura e arquivos do diretório local.

```
mirror -R
```

## Veja também

[Documentação oficial do LFTP](https://lftp.yar.ru/lftp-man.html).
