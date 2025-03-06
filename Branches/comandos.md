# Comandos
## `git branch -l o git branch (sin parámetros)`
Mostrar las ramas del repositorio.
## `git show-branch`
Mostrar las ramas del repositorio en detalle.
## `git branch (nombre de rama) (punto de inicio)`
Crear una rama.
Los nombres de las ramas **nunca** deben contener espacios, caracteres especiales o de control o "/" al final.
El punto de inicio se puede especificar con un [[tag]] o al menos 6 dígitos del hash de un commit. Si no se especifica, la rama se crea en base al último commit de la rama actual.

Usándolo en tándem con `git reset`, podemos corregir commits a ramas equivocadas para preservar el historial del proyecto.
El flujo sería (parado en develop/main):

`git branch work_in_progress`

`git reset --hard (commit sin problemas)`

`git checkout work_in_progress`
##  `git checkout (nombre de rama)`
Cambiar de rama.
> Si estás trabajando sobre una rama y decidís que querés pasarte a otra, es **muy** importante que hagas un commit o stash de **todos** los cambios que hayas efectuado en la rama actual.
> Git impide que te cambies de rama si los cambios que introduciste entran en conflicto con los de la rama destino, pero si no hay conflictos, vas a acarrear esas modificaciones a la rama destino.
## `git checkout -b (nombre de rama) (punto de inicio)`
Crear y cambiar de rama.
## `git branch -d (nombre de rama)`
Eliminar una rama.
## `git show (tag):(ruta del archivo)`
Ver los contenidos de un archivo dado un tag.
## `git checkout (tag) (ruta del archivo)`
Restaurar una versión anterior de un archivo.

