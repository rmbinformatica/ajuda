---
title: Como assinar commits do Git no Windows usando o GPG
author: "Renato Monteiro Batista"
date: 2026-05-25 11:20:08 -0300
category: [sistemas-operacionais, microsoft-windows]
layout: post
description: Este artigo descreve todas as etapas do procedimento necessário para configurar o Git no Windows para assinar commits automaticamente utilizando GPG (Gpg4win).
keywords: git, gpg, gpg4win, assinatura, assinar commits, windows, git bash, powershell, github, commit assinado, signingkey, gpg-agent, pinentry
revisao: 2026-05-25
---

O objetivo deste procedimento é configurar o Git no Windows para **assinar commits** com uma chave **GPG**, garantindo autoria e integridade do histórico.

> ##### ATENÇÃO
>
> Assinatura de commit não substitui backup, controle de acesso ou boas práticas de segurança. Ela **somente** garante que aquele commit foi assinado pela chave privada correspondente.
> {: .block-danger }

## Pré-requisitos

Antes de iniciar, verifique os itens abaixo:

* [Git for Windows](https://git-scm.com/install/windows) instalado
* Acesso de administrador para instalar programas (quando necessário)
* Um e-mail que você utiliza nos commits (o mesmo cadastrado no GitHub, caso queira o status *Verified*)

## 1. Conferir (ou configurar) nome e e-mail do Git

Abra o **Git Bash** (ou PowerShell) e execute:

```bash
git config --global user.name
git config --global user.email
```

Se não estiver definido, configure:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@dominio.com"
```

> ##### DICA
>
> Se você usa múltiplas identidades (trabalho/pessoal), **não** misture o e-mail do commit. Defina por repositório com `git config user.email "..."` dentro do projeto.
> {: .block-tip }

## 2. Instalar o GPG (Gpg4win)

No Windows, o caminho mais simples é instalar o **Gpg4win**, pois ele inclui o `gpg`, o `gpg-agent` e o gerenciador de chaves (Kleopatra). Disponível na [página de download do Gpg4win](https://www.gpg4win.org/download.html).

Instale o Gpg4win e confirme que o comando `gpg` está disponível.

No **Git Bash**:

```bash
gpg --version
```

Se o comando não for encontrado, pule para a seção **Solução de problemas** ao final.

## 3. Gerar sua chave GPG

No **Git Bash** (ou PowerShell), execute:

```bash
gpg --full-generate-key
```

Sugestão de parâmetros (recomendado):

* Tipo: **RSA and RSA**
* Tamanho: **4096**
* Validade: conforme sua política (ex.: 1 ano)
* Nome e e-mail: use os mesmos do `git config user.name` e `git config user.email`

Defina uma senha forte para proteger sua chave privada.

## 4. Localizar o ID da chave (key id)

Liste as chaves secretas e identifique a que você acabou de criar:

```bash
gpg --list-secret-keys --keyid-format=long
```

Exemplo de saída:

```
sec   rsa4096/ABCD1234EFGH5678 2026-05-25 [SC]
      0123456789ABCDEF0123456789ABCDEF01234567
uid                 [ultimate] Seu Nome <seu-email@dominio.com>
ssb   rsa4096/1111222233334444 2026-05-25 [E]
```

No exemplo acima, o **ID longo** é `ABCD1234EFGH5678`.

## 5. Configurar o Git para assinar commits automaticamente

Defina a chave de assinatura:

```bash
git config --global user.signingkey ABCD1234EFGH5678
```

Habilite assinatura automática em todos os commits:

```bash
git config --global commit.gpgsign true
```

### 5.1 Garantir que o Git está chamando o `gpg.exe` correto

Primeiro descubra onde está o `gpg`:

**No PowerShell:**

```powershell
where.exe gpg
```

**No Git Bash:**

```bash
which gpg
```

Se você tiver mais de um `gpg` instalado, **fixe** o binário usado pelo Git (ajuste o caminho conforme o seu caso):

```bash
git config --global gpg.program "C:/Program Files/GnuPG/bin/gpg.exe"
```

> ##### DICA
>
> No Windows, o Git costuma aceitar melhor caminhos com `/` (slash) mesmo sendo Windows.
> {: .block-tip }

## 6. Publicar sua chave GPG no GitHub (para aparecer como Verified)

Se você usa GitHub e quer que os commits apareçam como **Verified**, exporte sua **chave pública** em formato ASCII:

```bash
gpg --armor --export ABCD1234EFGH5678
```

Copie todo o bloco:

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
...
-----END PGP PUBLIC KEY BLOCK-----
```

Depois adicione no GitHub em:

* **Settings → SSH and GPG keys → [New GPG key](https://github.com/settings/gpg/new)**

## 7. Testar a assinatura

Dentro de qualquer repositório, faça um commit de teste:

```bash
git commit -m "teste de commit assinado"
```

Verifique a assinatura no log:

```bash
git log --show-signature -1
```

Você deve ver algo como `gpg: Good signature from ...`.

## 8. Evitar ficar digitando senha a cada commit (opcional)

Em geral, o `gpg-agent` faz cache da senha por um tempo. Em alguns ambientes, é necessário garantir que o terminal está “amarrado” ao GPG.

### 8.1 Git Bash: exportar GPG_TTY

No **Git Bash**, execute:

```bash
export GPG_TTY=$(tty)
```

Para tornar permanente, adicione ao arquivo `~/.bashrc` (ou `~/.bash_profile`).

### 8.2 Ajustar tempo de cache do gpg-agent

Edite o arquivo:

* `%APPDATA%\\gnupg\\gpg-agent.conf`

Adicione (ou ajuste) as linhas:

```
default-cache-ttl 28800
max-cache-ttl 86400
```

Recarregue o agente:

```bash
gpg-connect-agent reloadagent /bye
```

> ##### ATENÇÃO
>
> Aumentar o cache melhora a usabilidade, mas reduz segurança em máquinas compartilhadas. Ajuste conforme sua realidade.
> {: .block-danger }

## Solução de problemas

### Problema 1: `gpg: command not found` / `gpg não é reconhecido`

* Confirme se o **Gpg4win** foi instalado.
* Reinicie o terminal (Git Bash/PowerShell) após instalar.
* Verifique se o `gpg.exe` está no `PATH`.

Como alternativa, fixe o caminho do GPG no Git (conforme seção 5.1):

```bash
git config --global gpg.program "C:/Program Files/GnuPG/bin/gpg.exe"
```

### Problema 2: `error: gpg failed to sign the data`

Passos recomendados:

1. Verifique se existe chave secreta:

   ```bash
   gpg --list-secret-keys
   ```

2. Verifique se o `user.signingkey` está correto:

   ```bash
   git config --global user.signingkey
   ```

3. Tente assinar manualmente para ver o erro real:

   ```bash
   echo "teste" | gpg --clearsign
   ```

4. Se o problema for pinentry/janela de senha, confirme se o `gpg-agent` está ativo e se o Gpg4win (Kleopatra) está instalado corretamente.

### Problema 3: Commit assinado, mas no GitHub não aparece como Verified

* Confirme que o **e-mail do commit** (`git log -1 --pretty=format:%ae`) é o mesmo cadastrado no GitHub.
* Confirme que você adicionou a **chave pública** (não a privada) em *Settings → SSH and GPG keys*.

## Veja também

* [Comandos GIT](https://ajuda.rmbinformatica.com.br/guidelines/git)

*Caso persistam problemas após os procedimentos acima, revise as etapas para verificar se não esqueceu de executar alguma configuração. Persistindo os problemas mesmo após a execução de todas etapas, avalie reinstalar o Gpg4win e revisar conflitos de múltiplas instalações do GPG no Windows.*
