---
title: Instalando e configurando um servidor OpenVPN no windows
author: "Renato Monteiro Batista"
date: 2022-01-19
category: [redes-e-infraestrutura, openvpn]
layout: post
revisao: 2023-11-19
keywords: openvpn, vpn, servidor, windows, certificado, tls-auth, easyrsa
description: >-
  Este artigo descreve o processo de instalação e configuração de um servidor
  OpenVPN em um computador windows
---

Este artigo visa fornecer esclarecimentos adicionais a cerca da geração de certificados de um servidor OpenVPN para windows, visto que as informações existentes no **how-to** [https://openvpn.net/community-resources/how-to/](https://openvpn.net/community-resources/how-to/) não se encontram atualizadas referente ao uso da ferramenta EasyRSA 3.

<mark style="color:orange;">**Este artigo é direcionado à pessoas perfil técnico avançado.**</mark>

> ##### NOTA SOBRE O EasyRSA
>
> A nova ferramenta EasyRSA implementa uma shell no windows com suporte aos mesmos comandos da versão linux. Dessa forma os comandos do how-to direcionados aos usuários windows não são mais reconhecidos a menos que seja utilizada alguma versão anterior do EasyRSA, sendo necessário executar os comandos EasyRSA versão linux.
{: .block-tip }

> ##### CONSIDERAÇÕES SOBRE A SEGURANÇA
>
> NÃO RECOMENDAMOS O USO DO SISTEMA OPERACIONAL WINDOWS COMO SERVIDOR DE OPENVPN EM AMBIENTES DE PRODUÇÃO, considere usar linux para esse tipo de cenário.
{: .block-danger }

Inicialmente baixe a [versão mais recente do OpenVPN diretamente do site oficial](https://openvpn.net/community-downloads/) e realize a instalação. Durante a instalação escolha o método de instalação personalizada e selecione todos os componentes.

## Gerando o certificado do servidor

Para fins de arquivos temporários crie um diretório **c:\temp**, utilizando o prompt de comando `cmd` execute:

```batch
c:
cd\
md temp
```

Após a instalação acesse a pasta **C:\Program Files\OpenVPN\easy-rsa** e execute o `EasyRSA-Start.bat` em _modo administrador_.

Você acessará uma shell similar a shell do linux onde vamos gerar os certificados para autenticação com o servidor OpenVPN, executando os comandos abaixo dentro do shell:

```batch
easyrsa init-pki
export EASYRSA_TEMP_DIR="/temp"
easyrsa build-ca
```

Siga o assistente e preencha as informações do certificado CA. Agora vamos gerar o certificado do servidor e assinar.

```batch
easyrsa gen-req vpn-server nopass
easyrsa sign-req server vpn-server
```

Podemos executar uma verificação para testar se o certificado foi gerado corretamente.

```batch
openssl verify -CAfile pki/ca.crt pki/issued/vpn-server.crt
```

{% include gads.html %}

## Gerando os certificados dos clientes

Ainda na shell `EasyRSA-Start.bat`, execute o processo abaixo e repita para cada certifcado de cliente que desejar gerar. Substitua `client01` o por um nome para identificação do cliente.

```batch
easyrsa gen-req client01 nopass
easyrsa sign-req client client01
```

Da mesma forma, podemos verificar o certificado gerado usando o comando:

```batch
openssl verify -CAfile pki/ca.crt pki/issued/client01.crt
```

## Gerando a chave Diffie-Hellman

Ainda na shell `EasyRSA-Start.bat`, vamos gerar a chave Diffie-Hellman:

```batch
easyrsa gen-dh
```

## Gerando uma chave estática para tls-auth

Execute, num prompt de comando `cmd` _elevado_ (**administrador**):

```batch
cd "C:\Program Files\OpenVPN\bin"
openvpn --genkey tls-auth "C:\Program Files\OpenVPN\easy-rsa\pki\ta.key"Arquivos de configuração
```

Siga os modelos existentes na pasta **C:\Program Files\OpenVPN\sample-config** para criar o arquivo de configuração do servidor e dos clientes OpenVPN.

### Considerações sobre os caminhos dos arquivos no windows

No arquivo de configuração do OpenVPN para windows as barras nos caminhos dos arquivos devem ser duplicadas par que sejam interpretados pelo software, exemplo da localização dos arquivos de certificados para usar no arquivo de configuração:

```
ca "C:\Program Files\OpenVPN\\easy-rsa\\pki\\ca.crt"
cert "C:\\Program Files\OpenVPN\\easy-rsa\\pki\\issued\\vpn-server.crt"
key "C:\\Program Files\\OpenVPN\\easy-rsa\\pki\\private\\vpn-server.key" 
dh "C:\\Program Files\\OpenVPN\\easy-rsa\\pki\\dh.pem"
tls-auth "C:\\Program Files\\OpenVPN\\easy-rsa\\pki\\ta.key" 0
```

{% include gads.html %}

### Renovando certificados

Quando os certificados expirarem, eles poderão ser renovados com o comando a seguir:

```
easyrsa renew <nome-certificado>
easyrsa revoke-renewed <nome-certificado>
```

Uma vez renovado o certificado o arquivo com extensão .crt deve ser substituído no servidor cliente pelo novo certificado.

### Logs

Para resolução de problemas na implantação verifique sempre os arquivos de log do servidor disponíveis em `%USERPROFILE%\OpenVPN\log`.

## Veja também

* [2x HowTo OpenVPN](https://openvpn.net/community-resources/how-to/)
* [How to Install OpenVPN Server and Client with Easy-RSA 3 on CentOS 8](https://www.howtoforge.com/tutorial/how-to-install-openvpn-server-and-client-with-easy-rsa-3-on-centos-8/)
* [Easy-RSA v3 OpenVPN Howto](https://community.openvpn.net/openvpn/wiki/EasyRSA3-OpenVPN-Howto)