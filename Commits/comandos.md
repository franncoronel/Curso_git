# Comandos
## `git checkout`
## `git commit`
Confirmar cambios a nuestro proyecto.
Hay muchas opciones para realizar esta operación.

Una condición necesaria para hacer un commit es que los archivos que agregamos, modificamos, etc... estén indexados, es decir, que los hayamos agregado al *stage* con [`git add`](Programacion/Curso_git/Archivos/operaciones-CHEQUEAR.md).

Podemos confirmar los cambios a un solo archivo con

`git commit arch1`

O confirmar todos los cambios con:

`git commit -s/-m "mensaje"`

`git commit ./ -s/-m "mensaje"`

`git commit -a -s/-m "mensaje"`

(Recomiendo siempre agregar un mensaje con el flag -m para evitar la interfaz incómoda que aparece cuando nos olvidamos de agregar un mensaje de commit)
## `git tag (nombre_del_tag) (hash_del_commit)`
Crear una etiqueta que referencia a un commit. Debemos brindar al menos 6 dígitos del hash del commit para crear una referencia unívoca.
Más info sobre [tags](./tag.md).
## `git status`
Verificar el estado del proyecto. Es muy útil, casi obligatorio si nuestro IDE o editor de texto no tiene buena integración con Git.
Nos permite ver qué archivos se agregaron, modificaron o eliminaron de nuestro proyecto y cuántos de ellos han sido agregados al *stage*.
El próximo commit que hagamos sólo incluirá aquellos archivos que han sido agregados al *stage* con `git add`.
## `git log`
Revisar el historial de commits desde el último al primero.
Otro comando extremadamente útil, tanto en su versión extendida como en su versión abreviada que se obtiene ejecutando:

`git log --pretty=oneline`

No sólo podemos revisar los commits hechos, sino que podemos extraer su hash, dato muy útil para agregar tags, moverse entre commits, etc...
## `git reset (id_commit)`
Reestablecer el historial de commits a un punto determinado.
El id del commit puede ser su número de hash, su tag (si lo tiene) o
- HEAD
- HEAD~
- HEAD~~
- HEAD~2
Siendo HEAD el commit más reciente, HEAD~ el commit anterior a HEAD, HEAD~~ el commit anterior a HEAD~ y HEAD~2 el **abuelo** de HEAD

Sin flags adicionales, este comando altera el historial de commits, pero deja los archivos del proyecto intactos.

El flag --hard altera tanto el historial de commits como los archivos en sí. En esencia, es como si los commits posteriores al punto indicado nunca hubieran existido.

El flag --soft simplemente cambia la referencia de HEAD, sin eliminar los commits posteriores, tomando al commit especificado como el último en ser realizado.

El flag --mixed hace lo mismo que --soft, pero también actualiza el *index*, bajando cualquier cambio o introducción del *stage*.
## `git revert (id_commit)`
Revertir un commit.

Ojo, *revert* funciona distinto al más conocido `git reset`. Este comando crea un commit adicional con un set de cambios que revierten lo hecho por el commit especificado y lo ubica punta del historial, convirtiendose en HEAD.
