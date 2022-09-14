# **Git Cheat-Sheet**

> ## Tabla de Contenido
> 1. Instalar
> 2. Configurar herramientas
> 3. Crear repositorios
> 4. Hacer cambios
> 4. Ramas
> 5. El archivo .gitignore
> 6. Hacer cambios
> 7. Glosario
## Instalar
Repositorio en la nube GitHub

[GitHub](https://github.com/)

Sistema de Control de Versiones para todas las plataformas

[Git](git-scm.com)

## Configurar herramientas
> Configurar la información de usuario para todos los repositorios locales

Establece el nombre que desea adjuntar a sus transacciones de confirmación

`$ git config --global user.name "[name]"`

Establece el correo electrónico que desea adjuntar a sus transacciones de confirmación

`$ git config --global user.email "[email address]"`

## Crear repositorios
> Se puede crear un nuevo repositorio localmente o se puede clonar un repositorio existente. Cuando un repositorio se inicializó localmente, debe enviarlo a GitHub después.



El comando git init convierte un directorio existente en un nuevo repositorio Git dentro de la carpeta en la que está ejecutando este comando. 

`$ git init`

Después de usar el comando `git init`, vincule el repositorio local a un repositorio de **GitHub** vacío usando el siguiente comando:

$ git remote add origin [url]

> Especifica el repositorio remoto para su repositorio local. La URL apunta a un repositorio en **GitHub**.

Clonar (descargar) un repositorio que ya existe en GitHub, incluidos todos los archivos, ramas y confirmaciones

`$ git clone [url]`

## Hacer cambios
> Explore e inspeccione la evolución de los archivos del proyecto

Muestra el historial de versiones de la rama actual

`$ git log`

Enumera el historial de versiones del proyecto

`$ git log `

Instantáneas del archivo en preparación para el control de versiones

`$ git add [file]`

Registra instantáneas de archivos de forma permanente en el historial de versiones

`$ git commit -m "[descriptive message]"`

## Sincronizar cambios
> Sincronice su repositorio local con el repositorio remoto en GitHub.com

Descarga todo el historial de las ramas de seguimiento remoto

`$ git fetch`

Combina ramas de seguimiento remoto en la ramas local actual

`$ git merge`

Carga todas las confirmaciones de ramas locales en GitHub

`$ git push`

Actualiza su rama de trabajo local actual con todas las confirmaciones nuevas de la rama remota correspondiente en GitHub. git pulles una combinación de git fetchygit merge

`$ git pull`

## Ramas
> Las ramas son una parte importante del trabajo con Git. Cualquier compromiso que realice se realizará en la rama en la que actualmente está "desprotegido". Use `git status` para ver qué rama es esa.

Crea una nueva rama

`$ git branch [branch-name]`

Cambia a la rama especificada y actualiza el directorio de trabajo

`$ git switch -c [branch-name]`

Combina el historial de la rama especificada en la rama actual. Esto generalmente se hace en las solicitudes de incorporación de cambios, pero es una operación importante de Git.

`$ git merge [branch]`

Elimina la rama especificada

`$ git branch -d [branch-name]`

## El archivo .gitignore
> A veces puede ser una buena idea excluir archivos del seguimiento con Git. Esto normalmente se hace en un archivo especial llamado `.gitignore`. Puede encontrar plantillas útiles para archivos `.gitignore`  en [github.com/github/gitignore](github.com/github/gitignore).



## Glosario
**git** : un sistema de control de versiones distribuido de código abierto

**GitHub** : una plataforma para hospedar y colaborar en repositorios Git

**commit** : un objeto Git, una instantánea de todo su repositorio comprimido en un SHA

**rama o branch** : un puntero móvil ligero a una confirmación

**clon** : una versión local de un repositorio, incluidas todas las confirmaciones y ramas

**remoto** : un repositorio común en GitHub que todos los miembros del equipo usan para intercambiar sus cambios

**fork** : una copia de un repositorio en GitHub propiedad de un usuario diferente

**pull request** : un lugar para comparar y discutir las diferencias introducidas en una rama con revisiones, comentarios, pruebas integradas y más

**HEAD** : en representación de su directorio de trabajo actual, el puntero HEAD se puede mover a diferentes ramas, etiquetas o confirmaciones cuando se usagit switch
