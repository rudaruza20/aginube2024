# Guía de Instalación de OwnCloud Server en Debian 12

Esta guía detalla los pasos necesarios para instalar la última versión de OwnCloud Server en un sistema Debian 12.

## Requisitos Previos

1. **Sistema Operativo**: Debian 12 actualizado.
2. **Privilegios**: Acceso a una cuenta con privilegios de superusuario (`sudo`).
3. **Software**:
    - Servidor web Apache.
    - PHP 8.1 o superior.
    - Base de datos MySQL/MariaDB o PostgreSQL.

## Pasos de Instalación

### 1. Actualizar el Sistema
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Instalar Dependencias
```bash
sudo apt install apache2 mariadb-server libapache2-mod-php php php-mysql php-xml php-mbstring php-curl php-zip php-intl unzip wget -y
```

### 3. Configurar la Base de Datos
1. Iniciar sesión en MySQL:
    ```bash
    sudo mysql -u root -p
    ```
2. Crear una base de datos y un usuario:
    ```sql
    CREATE DATABASE owncloud;
    CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'password_seguro';
    GRANT ALL PRIVILEGES ON owncloud.* TO 'ownclouduser'@'localhost';
    FLUSH PRIVILEGES;
    EXIT;
    ```

### 4. Descargar OwnCloud
1. Descargar la última versión de OwnCloud:
    ```bash
    wget https://download.owncloud.org/community/owncloud-complete-latest.tar.bz2
    ```
2. Extraer el archivo:
    ```bash
    tar -xjf owncloud-complete-latest.tar.bz2
    ```
3. Mover los archivos al directorio web:
    ```bash
    sudo mv owncloud /var/www/html/
    ```

### 5. Configurar Permisos
```bash
sudo chown -R www-data:www-data /var/www/html/owncloud
sudo chmod -R 755 /var/www/html/owncloud
```

### 6. Configurar Apache
1. Crear un archivo de configuración para OwnCloud:
    ```bash
    sudo nano /etc/apache2/sites-available/owncloud.conf
    ```
2. Agregar el siguiente contenido:
    ```apache
    <VirtualHost *:80>
         ServerAdmin admin@example.com
         DocumentRoot /var/www/html/owncloud
         ServerName your-domain.com

         <Directory /var/www/html/owncloud>
              Options +FollowSymlinks
              AllowOverride All
              Require all granted
         </Directory>

         ErrorLog ${APACHE_LOG_DIR}/owncloud_error.log
         CustomLog ${APACHE_LOG_DIR}/owncloud_access.log combined
    </VirtualHost>
    ```
3. Habilitar la configuración:
    ```bash
    sudo a2ensite owncloud.conf
    sudo a2enmod rewrite
    sudo systemctl restart apache2
    ```

### 7. Completar la Instalación
1. Acceder a OwnCloud desde el navegador: `http://your-domain.com`.
2. Seguir las instrucciones en pantalla para completar la configuración.

### 8. Configuración Adicional (Opcional)
- **Habilitar HTTPS**:
  Instalar y configurar un certificado SSL con Let's Encrypt:
  ```bash
  sudo apt install certbot python3-certbot-apache -y
  sudo certbot --apache
  ```

## Conclusión
OwnCloud Server debería estar instalado y funcionando en tu sistema Debian 12. Asegúrate de realizar pruebas y configurar copias de seguridad periódicas.
