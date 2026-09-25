# Punto 3. Recipientes con capacidades diferentes

[3-bowl-mod.ipynb](../../notebooks/uninformed-search/3-bowl-mod.ipynb).

## Resultados

El estado es `(m, n)`: litros actuales en cada recipiente. Ambos empiezan en `(0, 0)`. BFS usa cola y marca el estado al descubrirlo. El objetivo se cumple cuando alguno de los dos recipientes tiene exactamente esa cantidad. `explorados` es el número de estados descubiertos al sacar la meta. Las acciones son llenar, vaciar o verter de uno al otro sin superar la capacidad.

El baseline usa 5 y 3 litros y busca 4. La modificación usa 11 y 5 litros y busca 8.

| Capacidades | Objetivo | Acciones | Explorados | Solución |
| --- | ---: | ---: | ---: | --- |
| 5 y 3 | 4 | 6 | 14 | Sí, `(4, 3)` |
| 11 y 5 | 8 | 14 | 30 | Sí, `(8, 5)` |

Secuencia encontrada para 11 y 5 litros:

| Paso | Acción | Estado |
| ---: | --- | --- |
| 0 | — | (0, 0) |
| 1 | Llenar M | (11, 0) |
| 2 | Verter M → N | (6, 5) |
| 3 | Vaciar N | (6, 0) |
| 4 | Verter M → N | (1, 5) |
| 5 | Vaciar N | (1, 0) |
| 6 | Verter M → N | (0, 1) |
| 7 | Llenar M | (11, 1) |
| 8 | Verter M → N | (7, 5) |
| 9 | Vaciar N | (7, 0) |
| 10 | Verter M → N | (2, 5) |
| 11 | Vaciar N | (2, 0) |
| 12 | Verter M → N | (0, 2) |
| 13 | Llenar M | (11, 2) |
| 14 | Verter M → N | (8, 5) |

Con capacidades 11 y 5 también existe solución. BFS devuelve 14 acciones y deja 8 litros en el recipiente grande. El espacio tiene `(11 + 1) × (5 + 1) = 72` estados posibles; la búsqueda descubre 30 antes de sacar la meta.
