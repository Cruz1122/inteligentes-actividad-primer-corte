# Pregunta final: ¿Puede una búsqueda más rápida producir una solución peor?

Sí. En el mapa de 12 × 12, Beam Search con k = 1 expandió 41 estados y devolvió un camino de costo 40. Costo Uniforme expandió 49 y A* 36, y los dos devolvieron costo 22. El haz corto recorre menos, pero se queda en el corredor que se ve cerca del objetivo y pierde el rodeo óptimo.

A* con Manhattan también recorre menos que Costo Uniforme, 36 contra 49, y conserva el mismo costo. Ahí la búsqueda más dirigida no empeora la solución. La diferencia está en qué se recorta: una heurística admisible ordena la frontera; un haz estrecho descarta candidatos y puede dejar afuera el camino de menor costo.
