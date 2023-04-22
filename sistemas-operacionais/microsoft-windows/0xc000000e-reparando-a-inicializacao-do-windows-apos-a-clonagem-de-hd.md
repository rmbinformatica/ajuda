---
description: >-
  Solução para o erro 0xc000000e, "arquivo \windows\system32\winload.efi não
  encontrado" durante a inicialização do Windows 10 após a clonagem de um HD ou
  SSD.
---

# Reparando a inicialização do Windows após a clonagem de HD

Este é um problema que ocorre com uma certa freqüência após a clonagem de HD com qualquer ferramenta.

Este artigo também se aplica em alguns casos onde o windows não inicia após a instalação de outro sistema operacional (ex.: linux).

## Procedimentos para a resolução do problema

Com o HD já instalado na máquina, inicialize a máquina com qualquer pendrive de boot UEFI de instalação do Windows 10.

Na primeira tela do instalador, prossiga pressionando o botão **seguinte**.

![Primeira tela do instalador do windows 10](<../../.gitbook/assets/image (74).png>)

Na segunda tela do instalador do windows 10, escolha a opção **Reparar o seu computador**.

![Segunda tela do instalador do windows 10](<../../.gitbook/assets/image (81).png>)

Escolha a opção **Resolução de problemas**

![Opção Resolução de problemas](<../../.gitbook/assets/image (78).png>)

Em seguida escolha a opção de Linha de comando ou prompt de comando

![Opção prompt de comando](<../../.gitbook/assets/image (4) (1) (1) (1) (1).png>)

### Execute o diskpart

Quando inicializar o prompt de comando, inicie o programa **`diskpart`** e quando estiver no prompt `DISKPART>` execute o comando **`list volume`**.

```batch
diskpart
DISKPART> list volume
```

Será exibida uma tabela com os volumes do disco, observe qual o seu volume do windows através do nome do volume na coluna _Label_. Verifique também o volume de inicialização do windows, normalmente esse volume é formatado no formato **FAT32** e é um volume **Oculto**.

Vamos selecionar o volume de inicialização do windows

```batch
select volume #
```

Substitua o `#` pelo respectivo número do volume de inicialização do windows.

Vamos atribuir uma letra de unidade para que possamos acessar esse volume:

```batch
assign letter w
```

_Nota: A letra `w` pode ser substituída por qualquer outra que não esteja sendo usada, mas nesse caso adapte os comandos seguintes para a letra escolhida._

Agora basta sair do diskpart usando o comando **`exit`**

### Reparando o bcd boot

De volta ao prompt de comando, execute o seguinte comando:

```batch
bcdboot C:\Windows /s w: /f UEFI
```

_Nota: Caso o computador possua mais de um disco é possível que, no modo do prompt de comando de reparação, a unidade onde o windows está instalado esteja diferente de `c:\`. Você pode verificar se essa é a correta acessando a unidade e listando os arquivos com um comando `dir`. Caso seja diferente, no comando acima substitua o **`C:\`** pela respectiva volume onde o windows está instalado e o **`w:`** pela a letra que você atribuiu no `diskpart` para o volume de inicialização do windows._

Deverá ser exibida a mensagem de sucesso, caso contrário verifique as letras das unidades conforme _nota_ acima.

Após executado o `bcdboot` com sucesso, saia do prompt de comando através do comando **`exit`** e em seguida reinicialize o computador sem o pendrive de instalação do windows.

O computador irá inicializar normalmente, provavelmente irá exibir uma lista perguntando qual sistema operacional deseja inicializar, escolha uma das opções, caso não dê certo escolha a outra.

### Removendo a lista de sistemas operacionais

Caso a inicialização apresente uma lista de sistemas operacionais para escolher, ao entrar no windows execute a ferramenta **`msconfig`**, clique na segunda aba de **inicialização** e remova as entradas desnecessárias (exceto a entrada que foi usada para boot).

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Artigos relacionados" %}
* [Como baixar o arquivo ISO de instalação do windows 10](como-baixar-o-arquivo-iso-de-instalacao-do-windows-10-diretamente-do-site-da-microsoft/)
{% endtab %}
{% endtabs %}
