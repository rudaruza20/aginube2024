# Administración por Azure CLI
### Ver información de la cuenta
```
az account show
```
### Listar los grupos de recursos creados en AZ
```
az group list -o table
```
### Crear grupo de recursos
```
az group create -l <region-name> -n <rg-name>
```
### Crear VM dentro de un RG
```
az vm create \
--name <vm-name> \
--resource-group <rg-name> \
--image <so-image> \
--location <region> \
--admin-username <username> \
--admin-password <username-pwd>
```
### Ver parámetros de configuración detallados de la VM
```
az vm show --resource-group <MyResourceGroup> --name <MyVm> --show-details
```
### Apagar una VM
```
az vm stop -g myRG -n myVM
```
### Iniciar una VM
```
az vm start -g myRG -n myVM
```
