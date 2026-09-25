# Punto 4. BFS para el 8-puzzle

[4-bfs-8puzzle.ipynb](../../notebooks/uninformed-search/4-bfs-8puzzle.ipynb).

## Resultados

El estado es una tupla de 9 casillas. El `0` es el espacio vacío. BFS usa cola y marca el estado al descubrirlo. No usa heurística. `explorados` es el número de estados descubiertos al terminar la búsqueda. Las acciones son el desplazamiento de la casilla vacía: Arriba, Abajo, Izquierda o Derecha.

Los dos casos buscan el mismo objetivo `(1, 2, 3, 4, 5, 6, 7, 8, 0)`.

| Caso | Estado inicial | Movimientos | Explorados | Solución |
| --- | --- | ---: | ---: | --- |
| Sin solución | `(1, 2, 3, 4, 5, 0, 6, 8, 7)` | — | 181440 | No |
| Distancia máxima | `(8, 6, 7, 2, 5, 4, 3, 0, 1)` | 31 | 181440 | Sí |

El primer tablero tiene una inversión impar y el objetivo tiene cero. En el 8-puzzle eso separa el espacio en dos componentes de `9! / 2 = 181440` estados. BFS recorre toda la componente del inicial y no alcanza la meta.

El segundo tablero está a 31 movimientos, la distancia máxima respecto de ese objetivo. BFS devuelve un camino de esa longitud. Como la meta está en el último nivel, la búsqueda descubre los 181440 estados de la componente antes de cerrar el resultado.

Secuencia encontrada para el caso de 31 movimientos:

| Paso | Acción | Estado |
| ---: | --- | --- |
| 0 | — | (8, 6, 7, 2, 5, 4, 3, 0, 1) |
| 1 | Arriba | (8, 6, 7, 2, 0, 4, 3, 5, 1) |
| 2 | Arriba | (8, 0, 7, 2, 6, 4, 3, 5, 1) |
| 3 | Izquierda | (0, 8, 7, 2, 6, 4, 3, 5, 1) |
| 4 | Abajo | (2, 8, 7, 0, 6, 4, 3, 5, 1) |
| 5 | Abajo | (2, 8, 7, 3, 6, 4, 0, 5, 1) |
| 6 | Derecha | (2, 8, 7, 3, 6, 4, 5, 0, 1) |
| 7 | Derecha | (2, 8, 7, 3, 6, 4, 5, 1, 0) |
| 8 | Arriba | (2, 8, 7, 3, 6, 0, 5, 1, 4) |
| 9 | Arriba | (2, 8, 0, 3, 6, 7, 5, 1, 4) |
| 10 | Izquierda | (2, 0, 8, 3, 6, 7, 5, 1, 4) |
| 11 | Abajo | (2, 6, 8, 3, 0, 7, 5, 1, 4) |
| 12 | Izquierda | (2, 6, 8, 0, 3, 7, 5, 1, 4) |
| 13 | Abajo | (2, 6, 8, 5, 3, 7, 0, 1, 4) |
| 14 | Derecha | (2, 6, 8, 5, 3, 7, 1, 0, 4) |
| 15 | Derecha | (2, 6, 8, 5, 3, 7, 1, 4, 0) |
| 16 | Arriba | (2, 6, 8, 5, 3, 0, 1, 4, 7) |
| 17 | Arriba | (2, 6, 0, 5, 3, 8, 1, 4, 7) |
| 18 | Izquierda | (2, 0, 6, 5, 3, 8, 1, 4, 7) |
| 19 | Abajo | (2, 3, 6, 5, 0, 8, 1, 4, 7) |
| 20 | Izquierda | (2, 3, 6, 0, 5, 8, 1, 4, 7) |
| 21 | Abajo | (2, 3, 6, 1, 5, 8, 0, 4, 7) |
| 22 | Derecha | (2, 3, 6, 1, 5, 8, 4, 0, 7) |
| 23 | Derecha | (2, 3, 6, 1, 5, 8, 4, 7, 0) |
| 24 | Arriba | (2, 3, 6, 1, 5, 0, 4, 7, 8) |
| 25 | Arriba | (2, 3, 0, 1, 5, 6, 4, 7, 8) |
| 26 | Izquierda | (2, 0, 3, 1, 5, 6, 4, 7, 8) |
| 27 | Izquierda | (0, 2, 3, 1, 5, 6, 4, 7, 8) |
| 28 | Abajo | (1, 2, 3, 0, 5, 6, 4, 7, 8) |
| 29 | Abajo | (1, 2, 3, 4, 5, 6, 0, 7, 8) |
| 30 | Derecha | (1, 2, 3, 4, 5, 6, 7, 0, 8) |
| 31 | Derecha | (1, 2, 3, 4, 5, 6, 7, 8, 0) |
