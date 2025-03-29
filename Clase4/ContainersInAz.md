# Az Commands para administrar Contenedores

### Login to AZ Account

```bash
az login
```

### Crear un Contenedor

```bash
az container create --resource-group myaci --image rudaruza/nginx:one --name acirudaruza --os-type Linux --memory 1.5 --cpu 1 --registry-login-server index.docker.io --registry-username rudaruza --registry-password <password> --ip-address Public --protocol TCP --ports 80
```

### Eliminar un contenedor

```bash
az container delete --name acirudaruza --resource-group myaci --yes
```

### Ingresar a un contenedor

```bash
az container exec --container-name acirudaruza --resource-group myaci --name acirudaruza --exec-command "/bin/bash"
```

### Listar contenedores

```bash
az container list --output table
```

### Crear un Contenedor con un az file share como volumen

```bash
az container create --resource-group myaci --image rudaruza/nginx:one --name acirudaruza --os-type Linux --memory 1.5 --cpu 1 --registry-login-server index.docker.io --registry-username rudaruza --registry-password "password" --ip-address Public --protocol TCP --ports 80 --azure-file-volume-account-name rudaruzastorage --azure-file-volume-account-key "volume-account-key" --azure-file-volume-share-name rudaruza --azure-file-volume-mount-path /usr/share/nginx/html/
```

### inspeccionar un ACI (equivale a docker inspect)

```bash
az container show --name acirudaruza --resource-group myaci
```
