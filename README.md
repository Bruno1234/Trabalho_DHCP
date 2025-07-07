# Projeto 

- Estrutura Terraform que provisiona localmente duas VMs usando KVM/libvirt, conectadas a uma rede virtual com DHCP, em que:
- Uma VM atua como servidor DHCP
- Outra como cliente DHCP
- Um roteador/gateway opcional pode ser configurado (simples forwarding + NAT)
  
# Pre-requisitos

sudo apt update && sudo apt upgrade -y
 sudo apt install -y \
  qemu-kvm \
  libvirt-daemon-system \
  libvirt-clients \
  virtinst \
  bridge-utils \
  virt-manager \
  dnsmasq-base \
  net-tools \
  cloud-image-utils \
  genisoimage
 sudo apt install -y unzip wget
wget https://releases.hashicorp.com/terraform/1.8.4/terraform_1.8.4_linux_amd64.zip
unzip terraform_1.8.4_linux_amd64.zip
sudo apt install genisoimage
wget https://cloud-images.ubuntu.com/focal/current/focal-server-cloudimg-amd64.img

# Execução passo-passo:
```
sudo su
virsh net-define gateway.xml
virsh net-start gateway
virsh net-autostart gateway
terraform init
terraform apply
```

# Equipe:
- Luis Eduardo
- Bruno Eduardo
- Joao Otavio

````mermaid
block-beta
columns 1
  db(("DB"))
  blockArrowId6<["&nbsp;&nbsp;&nbsp;"]>(down)
  block:ID
    A
    B["A wide one in the middle"]
    C
  end
  space
  D
  ID --> D
  C --> D
  style B fill:#969,stroke:#333,stroke-width:4px
```
