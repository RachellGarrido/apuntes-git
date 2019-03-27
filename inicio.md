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
* git checkout -- <file>    (Recupera un archivo borrado)

## Renombre

* git mv fromfile fileto    (renombrar archivos)
Equivalente a:
1. renombrar el archivo manualmente.
2. git rm para eliminar el archivo
3. git add para agregar el archivo con el nuevo nombre

# Git ignore (Patrones de nombres que git ignorará)

* gitignore.io

* Crear un archivo gitignore.md y dentro tipear los archivos a ignorar.