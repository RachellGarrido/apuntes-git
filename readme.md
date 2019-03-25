#Apuntes Git desde 0

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
* git commit -m ""  (Comentario de cambios)
* git log           (Ver cambios y registros)
* git diff          (ver cambios del archivo en terminal)
* git diff --staged (Ver cambios entre archivo preparado y work)
