---
description: Como alterar o mapa de partições a partir do terminal
---

# Gerenciando partições via terminal

## Listar partições existentes

```
diskutil list
```

Em todos os comandos a seguir considere o _N_ de _diskN_ como o identificador do disco, conforme mostrado na listagem do comando acima.

## Desmontando uma unidade de disco

```
diskutil umountDisk /dev/diskN
```

## Removendo uma partição GPT

```
gpt remove -i 2 /dev/diskN
```

Nesse caso seria removido a partição relativa à entrada # 2 da listagem.

## Removendo todas as partições GPT

```
gpt destroy /dev/diskN
```

## Apagando todo o conteúdo de um disco e deixando sem partições

```
diskutil zeroDisk /dev/diskN
```

