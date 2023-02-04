---
description: Dicas do sistema operacional linux
---

# Linux

## Contando arquivos no diretório atual

```
ls -1 | wc -l
```

## Retornando as linhas contendo um texto buscado usando grep

```
grep -in [texto] [arquivo]
```

## Dividindo um arquivo em vários pelo numero de linhas

```
split -l [linhas] [arquivo]
```

## Apagando linhas específicas de um arquivo usando o sed

No exemplo abaixo vamos apagar as linhas de 7 a 14, e a linha 28

```
sed -e '7,14d;28d' [arquivo]
```

## Executando um comando para cada arquivo no diretório atual usando bash script

Substitua a linha do echo pelo comando desejado

```
for i in * 
do
    if -f "$i" 
    then
       echo "Encontrei arquivo $i"
    fi
done
```

## Buscando todos os arquivos em um determinado caminho contendo um texto específico

```
grep -rnw '/caminho/a/pesquisar/' -e 'texto'
```

## Ajustando o horário do linux de acordo com a hora oficial brasileira

```bash
ntpdate pool.ntp.br
```

## Sintaxe de arquivo cron para executar um comando a cada inicialização (reboot)

```
@reboot [path to command] [argument1] [argument2] … [argument n]
@reboot [part to shell script]
```

## Como se reconectar a sessões abertas utilizando o tmux

```bash
tmux ls
tmux attach -d -t [id]
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}