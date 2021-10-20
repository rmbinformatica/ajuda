---
description: Guia rápido de comandos do GIT
---

# Comandos GIT

## Configurações iniciais do cliente de git

Defina seu nome de usuário e e-mail.

```
git config user.name "<seuNome>"
git config --global user.email "<seu@email.com>"
```

## Inicializar um repositório de maneira local

Permite que se inicialize o diretório atual como um repositório git.

```
git init
```

## Adicionar um repositório remoto

Uma vez que o caminho local seja um repositório git inicializado, é possível adicionar os caminhos para o repositório remoto.

```
git remote add <origin> <url>
```

Onde:

* _origin_ = pode ser modificado para qualquer nome desejado, sendo o padrão a palavra _origin_;
* _url_ = é obtida do repositório git em sites como [GitHub](https://github.com), [BitBucket](https://bitbucket.org) e [GitLab](https://gitlab.com).

### Adicionar um segundo repositório remoto

É possível que um repositório local tenha mais de um repositório remoto, para isso basta adicionar um novo:

```
git remote set-url origin --push --add <url>
```

## Listagem dos repositórios remotos

```
git remote
```

### Listagem detalhada

```
git remote -v
```

## Adicionar um arquivo ao staged

Staged é a fila de arquivos a ser commitada.

```
git add <nomeDoArquivo>
```

OBS: Utilize \* como _nomeDoArquivo_ para adicionar todos os arquivos.

## Realizar um commit (da fila staged)

```
git commit -m "<comentário>"
```

## Adicionar arquivo e commitar ao mesmo tempo

```
git commit -am "<comentario>"
```

## Alterar a data de um commit

```
git commit --date="aaaa-mm-ddThh:mm:ss"
```

Onde:

* _aaaa_ = Ano (com quatro dígitos);
* _mm_ = Mês (com dois dígitos);
* _dd_ = Dia do mês (com dois dígitos);
* _hh_ = Hora do dia (formato 24h);
* _mm_ = Minutos;
* _ss_ = Segundos.

## Enviar arquivos ao repositório remoto

Considerando que o repositório remoto foi definido como _origin_:

```
git push origin master
```

### Observação:

Pode-se dispensar a necessidade de colocar especificar origin master em todo push.

```
git push -u origin master
```

## Clonando código de um repositório remoto

Faz uma cópia do repositório remoto para a se for omitido será criada uma subpasta com o nome do repositório remoto.

```
git clone <url> <pastaLocal>
```

## Status das alterações em relação ao último commit

Relaciona todos os arquivos que foram modificados desde o último commit.

```
git status
```

## Mostra o que foi alterado nos arquivos

O parâmetro _nomeDoArquivo_ é opcional, se for omitido será exibida o detalhe do que foi alterado em todos os arquivos.

```
git diff <nomeDoArquivo>
```

### Listagem dos nomes dos arquivos que foram alterados

Mostra somente o nome dos arquivos e não o conteúdo do que foi alterado.

```
git diff --name-only
```

## Logs dos commits

Detalha cada commit, listando nome do autor e comentários dos commits.

```
git log
git log --graph
git log --decorate
```

### Filtrar commits por autor

```
git log --author="<nomeDoAutor>"
```

## Listar as contribuições de por autor

```
git shortlog
```

### Mostrar somente a quantidade de contribuições por autor

```
git shortlog -sn
```

## Detalhes de um commit

```
git show <hashDoCommit>
```

## Retornar um arquivo específico à ultima versão commitada

```
git checkout <nomeDoArquivo>
```

## Retirar um arquivo da fila do staged

```
git reset head
```

## Desfazer um commit

É possível desfazer um commit de três maneiras.

### Mantendo as alterações feitas no arquivo e o arquivo na staged:

```
git reset --soft <hashAnteriorAoCommit>
```

### Mantendo as alterações feitas, mas sem o arquivo na staged:

```
git reset --mixed <hashAnteriorAoCommit>
```

### Apagando todas as alterações do commit e voltando ao anterior:

```
git reset --hard <hashAnteriorAoCommit>
```

### Voltando o commit anterior como se fosse um novo commit:

```
git revert <hashDoCommitADesfazer>
```

## Trabalhando com branches

### Criar um branch

```
git checkout -b <nomeDoBranch>
```

### Listagem dos branches

```
git branch
```

### Mudar de branch

```
git chechout <nomeDoBranch>
```

### Apagar um branch

```
git branch -D <nomeDoBranch>
```

### Apagar um branch do repositório remoto

```
git push origin :<nomeDoBranch>
```

## Fazendo merge de branches

### Não-linear

```
git merge <nomeDoBranch>
```

### Merge linear

```
git rebase <nomeDoBranch>
```

## Criar Work In Progress (WIP)

```
git stash
```

### Trazer as mudanças do WIP de volta

```
git stash apply
```

### Listagem dos stashes

```
git stash list
```

### Limpar os stashes

```
git stash clear
```

## Criar um alias (atalho) para comandos

```
git config --global alias.<atalho> <comando>
```

### Exemplo:

Criar um atalho _pom_ que represente o comando _push origin master_

```
git config --global alias.pom "push origin master"
```

Feito isso os novos pushes para o repositório remoto podem ser feitos usando o comando `git pom`

## Versionando com tag

```
git tag -a <versao> -m "<comentario>"
git push origin master --tags
```

### Deletar tag do repositório remoto

```
git push origin :<versaoAApagar>
```

Conheça também as ferramentas [Atom](https://atom.io), [GitHub Desktop](https://desktop.github.com) e [GitKraken](https://www.gitkraken.com) que fornecem um ambiente gráfico para trabalhar com o git.
