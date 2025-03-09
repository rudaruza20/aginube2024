# Pasos para la habilitación de la cuenta de Azure for Students

1. Auntenticarse en <https://portal.azure.com> con un correo personal de hotmail / Outlook    <image src="/Clase1/Imgs/Autenticacion.png">    
2. Dirigirse a la sección EDUCACION / EDUCATION mediante la barra de búsqueda    <image src="/Clase1/Imgs/Educa&Subs.png">    
3. Dar click en botón "Suscríbase ahora"    <image src="/Clase1/Imgs/SusAZStudents.png">    
4. Llenar el formulario de validar estado de estudiante e introduzca el e-mail de la UTA *@.uta.edu.ec en el apartado de cuenta educativa
5. Revisar la bandeja de entrada de su cuenta de correo *@uta.edu.ec y dar click en enlace de verificación enviado por Microsoft
6. Comprobar estado de la suscripción        <image src="/Clase1/Imgs/Educa&Subs.png">     
    Ir a EDUCATION y comprobar el crédito disponible de 100 USD.    
    Ir a SUSCSRIPCIONES y comprobar que esté añadida la Suscripción de MS Azure for Students.    <image src="/Clase1/Imgs/Suscripcion.png">
7. Dar click sobre la SUSCRIPCIÓN e ir al menú CONFIGURACIÓN y luego a "USO y CUOTAS" y observar los recursos disponibles    <image src="/Clase1/Imgs/UsoYCuota.png"> 

# Instalación de Visual Studio Code
1. Bajar el software desde: <https://code.visualstudio.com>
2. Instalar 
3. Una vez instalado dirigirse a "Extensiones"
3. Buscar e instalar la extensión "Start git-bash"    
<image src="/Clase1/Imgs/Git-bashExt.png">
4. Abrir una Terminal de PowerShell 

# Instalación del Módulo de Azure Az en PowerShell tanto en local como en la Nube CloudShell
Referencia: <https://docs.microsoft.com/en-us/powershell/azure/install-az-ps?view=azps-7.3.2>
### Instalar el módulo a través del siguiente comando en PowerShell y CloudShell
```
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```
### Si ya tiene instalado lo puede actualizar mediante el siguiente comando
```
Update-Module -Name Az -Force
```
### Comprobar que está instalado el módulo con el siguiente comando
```
Get-InstalledModule
```
### Para ejecutar ciertos comando puede ser necesario luego importar librerias que les mostrará en pantalla el mismo error
```
Import-Module Az.Accounts
```
```
Import-Module Az.Resources
```