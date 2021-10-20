---
description: >-
  Guia de referência sobre como executar determinadas operações no microsoft
  windows através da linha de comando, podendo ser utilizado em scripts batch
  (extensão .bat).
---

# cmd & batch script - usando linha de comando

## Listagem de diretório atual

```
dir
```

## Mudando de diretório

```
cd [caminho]
```

## Adicionando credenciais de acesso a um servidor de rede no cofre do usuário

```
cmdkey /add:[nome_ou_ip] /user:[username] /pass:[senha]
```

## Configurando o ip da máquina

```
netsh interface ip set address "Conexão Local" static [ip] [mascara] [gateway padrao]
```

Substitua o _Conexão Local_ pelo nome da interface de rede conforme aparece na _Central de redes e compartilhamento_. Para execução dessa operação via script recomendamos renomear a conexão nas configurações do adaptador para um nome simplificado, tal como **LAN**.

### Atribuindo um segundo endereço de IP estático a uma máquina

```
netsh interface ipv4 add address "LAN" [ip] [mascara] [gateway padrao]
```

## Exibindo uma mensagem popup para um usuário

```
msg * "Texto da mensagem"
```

## Reiniciando o sistema

```
shutdown -r -t [tempo em segundos] -c "Mensagem a exibir ao usuário"
```

## Habilitando e desabilitando interface de redes via prompt de comando

```
netsh interface set interface name="WANSATELITE" admin=ENABLED
netsh interface set interface name="VELOX" admin=DISABLED
```

## Calculando o hash md5  ou SHA1 de um arquivo no windows via prompt de comando

```
certutil -hashfile <nome_do_arquivo> MD5
certutil -hashfile <nome_do_arquivo> SHA1
```

{% hint style="info" %}
Nota: Os algoritmos de hash suportados pelo `certutil` do _Windows 10_ são: **MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512**
{% endhint %}

## Obtendo o número serial da instalação do Windows gravado na BIOS via linha de comando

As versões mais recentes do Windows pré-instaladas na máquina (OEM) não vem com o selo de autenticidade (COA) com o número de série, pois esses passaram a ser gravados na BIOS da máquina. Para verificar a chave de instalação (número serial) de um windows original adquirido junto com um novo computador execute o seguinte comando:

```
wmic path softwarelicensingservice get OA3xOriginalProductKey
```

