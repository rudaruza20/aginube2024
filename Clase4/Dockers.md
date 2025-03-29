# Manual de Ejecución de Comandos Docker

## Despliegue de Contenedor
Para desplegar un contenedor con Docker, puedes usar los siguientes comandos:

```bash
docker run --name web-server1 -p 80:80 -d nginx
```    
```bash 
docker run --name web-server2 -p 81:80 -d nginx
```    

## Despliegue de Contenedor con Volumen
Si necesitas montar un volumen en el contenedor, utiliza el siguiente comando. Esto permite que el contenido del directorio local `${PWD}/web-sites` se sincronice con el directorio `/usr/share/nginx/html` dentro del contenedor:

```bash
docker run --name web-server3 -p 82:80 -v ${PWD}/web-sites:/usr/share/nginx/html -d nginx
```

## Gestión de Contenedores
Comandos útiles para gestionar contenedores:

- Ver contenedores en ejecución:
    ```bash
    docker ps
    ```

- Ver todos los contenedores (incluidos los detenidos):
    ```bash
    docker ps -a
    ```

- Ver todos los contenedores (equivalente a `docker ps -a`):
    ```bash
    docker container ls
    ```

- Inspeccionar los parámetros de un contenedor:
    ```bash
    docker inspect <container>
    ```

- Interactuar con un contenedor enviándole un comando (por ejemplo, `sh` o `bash`):
    ```bash
    docker exec -it <container> [sh, bash]
    ```

- Detener un contenedor:
    ```bash
    docker stop <container>
    ```

- Iniciar un contenedor detenido:
    ```bash
    docker start <container>
    ```

- Borrar un contenedor (debe estar detenido):
    ```bash
    docker rm <container>
    ```

- Copiar archivos o directorios desde/hacia un contenedor:
    ```bash
    docker cp origen destino (container:/path/)
    ```

## Crear un Archivo en Docker
Para crear un archivo dentro de un contenedor Docker, puedes usar el siguiente comando:

```bash
cat > index.html
```

## Desplegar Nginx con un Script en una VM Linux
Puedes desplegar Nginx en una máquina virtual Linux utilizando el siguiente script:

[Script de configuración de Nginx](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh)

## Crear una Imagen Personalizada desde un Contenedor en Ejecución
### A) Crear la Imagen
Para crear una nueva imagen personalizada desde un contenedor en ejecución, utiliza el siguiente comando:

```bash
docker commit 3f4c1c8d1234 mi_nueva_imagen:latest
docker images ls
```

### B) Publicar la Imagen en un Registro (Docker Hub)
Para publicar la imagen en Docker Hub, sigue estos pasos:

1. Inicia sesión en Docker Hub:
     ```bash
     docker login
     ```

2. Etiqueta la imagen:
     ```bash
     docker tag mi_nueva_imagen:latest usuario_dockerhub/mi_nueva_imagen:latest
     ```

3. Publica la imagen:
     ```bash
     docker push usuario_dockerhub/mi_nueva_imagen:latest
     ```
