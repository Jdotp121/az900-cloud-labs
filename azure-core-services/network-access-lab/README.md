# Network Access Lab (AZ-900)

## Objective
Configure a network security group (NSG) to allow HTTP (port 80) access to an Azure VM running Nginx.

## Key Steps
1. Verified VM public IP using Azure CLI.
2. Attempted to access the web server (curl + browser) — failed due to no HTTP access.
3. Checked existing NSG rules — only SSH (port 22) allowed.
4. Added new NSG rule `allow-http` to allow inbound on port 80.
5. Re-tested access — successfully viewed Nginx welcome page via curl and browser.

## Commands Used
```bash
az vm list-ip-addresses ...
curl --connect-timeout 5 http://$IPADDRESS
az network nsg rule list ...
az network nsg rule create ...

