# Operaciones sobre repositorios remotos

## Definir el repositorio remoto/origen

`git remote add origin protocolo://sitio.web/ruta/del/repositorio`

Si definimos el valor de *origin* antes de comenzar a trabajar con un repositorio remoto, podemos simplificar muchos de los comandos explicados 
en este artículo, ya que se usará esta url para pedir y enviar actualizaciones por defecto.

## Crear una copia local de un repositorio remoto

Esta operación se realiza con el comando: 

`git clone (git://url del repositorio)`

No es necesario inicializar un repositorio de git en la carpeta destino, este comando se encarga de hacerlo.
El protocolo git:// es el más rápido, pero no es el único que se puede utilizar para clonar un repositorio. Podemos usar ssh://, https://, rsync://, etc...

La opción --no-hardlinks le indica a git que no cree hard links al clonar un repositorio **local**. Los hard links ahorran espacio de almacenamiento pero acoplan a los dos repositorios cuando quizás queremos mantener su independencia.

## Actualizar la copia local

Con git `git show-ref` y `git ls-remote` podemos observar el contenido del directorio .git/refs, que indica los distintos objetos almacenados en el *object store*. Si notaramos que el repositorio remoto contiene objetos que no están en la copia local, podríamos sincronizar ambas versiones con `git pull`

`git pull origin rama` simplifica la operación de actualización del repo local, realizando dos operaciones en un solo paso:

`git fetch`

`git merge origin/rama`

Si no le pasamos parámetros, efectúa el merge sobre la rama en la que estamos ubicados al ejecutar.
## Enviar cambios locales al repositorio remoto

Antes de enviar una actualización al repositorio remoto, es importante asegurarnos que nuestros cambios locales estén organizados en commits y que el proyecto no tenga archivos basura.
Hecho este paso, ejecutamos:

`git push git://url.remota/ruta/del/repo.git rama_a_actualizar`

Se puede obviar la url si definimos el repositorio remoto previamente, y si no especificamos la rama, se actualizará a la rama análoga a nuestra rama actual.

## Hacer que nuestro repositorio local esté disponible para otros desarrolladores

Podemos clonar un proyecto local agregando la opción `--bare` para crear una copia del *repositorio* de Git al que otros usuarios conectados a la misma red pueden enviar cambios o traerlos desde él.

Para que otros desarrolladores puedan clonar este repositorio a través red es necesario configurar el *git daemon*.
Primero hay que instalar el servicio Git daemon.
Una vez instalado, creamos un archivo git-daemon-export-ok en el directorio principal.
Ejecutamos el servicio con:

`git daemon &`

Y ahora es posible clonar nuestro repositorio ejecutando:

`git clone (ip.pública:/ruta/del/directorio)`

Para habilitar la función `git push` a nuestro repositorio, debemos agregar las líneas
```
[daemon]
receivepack = true
```
al archivo de configuración del repositorio.



