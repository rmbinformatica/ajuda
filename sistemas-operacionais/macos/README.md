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

