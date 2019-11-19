---
description: >-
  Guia de referência sobre como executar determinadas operações no microsoft
  windows através da linha de comando, podendo ser utilizado em scripts batch
  (extensão .bat).
---

# cmd & batch script - usando linha de comando

## Listagem de diretório atual

```text
dir
```

## Mudando de diretório

```text
cd [caminho]
```

## Adicionando credenciais de acesso a um servidor de rede no cofre do usuário

```text
cmdkey /add:[nome_ou_ip] /user:[username] /pass:[senha]
```

## Configurando o ip da máquina

```text
netsh interface ip set address "Conexão Local" static [ip] [mascara] [gateway padrao]
```

Substitua o _Conexão Local_ pelo nome da interface de rede conforme aparece na _Central de redes e compartilhamento_. Para execução dessa operação via script recomendamos renomear a conexão nas configurações do adaptador para um nome simplificado, tal como **LAN**.

### Atribuindo um segundo endereço de IP estático a uma máquina

```text
netsh interface ipv4 add address "LAN" [ip] [mascara] [gateway padrao]
```

## Exibindo uma mensagem popup para um usuário

```text
msg * "Texto da mensagem"
```

## Reiniciando o sistema

```text
shutdown -r -t [tempo em segundos] -c "Mensagem a exibir ao usuário"
```



