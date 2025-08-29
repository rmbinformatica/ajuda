---
title: Reparando um banco de dados RPM corrompido
author: "Renato Monteiro Batista"
date: 2025-07-23
category: [sistemas-operacionais, linux]
layout: post
revisao: 2025-07-23
keywords: rpm, corrompido, banco de dados, reparo, linux, sistema operacional, tutorial, howto, guia, passo a passo, RPM, database, corrupted, repair, Linux, operating system, tutorial, howto, guide, step by step
description: Solução para o problema "DB_RUNRECOVERY: Fatal error, run database recovery" ao tentar utilizar o gerenciador de pacotes.
---

## Detalhamento do problema

O problema ocorre ao tentar instalar ou atualizar pacotes utilizando o gerenciador de pacotes RPM, onde é apresentada a mensagem de erro: 

```
error: rpmdb: BDB0113 Thread/process 29364/140116298053440 failed: BDB1507 Thread died in Berkeley DB library
error: db5 error(-30973) from dbenv->failchk: BDB0087 DB_RUNRECOVERY: Fatal error, run database recovery
error: cannot open Packages index using db5 -  (-30973)
error: cannot open Packages database in /var/lib/rpm
CRITICAL:yum.main:

Error: rpmdb open failed
```

## Reparando o banco de dados RPM

Para resolver o problema, siga as seguintes etapas.

### 1 - Realize o banckup do banco de dados RPM atual

```bash
mkdir /var/lib/rpm/backup
cp -a /var/lib/rpm/__db* /var/lib/rpm/backup/
```

### 2 - Remova os arquivos de banco de dados RPM corrompidos

```bash
rm -f /var/lib/rpm/__db.[0-9][0-9]*
```

### 3 - Reconstrua o banco de dados RPM

```bash
rpm --rebuilddb
```

{% include gads.html %}

### 4 - Limpe o cache do gerenciador de pacotes

```bash
yum clean all
```

### 5 - Verifique se o problema foi resolvido

Tente novamente instalar ou atualizar um pacote para verificar se o erro foi resolvido. Por exemplo:

```bash
yum update
```

## Conclusão

Após seguir os passos acima, o banco de dados RPM deve estar reparado e você poderá utilizar o gerenciador de pacotes normalmente. Se o problema persistir, pode ser necessário investigar mais a fundo ou considerar a reinstalação do RPM ou do sistema operacional.