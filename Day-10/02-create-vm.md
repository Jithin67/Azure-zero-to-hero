# Create VM using Azure CLI

### Start with creating a Resource Group

```
az group create --name learn-azure-cli --location eastus
```

### Set the Resource Group as default (Optional)

```
az config set defaults.group=learn-azure-cli
```

### Create VM with Vnet

```
# Set Variables
$resourceGroup = "JK_RSG"
$vmName = "TutorialVM1"
$image = "Ubuntu2204"
$vnetName = "JK_Vnet"
$subnetName = "JK_Subnet"
$adminUsername = "adminuser"  # Replace with your chosen valid username

# Run Azure CLI Command
az vm create `
    --resource-group $resourceGroup `
    --name $vmName `
    --image $image `
    --vnet-name $vnetName `
    --subnet $subnetName `
    --admin-username $adminUsername `
    --generate-ssh-keys `
    --output json `
    --verbose
```

### Delete the Resource Group to delete all the resources

```
az group delete --name learn-azure-cli
```

