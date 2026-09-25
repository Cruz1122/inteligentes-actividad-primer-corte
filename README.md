# Actividad final

## Búsqueda no informada (Uninformed Search)

En esta sección se presentan los algoritmos de búsqueda no informada, que resuelven problemas sin utilizar información adicional sobre la meta más allá de la estructura del propio problema. Son útiles cuando no se dispone de heurísticas u otro conocimiento específico.

- [Carpeta de Búsqueda No Informada](/notebooks/uninformed-search/)
- [Resultados de Ejecución](/results/uninformed-search/)

Los algoritmos incluidos (como búsqueda en anchura y búsqueda en profundidad) exploran el espacio de estados sistemáticamente. La diferencia principal radica en el orden en que expanden los nodos y la eficiencia en encontrar una solución dependiendo del problema concreto y de su tamaño.

## Búsqueda informada (Informed Search)

En esta sección se presentan los algoritmos de búsqueda informada, que usan una heurística para orientar la expansión hacia la meta. Sirven para recortar el espacio de estados cuando hay una estimación del costo restante.

- [Carpeta de Búsqueda Informada](/notebooks/informed-search/)
- [Resultados de Ejecución](/results/informed-search/)

Los algoritmos incluidos (como costo uniforme, A* y Beam Search) combinan el costo acumulado con esa estimación. La diferencia principal radica en si conservan optimalidad y cuántos estados expanden en el mismo problema.