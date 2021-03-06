#Apuntes Git desde 0
Git es un sistema de control de versiones para el mantenimiento eficiente y confiable de archivos.


##Estados de Git

1. Working Directory:   Raiz del proyecto.
2. Staging Area     :   Archivos preparados para cambios.
3. .Git Repository  :   Cambios confirmados.

Flujo de trabajo básico en Git

1. Modificar archivos en el directorios.
2. Preparar archivos.
3. Confirmar los cambios de los archivos en preparación se almacena la copia de manera permanente en git.

## Configurando GIT

* CMD > git -- version
* [Instalar-git] htttp://www.git-scm.com

### Configuración básica de Git.

nombre: git config --global user.name "Nombre"
        git config user.name

email:  git config --global user.email "correo"
        git config user.email

editor: git config --global core.editor editorcmd
        git config core.editor

## Revisar configuraciones

* git config --list
* git config --list | grep filtro

### ayuda

* git help config   
* git config --help


## Guardando cambios en el repositorio

### Iniciar repositorio 
* git init                  (En la carpeta seleccionada por la CMD)
* git status                (Revisar archivos de la carpeta)
* git add file.extension    (Añadir el archivo a la preparación)

### Crear punto en la historia
* git commit -m ""          (guarda los archivos ya preparados)
* git log                   (Ver cambios y registros)
* git diff                  (ver cambios del archivo en terminal)
* git diff --staged         (Ver cambios entre archivo preparado y work)
    
* git add .                 (Agrega todos los archivos a preparación)
* git reset HEAD file.ext   (Quita un archivo del área de preparación)
* git add -A                (Agrega todos los archivos en seguimiento al área de preparación)

* git commit -a -m          (Guarda los archivos ya preparados y todos los archivos rastreados, saltando el área de preparación)


## Borrando archivos

* git rm file               (Elimina archivos rastreados del repositorio )
* git checkout -- <file>    (Recupera un archivo borrado y deshace los cambios de x archivo)

## Renombre

* git mv fromfile fileto    (renombrar archivos)
Equivalente a:
1. renombrar el archivo manualmente.
2. git rm para eliminar el archivo
3. git add para agregar el archivo con el nuevo nombre

# Git ignore (Patrones de nombres que git ignorará)

* gitignore.io
* Crear un archivo gitignore.md y dentro tipear los archivos a ignorar.


## Git log

* git log --oneline (Muestra el historial en lineas abreviado)
* git log --graph   (Añade gráfico ASCII mostrando el historias de ramificación)
* git log --oneline --graph
* git log -numero (Permite filtrar el historial de los últimos cambios)

* git log --pretty=format:"%h - %an, %ar : %s"  (Formateado de texto para ver el historial) (hash autor fecha referencial texto)

* git log --after="2019-03-26"  (Filtro log por fecha despues de)
* git log --before="2019-03-26"  (Filtro log por fecha) antes de)
* git log --after="2019-03-26" --before="2019-03-26" (entre)

## Rehacer confirmación

* git commit --amend    (Abre la última confirmación y le permite realizar cambios en el texto incluido)

## clonar repositorio

* por GitHub descargar el zip

* git clone url  nombre-opcional (Descargar repositorio por https y cmd)


##salto en la historia

* git diff commit commit (git diff 457eb8f 4800dsk) (En rojo lo borrado, verde lo agregado)

* git checkout commit (volver los cambios)

* git checkout master (volver al presente)

* git checkout etiqueta (ir a una etiqueta)


## Etiquetas y marcadores (Se ordena en alfabético)

1. ligeras: git tag marcador (se agrega el último commit, uso básico)
2. anotadas: git tag -a etiqueta -m "commit" (Se guardan en BD como un objeto entero y contiene el nombre, email, fecha y mensaje del editor)
* git show _____    (etiqueta, commit etc, el comando muestra el git)
* git tag etiqueta e4fba8c (Para tagger en un punto diferente)
* git tag -l "patron" (filtra las etiquetas por el patrón 
buscado)

* git tag -d etiqueta    (borrar la etiqueta)


## Ramas de Git

Son apuntadores móviles (las etiquetas igual) que nos indican a que rama pertenece el commit
La rama máster es por defecto y no más importante que otras.
Se pueden crear nuevas ramas y nombrarlas.
(Testing,estable, v.1, marchablanca)
HEAD siempre nos indica donde estamos parados en la historias.

* Git branch --help     (ayuda)
* Git branch nombreRama (nueva rama)
* Git checkout rama     (moverse a la rama)
* git checkout -b rama  (crear y moverse a la rama)

* git branch            (muestra las ramas y la posición actual)
* git branch -v         (Muestra el último commit de cada rama)

## Fusiones de git 

* git merge nombre-rama (fusionar rama a la principal)
* git branch -d          (elimina la rama si ya ha sido fusionada)
* git branch -D         (Elimina la rama a la fuerza)
* git branch --no-merged  (Muestra las ramas que no hemos fusionado aún)
* git branch --merged   (muestra las ramas ya fusionadas, y no borradas)

* Si hay problemas de compatibilidad ya que cada archivo modifica cada linea en las ramas, la solución es borrar las lineas de aviso, o cambiar el archivo y hacer un commit.

###¿Volver a la rama?
* git checkout commit
* git checkout -d nombrerama

# GitHub

##Subir a GitHub
* pasos:
1. Crear nuevo repositorio.
2. Indicar carácteristicas.
3. subir repositorio (local) con git remote add origin (en el proyecto local)
4. git push origin master (indicar la rama a subir)

### git remote add origin
* https://github.com/RachellGarrido/apuntes-git

### git push origin master  (subimos la rama a gh)
* Se sube la rama al proyecto.

### Fork para copias y clonar el proyecto después.

## Pasos para aportar 
1. Hacer fork en GitHub.
2. Clonar el repositorio desde mi cuenta de GitHub.
3. Crear una rama local.
4. Realizar mis cambios en mi nueva rama local.
5. confirmar los cambios realizados en local.
6. Hacer push de mis cambios(Enviar commits a github) git push origin nombrerama
7. Crear un pull request con la nueva rama de mi respositorio en github.
8. Esperar que el admin del repositorio original acepte mis cambios

* Desde admin, hay que jalar los cambios a nuestro proyecto local.
1. git fetch origin master
2. git merge origin master

* (Mezclar los cambios desde GH)

### otros remotos
* git remote --verbose
* git remote add user urlgithub
* git remote add origin


##Otras Herramientas
* SourceTreeApp
* Github
* Gitlab
* Bitbucket

# Flujo lógico.

1. Crear proyecto Git.
2. Hacer commits correspondientes.
3. Crear nuevas ramas para commits carácteristicos.
4. Hacer merge de las ramas a master.
5. Subir a GitHub.

# Llaves SHH

1. Crear carpeta Key local (c:)
2. comando git para generar la llave
    * ssh-keygen -t rsa -C "Email"
    * folder /keyname_sra
3. Mostrar la llave en git bash
    * cat /folder/folder/keyname_rsa.pub
4. Copiar y pegar la llave en github.

## activar en cmd

1. añadir llave: ssh de github a remote add.
2. activar agente (para push): eval "$(ssh-agent -s)"
3. añadir llave: ssh-add /folder/folder/github_rsa

##Otros apuntes
* git rebase : merge lineal.
* git stash : cambios provisionales
* git cherry-pick : cambiar commit de rama

* Usar GitHub como host.
