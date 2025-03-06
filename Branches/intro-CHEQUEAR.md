# Introducción
Las ramas o _branches_ son fundamentales para el desarrollo colaborativo usando git.
Los repositorios suelen organizarse en una rama principal **master** o **main** e infinitas ramas que se desprenden de esta.
A nivel técnico, la rama **main** es igual a las demás. Su importancia corresponde a una decisión organizacional y política que toma un desarrollador o equipo de desarrollo.

Definir la rama principal organiza al desarrollo en torno a ella. Generalmente, la rama **main** contiene una versión funcional del proyecto, y los nuevos desarrollos u operaciones de mantenimiento deberían realizarse en ramas que se desprendan de ella y ser reintegrados al completarse.

El trabajo con ramas también permite al desarrollador enfocarse en un problema específico y no preocuparse por cambios conflictivos o código en constante cambio, al menos hasta el momento del **merge**.

## Nombres de ramas vs Tags

Una rama es como un tag al que le podes agregar commits.
Digamos, dado un punto del desarrollo, podemos