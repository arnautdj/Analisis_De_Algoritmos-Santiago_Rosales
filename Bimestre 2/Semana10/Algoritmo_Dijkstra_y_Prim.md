
# Algoritmo de Dijkstra y Prim

## Grafo Dirigido

- Un grafo dirigido G consiste en un conjunto de vértices V y un conjunto de arcos A.
- Los vértices se denominan nodos o puntos. Los arcos pueden llamarse también líneas dirigidas.
- Un arco es un par ordenado de vértices (v, w); donde **v** es la cola y **w** la cabeza del arco.

---

## Algoritmo de Dijkstra

El algoritmo de Dijkstra permite encontrar el camino más corto desde un vértice origen hacia todos los demás en un grafo dirigido ponderado.

### Pseudocódigo

```
función Dijkstra(L[1..n, 1..n]): matriz [2..n]
  matriz D[2..n]
  // Iniciación
  C ← {2, 3, ..., n}  // S = N \ C sólo existe implícitamente

  para i ← 2 hasta n hacer
    D[i] ← L[1, i]

  // Bucle voraz
  repetir n - 2 veces
    v ← algún elemento de C que minimiza D[v]
    C ← C \ {v}   // implícitamente S ← S ∪ {v}

    para cada w ∈ C hacer
      D[w] ← min(D[w], D[v] + L[v, w])

  devolver D
```

---

## Algoritmo de Prim

Este algoritmo encuentra un árbol de expansión mínima para un grafo no dirigido y ponderado.

### Pseudocódigo

```
función Prim(G = (N, A); grafo; longitud A → ℓ): conjunto de aristas
  // Iniciación
  T ← ∅
  B ← {un miembro arbitrario de N}

  mientras B ≠ N hacer
    buscar e = {u, v} de longitud mínima tal que
      u ∈ B y v ∈ N \ B

    T ← T ∪ {e}
    B ← B ∪ {v}

  devolver T
```

---

## Ejemplo: Ejecución paso a paso del algoritmo de Prim

Dado el siguiente grafo con pesos:

```
N = {1, 2, 3, 4, 5, 6}
A = {(1,2), (1,3), (1,4), (2,3), (2,5), (3,4), (3,6), (4,6), (5,6)}
```

Se sigue el siguiente proceso:

| T          | B           | N\B        | e = {u,v} | peso |
|------------|-------------|-------------|-----------|------|
| ∅          | {1}         | {2,3,4,5,6} | (1,3)     | 4    |
| {(1,3)}    | {1,3}       | {2,4,5,6}   | (3,6)     | 3    |
| {(1,3),(3,6)} | {1,3,6}  | {2,4,5}     | (6,5)     | 2    |
| {(1,3),(3,6),(6,5)} | {1,3,5,6} | {2,4} | (5,2)     | 5    |
| {(1,3),(3,6),(6,5),(5,2)} | {1,2,3,5,6} | {4} | (1,4) | 6    |

