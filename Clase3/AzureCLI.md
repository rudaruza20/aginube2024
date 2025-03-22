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
### Ver NSGs creados dentro de un RG
```
az network nsg list -g myRG -o table
```
### Ver reglas del NSG (Network security Group)
```
az network nsg rule list -g myRG --nsg-name myVMNSG -o table
```
### Añadir una regla en el NSG (Network security Group)
```
az network nsg rule create \
  --resource-group <NombreDelGrupoDeRecursos> \
  --nsg-name <NombreDelNSG> \
  --name <NombreDeLaRegla> \
  --priority <Prioridad> \
  --direction <Dirección> \
  --access <PermitirODenegar> \
  --protocol <Protocolo> \
  --source-address-prefixes <PrefijosDeOrigen> \
  --source-port-ranges <PuertosDeOrigen> \
  --destination-address-prefixes <PrefijosDeDestino> \
  --destination-port-ranges <PuertosDeDestino>
```
### Desplegar una VM mediante plantilla ARM
```
az deployment group create --resource-group <RG-name> --template-file 'templatevm.json' --parameters 'parameters.json'
```

