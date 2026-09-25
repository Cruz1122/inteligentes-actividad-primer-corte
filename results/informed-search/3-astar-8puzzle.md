# Punto 3. A* y BFS para el 8-puzzle

[3-astar-8puzzle.ipynb](../../notebooks/informed-search/3-astar-8puzzle.ipynb).

## Resultados

El estado es una tupla de 9 casillas. El `0` es el espacio vacío. `expandidos` es el número de estados que salen de la frontera. Las acciones son el desplazamiento de la casilla vacía. El tablero inicial es `(8, 6, 7, 2, 5, 4, 3, 0, 1)` y el objetivo es `(1, 2, 3, 4, 5, 6, 7, 8, 0)`.

BFS no usa heurística. A* con fichas fuera de lugar usa `h1(n)`: número de fichas que no están en su posición, sin contar el vacío. A* con Manhattan usa `h2(n)`: suma de distancias de cada ficha a su casilla objetivo.

| Algoritmo | Movimientos | Expandidos | Tiempo |
| --- | ---: | ---: | ---: |
| BFS | 31 | 181439 | 0.400 s |
| A* fichas fuera de lugar | 31 | 143849 | 0.680 s |
| A* Manhattan | 31 | 21198 | 0.164 s |

Los tres algoritmos encuentran una solución de 31 movimientos, la distancia máxima respecto de ese objetivo. BFS recorre casi toda la componente conexa, 181439 estados. Las fichas fuera de lugar recortan poco: 143849 estados. Manhattan baja la expansión a 21198. El tiempo de A* con fichas fuera de lugar queda por encima de BFS porque cada nodo calcula la heurística; la diferencia útil está en los estados expandidos.
