---
description: >-
  Guia de referência sobre como executar determinadas operações no microsoft
  windows através da linha de comando, podendo ser utilizado em scripts batch
  (extensão .bat).
---

# cmd & batch script - usando linha de comando

## Listagem de diretório atual

```bat
dir
```

## Mudando de diretório

```bat
cd [caminho]
```

## Adicionando credenciais de acesso a um servidor de rede no cofre do usuário

```bat
cmdkey /add:[nome_ou_ip] /user:[username] /pass:[senha]
```

## Configurando o ip da máquina

```bat
netsh interface ip set address "Conexão Local" static [ip] [mascara] [gateway padrao]
```

Substitua o _Conexão Local_ pelo nome da interface de rede conforme aparece na _Central de redes e compartilhamento_. Para execução dessa operação via script recomendamos renomear a conexão nas configurações do adaptador para um nome simplificado, tal como **LAN**.

### Atribuindo um segundo endereço de IP estático a uma máquina

```bat
netsh interface ipv4 add address "LAN" [ip] [mascara] [gateway padrao]
```

## Exibindo uma mensagem popup para um usuário

```bat
msg * "Texto da mensagem"
```

## Reiniciando o sistema

```bat
shutdown -r -t [tempo em segundos] -c "Mensagem a exibir ao usuário"
```

## Habilitando e desabilitando interface de redes via prompt de comando

```bat
netsh interface set interface name="WANSATELITE" admin=ENABLED
netsh interface set interface name="VELOX" admin=DISABLED
```

