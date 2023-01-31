# SAMBA

## Modelos de arquivos de configuração

* [Configuração para compartilhamento de pasta pública e diretórios individuais do usuário.](https://github.com/rmbinformatica/bash-scripts/blob/main/config-exemplo/modelo\_pasta\_publica\_e\_usuarios-smb.conf)
* [Configuração para compartilhamento de pasta pública, diretórios individuais do usuário, pastas de grupos e restrição de acesso a subdiretórios específicos.](https://github.com/rmbinformatica/bash-scripts/blob/main/config-exemplo/modelo\_grupos\_e\_restricao\_subpastas-smb.conf)

## Restringindo o acesso de usuários a um subdiretório de um compartilhamento

Neste exemplo adotaremos a seguinte estrutura de pastas como exemplo:

* `diretorio`
  * `subdiretorio`
  * `pasta`

Considerando que o **`diretorio`** é a pasta que já está compartilhada com um determinado grupo de usuários **`grupo_pai`** e desejamos restringir o acesso a **`subdiretorio`** para parte desses usuários somente que serão especificados em **`grupo_subdir`**, o acesso a **`pasta`** e demais arquivos contidos em **`direitorio`** permanece a todos do grupo. Abaixo modelo do arquivo `smb.conf`:

```
[diretorio]
   path = /home/diretorio/
   valid users = @grupo_pai
   force group = grupo_pai
   browsable =yes
   writable = yes
   guest ok = no
   read only = no
   create mask = 0775
   directory mask = 0775
   
[subdiretorio]
   path = /home/diretorio/subdiretorio
   valid users = @grupo_subdir
   force group = +grupo_subdir
   browseable = no
```

Além das alterações do arquivo de configuração do samba, é necessário criar o grupo e adicionar os usuários no grupo do linux, bem como configurar as permissões da pasta, conforme comandos abaixo:

```bash
groupadd grupo_subdir
usermod -a -G grupo_subdir [usuario_com_permissao]
chgrp -R grupo_subdir /home/diretorio/subdiretorio
chmod 2770 /home/diretorio/subdiretorio
```

Comando especificado na linha **2** deve ser repetido para cada usuário que for ter acesso ao **`subdiretorio`**.

Por fim, vamos reiniciar o samba para aplicar as alterações.

```bash
systemctl restart smb.service
systemctl restart nmb.service
```

{% tabs %}
{% tab title="Autor" %}
<table data-card-size="large" data-view="cards"><thead><tr><th data-type="users" data-multiple></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td></td><td><p><strong>Renato Monteiro Batista</strong></p><p>Engenheiro de Computação</p></td><td></td><td><a href="../../.gitbook/assets/renato-monteiro-batista.jpeg">renato-monteiro-batista.jpeg</a></td><td><a href="http://renato.ovh">http://renato.ovh</a></td></tr><tr><td></td><td><em>Envie um pix</em></td><td>Se esse artigo te ajudou, colabore com nosso site enviando um pix.</td><td><a href="../../.gitbook/assets/qr-pix-largo.png">qr-pix-largo.png</a></td><td><a href="../../colabore-com-nosso-site.md">colabore-com-nosso-site.md</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}