# Operaciones

## Fusionar una rama con la rama actual

Dado un repositorio con al menos dos ramas, podemos ejecutar:

`git checkout rama1`

`git merge rama2`

Para movernos a la rama que recibirá los cambios e introducirle todos los archivos y directorios correspondientes a la rama entrante.

Para una experiencia más prolija, es recomendable organizar los cambios e introducciones realizados en la rama 2 en distintos commits.

Cuando no se encuentran conflictos en las ramas, el proceso de fusión termina con un reporte breve.

## Solucionar conflictos

Lo más esperable es que un *merge* entre dos ramas genere conflictos en algunos archivos, los cuales se plasman en el archivo con un diff

```git
<<<<<<< HEAD:arch1
contenido
=======
conteni2
>>>>>>> develop:arch1
```

En esta situación tenemos dos formas distintas de encarar el problema:
#### Usando git reset
Con el comando git reset, podemos revertir el merge para trabajar sobre los archivos conflictivos en alguna de las dos ramas, asegurarnos de que estén resueltos y volver a intentar.
Ejecutando:

`git reset --hard rama1`

Volveremos al estado previo a la fusión.

#### Sin revertir el merge
Sino, podemos trabajar sobre el/los archivos "rotos" en la fusión, editándolos para obtener el resultado que esperábamos.
Una vez que los archivos estén listos, es cuestión de ejecutar:

`git add arch1` / `git add .`

`git commit -m "Arreglo conflictos tras merge"`

No hay una "mejor" manera de encarar el problema, pero conviene tener alternativas si el merge resulta muy conflictivo.
