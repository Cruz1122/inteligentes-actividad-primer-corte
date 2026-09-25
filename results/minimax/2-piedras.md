# Punto 2. Juego de las piedras con 1, 2 o 4

[2-piedras.ipynb](../../notebooks/minimax/2-piedras.ipynb).

## Resultados

Quien toma la última piedra gana. En cada turno se retiran 1, 2 o 4 piedras. MAX mueve primero. El valor `+1` es posición ganadora para MAX. El `-1` es perdedora si MIN juega racionalmente. `retirar` es una jugada óptima; cuando hay varias, la función se queda con la primera.

| Piedras | Valor | Mejor movimiento | Opciones `(valor, retirar)` |
| ---: | ---: | ---: | --- |
| 1 | +1 | 1 | (1, 1) |
| 2 | +1 | 2 | (-1, 1), (1, 2) |
| 3 | -1 | 1 | (-1, 1), (-1, 2) |
| 4 | +1 | 1 | (1, 1), (-1, 2), (1, 4) |
| 5 | +1 | 2 | (-1, 1), (1, 2), (-1, 4) |
| 6 | -1 | 1 | (-1, 1), (-1, 2), (-1, 4) |
| 7 | +1 | 1 | (1, 1), (-1, 2), (1, 4) |
| 8 | +1 | 2 | (-1, 1), (1, 2), (-1, 4) |
| 9 | -1 | 1 | (-1, 1), (-1, 2), (-1, 4) |
| 10 | +1 | 1 | (1, 1), (-1, 2), (1, 4) |
| 11 | +1 | 2 | (-1, 1), (1, 2), (-1, 4) |
| 12 | -1 | 1 | (-1, 1), (-1, 2), (-1, 4) |
| 13 | +1 | 1 | (1, 1), (-1, 2), (1, 4) |
| 14 | +1 | 2 | (-1, 1), (1, 2), (-1, 4) |
| 15 | -1 | 1 | (-1, 1), (-1, 2), (-1, 4) |
