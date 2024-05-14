<div align="center">  
<img src="./assets/Logo.png" width="200"> 
<h1> Start Proyects BackEnd </h1> 
📅 Creation Date: 09/05/24 
</div> 
 
## Index 




- [Descripción](#🎯-descripción)  
- [ProcketBase](#pocketbase) 
- [Python y django](#python-y-django) 
  

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
