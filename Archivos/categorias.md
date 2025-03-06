# Categorías de archivos
Los archivos en un proyecto pueden caer en una de las siguientes tres categorías:
### Rastreado
Un archivo rastreado ya forma parte del repositorio de Git o recibió cambios que fueron agregados al *stage*. (`git add arch`)
### Ignorado
Los archivos ignorados son **invisibles** para Git. Podemos declarar los objetos que queremos que Git ignore modificando o creando un archivo .gitignore.
En este archivo podemos definir nombres específicos o patrones de nombres de archivos a ignorar (`*.o` -> Cualquier archivo con formato .o)
Si quisieramos hacer una distinción para un solo archivo .o, podríamos agregar una regla:

`!objeto.o`

Para excluir a ese archivo .o del patrón declarado más arriba.
### Sin rastrear
Si un archivo no forma parte del repositorio y no está siendo ignorado, está sin rastrear.
El comando `git status` nos muestra claramente cuales archivos están siendo rastreados y nos advierte sobre aquellos que están sin rastrear. Si no los agregamos al index, el próximo commit no los incluirá a menos que hagamos un `git commit .`.
