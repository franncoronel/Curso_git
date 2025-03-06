# Debugging con `git bisect`
Supongamos que estamos codeando un proyecto que en un momento dado compilaba, y varios commits más tarde, ya no compila más.
Git tiene una herramienta muy útil para encontrar muy rápidamente al commit que rompió todo.
Sin entrar en detalles técnicos, nos permite encontrar al commit "malo" entre, por ejemplo, 1024 commits en no más de diez pasos.

Este proceso comienza con tres comandos:

- `git bisect start` - Comienza el proceso de bisección
- `git bisect bad (id de commit opcional)` - Indicamos que el proyecto en el punto dado arrastra un bug
- `git bisect good (id de commit)` - Indicamos un punto del desarrollo previo al bug

Hechos estos pasos, Git nos llevará a un commit en un punto medio entre *good* y *bad*. Luego probamos el código y vemos si el bug sigue ahí.

Si el bug persiste, etiquetamos a ese commit con `git bisect bad`

Si el bug aún no está en ese punto, etiquetamos a ese commit con `git bisect good`

Ante cada respuesta, Git acota el rango de commits y nos lleva a otro punto intermedio para encontrar el punto exacto en el que se introdujo el error.

Una vez que terminamos, ejecutamos

`git bisect reset`

Para volver al estado inicial pre bisección.