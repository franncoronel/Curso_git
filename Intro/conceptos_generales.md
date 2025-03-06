# Introducción
Git es una herramienta de control de versiones diseñada para superar las limitaciones de sus predecesores, especialmente en entornos de desarrollo distribuido.

A diferencia de otros sistemas de control de versiones, Git no distingue entre un repositorio central y sus clones. Cualquier usuario que clone un repositorio tiene acceso a **todo** el código. Entonces, definir cuál de todos estos repositorios es el central es una decisión administrativa.
Distribuir todo el código mejora la calidad de las colaboraciones, y Git ofrece herramientas específicas para gestionar las fusiones entre las distintas versiones del código, asegurando un control preciso durante el proceso de integración con el repositorio central.

La unidad básica de Git son los blobs o *binary large objects* y no los archivos, marcando una enorme diferencia con sus antecesores.
Esta diferencia trae consigo varios beneficios, entre ellos:
- Rapidez para buscar y obtener el contenido de un archivo en un momento específico. Cada versión de los contenidos corresponde a un blob. Ni siquiera es necesario comparar los contenidos de los blobs, con comparar sus ID alcanza para distinguir entre versiones.
- La posibilidad de usar un mismo blob para identificar a dos archivos con el mismo contenido.
  Si el contenido de alguno de los dos archivos cambiara, Git asociaría un nuevo blob al nuevo contenido.
- La posibilidad de aplicar cambios a varios archivos por la separación entre contenidos y metadatos de los archivos.
### Repositorio
Un repositorio de Git es una base de datos que contiene cada bit necesario para almacenar un proyecto, mostrar su historia de cambios y administrar los cambios propuestos o efectuados.
### Estructuras de datos
- **Object store:** Contiene las "tripas" del proyecto en forma de objetos binarios.
- **Index:** Es un archivo binario que funciona como una caché donde podemos almacenar los cambios aún no *commiteados*. Cuando agregamos archivos al *stage* con el comando `git add`, estamos actualizando el *index*.
### Objetos
- **Blobs:** Los blobs son "pedazos" de datos binarios que almacenan una versión del contenido de un archivo. Ni su nombre, ni otros metadatos, solo el contenido.
- **Trees:** Los _trees_ son estructuras que organizan los blobs. Estos almacenan los identificadores (IDs) de los blobs y los pathnames de los archivos, representando así la jerarquía de directorios dentro del repositorio.
- **Commits:** Los commits son conjuntos de cambios que definen el estado del tree en un momento determinado. Son como una "foto" del estado del repositorio. Excepto por el primer commit, todos los commits tienen un padre y pueden tener hijos.
- **Tags:** Con un tag se le puede asignar un nombre significativo a un commit o rama. Esto facilita la identificación de puntos importantes en el historial del repositorio, como versiones o hitos del proyecto.
