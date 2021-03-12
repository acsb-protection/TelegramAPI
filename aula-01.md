# AULA 01

Instalando Agente do Terraform

```text
sudo wget https://releases.hashicorp.com/terraform/0.12.5/terraform_0.12.5_linux_amd64.zip

sudo unzip ./terraform_0.12.5_linux_amd64.zip -d /usr/local/bin/

terraform -v
```

Instalando o Packer

```text
wget https://releases.hashicorp.com/packer/1.4.5/packer_1.4.5_linux_amd64.zip

sudo unzip ./packer_1.4.5_linux_amd64.zip

sudo mv packer /usr/local/bin

packer -v
```

**Terraform**  
Após fazer o clone do repositório alterar o arquivo connection.tf com suas credenciais da aws

```text
sudo git clone https://github.com/treinacloud/cloudcamp-devops.git

sudo terraform init

sudo terraform validate

sudo terraform apply
```



