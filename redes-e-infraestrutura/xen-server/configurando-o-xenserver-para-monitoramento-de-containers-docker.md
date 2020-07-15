---
description: >-
  Este artigo descreve como configurar o xenserver e uma vm linux centos para
  integração monitoramento de containers.
---

# Configurando o xenserver para monitoramento de containers docker

Antes de proceder a configuração, é necessário que pacote adicional de containers esteja instalado e funcionando no servidor xen, vamos habilitar esse componente no servidor xen.

## Instalando o pacote suplementar de containers no xenserver

```bash
wget [url_do_iso]
xe-install-supplemental-pack [arquivo_iso]
```

#### Onde baixar os pacotes suplementares:

* XenServer 6.5: [XenServer-6.5.0-SP1-xscontainer.iso](http://downloadns.citrix.com.edgesuite.net/10343/XenServer-6.5.0-SP1-xscontainer.iso)
* XenServer 7.0: [XenServer-7.0.0-xscontainer.iso](http://downloadns.citrix.com.edgesuite.net/11621/XenServer-7.0.0-xscontainer.iso)
* XenServer 7.2: [XenServer-7.2.0-xscontainer.iso](http://downloadns.citrix.com.edgesuite.net/11993/XenServer-7.2.0-xscontainer.iso)

Para outras versões, consulte o [site da Citrix](https://www.citrix.com/downloads/citrix-hypervisor/).

### Gerando uma chave SSH no servidor XEN

```bash
ssh-keygen
```

Consulte a chave ssh pública gerada e copie essa informação.

```bash
cat .ssh/id_rsa.pub 
```

## Instalando requisitos na VM CentOS

Conecte-se na VM CentOS via SSH e realize a instalação dos pré-requisitos:

### Instalando o docker e componentes requeridos pelo Xen

```bash
yum -y install docker nmap-ncat openssh-server
# Habilitar o serviço docker
systemctl enable docker.service
# Iniciar o serviço docker
systemctl start docker.service
```

### Instale o Xen guest-tools no CentOS

No XenCenter insira o dvd guest-tools.iso no drive da VM linux e, em seguida, execute via ssh:

```bash
# Montando o cd-rom
mount /dev/cdrom /mnt
# Acessando a pasta do instalador
cd /mnt/Linux/
# Executando o instalador
./install.sh
```

Após a instalação você deve **reiniciar** a VM.

### Criando usuário que o Xen utilizará para conexão à VM

Neste exemplo usaremos o usuário **dockermanager** mas esse pode ser substituído pelo nome de sua escolha.

```bash
# Criando o grupo docker
groupadd docker
# Criando o usuario dockermanager
useradd dockermanager
# Adicionando o usuario dockermanager ao grupo docker
usermod -aG docker dockermanager
```

### Cadastre a chave ssh pública do Xen no usuário

```bash
su dockermanager
mkdir -p ~/.ssh
echo "[chave-ssh-pub]" > ~/.ssh/authorized_keys
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
exit
```

## Conectando o servidor Xen a VM

Execute no servidor XEN, via SSH:

### Identificando o UUID da VM

```bash
xe vm-list
```

Precisaremos da informação uuid relacionada a VM Linux CentOS, substitua essa informação nos comandos seguintes.

### Preparando a VM para o monitoramento de containers do Xen

```text
xscontainer-prepare-vm -v [uuid_vm] -u [usuario_vm]
```

Após concluído o processo já será possível ver o monitoramento de containers no XenCenter, basta abrir o ícone **+** ao lado do nome da vm.

![Monitoramento de containers no XenCenter](../../.gitbook/assets/image%20%2810%29.png)

