---
description: >-
  Guia de referência sobre como executar determinadas operações no microsoft
  windows através da linha de comando, podendo ser utilizado em scripts batch
  (extensão .bat).
---

# cmd & batch script - usando linha de comando

## Listagem de diretório atual

```batch
dir
```

## Mudando de diretório

```batch
cd [caminho]
```

## Adicionando credenciais de acesso a um servidor de rede no cofre do usuário

```batch
cmdkey /add:[nome_ou_ip] /user:[username] /pass:[senha]
```

## Configurando o ip da máquina

```batch
netsh interface ip set address "Conexão Local" static [ip] [mascara] [gateway padrao]
```

Substitua o _Conexão Local_ pelo nome da interface de rede conforme aparece na _Central de redes e compartilhamento_. Para execução dessa operação via script recomendamos renomear a conexão nas configurações do adaptador para um nome simplificado, tal como **LAN**.

### Atribuindo um segundo endereço de IP estático a uma máquina

```batch
netsh interface ipv4 add address "LAN" [ip] [mascara] [gateway padrao]
```

## Exibindo uma mensagem popup para um usuário

```batch
msg * "Texto da mensagem"
```

## Reiniciando o sistema

```batch
shutdown -r -t [tempo em segundos] -c "Mensagem a exibir ao usuário"
```

## Habilitando e desabilitando interface de redes via prompt de comando

```batch
netsh interface set interface name="WANSATELITE" admin=ENABLED
netsh interface set interface name="VELOX" admin=DISABLED
```

## Calculando o hash md5  ou SHA1 de um arquivo no windows via prompt de comando

```batch
certutil -hashfile <nome_do_arquivo> MD5
certutil -hashfile <nome_do_arquivo> SHA1
```

{% hint style="info" %}
Nota: Os algoritmos de hash suportados pelo `certutil` do _Windows 10_ são: **MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512**
{% endhint %}

## Obtendo o número serial da instalação do Windows gravado na BIOS via linha de comando

As versões mais recentes do Windows pré-instaladas na máquina (OEM) não vem com o selo de autenticidade (COA) com o número de série, pois esses passaram a ser gravados na BIOS da máquina. Para verificar a chave de instalação (número serial) de um windows original adquirido junto com um novo computador execute o seguinte comando:

```batch
wmic path softwarelicensingservice get OA3xOriginalProductKey
```

## Visualizando e removendo as chaves de produto (product key) do Microsoft Office instaladas na máquina

Todos os comandos precisam ser executados a partir da pasta onde o office está instalado, neste exemplo consideraremos que o office está instalado no caminho **`C:\Program Files\Microsoft Office\Office16`** faça os ajustes necessários conforme seu caso.&#x20;

```
cd "C:\Program Files\Microsoft Office\Office16"
cscript ospp.vbs /dstatus
cscript ospp.vbs /unpkey:[FinalChave]
```

Na segunda linha o comando exibe as chaves atualmente instaladas, note que haverá uma ou mais linhas no resultado contendo a informação: **`Last 5 characters of installed product key: XYZ99`** nesse caso o _XYZ99_ seria a informação que seria preenchida no comando da terceira linha no espaço indicado como **`[FinalChave]`**.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><a href="http://renato.ovh">Renato Monteiro Batista</a></td><td>Engenheiro de Computação</td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Artigos relacionados" %}
* [Comandos úteis do PowerShell](comandos-uteis-do-powershell)
{% endtab %}
{% endtabs %}