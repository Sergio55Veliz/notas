# Sync Databricks in Local


Validar si existe Databricks en el sistema
``` bash
databricks -v
```

Ir a la carpeta que contiene la que queremos guardar el proyecto (cree una con antelación)
``` bash
cd C:\Users\sveliza\Documents\databricks_sync
cd..
```

### Configurar host
``` bash
# databricks configure --host [link de tu repositorio hasta .net]
# Ejemplo: (este es un link inventado)
databricks configure --host https://adb-2437910255562706.6.azuredatabricks.net
```

### Para obtener el foloder del proyecto de databricks
En tu *Workspace*...
1.  Accede a la carpeta de tu proyecto que deseas sincronizar (si recién lo estás creando, crea una nueva carpeta)
2. Da click en el menú de tres puntitos.
3. Da click en *Copiar URL/Ruta*.
4. Da click en *Ruta completa*
Ya tienes en tu porta papeles el path del folder de tu proyecto ubicado en Databricks. Ahora guárdalo en un lugar seguro para ser utilizado en los siguientes pasos.

### Obtener token
También necesitarás un token de databricks para la sincronización, para generarlo haz lo siguiente:
1. Da click en tu ícono de usuario
2. Click en "Ajustes". Te redirijirá a la ventana de *Ajustes*.
3. En la sección de *Usuario*, da click en *Desarrollador*.
4. Busca *Token de Acceso* y da click en el botón *Administrar*
5. Da click en el botón *Generar Nuevo Token*
6. En la ventana emergente que te sale, dale un nombre y el tiempo de visa útil.
7. Dale click a *Generar* y se te copiará en el porta papeles el token. Guárdalo en algún lugar que consideres seguro para que no se te pierda.

### Sincronizar código local a Databricks
En el siguiente paso puedes una de las siguientes dos cosas:
  1. Hacer un "One Shoot" que sería ejecutar la línea para guardar lo que se tiene ahora.
``` bash
    # databricks sync [local_folder] [folder_databricks_proyect]
    databricks sync .\databricks_sync\ /Workspace/Users/sveliza@bolivariano.com
```
  2. Ejecutar el *watch* para que en tiempo real se vaya guardando cualquier cambio que hagas
  La diferencia entre las líneas no es mucha.
``` bash
    # databricks sync [local_folder] [folder_databricks_proyect]
    databricks sync .\databricks_sync\ /Workspace/Users/sveliza@bolivariano.com --watch
```
Luego de ejecutar la línea de comando te pedirá ingreses el token. Si no te funciona en la terminal de VS Code, pruebalo en la terminal del cmd.


Si tienes el siguiente error, tu computador no tiene los permisos para conectarse a Databricks.
``` bash
Error: open C:\Users\sveliza\Downloads\c1-retail-banking\c1-retail-banking\databricks_sync\.gitignore: El sistema no puede encontrar la ruta especificada.
```

<br>


Si todo va bien, **ya tienes tu código sincronizado**.



