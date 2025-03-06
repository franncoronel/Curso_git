# Operaciones sobre archivos
## `git add (nombre_de_archivo)/(ruta_de_directorio)`
Guarda los blobs asociados a uno o más archivos al *object store* y agrega referencias a ellos al index.
Básicamente, estamos preparando los archivos y directorios que queremos confirmar como parte del repositorio.
Se usa tanto para agregar archivos nuevos como para introducir cambios a archivos ya existentes.
El flag -i permite elegir los archivos a agregar al stage de forma interactiva. El flag -u permite actualizar todos los archivos que git ya conoce.
Si estuvieramos preparando un commit sobre los cambios al estilo de una página web, podríamos agregar un patrón como \*.css para agregar todos los archivos de css al *stage*.
Dado un proyecto web, podríamos específicar un directorio como .../Features/ para agregar todos los features que hayamos agregado y los cambios a aquellos features ya existentes.
## `git rm`
Elimina uno o más archivos del *index*, pero no lo elimina del repositorio a menos que efectuemos un commit.
Si lo único que queremos es "bajar" un archivo del stage porque consideramos que no tiene nada que ver con el commit que estamos por efectuar, tenemos que ejecutar

`git rm arch1 --cached`
## `git mv`
Sirve para renombrar un archivo y agregar al archivo con su nuevo nombre al *stage*.
Por como funciona Git, esta operación es simple ya que implica modificar los metadatos del archivo, pero no su blob asociado. Como el contenido no cambia, es cuestión de actualizar una referencia.
Su sintaxis es:

`git mv nombre_viejo nombre_nuevo`
## `git ls-files`
Muestra los archivos que forman parte del *index*. Si quisieramos mostrar sólo los archivos que están sin rastrear, deberíamos ejecutar:

`git ls-files --others --exclude-standard`