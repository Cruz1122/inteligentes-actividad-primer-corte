# Punto 1. Orden de movimientos en BFS

[1-movement-comparison.ipynb](../../notebooks/uninformed-search/1-movement-comparison.ipynb).


## Resultados

BFS con cola. La celda se marca al descubrirla y la búsqueda para al sacar la meta. `explorados` es el número de celdas descubiertas en ese momento. El número sobre cada celda es el paso de expansión. La línea roja es el camino devuelto.

| Orden de sucesores | Pasos | Explorados | Tiempo |
| --- | ---: | ---: | ---: |
| IZQ, DER, ARR, ABA | 8 | 17 | 0.071 ms |
| IZQ, ARR, ABA, DER | 8 | 16 | 0.059 ms |
| ABA, IZQ, ARR, DER | 8 | 16 | 0.045 ms |
| DER, ABA, IZQ, ARR | 8 | 16 | 0.051 ms |

<table>
  <tr>
    <td><img src="images/1-izq-der-arr-aba.png" width="170" alt="IZQ, DER, ARR, ABA"></td>
    <td><img src="images/1-izq-arr-aba-der.png" width="170" alt="IZQ, ARR, ABA, DER"></td>
    <td><img src="images/1-aba-izq-arr-der.png" width="170" alt="ABA, IZQ, ARR, DER"></td>
    <td><img src="images/1-der-aba-izq-arr.png" width="170" alt="DER, ABA, IZQ, ARR"></td>
  </tr>
</table>

Los cuatro órdenes cuestan 8 pasos. El tiempo no distingue eficiencia: las cuatro corridas quedan por debajo de 0.1 ms. En estados la diferencia es una celda, 16 o 17. Cambiar el orden no hace a BFS más barato; cambia qué camino de ese costo devuelve y en qué orden se van marcando las celdas.
