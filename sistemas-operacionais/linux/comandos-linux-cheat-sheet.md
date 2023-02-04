---
description: Folha de dicas de comandos linux
---

# Folha de dicas de comandos do linux

## Operações básicas com o sistema de arquivos

### ls

lista o conteúdo de um diretório e um pouco mais

### exa

exa é uma versão moderna que planeja substituir o ls

### lsd

lsd é uma versão moderna que planeja substituir o ls

### cp

copia um arquivo ou diretório

### mv

move ou renomeia um arquivo ou diretório

### rm

remove um arquivo ou diretório

### rmdir

remove um diretório vazio

### ln

cria links (nomes alternativos ou apelidos) entre arquivos ou diretórios

### shred

sobrescreve um arquivo com zeros e depois o remove, o objetivo é oferecer uma forma segura de remover arquivos confidenciais dificultando a possibilidade de recuperação de dados

## Exibição de textos e mensagens

### echo

mostra uma mensagem na tela

### printf

mostra uma mensagem na tela que pode ser formatada

### yes

mostre uma mensagem na tela repetidamente

### seq

exibe números de maneira sequencial

### clear

limpa a tela

### tput

altera as configurações do terminal

## Criação e edição de arquivos

### touch

cria um arquivo vazio

### emacs

editor de texto

### nano

editor de texto

### vi

editor de texto

### vim

editor de texto

### tee

lê a entrada padrão e a escreve em um arquivo e na saída padrão

## Propriedades e metadados de arquivos

### stat

mostra informações sobre um arquivo

### wc

conta linhas, palavras e caracteres

### file

determina o tipo de um arquivo

### touch

altera a data de acesso e modificação de um arquivo

### chmod

altera as permissões de um arquivo

### chown

altera o dono de um arquivo

### chgrp

altera o grupo de um arquivo

### chattr

altera os atributos de um arquivo

### umask

define as permissões padrão para novos arquivos

### lsattr

lista os atributos de um arquivo

## Busca de arquivos

### find

busca arquivos e diretórios

### which

busca por um comando

### whereis

busca por um arquivo, diretório ou comando

### type

busca por um comando

## Compressão e descompressão de arquivos

### tar

cria e extrai arquivos compactados, por padrão o tar não comprime os arquivos, sendo necessário usar o próximo comando

### gzip

comprime arquivos no formato GNU Zip

### gunzip

descomprime arquivos no formato GNU Zip

### bzip2

comprime arquivos no formato BZip

### bunzip2

descomprime arquivos no formato BZip

### bzcat

comprime e descomprime arquivos no formato BZip

### xz

comprime arquivos no formato XZ

### unxz

descomprime arquivos no formato XZ

### xzcat

comprime e descomprime arquivos no formato XZ

### zip

comprime arquivos no formato ZIP

### unzip

descomprime arquivos no formato ZIP

### 7z

comprime arquivos no formato 7z

### 7za

descomprime arquivos no formato 7z

## Processos

### ps

mostra os processos em execução

### pidof

mostra o PID de um processo

### top

mostra os processos em execução em tempo real no formato bolsa de valores

### htop

mostra os processos em execução em tempo real no formato bolsa de valores e com gráficos mostrando o uso de CPU e memória

### powertop

mostra os processos em execução em tempo real no formato do ps permitindo a navegação entre as páginas

### kill

envia um sinal para um processo, podendo encerrar a execução do mesmo

### killall

envia um sinal para todos os processos com o mesmo nome

### nice

altera a prioridade de um processo

### renice

altera a prioridade de um processo em execução

### nohup

executa um comando ignorando sinais de encerramento

### pgrep

busca por um processo

### pkill

envia um sinal para um processo

### pstree

mostra os processos em execução em forma de árvore

### jobs

mostra os processos em execução em segundo plano

### fg

coloca um processo em execução em primeiro plano

### bg

coloca um processo em execução em segundo plano

## Usuários logados

### w

mostra os usuários logados

### who

mostra os usuários logados

### whoami

mostra o nome do usuário logado

### last

mostra os últimos usuários logados

### lastlog

mostra os últimos usuários logados

### users

mostra os usuários logados

### id

mostra o id, nome do usuário logado e o seu grupo

### history

mostra o histórico de comandos executados pelo usuário logado

## Data e hora

### date

mostra a data e hora

### cal

mostra o calendário

## Visualização de arquivos

### cat

mostra o conteúdo de um arquivo

### tac

mostra o conteúdo de um arquivo de trás para frente

### more

mostra o conteúdo de um arquivo, uma página por vez

### less

mostra o conteúdo de um arquivo, uma página por vez

### head

mostra as primeiras linhas de um arquivo

### tail

mostra as últimas linhas de um arquivo

### od

mostra o conteúdo de um arquivo em formato octal

### nl

mostra o conteúdo de um arquivo numerando as linhas

### strings

mostra o conteúdo de um arquivo em formato texto

### hexdump

mostra o conteúdo de um arquivo em formato hexadecimal

### base64

codifica e decodifica arquivos em base64

## Comparação entre arquivos

### diff

compara dois arquivos

