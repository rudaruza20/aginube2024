# Pasos para la habilitación de la cuenta de Azure for Students

1. Auntenticarse en portal.azure.com con un correo personal de hotmail / Outlook
![Descripción de la imagen](/Imgs/Autenticacion.png)
2. Dirigirse a la sección EDUCACION / EDUCATION mediante la barra de búsqueda
![Descripción de la imagen](/Imgs/Educa&Subs.png)
3. Dar click en botón "Suscríbase ahora"
![Descripción de la imagen](/images/SusAZStudents.png)
4. Llenar el formulario de validar estado de estudiante e introduzca el e-mail de la UTA *@.uta.edu.ec en el apartado de cuenta educativa
5. Revisar la bandeja de entrada de su cuenta de correo *@uta.edu.ec y dar click en enlace de verificación enviado por MS
6. Comprobar estado de la suscripción
    ![Descripción de la imagen](/Imgs/Educa&Subs.png)
    Ir a EDUCATION y comprobar el crédito disponible de 100 USD
    Ir a Suscripciones y comprobar que esté añadida la Suscripción de MS Azure for Students

# Instalacion de Visual Studio Code
1. Bajar el software desde: <https://code.visualstudio.com>
2. Instalar 
3. Una vez instalado dirigirse a "Extensiones"
3. Buscar e instalar la extensión "Start git-bash"
![Descripción de la imagen](/Imgs/Git-bash.png)
4. Abrir una Terminal de PowerShell 

# Instalación del Módulo de Azure Az en PowerShell tanto en local como en la Nube CloudShell
Referencia: <https://docs.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-7.3.2>
## Instalar el módulo a través del siguiente comando en PowerShell y CloudShell
```
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```
## Si ya tiene instalado lo puede actualizar mediante el siguiente comando
```
Update-Module -Name Az -Force
```
## Comprobar que está instalado el módulo con el siguiente comando
```
Get-InstalledModule
```
## Para ejecutar ciertos comando puede ser necesario luego importar librerias que les mostrará en pantalla el mismo error
```
Import-Module Az.Accounts
```
```
Import-Module Az.Resources
```