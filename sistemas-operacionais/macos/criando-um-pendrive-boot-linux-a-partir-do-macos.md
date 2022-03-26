---
description: >-
  Este artigo descreve o procedimento para criação de pendrive de boot linux a
  partir do terminal do MacOS
---

# Criando um pendrive boot linux a partir do MacOS

Visite a página da distribuição linux desejada e baixe a imagem **iso** da mídia de instalação. Neste artigo utilizaremos o [CentOS linux](https://www.centos.org/download/).

Abra o terminal e converta a imagem do formato **`iso`** para o formato que será gravado no [pendrive](https://amzn.to/3LzEIEP), utilizando o **`hdiutil`**:

```
hdiutil convert -format UDRW -o centos.img CentOS-7.0-1406-x86_64-Everything.iso
```

Identifique qual o caminho do [pendrive](https://amzn.to/3LzEIEP) onde você deseja gravar a imagem, isso pode ser feito através do `diskutil`:

```
diskutil list
```

O diskutil irá retornar informações sobre os discos conectados em sua máquina:

{% code title="retorno do diskutil" %}
```
/dev/disk0 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *500.3 GB   disk0
   1:                        EFI EFI                     209.7 MB   disk0s1
   2:                 Apple_APFS Container disk1         500.1 GB   disk0s2

/dev/disk1 (synthesized):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      APFS Container Scheme -                      +500.1 GB   disk1
                                 Physical Store disk0s2
   1:                APFS Volume RenatoSSD               359.1 GB   disk1s1
   2:                APFS Volume Preboot                 47.1 MB    disk1s2
   3:                APFS Volume Recovery                509.7 MB   disk1s3
   4:                APFS Volume VM                      4.3 GB     disk1s4

/dev/disk2 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *4.0 TB     disk2
   1:                        EFI EFI                     209.7 MB   disk2s1
   2:                  Apple_HFS 4TMN-CLOUD              4.0 TB     disk2s2

/dev/disk3 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:     FDisk_partition_scheme                        *15.7 GB    disk3
   1:               Windows_NTFS                         15.7 GB    disk3s1
```
{% endcode %}

Note que no caso acima o [pendrive](https://amzn.to/3LzEIEP) onde eu desejo instalar está localizado em **/dev/disk3**, é possível identificar isso pelo nome do volume (_NAME_) e também pelo  tamanho do volume (_SIZE_).

Agora vamos desmontar o [pendrive](https://amzn.to/3LzEIEP), lembre-se de substituir o **disk3** pelo equivalente do seu caso:

```
diskutil unmountDisk /dev/disk3
```

Uma vez desmontado, vamos utilizar o dd para gravar a imagem no [pendrive](https://amzn.to/3LzEIEP):

```
time sudo dd if=centos.img.dmg of=/dev/disk3 bs=1m
```

Após concluído, será possível realizar o boot usando o [pendrive](https://amzn.to/3LzEIEP) criado.

[Encontre agora as melhores ofertas de pendrive na amazon](https://amzn.to/3LzEIEP).
