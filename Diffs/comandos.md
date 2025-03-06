# Comandos
## `git diff`

Con este comando a secas podemos analizar las diferencias entre los cambios que introducimos en la iteración actual (pero aún no confirmamos) y los commits previos.
Una vez que realizamos el commit, este comando no tiene *output*.
## `git diff (commit) (otro_commit)`  
Especificando los commits podemos mostrar la diferencia entre la versión actual y una versión anterior o posterior. Los commits se pueden indicar mediante tags o los primeros 6 dígitos de sus hash.
También es posible que el tag apunte a una rama, permitiendo comparar el estado del proyecto en un momento dado respecto a otra rama.
El flag **--staged** muestra las diferencias entre el commit indicado y los cambios introducidos actualmente, siempre y cuando los archivos modificados hayan sido agregados usando **git add**.
El flag **--stat** muestra datos estadísticos de las diferencias en vez de detallar los cambios línea por línea.


