Autores:

Amos: [amoraldo@gmail.com](amoraldo@gmail.com)<br>
Casescas: [casescas@gmail.com](casescas@gmail.com)


# **Contenido**

||Link|
|-----------|-----------|
|Introducción a Git y Git| 1|
|Ejemplo práctico 0 de Git y GitHub|2|


### #1 Introducción a Git - Amos

##### Listado de comandos básicos en Git:

||||
|-----------|-----------|---------|
|Locales:|||
||Consulta:||
|||git<br>git status<br>git log<br>git branch|
||Iniciazación:||
|||git init<br>git config --global user.name “Tu_nombre_aqui”<br>git config --global user.email “Tu_email_aqui@example.com”|
||Utilización:||
|||git add .<br>git commit -m “mensaje para el comiteado”<br>git checkout master<br>git diff<br>git merge|
|Remoto:|||
||Consulta:||
|||git remote -v|
||Iniciazación:||
|||git remote add origin git@github.com:deigocmartin/demo-git.git<br>git push -u origin master|
||Utilización:||
|||git fetch<br>git pull<br>git push<br>git clone|

##### Referencias y links de #1

* git site: [https://git-scm.com/](https://git-scm.com/)
* git tutorial: [https://git-scm.com/docs/gittutorial](https://git-scm.com/docs/gittutorial)
* git tutorial español: [https://www.diegocmartin.com/tutorial-git/](https://www.diegocmartin.com/tutorial-git/)

<VOLVER A CONTENIDO>

### #2 Ejemplo practico 0 de Git y GitHub – Amos

Comenzamos con un ejemplo bien práctico de como introducirnos en Git y GitHub

Primero deberemos instalarlo en nuestro sistema. Desde el sitio oficial, [https://git-scm.com/](https://git-scm.com/) lo descargamos e instalamos.
Tanto en Windows como en Linux abrimos una terminal y probamos escribiendo: 

    git

Debería respondernos con la ayuda por línea de comandos
Configuramos nuestro nombre de usuario y correo electrónico, de manera de identificarnos a la hora de compartir el material

    git config --global user.name “Andres”
    git config --global user.email “andres@email.com.ar”

Ahora si, navegamos hasta el directorio donde crearemos nuestro primer proyecto. Yo lo pondré dentro de ~/Documentos/Proyectos/HolaMundo$

    >cd ~/Documentos/Proyectos/HolaMundo
    ~/Documentos/Proyectos/HolaMundo>

1) Iniciamos nuestro proyecto con el comando “git init”

    
    ~/Documentos/Proyectos/HolaMundo>git init

Esto nos creará una carpeta oculta .git, donde guardara la información de nuestro proyecto
Una vez iniciado, generamos algo de material de nuestro proyecto.
En nuestro caso, hacemos un archivo de texto llamado “HolaMundo.txt”. Dentro pondremos el siguiente contenido:

>Este es un archivo de prueba

y guardemos el archivo.
Hagamos uso de dos comandos de git: add y commit. El primero adicionara el o los archivos (con “.” adiciona todos los cambios) y el segundo realizara la actualización de los mismos.


    ~/Documentos/Proyectos/HolaMundo>git add .
    ~/Documentos/Proyectos/HolaMundo>git commit -m “mi primer commit" 
    
Agrego el archivo HolaMundo.txt”

podemos experimentar con el comando log, status, branch y ver que nos devuelve en cada caso.

    ~/Documentos/Proyectos/HolaMundo>git log
    ~/Documentos/Proyectos/HolaMundo>git status
    ~/Documentos/Proyectos/HolaMundo>git branch

Para tener en cuenta, estamos dentro de la unica rama creada (master)

Ahora realizamos un cambio a nuestro archivo “HolaMundo.txt”. El contenido sera el siguiente 

>Este es mi archivo de prueba Hola Mundo<br>
>Bienvenido

Una vez guardado debemos saber que nuestro contenido actualizado sera diferente al contenido que hemos subido. Si lo queremos actualizar, usaremos nuevamente add y commit

    ~/Documentos/Proyectos/HolaMundo>git add .
    ~/Documentos/Proyectos/HolaMundo>git commit -m “Hago cambios cordiales en HolaMundo.txt”

Ahora cuando hacemos un git log veremos dos versiones disponibles. Para movernos entre versiones usamos checkout y el numero de commit que nos aparece (no hace falta escribir todo el numero. Es suficiente con los primeros 7 u 8 caracteres del código)
Identificaremos donde estamos parados porque encontraremos la palabra HEAD luego del numero de commit

    ~/Documentos/Proyectos/HolaMundo>git checkout 282c6730

luego de cada checkout podemos ver como cambia el contenido de nuestro archivo “HolaMundo.txt”

Hagamos un cambio mas visible: crearemos una carpeta en nuestro directorio. En Windows usaremos “md Archivador” o en Linux “mkdir Archivador”. Luego haremos el backup de los cambios

    ~/Documentos/Proyectos/HolaMundo>mkdir Archivador
    ~/Documentos/Proyectos/HolaMundo>git add .
    ~/Documentos/Proyectos/HolaMundo>git commit -m “Cambios en la estructura de directorio”

Haciendo un checkout veremos como aparece y desaparece la carpeta que creamos en cada versión de nuestro proyecto

    ~/Documentos/Proyectos/HolaMundo>git checkout 282c6730
    ~/Documentos/Proyectos/HolaMundo>git checkout 8c995882

2) Demos un paso mas: Ahora crearemos una rama de nuestro proyecto, es decir, una desviación. Para esto, usaremos branch.


    ~/Documentos/Proyectos/HolaMundo>git branch “develop”

Ahora tenemos dos proyectos, cada uno con su control de cambios. Luego veremos que podremos volver a juntarlos en un único proyecto. Si usamos git branch, veremos en que rama nos encontramos parados. Con un checkout nos podremos también mover entre ramas.


    ~/Documentos/Proyectos/HolaMundo>git branch 
    ~/Documentos/Proyectos/HolaMundo>git checkout “master”
    ~/Documentos/Proyectos/HolaMundo>git checkout “develop”

Recordemos volver a la rama “develop” antes de continuar. Ahora hagamos un nuevo cambio, por ejemplo crearemos un nuevo archivo de texto, pegaremos una imagen o cualquier cambio que se nos ocurra dentro de la carpeta “Archivador”

Si saltamos de una rama a otra, veremos los cambios

    ~/Documentos/Proyectos/HolaMundo>git checkout “master”
    ~/Documentos/Proyectos/HolaMundo>git checkout “develop”

3) Ahora pasemos a realizar un repositorio remoto, es decir, ya no solo estará dentro de nuestra pc, sino que también estará dentro del repositorio de github.
Para esto, entraremos al sitio de github (www.github.com) y nos crearemos una cuenta.
Por linea de comandos a nuestro proyecto le diremos cual sera nuestro repositorio remoto:


    ~/Documentos/Proyectos/HolaMundo>git remote add origin git@github.com:amoraldo/BookCommunity/Demos.git

Si en algún momento quisieramos consultarlo, utilizaremos la opcion -v

    ~/Documentos/Proyectos/HolaMundo>git remote -v

Una vez configurado, podemos subir nuestros cambios a GitHub

    ~/Documentos/Proyectos/HolaMundo>git push origin develop

##### Referencias y links de #2

* git site: [https://git-scm.com/](https://git-scm.com/)
* git tutorial: [https://git-scm.com/docs/gittutorial](https://git-scm.com/docs/gittutorial)
* git tutorial español: [https://www.diegocmartin.com/tutorial-git/](https://www.diegocmartin.com/tutorial-git/)

<VOLVER A CONTENIDO>
