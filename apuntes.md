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


## Etiquetas y marcadores (Se ordena en alfabético)

1. ligeras: git tag marcador (se agrega el último commit, uso básico)

2. anotadas: git tag -a etiqueta -m "commit" (Se guardan en BD como un objeto entero y contiene el nombre, email, fecha y mensaje del editor)

* git show _____    (etiqueta, commit etc, el comando muestra el git)

* git tag etiqueta e4fba8c (Para tagger en un punto diferente)