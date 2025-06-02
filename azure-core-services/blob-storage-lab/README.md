# 📦 Azure Blob Storage Lab

## Objective

Deploy and test an Azure Storage Account, upload blobs, and manage container permissions.

## Steps

1. Create a Storage Account (Standard)
2. Create a container inside Blob service
3. Upload a file
4. Generate SAS token
5. Test access via shared URL

## Key Concepts

- Hot, Cool, and Archive tiers
- Redundancy: LRS, GRS, ZRS
- Access levels (private, blob, container)

# Azure Blob Storage Lab (AZ-900)

## ✅ Objective
Use Azure CLI and the Azure Portal to:
- Create a Storage Account
- Create a container
- Upload a blob (image)
- Configure access settings for public blob access

## 🔧 Key Steps
1. Created a new storage account (`thegithub`) in the West US region.
2. Created a private container (`thegithubcontainer`).
3. Uploaded a sample image of Wukong.
4. Attempted access — received `ResourceNotFound` error.
5. Changed container access level to `Blob`.
6. Successfully accessed the image via public URL.

## 💻 CLI Replication (Optional)
```bash
az group create ...
az storage account create ...
az storage container create ...
az storage blob upload ...
az storage container set-permission ...

