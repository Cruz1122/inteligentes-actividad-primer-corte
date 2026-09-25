# Punto 1. Costo Uniforme, A* y Beam Search en una cuadrícula

[1-grid-search.ipynb](../../notebooks/informed-search/1-grid-search.ipynb).

## Resultados

Mapa de `12 × 12`. El `0` es celda libre y el `1` es obstáculo. El inicio está en `(0, 0)` y el objetivo en `(11, 11)`. Cada movimiento cuesta 1. `expandidos` es el número de estados que salen de la frontera. La línea roja es el camino devuelto.

Costo Uniforme ordena por `g(n)`. A* ordena por `g(n)` más distancia Manhattan. Beam Search conserva solo los `k` candidatos con menor Manhattan de cada nivel.

| Algoritmo | Costo | Expandidos | Solución |
| --- | ---: | ---: | --- |
| Costo Uniforme | 22 | 49 | Sí |
| A* | 22 | 36 | Sí |
| Beam Search k=1 | 40 | 41 | Sí |
| Beam Search k=2 | 22 | 44 | Sí |
| Beam Search k=4 | 22 | 48 | Sí |
| Beam Search k=8 | 22 | 48 | Sí |

<table>
  <tr>
    <td><img src="images/1-ucs.png" width="220" alt="Costo Uniforme"></td>
    <td><img src="images/1-astar.png" width="220" alt="A*"></td>
    <td><img src="images/1-beam-k1.png" width="220" alt="Beam Search k=1"></td>
  </tr>
  <tr>
    <td><img src="images/1-beam-k2.png" width="220" alt="Beam Search k=2"></td>
    <td><img src="images/1-beam-k4.png" width="220" alt="Beam Search k=4"></td>
    <td><img src="images/1-beam-k8.png" width="220" alt="Beam Search k=8"></td>
  </tr>
</table>
