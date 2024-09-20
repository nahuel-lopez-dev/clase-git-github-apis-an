<section id="inicio" align="center">
    <h1>Git, GitHub e Introducción a las APIs</h1>
    <img src="./analitica_noviembre_logo.jpg"/>
    <h2 align="center">Bootcamp de <a href="https://analiticanoviembre.com.ar/">Analítica Noviembre</a></h2>
</section>


<h3><a>Para la mejor comisión de alumnos de Analítica Noviembre</a></h3>

### Tabla de contenidos:

- [**Información del proyecto**](#información-del-proyecto)
- [**Git**](#git)
  - [Introducción a Git](#introducción-a-git)
  - [git status](#git-status)
  - [Comandos de ayuda](#comandos-de-ayuda)
  - [Sobre la configuración](#sobre-la-configuración)
    - [Configuración global (única vez):](#configuración-global-única-vez)
    - [Comprobaciones:](#comprobaciones)
  - [Cambiar el nombre de la rama](#cambiar-el-nombre-de-la-rama)
  - [Actualizar Git a la última versión (en Windows)](#actualizar-git-a-la-última-versión-en-windows)
  - [Comenzar a trabajar con Git](#comenzar-a-trabajar-con-git)
  - [Crear repositorio](#crear-repositorio)
  - [Agregar al stage](#agregar-al-stage)
  - [Sacar del Stage](#sacar-del-stage)
  - [Guardar los cambios con commit](#guardar-los-cambios-con-commit)
  - [Modificar mensaje del commit:](#modificar-mensaje-del-commit)
  - [Sobre el historial de los commits](#sobre-el-historial-de-los-commits)
  - [Revertir commit:](#revertir-commit)
  - [Flujo normal de trabajo para arrancar con Git:](#flujo-normal-de-trabajo-para-arrancar-con-git)
  - [Sobre Ramas](#sobre-ramas)
  - [Viajes en el tiempo:](#viajes-en-el-tiempo)
  - [Crear Alias](#crear-alias)
- [**GitHub**](#github)
  - [Introducción a GitHub](#introducción-a-github)
  - [Comandos más utilizados:](#comandos-más-utilizados)
  - [Clonar un repositorio](#clonar-un-repositorio)
  - [Fork en un repositorio](#fork-en-un-repositorio)
  - [Métodos de trabajo en equipo:](#métodos-de-trabajo-en-equipo)
    - [Git Flow](#git-flow)
    - [Cómo colaborar en la rama de un colega de equipo:](#cómo-colaborar-en-la-rama-de-un-colega-de-equipo)
- [**Introducción a las APIs**](#introducción-a-las-apis)
- [**Agradecimientos**](#agradecimientos)
- [**Información adicional**](#información-adicional)
- [**Autor**](#autor)


## **Información del proyecto**

Proyecto para la clase de Git, GitHub e Introducción a las APIs del Bootcamp de Analítica Noviembre.\
Los contenidos en esta clase son sobre Git, GitHub e Introducción a las APIs.\
Para trabajar con Git y GitHub, el enfoque está puesto en el uso de la terminal, con explicaciones teóricas añadidas para una mejor claridad del uso de los comandos utilizados.\
Para la introducción a las APIs, hay un notebook preparado con material teórico práctico. 

De forma general, los contenidos a tratar serán:

`Git`

- Introducción a Git
- Configuraciones iniciales
- Iniciar el seguimiento con Git
- Agregar archivos al stage
- Commitear los cambios
- Sacar del Stage
- Modificar nombre del commit
- Ver el historial de commits
- Deshacer un commit
- Manejo de branches

`GitHub`

- Introducción a GitHub
- Repositorio en GitHub
- Crear repositorio
- Hacer Push
- Hacer Pull
- Markdown y README.md
- Clonar proyecto
- Forkear proyecto
- Adicional: 
    - Gist
    - Projectos en GitHub
  
`Introducción a las APIs`

- Introducción a las APIs, teoría.
- Consumir APIs con Request

`Actividades de la clase:`

- Actividad Individual:
  
1) Configuraciones iniciales en Git, user & email
2) Crear repositorio, agregar al stage y commitear
3) Subir proyecto a GitHub
4) Crear README y pushear los cambios
5) Hacer pull


- Actividad grupal (grupos de 4 o 3):

1) Uno crea repositorio, otros clonan.
   - Agregar colaboradores
   - Cada uno crea archivo_NombreAlumno y pushea
   - Cada uno hace git pull para tener las actualizaciones


## **Git**

### Introducción a Git

Git es un es un sistema de control de versiones. 
Utiliza comandos en su versión para la terminal.

Para realizar el control de versiones, maneja tres estados que permiten identificar el seguimiento en el que se encuentra un archivo.
Cuando se inicializa un proyecto con Git (git init), se encuentran sin registrar, luego existe una posterior etapa de agregar al stage (git add) donde quedarán listos para ser guardados, y la última donde se guardan los cambios subidos al stage (git commit) que es como capturar una foto del momento en el que se encuentra nuestro proyecto. 

Para saber en qué estado estamos trabajando:

- 1° estado: no registrados pero con seguimiento, con git init  (U: Untracked)
- 2° estado: ya registrados, con git add (A: Added)
- 3° estado: ya guardados (con git commit, aunque requiere previo registro con el git add)

Luego cuando se modifique un archivo, aparecerá la M para indicar que el archivo ha sido modificado.

Enlace a la página de Git:\
[Página Oficial de Git](https://git-scm.com/)

### git status 

Muestra en que rama estamos trabajando, el estado de los archivos, que archivos han sido modificados y no se registraron los cambios (no pasaron al stage "escenario", porque no se les hizo git add), y los que si están listos para "sacarse la foto" porque se registraron (pasaron al stage con git add) y están listos para ser "comiteados" con git commit.\
Si los archivos están en rojo no se registraron los cambios o fueron modificados "no están en el stage".\
Si están en verde, ya se registraron (pasaron al stage) y están listos para guardarse con git commit.\
Si los archivos ya fueron commiteados (todos los cambios fueron registrados y guardados), entonces al hacer git status debería decir:\
        
        on branch master
        nothing to commit, working tree clean

Esto quiere decir que todos los archivos con sus modificaciones han sido registrados y guardados, y que estamos en la rama master.


### Comandos de ayuda

Para conocer la versión de Git

    git --version 
    
    git -v (forma corta)

Para tener información de los comandos
    
    git help 
    
    git help config
    
Para tener información de un comando en particular

    git help <nombredelcomando> 


### Sobre la configuración

#### Configuración global (única vez):

Para configurar el nombre

    git config --global user.name "name or alias" 

Para configurar el email

    git config --global user.email "email" 

Como es muy parecido, se puede usar la tecla arriba para que vuelva a aparecer.

#### Comprobaciones:

Comprueba que valor tiene la clave nombre de usuario:
    
    git config user.name 

Comprueba que valor tiene la clave email:

    git config user.email 

Lista la configuración global, el email y el nombre:

    git config --global -l

lista configuraciones, el email y el nombre:

    git config --list
  
Abre el editor por defecto para modificar la información de la configuración:

    git config --global -e 

En terminal, muestra toda la configuración y permite hacer modificaciones si se toca la tecla "a" porque lo pone en modo escritura. Se sale con ESC y luego :q!
Si se hicieran cambios y se quieren guardar sería ESC y luego :wq!
Si está vinculado a un editor de código como el VSC, se abrirá este para realizar las modificaciones

### Cambiar el nombre de la rama

Para cambiar el nombre de la rama por defecto: 
Viene como master, pero por una cuestión cultural se está utilizando main.

    git config --global init.defaultBranch <name> 


### Actualizar Git a la última versión (en Windows)

Para actualizar Git a su última versión en windows por medio de la terminal:

    git update-git-for-windows

---

### Comenzar a trabajar con Git

Para empezar a trabajar con un proyecto o archivo:
    
    cd + espacio + arrastrar la carpeta desde la consola o una terminal

    Abrirlo desde un editor es otra forma


### Crear repositorio

Para iniciar el seguimiento con git, se debe crear el repositorio local: 
Indica que en ese directorio donde estamos ejecutando el comando, se usará git (que se crea como un archivo invisible .git)

    git init 

Luego de esto, nuestra carpeta o proyecto pasa a llamarse repositorio, porque tiene seguimiento de Git.


### Agregar al stage

Agregar al stage todos los archivos:
(se agregan al stage = se registran)

    Tres maneras de hacer lo mismo:
    
    git add . 
    git add --all 
    git add -A 

Agregar al stage un archivo específico:

    git add <archivo> 

Agregar al stage todos los archivos que están en una carpeta:

    git add css/ 
    git add notebooks/

Agregar al stage todos los archivos del proyecto de un determinado tipo:

    git add ".txt"
    git add .py 

Agregar al stage todos los archivos del directorio actual con extensión de un determinado tipo:

    git add *.png 
    git add *.txt 
    git add *.ipynb
    git add *.py

Agregar todos los archivos de una determinada extensión dentro de una carpeta en específico:

    git add notebooks/*.ipynb  

### Sacar del Stage

Sacar todos los archivos del Stage

    git reset

Para sacar del stage el archivo

    git reset <nombredelarchivo>

Sacar del registro a todos los archivos con una determinada extensión:

    git reset *.py
    git reset *.js 


### Guardar los cambios con commit

Genera un registro histórico de los cambios que sucedieron en el escenario en ese preciso momento "saca la foto" y guarda ese momento.

    git commit -m "mensaje breve y claro de lo que se está guardando" 

Agregar al stage y hacer commit a la vez:
(Manda al stage y comitea a la vez)

    git commit -am "mensaje" 

    
Notar: 

hacer el registro o agregar al stage es git add que es distinto a "sacar la foto" y guardar los cambios de ese preciso momento con git commit.

git add es el paso previo a git commit
Aunque se pueden hacer juntos con git commit -am "mensaje"
si no se le agrega el mensaje, la consola o terminal da la posibilidad de escribirlo al momento siguiente de forma inmediata

### Modificar mensaje del commit:

Arreglar mensaje del último commit:
    
    git commit --amend -m "mensaje nuevo"

### Sobre el historial de los commits

Para ver el historial de cambios:

Mostrar todo el historial de cambios en nuestro repositorio, desde el cambio más reciente al más antiguo "como una línea de tiempo", mostrando los códigos de los commits realizados. con :q se sale de la pantalla creada con la información:

    git log 

Mostrar el historial de cambios de una forma más breve, indicando los códigos de los commits realizados:

    git log --oneline 

Mostrar el historial de cambios de todas las ramas de una forma breve, indicando los commits realizados, pero con cierta decoración de asteriscos, para agregarle estilo y una mejor visualización

    git log --oneline --decorate --all --graph


### Revertir commit:

Se utiliza:
reset soft o reset hard | HEAD^ o hash del commit
    
El símbolo ^ apunta al último commit, si quisiéramos apuntar al anteúltimo commit para eliminarlo sería:\
git reset --soft HEAD^2 que indica del head dos commits atrás, y así sucesivamente se le pueden ir agregar números para llevar esa referencia.\
En casos donde esto no sea práctico, puede reemplazarse el HEAD por el hash del commit al que hace referencia para indicarlo explícitamente.

Usando reset --soft, se elimina el commit pero queda la modificación efectuada por este. Hay que deshacerla.

Eliminar el último commit con reset --soft

    git reset --soft HEAD^

Deshacer los commits hasta uno en particular. Si se quiere eliminar uno en particular, hay que apuntar al anterior.

    git reset --soft <hash del commit>

Usando reset --hard, se elimina directamente hasta el commit que se indica.

Eliminar el último commit con reset --hard

    git reset --hard HEAD^

Deshacer los commits hasta uno en particular. Si se quiere eliminar uno en particular, hay que apuntar al anterior.

    git reset --hard <hash del commit>

Volver los commits eliminados, incluso con reset --hard

    git reflog

Aclaración:\
Nada se elimina realmente de Git, van quedando los registros de las modificaciones que se commitean. La única forma de borrarlo todo, es eliminando el archivo .git que da seguimiento al repositorio.

---

### Flujo normal de trabajo para arrancar con Git:

Ya estando en posicionado en el proyecto, o el archivo, desde la consola o alguna terminal:

Iniciar el repositorio local, sólo en caso que no estemos trabajando con un repositorio que ya tiene seguimiento:
    
    git init 

Mostrar en qué rama estamos trabajando, que archivos han sido modificados, y cuales están listos para sacarse la foto:

    git status 

- Si todavían no se registraron con git add se ven en rojo. 
- Si ya se registraron están en verde

Agregar los cambios al stage:

    git add . 

Para todo lo que está en la carpeta o git add archivo.xxxx (para un archivo específico) ... lo que hace es "ponerlo en el escenario, listo para la foto (que hace el registro)"

Commitear los cambios en el stage para guardarlos:

    git commit -m "mensaje del commit" 

Saca la foto. Genera un registro histórico de los cambios que sucedieron en el escenario en ese preciso momento 

---

### Sobre Ramas 

Una rama es una línea de tiempo de nuestros commits.

Para saber el nombre de la rama actual:

    git branch 

Para ver todas las ramas que hay
    
    git branch -a

Para crear una rama:

Es una copia del proyecto en una línea paralela a nuestro trabajo, que permite trabajarlo en ese historial de cambios sin modificar el original. Luego, esta rama paralela se puede fusionar, si queremos, con el proyecto en la rama master o main (nuestra línea original de trabajo y el principio de la creación)

    git branch <nombre de la rama> 

Para modificar el nombre de la rama principal master a main. 
Muy importante para trabajar con github y la forma que se viene adoptando (dejando de lado master por main):

    git branch -M main 

Para borrar la rama: 
Si fusionamos la rama con la línea master o main, lo más probable es que después querramos borrar la rama, que no se va cuando se fusionan ambas líneas de trabajo a no ser que la borremos.

    git branch -d <nombre de la rama> 

Para cambiar a la rama que previamente creamos y empezar a trabajarla.
        
    git checkout <nombre de la rama>

Para crear la rama y cambiar a la rama creada, es una combinación de git branch con git checkout:

    git checkout -b <nombre de la rama>

Fusiones de ramas:

Para fusionar una rama con la línea principal ya sea master o main:

Para fusionar se requiere estar ubicado en la rama donde se quieren incorporar los cambios, por lo que si estamos trabajando en la línea de la rama main, primero debemos pasar a la línea main con git checkout main. Luego se puede "mergear" con este comando.

    git merge <nombre de la rama>


### Viajes en el tiempo:

Para "volver en el tiempo" el trabajo que teníamos hecho se debe utilizar el número de identificación del commit (Lo obtenemos con algún git log). Esto permite volver al punto de nuestro trabajo dondea había quedado con ese commit en específico. Ej: con git log --oneline vemos que el commit al que queremos ir es: 
        
    id commit 125021 

Entonces para ir a ese commit sería: 

    git checkout 125021 

y volvemos el trabajo a ese commit.

En general para regresar a cualquier punto de nuestro trabajo utilizaremos el hash del commit de esta forma:

    git checkout <id commit> 

Para regresar al último commit:

Si por alguna razón se llegara a borrar todo el trabajo, este comando permite recuperarlo todo al último commit realizado.

    git checkout -- .  


### Crear Alias

Crear alias es útil para tener shortcuts de los comandos que utilicemos a diario y resulten largos de escribir o bien simplemente queramos acortarlos por comodidad, como en los siguientes ejemplos:

Ejemplo 1:

    git config --global alias.lg "log --oneline --decorate --all --graph"

Con eso al hacer git lg va a hacer lo mismo que si ejecutaramos:

    git log --oneline --decorate --all --graph

Ejemplo2:

    git config --global alias.s "status -s -b"

Con eso ahora al hacer git s va a hacer lo mismo que si ejecutaramos:

    git status -s -b o lo que es lo mismo git status -sb


## **GitHub**

### Introducción a GitHub

¿Qué es GitHub?\
GitHub es mucho más que una plataforma para alojar nuestros proyectos y realizar un desarrollo colaborativo.\
GitHub es una plataforma de desarrollo de software que permite almacenar, compartir y trabajar en proyectos de código abierto, pero también permite una forma de hacer networking entre desarrolladores de todo el mundo, generar una carta de presentación al mundo IT, y aprender de proyectos avanzados y bien documentados. 
Hoy en día en GitHub se encuentran tantos proyectos pequeños como soluciones complejas con grandes documentaciones, y repositorios que alojan miles de recursos para estudiar y aprender de forma autodidacta.

Entre sus principales características, se encuentran: 
 
- Almacenar el código en repositorios 
 
- Compartir el trabajo 
 
- Seguir y administrar los cambios en el código 
 
- Intercambiar archivos de código 
 
- Trabajar en proyectos colaborativos 
 
- Instalar la plataforma en servidores particulares para mayor seguridad y privacidad 
 
- Conectar desarrolladores con usuarios para colaborar en la mejora de las aplicaciones 
 
GitHub también cuenta con un entorno de desarrollo integrado llamado "Codespace", que permite editar, depurar, ejecutar y realizar acciones del sistema de versiones sin necesidad de clonar el repositorio. 

Además de esto, tiene una integración online con el editor de código Visual Studio Code, para poder hacer modificaciones desde el mismo repositorio.

El truco es posicionarse en el nombre del repositorio y tocar la tecla que contiene el punto en el teclado. Con eso se abre el editor.

Enlace a la plataforma de GitHub:\
[GitHub](https://github.com/)

> Importante:\
En el archivo .gitignore se suelen ignorar todos aquellas carpetas con archivos que no deseamos subir a GitHub, ya sea porque contiene información sensible como contraseñas, o bien porque son carpetas con dependencias que bien pueden recrearse de forma local.
Ejemplo de esto es la carpeta node_modules de Node, o el venv del virtual enviroment de Python, los users y passwords de bases de datos, etc.

Primera vez:

1. Crear el repositorio en github con start a project o new repository
2. En la consola, git bash, o alguna terminal:
cd + espacio + dirección del rep.
3. Copio la primer línea que empieza así:
git remote add origin ... 
Ej : git remote add origin https://github.com/Nahuel-DevOne/initializr.git
4. git branch -M main para modificar el nombre de la rama master a main, que es una opción que considera GitHub. Este paso no es necesario si ya trabajo con rama main. 
5. git push -u origin main (o el nombre de tu rama) por única vez, sólo cuando se hace el primer git push al repositorio. Luego, todas siguientes subidas a GitHub son sólo con git push.

El -u permite que se configure por defecto el origin main, de forma que no sea necesario repetir git push -u origin main, sino sólo git push

### Comandos más utilizados:

Para llevar el proyecto a GitHub:

    git push origin <nombre de la rama> (sólo por el primer push)
    
    git push (luego del primer push, los demás serán git push)

Para traer los cambios del proyecto en GitHub a nuestro repositorio local:

    git pull 

Para traer todo y las referencias de otras ramas:

    git pull --all 

Para ver el path al que apunta el repositorio:

    git remote -v


### Clonar un repositorio

    git clone + <enlace al repositorio> + nombre opcional si lo queremos cambiar para clonar un repositorio

Con esto clonamos un proyecto con todo el historial de los commits.

Tener en cuenta:
Desde GitHub es posible descargar el proyecto, pero no es lo mismo que clonar, ya que no traerá todo el historial de los commits, ni el seguimiento de Git que se ha realizado. Al descargarlo, lo que se trae es el proyecto como está en ese momento, sin seguimiento de Git.


### Fork en un repositorio

Al forkear un repositorio, es posible trabajar y hacerle modificaciones a este que pasa a ser un arbol que está de nuestro lado. Generalmente se utiliza para traer el repositorio a nuestro GitHub, hacerle alguna implentación que busquemos o veamos que necesita, y eso habilita a que hagamos un pull request al propietario del proyecto para que acepte nuestras modificaciones si así lo desea.
También es útil forkear proyectos que son públicos y muy famosos por sus utilidades, como Public Apis para guardar información valiosa que otras personas hicieron. Estas contribuciones aceleran el desarrollo y es recomendado dar al menos una star en estos proyectos como señal de agradecimiento.

También es una forma de trabajo, para hacer modificaciones sin tocar el proyecto original, y mediante pull request sugerir las nuevas integraciones.

### Métodos de trabajo en equipo:

#### Git Flow

Trabajo en ramas paralelas a la rama main o master o la rama de trabajo como sea que se llame.

- Crear repositorio local

        git clone <ruta>

- Crear rama de trabajo con la información de la rama principal o la rama de la cual se tiene la información desde donde partir

        git checkout -b <BranchName> <BranchMain o Branch principal>

        Para asegurar el pull de la rama principal a la rama donde vamos a trabajar:

        git pull origin <BranchMain o Branch principal>

- Si es necesario:

        git pull --all

- Para ir trabajando los avances y llevarlos a GitHub
Ya uno está parado en su branch con el comando anterior por lo que se debe hacer

        git add .

        git commit -m "tu mensaje de avance"

- Por única vez en el primer push

        git push --set-upstream origin <YourBranchName>

Luego los demás push serán solo 

    git push

Para integrar los commits que se realizan en nuestra rama a la rama main, se debe hacer por medio de pull request. Luego, desde la rama main se realiza el merge de este pull request, controlando los cambios y resolviendo los conflictos si es que los hubiera.

- Para mergear los cambios entre la rama de trabajo de uno y la rama principal o una rama de trabajo previa a la main

#### Cómo colaborar en la rama de un colega de equipo:

    git fetch

    git branch -a

    git checkout <RamaDelColega>

De esta forma se accede a trabajar en la rama de un colega de equipo.


## **Introducción a las APIs**

¿Qué es una API?

Explicación

Códigos de errores más comunes:

- un error
- otro error


## **Agradecimientos**

Agradecimientos a Analítica Noviembre por el espacio brindado para dar estos temas.

Agradecimientos a los alumnos por su participación.

## **Información adicional**

LinkedIn de [Analítica Noviembre](https://www.linkedin.com/company/analitica-noviembre/)

Plataforma de [Analítica Noviembre](https://www.linkedin.com/company/analitica-noviembre/)


## **Autor**

<div>
  <p>¡Hola, mi nombre es <b><i>Nahuel</i></b> 👋🏽!! <br></p>
  <p>Soy de Buenos Aires (Argentina) y tengo formación en Desarrollo con Python, Ingeniería y Ciencia de Datos. Me desempeño como Data Engineer en una empresa consultora, aunque en mi trabajo diario hago tanto ingeniería de datos como ciencia de datos, machine learning y desarrollo con Python.
  <br>Amo el mundo de los datos pero también el desarrollo. <br>Actualmente, estudio Ingeniería en Sistemas, y en mis momentos libres dedico gran parte de mi tiempo a seguir aprendiendo nuevas tecnologías, como así también a practicar y reforzar mi stack como Ingeniero de Datos.</p>
</div>

Si quieres saber más sobre mí, puedes ir a mi perfil de GitHub:

[![GitHub Profile](https://img.shields.io/badge/GitHub:-Nahuel_Lopez_Dev♾️-05122A?flat&logo=github&logoColor=white&labelColor=343941)](https://github.com/nahuel-lopez-dev)
  
💬 Siéntete libre de ponerte en contacto conmigo:

[![Contact Me](https://img.shields.io/badge/Gmail-informational?flat&logo=Mail.Ru&logoColor=fff&color=c6362c)](mailto:nahuel.developer1@gmail.com)&nbsp;
[![LinkedId](https://img.shields.io/badge/LinkedIn-informational?flat&logo=linkedin&logoColor=fff&color=0274b3)](https://www.linkedin.com/in/nahuel-developer/)&nbsp;
[![Linktree](https://img.shields.io/badge/-Linktree-323330?flat&logo=linktree&logoColor=#41e45f)](https://linktr.ee/nahuel.lopez)


[![Inicio](https://img.shields.io/badge/Ir_al_inicio:-Wingardium_Leviosa!🪄-343941?flat&logo=markdown&logoColor=white&labelColor=05122A)](#inicio)

<div align="center">
  <p>Desarrollado con 💙 por <i><b>NaLo Dev♾️</b></i></p>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=C2D9F8&height=80"/>