### cmp

compara dois arquivos

### comm

compara dois arquivos

## Cálculo de hashes e checksums

Hashes são funções matemáticas que transformam um arquivo em uma sequência de caracteres que representa o conteúdo do arquivo. Essa sequência de caracteres é chamada de hash do arquivo. O hash de um arquivo pode ser usado para:

- verificar se o arquivo foi alterado ou não
- verificar se o arquivo foi corrompido ou não
- verificar se o arquivo foi baixado corretamente
- verificar a duplicidade de arquivos

### md5sum

calcula o hash MD5 de um arquivo

### sha1sum

calcula o hash SHA1 de um arquivo

### sha256sum

calcula o hash SHA256 de um arquivo

### sha512sum

calcula o hash SHA512 de um arquivo

### cksum

calcula o checksum de um arquivo

### sum

calcula o checksum de um arquivo

## Operações com diretórios

### pwd

mostra o caminho (path) diretório atual

### mkdir

cria um diretório vazio

### rmdir

remove um diretório vazio

### rm -r

remove um diretório e todo o seu conteúdo

### cd

muda o diretório atual

### basename

mostra o nome do arquivo de um caminho

### dirname

mostra o nome do diretório de um caminho

### ls

lista os arquivos e diretórios

## Manipulação de arquivos e texto

Alguns dos comandos aqui descritos estão mais detalhados no artigo [Folha de dicas para análise de logs](log-parsing-cheat-sheet.md).

### grep

busca por padrões ou expressões regulares em arquivos

### sed

filtra e transforma texto

### awk

filtra e transforma texto

### cut

filtra e transforma texto

### sort

ordena linhas de texto

### paste

une linhas de texto

### tr

filtra e transforma texto

### uniq

filtra linhas duplicadas

### join

une linhas de texto

### wc

conta linhas, palavras e caracteres

## Desligamento e reinicialização

### halt

desliga o sistema

### poweroff

desliga o sistema

### reboot

reinicia o sistema

### shutdown

desliga ou reinicia o sistema

### uptime

mostra quanto tempo o sistema está ligado

## Agendamento de tarefas

### at

executa um comando em um horário específico

### sleep

aguarda um tempo antes de executar um comando

### watch

executa um comando periodicamente

## Discos e sistemas de arquivos

### df

mostra o espaço livre em disco

### du

mostra o espaço ocupado em disco

### mount

monta um dispositivo de armazenamento

### umount

desmonta um dispositivo de armazenamento

### fdisk

cria, edita e remove partições em discos

### mkfs

cria um sistema de arquivos em um dispositivo de armazenamento

### mkswap

cria uma partição de swap em um dispositivo de armazenamento

### mkfs.ext2

cria um sistema de arquivos ext2 em um dispositivo de armazenamento

### fsck

verifica e corrige erros em um sistema de arquivos

### sync

sincroniza os dados em disco

### dd

clona dispositivos de armazenamento e cria imagens de disco

### lsblk

lista os dispositivos de armazenamento

### sfdisk

cria, edita e remove partições em discos

### blkid

mostra informações sobre dispositivos de armazenamento

### partprobe

atualiza a tabela de partições

### swapon

ativa uma partição de swap

### swapoff

desativa uma partição de swap

## Informações da máquina

### uname

mostra informações sobre o sistema operacional

### hostname

mostra o nome da máquina

### hwinfo

mostra informações sobre o hardware

### lspci

mostra informações sobre os dispositivos PCI

### lsusb

mostra informações sobre os dispositivos USB

### lsmod

mostra os módulos do kernel carregados

### lscpu

mostra informações sobre a CPU

### lsmem

mostra informações sobre a memória

### lsof

mostra os arquivos abertos por processos

### free

mostra informações sobre a memória

## Comandos de rede

### ifconfig

configura interfaces de rede ou exibe as configurações atuais

### ip

configura interfaces de rede ou exibe as configurações atuais

### route

configura rotas ou exibe as rotas atuais

### netstat

exibe informações sobre conexões de rede

### ping

envia pacotes ICMP para um host

### traceroute

mostra o caminho de pacotes ICMP até um host

### dig

consulta DNS

### nslookup

consulta DNS

### host

consulta DNS

### wget

faz download de arquivos

### curl

faz download de arquivos

### ssh

acessa um host remoto via SSH

### scp | rsync | sftp

copia arquivos entre hosts via SSH

## Gerenciamento de usuários

### useradd

cria um novo usuário

### userdel

remove um usuário

### usermod

modifica um usuário

### passwd

altera a senha de um usuário

### groupadd

cria um novo grupo

### groupdel

remove um grupo

### groupmod

modifica um grupo

### chfn

altera informações sobre um usuário

### chsh

altera o shell padrão de um usuário

## Cálculos matemáticos

### bc

calculadora de linha de comando

### expr

calculadora de linha de comando

### dc

calculadora de linha de comando

### factor

fatora números

### seq

gera sequências numéricas

### shuf

gera números aleatórios

## Permissões administrativas

### sudo

executa comandos como outro usuário

### su

executa comandos como outro usuário

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}