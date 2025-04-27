## Algoritmo Merge

El algoritmo **Merge** es una parte fundamental del método de ordenamiento **Merge Sort**.  
Su propósito es **fusionar** dos subarreglos ordenados en un único arreglo ordenado.

### Funcionamiento general

1. **División**: Se crean dos arreglos auxiliares:
    - `L[0..nL-1]` que contiene los elementos de `A[p..q]`.
    - `R[0..nR-1]` que contiene los elementos de `A[q+1..r]`.

2. **Fusión**:
    - Se comparan los elementos actuales de `L` y `R`.
    - El elemento menor se copia al arreglo original `A`.
    - Se avanza el índice del arreglo desde el cual se extrajo el elemento.

3. **Copiado restante**:
    - Si un arreglo (`L` o `R`) se queda sin elementos, se copian directamente los elementos restantes del otro arreglo a `A`.

### Pseudocódigo resumido

```pseudo
nL = q - p + 1
nR = r - q
Let L[0..nL-1] y R[0..nR-1]

for i ← 0 to nL-1
  L[i] ← A[p+i]

for j ← 0 to nR-1
  R[j] ← A[q+1+j]

i, j ← 0
k ← p

while i < nL and j < nR
  if L[i] ≤ R[j]
    A[k] ← L[i]
    i ← i + 1
  else
    A[k] ← R[j]
    j ← j + 1
  k ← k + 1

while i < nL
  A[k] ← L[i]
  i ← i + 1
  k ← k + 1

while j < nR
  A[k] ← R[j]
  j ← j + 1
  k ← k + 1

```
## Multiplicación de Matrices

### Algoritmo de multiplicación de matrices


```pseudo
a[m][n] ; b[n][p] ; c[m][p]

for i ← 1 to m
  for j ← 1 to p
    for k ← 1 to n
      C[i][j] ← C[i][j] + A[i][k] × B[k][j]
```

#### Ejemplo

Multiplicando las matrices:

Matriz A:

| 2 | 1 |
|---|---|
| 3 | 2 |

Matriz B:

| 4 | 5 |
|---|---|
| 2 | 3 |

Resultado (Matriz C = A × B):

| 12 | 13 |
|----|----|
| 16 | 21 |

