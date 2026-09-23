# Punto 1. Orden de movimientos en BFS sobre el laberinto

Fuente: [1-movement-comparison.ipynb](../../notebooks/uninformed-search/1-movement-comparison.ipynb).

El algoritmo ejecutado es **BFS** (`bfs_camino_laberinto`): cola FIFO, un estado se marca al descubrirlo y la búsqueda se detiene al **sacar** la meta de la cola. El orden de los movimientos no cambia el costo del camino. Cambia cuál camino mínimo se devuelve y cuántas celdas ya están en `visitados` en ese momento.

Inicio `(0, 0)`, meta `(4, 4)`. `0` es pasillo y `1` es pared.

```text
(0,0) S   #   .   .   .
(1,0) .   #   .   #   .
(2,0) .   .   .   #   .
(3,0) .   #   .   #   #
(4,0) .   .   .   .   G (4,4)
```

Cada desplazamiento es `(Δfila, Δcolumna)`: izquierda `(0, -1)`, derecha `(0, 1)`, arriba `(-1, 0)`, abajo `(1, 0)`. Los sucesores se generan en ese orden y entran a la cola en ese mismo orden.

## Resultados

Las cuatro corridas devuelven un camino de **8 pasos** (9 celdas). En un grafo no ponderado, BFS garantiza ese mínimo. Hay dos caminos distintos de ese costo.

| Orden real de sucesores | Pasos | Explorados | Tiempo | Camino |
| --- | ---: | ---: | ---: | --- |
| IZQ, DER, ARR, ABA | 8 | 17 | 0.071 ms | por el centro: `(2,1) → (2,2) → (3,2) → (4,2)` |
| IZQ, ARR, ABA, DER | 8 | 16 | 0.059 ms | por la izquierda y la fila inferior |
| ABA, IZQ, ARR, DER | 8 | 16 | 0.045 ms | por la izquierda y la fila inferior |
| DER, ABA, IZQ, ARR | 8 | 16 | 0.051 ms | por el centro: `(2,1) → (2,2) → (3,2) → (4,2)` |

`explorados` es `len(visitados)` al extraer la meta: estados **descubiertos** (inicio, meta y celdas ya encoladas), no solo los expandidos. El tiempo es una sola ejecución sobre una matriz de 5×5; las cuatro cifras están por debajo de 0.1 ms y no sirven para comparar algoritmos.

### Camino por el centro

Órdenes: **IZQ, DER, ARR, ABA** y **DER, ABA, IZQ, ARR**.

```text
(0,0) → (1,0) → (2,0) → (2,1) → (2,2) → (3,2) → (4,2) → (4,3) → (4,4)
```

En `(2,0)` la derecha es válida y se genera **antes** que bajar. `(2,1)` entra a la cola antes que `(3,0)`, así que la rama central avanza primero y es la que encola `(4,4)`.

Con **IZQ, DER, ARR, ABA** se descubren **17** celdas. Al expandir el pasillo superior, `(0,4)` alcanza a generar `(1,4)` antes de que la cola entregue `(4,4)`. Esa celda no pertenece al camino; solo ya estaba descubierta.

### Camino por la columna izquierda y la fila inferior

Órdenes: **IZQ, ARR, ABA, DER** y **ABA, IZQ, ARR, DER**.

```text
(0,0) → (1,0) → (2,0) → (3,0) → (4,0) → (4,1) → (4,2) → (4,3) → (4,4)
```

En `(2,0)` bajar se genera **antes** que ir a la derecha. `(3,0)` queda por delante de `(2,1)`, la fila 4 se recorre antes y `(4,4)` se descubre por `(4,3)` viniendo de la izquierda. Se descubren **16** celdas: `(1,4)` todavía no se ha generado cuando la meta sale de la cola.

## Qué muestra la comparación

1. **El costo no depende del orden.** Los cuatro caminos tienen 8 pasos, el mínimo entre `(0,0)` y `(4,4)` en este laberinto.
2. **El camino concreto sí depende del orden.** Si en la bifurcación `(2,0)` la derecha entra antes que abajo, gana el camino del centro. Si abajo entra antes, gana el camino de la fila inferior.
3. **El número de explorados cambia poco.** La meta está a profundidad 8 y casi todo el pasillo queda a profundidad menor o igual, así que BFS descubre 16 o 17 de las 18 celdas libres antes de terminar. La celda que marca la diferencia es `(1,4)`.
4. **En BFS el orden es un desempate entre caminos óptimos.** No acorta ni alarga la solución. El mismo experimento con DFS sí cambiaría la longitud, porque DFS sigue la primera rama hasta el fondo.

## Nota sobre la salida impresa

Los `print` de las tres últimas corridas no describen las listas que realmente se pasaron a la función. Los números de arriba corresponden a estas listas del notebook:

| Texto impreso | Lista usada |
| --- | --- |
| `IZQ, DER, ARR, ABA` | `MOV_IZQ_DER_ARR_ABA` |
| `IZQ, ARR, DER, ABA` | `MOV_IZQ_ARR_ABA_DER` → IZQ, ARR, **ABA, DER** |
| `ARR, IZQ, DER, ABA` | `MOV_ABA_IZQ_ARR_DER` → **ABA, IZQ, ARR, DER** |
| `ABA, IZQ, ARR, DER` | `MOV_DER_ABA_IZQ_ARR` → **DER, ABA, IZQ, ARR** |
