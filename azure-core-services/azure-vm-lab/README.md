# 🧪 Azure Virtual Machine Lab

## Objective

Learn to deploy a Linux Virtual Machine via the Azure Portal, configure networking, and connect via SSH.

## Steps

1. Create a Resource Group
2. Launch a VM using Ubuntu LTS
3. Configure NSG for port 22
4. Connect via SSH
5. View VM metrics (CPU, disk)

## Key Concepts

- Regions and Availability Zones
- Virtual networks and subnets
- Public vs private IPs
- Inbound port rules

## Screenshots
Screenshots of VM deployment, NSG setup, and terminal connection go here → `/screenshots/`

# 🧪 Azure Virtual Machine Lab

## ✅ Objective

Learn how to deploy a Linux VM on Azure using the **Azure CLI**, enable secure SSH access, and install **NGINX** via a custom script extension.

---

## 🛠️ Tools Used

- Azure Cloud Shell (Azure CLI)
- Ubuntu 22.04 LTS Image
- SSH key pair (auto-generated)
- NGINX setup via Microsoft Extension

---

## 📌 Steps Performed

### 1. Create a Linux VM using Azure CLI

```bash
az vm create \
  --name my-vm \
  --resource-group learn-abc123 \
  --public-ip-sku Standard \
  --image Ubuntu2204 \
  --admin-username azureuser \
  --generate-ssh-keys

- This also generated SSH keys at:

~/.ssh/id_rsa and ~/.ssh/id_rsa.pub

- VM created successfully and returned a public IP of:

52.159.235.105

2. Install NGINX with a Custom Script Extension

az vm extension set \
  --resource-group "learn-abc123" \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'

Result:
The NGINX installation script ran successfully and provisioned the server.

