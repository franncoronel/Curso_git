# Introducción
El merge o fusión es el proceso inverso al branching o apertura de ramas, y se da en el momento en el que se deciden unificar cambios aplicados por distintos desarrolladores en una sola rama de desarrollo.

Este proceso no siempre es dificil, ya que cuando no existen conflictos entre los cambios a fusionar, ambos se aplican de manera armoniosa.

Pero los problemas pueden surgir incluso después de una fusion armoniosa si los conjuntos de cambios aplicados trabajaron sobre el mismo problema pero en lugares distintos.

Git ofrece la herramienta [Bisect](../Commits/bisect.md) para facilitar la resolución de este tipo de conflictos, y una metodología ordenada, de commits pequeños también es una gran aliada para arreglar merges problemáticos.
