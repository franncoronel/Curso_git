## Rebasing

El rebasing es una operación distinta al merging que permite sincronizar ramas paralelas sin fusionarlas.

`git rebase` ofrece una solución a la siguiente situación:
Estamos trabajando en un proyecto colaborativo y tras una reunión dividimos las tareas equitativamente. Cada uno abre una rama desde main y comienza a codear. Un integrante completa su trabajo, hace un pull request, y fusiona su rama con main. Nosotros seguimos trabajando en nuestra rama, pero consideramos que el trabajo que realizó nuestro compañero podría sernos útil.
Entonces, en vez de fusionar nuestro trabajo incompleto y volver a abrir una rama, podemos ejecutar un **rebase**.

El proceso de rebase sigue tres pasos:
1. Se revierten los cambios que realizamos en nuestra rama
2. Se agregan los cambios sobre la rama main a nuestra rama
3. Los cambios revertidos se aplican otra vez en la punta del historial de commits

Para realizar un rebase sobre nuestra rama de desarrollo debemos ejecutar:

`git checkout develop`

`git rebase main develop`

El rebase puede traer conflictos, los cuales conviene resolver en la misma rama, sin revertir el rebase. Tras resolver los conflictos, agregamos los archivos modificados con `git add` y una vez terminados, ejecutamos:

`git rebase --continue`

Si la resolución de conflictos resulta ser muy hostil, podemos abortar el proceso con:

`git rebase --abort`

El rebasing parece muy cómodo en teoría, pero puede traer algunos problemas, ya que es una operación que reescribe el historial de commits.
Es conveniente tener tests unitarios de las funcionalidades sobre las que estábamos trabajando en nuestra rama para verificar que sigan funcionando tras el rebase.
Si trabajamos con commits pequeños, estos se colapsarán en un solo gran commit al ser agregados por encima de los cambios traídos de main.
Si otra rama dependía de nuestra rama pre-rebase, acabamos de alterar el código significativamente, y obligaremos al encargado de esa rama a adaptar el código y resolver conflictos.

En definitiva, el rebasing genera más dolores de cabeza de los que resuelve.
