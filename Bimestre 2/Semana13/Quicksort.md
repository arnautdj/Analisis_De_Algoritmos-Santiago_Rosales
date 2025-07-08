# Algoritmo de Ordenación Rápida (Quicksort)

## Introducción

El algoritmo **Quicksort** es un método de ordenamiento basado en la técnica de *divide y vencerás*. Se selecciona un elemento llamado **pivote**, se reordenan los elementos de la lista de manera que los menores al pivote queden a su izquierda y los mayores a su derecha, y luego se aplica recursivamente el mismo procedimiento a las sublistas.

---

## Ejemplo paso a paso

Dada la siguiente matriz:

```
3 | 1 | 4 | 1 | 5 | 9 | 2 | 6 | 5 | 3 | 5 | 8 | 9
```

1. Se toma el primer elemento como pivote, es decir, `p = 3`.
2. Se buscan los elementos mayor al pivote (subrayado) y menor o igual (superrayado):

```
3 | 1 | 4 | 1 | 5 | 9 | 2 | 6 | 5 | 3 | 5 | 8 | 9
```

3. Se intercambian esos elementos:

```
3 | 1 | 3 | 1 | 5 | 9 | 2 | 6 | 5 | 4 | 5 | 8 | 9
```

4. Se repite la exploración en ambas direcciones:

```
3 | 1 | 3 | 1 | 2 | 9 | 6 | 5 | 5 | 4 | 5 | 8 | 9
```

5. Se intercambia el pivote con el valor final de la partición:

```
2 | 1 | 3 | 1 | 3 | 9 | 6 | 5 | 5 | 4 | 5 | 8 | 9
```

---

## División recursiva

Se continúa dividiendo recursivamente en sublistas menores y mayores al pivote.

Ejemplo de división con el array:
```
42, 124, 23, 5, 89, -1, 44, 643, 34
```

- Pivote: 42
- Izquierda: [23, 5, -1, 34]
- Derecha: [124, 89, 44, 643]

```
                     42
                  /      \
       [23, 5, -1, 34]    [124, 89, 44, 643]
```

Este proceso se repite recursivamente hasta llegar a sublistas de un solo elemento o vacías.

---

## Concatenación final

Se concatenan los nodos ordenados con sus respectivos pivotes para formar el arreglo final:

```
[-1, 1, 23, 34, 42, 44, 89, 124, 643]
```

---

## Implementación en pseudocódigo

```plaintext
procedimiento quicksort(T, l, j)
    si j - l es suficientemente pequeño entonces
        insertar(T, l, j)
        stop
    p = pivot(T[l..j])
    quicksort(T[l..p-1])
    quicksort(T[p+1..j])
```

### Pivot

```plaintext
procedimiento pivot(T[l..j], var i)
    k = l; i = j + 1
    repetir { k = k + 1 } hasta que T[k] > p o k ≥ j
    repetir { i = i - 1 } hasta que T[i] ≤ p
    mientras k < i hacer
        intercambiar T[k] y T[i]
        repetir { k = k + 1 } hasta que T[k] > p
        repetir { i = i - 1 } hasta que T[i] ≤ p
    intercambiar T[l] y T[i]
```

---

## Complejidad temporal

- **Mejor caso:** O(n log n)
- **Peor caso:** O(n²)
- **Promedio:** O(n log n)

El algoritmo Quicksort es muy eficiente en la práctica y es ampliamente utilizado para ordenar grandes cantidades de datos.

