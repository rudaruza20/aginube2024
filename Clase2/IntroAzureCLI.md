# Introducción a Azure CLI
## Comando PowerShell y Bash equivalente
### Autenticarse en el portal de Azure con la suscripción correspondiente
```
Connect-AzAccount
```    
```
az login
```
### Listar los grupos de recursos existentes
```
Get-AzResourceGroup
```    
```
az group list -o table
```
### Listar las máquinas virtuales existentes
```
Get-AzVM
```    
```
az vm list -o table
```