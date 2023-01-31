---
description: >-
  Este artigo descreve os procedimentos para solução do problema onde o windows
  cria um perfil temporário de usuário durante uma atualização automática.
---

# Windows 10: Todos os ícones da área de trabalho sumiram

## Causa provável

Este problema ocorre comumente quando ocorre o desligamento do computador durante a instalação de atualizações do windows. Sendo comum em notebooks cuja vida útil da bateria já está desgastada e por algum motivo o usuário desconectou da tomada sem saber que havia uma atualização em andamento.

## Diagnóstico

A solução descrita nesse artigo se aplica quando:

* É possível observar que os arquivos do usuário continuam no disco na pasta **C:\Users\\\[**_**usuario**_**]**
* Existe uma pasta temporária no diretório de dados dos usuários (**C:\Users**)
* Ao verificar o perfil do usuário do windows constatar que o login foi feito com um perfil temporário.

## Solução A - Reiniciar o computador 5 vezes

Nossa primeira recomendação nesses casos é que o computador seja reinicializado por completo **5** (**cinco**) vezes.

## Solução B - Alteração do registro

Caso o procedimento de reiniciar o computador cinco vezes não resolva o problema, será necessário realizar as seguintes alterações no registro:

* Abra o editor de registros `regedit`
* Localize a chave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
*   Localize a UUID do usuário corrompido&#x20;

    ```
    wmic useraccount where name='<USERNAME>' get sid
    ```
* Verifique se o usuário corrompido possui duas chaves de registro, sendo uma **`S-X-X-XX-UUID`** e outra **`S-X-X-XX-UUID.bak`** terminada em **.bak**.
* Exporte um arquivo **.reg** com os dados do registro antes de fazer qualquer alteração, para fins de backup.
* Poderá se observar que a chave com o uuid do usuário terá o valor `ProfileImagePath` apontando para o diretório **TEMP** ao passo que a chave terminada em .bak estará com o caminho correto do diretório do usuário.
* Renomeie a chave terminada em UUID para outro nome e renomeie a chave terminada em .bak removendo a terminação .bak.
* Reinicie o computador

Executados os procedimentos acima o perfil deverá estar corrigido com todos os dados do usuário de volta.

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}