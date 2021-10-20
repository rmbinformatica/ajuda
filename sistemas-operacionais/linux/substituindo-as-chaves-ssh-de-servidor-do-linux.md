---
description: >-
  Este artigo descreve o processo de substituição das chaves SSH de servidor de
  um linux.
---

# Substituindo as chaves SSH de servidor do linux

## Realize um backup das chaves anteriores

Antes de proceder a substituição das chaves recomendamos o backup das chaves anterior para caso de necessidade futura.

```bash
tar -cf antigo.tar /etc/ssh/*key*
```

## Removendo as chaves antigas

```bash
rm -fv /etc/ssh/*key*
```

## Reiniciando o serviço SSHD

Ao reiniciar o serviço sshd as novas chaves serão geradas automaticamente.

```bash
service sshd restart
```
