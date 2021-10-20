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

