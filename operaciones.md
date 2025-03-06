# Comandos y operaciones útiles
## Renombrar la rama master por main
Localmente, debemos ejecutar estos comandos:

`git checkout master`

`git branch -m master main`

Para sincronizar este cambio con la rama remota (obligatorio):

`git push -u origin main`

`git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main`
## Definir la identidad del autor de los commits
`git config user.name "Nombre Apellido"`

`git config user.email "correo@mail.com"`

Estos comandos son especialmente útiles si el repositorio en el que estamos trabajando requiere commits firmados. Esta información se agregará al pie del commit si ejecutamos:
`git commit -s`

Si queremos que esta configuración se aplique a **todos** los repositorios que creamos, hace falta agregar el flag `--global`.

Si quisieramos verificar nuestros datos en un repositorio específico, podemos ejecutar `cat .git/config` para mostrar el contenido del archivo de configuración del repositorio.
## `git gc`
Pasar el recolector de basura.

Sí! Git tiene una herramienta para compactar repositorios que han crecido mucho en tamaño.
## `git fsck`
Verificar errores en el repositorio.

En general, este comando busca objetos que se hayan quedado sin referencias.
## `git prune`
Eliminar objetos (commits, trees, blobs, tags) que ya no son accesibles desde ninguna rama o tag.

Podemos ejecutar `git prune -n` primero para verificar el *output* del comando, y luego ejecutar el mismo comando sin flags para efectivamente limpiar los objetos sin referencias de nuestro repositorio.
## `git blame`
Descubrir al responsable de una o más lineas o un archivo.