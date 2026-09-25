# Actividad final del primer corte

Sistemas Inteligentes I. Talleres de búsqueda no informada, informada, Minimax y poda Alfa–Beta.

## Integrantes

- Juan Camilo Cruz Parra — 37552

## Descripción

La actividad desarrolla los talleres de los notebooks de clase. Cada tema tiene un notebook baseline con el código visto en clase, las respuestas conceptuales en celdas Markdown y enlaces a los experimentos. Los resultados de cada experimento están en `results/`.

## Notebooks

### 1. Búsqueda no informada: BFS y DFS

- [notebooks/uninformed-search/baseline.ipynb](notebooks/uninformed-search/baseline.ipynb)
- Talleres: [orden de movimientos](notebooks/uninformed-search/1-movement-comparison.ipynb), [BFS vs DFS](notebooks/uninformed-search/2-bfs-dfs-comparison.ipynb), [recipientes](notebooks/uninformed-search/3-bowl-mod.ipynb), [8-puzzle](notebooks/uninformed-search/4-bfs-8puzzle.ipynb)
- Resultados: [results/uninformed-search/](results/uninformed-search/)

### 2. Búsqueda informada

- [notebooks/informed-search/baseline.ipynb](notebooks/informed-search/baseline.ipynb)
- Talleres: [cuadrícula 12 × 12](notebooks/informed-search/1-grid-search.ipynb), [heurísticas](notebooks/informed-search/2-heuristics.ipynb), [A* 8-puzzle](notebooks/informed-search/3-astar-8puzzle.ipynb)
- Resultados: [results/informed-search/](results/informed-search/)

### 3. Búsqueda adversarial: Minimax

- [notebooks/minimax/baseline.ipynb](notebooks/minimax/baseline.ipynb)
- Talleres: [tres en raya](notebooks/minimax/1-tictactoe.ipynb), [piedras 1, 2 o 4](notebooks/minimax/2-piedras.ipynb)
- Resultados: [results/minimax/](results/minimax/)

### 4. Búsqueda adversarial: poda Alfa–Beta

- [notebooks/alpha-beta-pruning/baseline.ipynb](notebooks/alpha-beta-pruning/baseline.ipynb)
- Taller: [tres en raya](notebooks/alpha-beta-pruning/1-tictactoe.ipynb)
- Resultados: [results/alpha-beta-pruning/](results/alpha-beta-pruning/)

## Cómo ejecutar

1. Python 3.12 o superior.
2. Crear un entorno e instalar dependencias:

```bash
python -m venv .venv
source .venv/bin/activate
pip install matplotlib jupyter ipykernel
```

3. Ejecutar los notebooks, hay varias formas:
- Abrir Jupyter desde la raíz del repositorio y ejecutar.
- Si tienes la extensión de Jupyter en algún IDE como VSCode o sus forks como Cursor, selecciona el Kernel en la parte superior derecha, y selecciona el entono virtual de Python que acabamos de instalar.

**Importante:** primero ejecutar el `baseline.ipynb` de cada carpeta (estos son los notebooks que vimos en clase pero organizaditos). Los talleres de la misma carpeta son los que se especifican en dichos notebooks, y ya traen sus salidas.

## Uso de IA generativa
Ver [ai-usage.md](ai-usage.md) :)
