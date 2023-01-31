---
description: Dicas do sistema operacional Mac OS
---

# MacOS

## Como limpar o cache de DNS do mac

Para limpar o cache do dns do mac é muito simples, acesse o aplicativo terminal e execute o seguinte comando:

```bash
sudo killall -HUP mDNSResponder
```

## Como alterar o nome da máquina usando o terminal

Para trocar o nome do computador usando o terminal execute:

```bash
sudo scutil --set HostName <novoNome>
sudo scutil --set LocalHostName <novoNome>
sudo scutil --set ComputerName <novoNome>
dscacheutil -flushcache

```

## Como remover a senha de arquivos PDF no Mac usando o terminal?

Caso não possua, instale o qpdf:

```bash
brew install qpdf
```

Sintaxe de uso:

```bash
qpdf --decrypt --password=<senha> <arquivoComSenha>.pdf <saidaSemSenha>.pdf
```

## Exibindo a tabela de rotas do mac usando o terminal

```bash
netstat -rn
```

## Verificando o hash md5 de arquivos, no mac, usando o terminal

```bash
md5 [caminho-do-arquivo]
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}