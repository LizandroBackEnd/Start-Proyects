<div align="center">  
<img src="./assets/Logo.png" width="200"> 
<h1> Start Proyects BackEnd </h1> 
📅 Creation Date: 09/05/24 
</div> 
 
## Index 




- [Descripción](#🎯-descripción)  
- [ProcketBase](#pocketbase) 
- [Python y django](#python-y-django)  
- [Docker](#docker)  
- [Laravel](#laravel) 


  

# 🎯 Descripción

Documentación para poder hacer una buena estructura de proyectos BackEnd, así como el uso de los comandos correctos para crear un proyecto en los diferentes sistemas operativos.

# PocketBase   

<h3> Start proyect Windows </h3> 
 
- Abrir el programa de PocketBase, para ver lo comandos que puedes ejecutar 
```bash
./pocketbase.exe
```   
 
- Para arrancar el servidor lo tienes que hacer con el siguiente comando 
```bash
./pocketbase.exe serve
```   
Lo cual te debe de arrojar algo como lo siguiente 
```bash
2024/05/10 10:55:21 Server started at http://127.0.0.1:8090
├─ REST API: http://127.0.0.1:8090/api/
└─ Admin UI: http://127.0.0.1:8090/_/
```   
<h4> 💡 Rutas</h4> 
  
`Server` Esta es la dirección http principal donde se debe de configurar el proyecto <br>
`REST API` Esta es la dirección http donde se puede interactuar con aplicaciones cliente <br> 
`Admin UI` Esta es la dirección donde se encuentra el panel de administración, un panel que te proporciona PocketBase
 

# Python y Django  

<h3> Start proyect Windows </h3>  
 

- Crear entorno virtual, para que los modulos que descargues se instalen y este disponibles solo para el proyecto, de esa forma evitar de que instalen de forma global y así poder trabajar con diferentes versiones
```bash
python -m virtualenv env
``` 
 
- Activar entorno virtual 
```bash
env/Scripts/activate
``` 
 
- Instalar `Django` en el proyecto  
```bash
pip install django
```   
 
- Crear las carpetas para el proyecto, donde primero se creará el `proyecto` y después la `aplicación`
```bash
django-admin startproject name . 
django-admin startapp name
```  
 
- Arrancar sevidor local 
```bash
python manage.py runserver
```  

- Desactivar entorno virtual 
```bash
deactivate
``` 

🕯️Nota: Se recomienda crear un archivo con el nombre de `requirements.txt` y ejecutar el siguiente comando para agregar todas las dependencias y modelos de tu proyecto, para que así si alguien más usa el proyecto se pueda descargar todas las cosas que usaste.   

```bash
pip freeze > requirements.txt
``` 
Al igual que se debe de hacer un `.gitignore` y agregar la carpeta del entorno virtual y la base de datos, para que así solo se suba a `GitHub` lo importante  

```bash
env/ 
db.sqlite3 
``` 
 
# Docker 
 
Para ver las imagenes que tienes instaladas en tu ordenador ahi que ejecutar el comando: 
  
```bash
docker image list 
```  
 
- Lo que debe de dar algo como lo siguiente: 
 
```bash
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
debian        latest    5027089adc4c   4 days ago      117MB
hello-world   latest    d2c94e258dcb   12 months ago   13.3kB 
```  
 
- Para crear un contenedor de docker se tiene que ejecutar el siguiente comando: 
 
```bash
docker container create --name debian-test debian
```  
💡 NOTA: Tienes que pasarle un nombre y obligatoriamente le tienes que pasar una imagen  
 
- Ver todos lo contenedores que tienes parados 
```bash
docker container list --all
```  
 
- Arrancar un contenedor de docker 
 
```bash
docker container start name-container
``` 
- Para poder crear el contenedor y que bash no te de problemas es importante que la terminal reconozca los comandos y sepa que esta la existencia de un tty. 
```bash
docker container create --interactive --tty --name debian-console debian
```  
 
`STDIN` = interactive <br>
`tty`  = interfaz de terminal
 
 
> [!IMPORTANT]
> Se le tiene que pasar el nombre de la imagen del contenedor. 
  
  
- Ejemplo de como te puedes montar el contenedor: 
```bash
docker start -i debian-console
```  

```bash
root@ff56024a869f:/# ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
root@ff56024a869f:/# ls --color=auto
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
```   
 
`ls --color=auto`  = Hace que se te acomode la terminal de modo que puedas leerlo mejor. 
 

- Para salir de la consola  
```bash
root@ff56024a869f:/# exit
```  
 
🕯️ Pasos para arrancar un contenedor 
 
 
`1. docker image pull` <br>
`2. docker container create` <br>
`3. docker container start` 
 
- Todos estos comandos pueden ser automatizados por el siguiente comando: 
```bash
docker container run --iteractive --tty --name fedora-container fedora
```  
 
- Versión más corta: 

```bash
docker container run -it --name fedora-container fedora
```  

<div class="notecard warning">
  <p><strong>Advertencia:</strong> Para poder borrar un contendor puedes hacer uso del siguiente comando: </p>
</div>

```bash 
docker container remove id o name container 
```  
- Versión más corta: 
```bash
docker rm id o name container
```   
 
<div class="notecard warning">
  <p><strong>Advertencia:</strong> Para poder borrar todos los contenedores parados por alguna razon puedes hacer uso del comando:</p>
</div>
 
```bash
docker container prune
```  
<div class="notecard warning">
  <p><strong>Advertencia:</strong> Para poder borrar un contenedor que esta iniciado puedes hacer uso del siguiente comando: </p>
</div> 

```bash
docker rm -f id o name container
```  
 
`Donde f` = significa `force`   
 
- Para ver la imagenes que tienes puedes hacer uso del siguiente comando: 
```bash
docker images
```  

<div class="notecard warning">
  <p><strong>Advertencia:</strong> Para poder borrar una imagen puedes hacer uso del siguiente comando:</p>
</div> 
 
```bash
docker images rm id o name image
```  
 
- Version mas corta: 
```bash
docker rmi  id o name image
``` 
 
 

## Laravel 
  
- Crear proyecto de Laravel 
 
```bash
composer create-project laravel/laravel name-proyect 
``` 

🕯️ Para checar que te esta funcionando php con composer en el proyecto, puedes ejecutar el siguiente comando: 
```bash
php artisan
```  
  
Si te salen una serie de comandos quiere decir que esta bien. 
 
- Arrancar el server 
 
```bash
php artisan serve
``` 