
# Algoritmo de Ordenamiento por Fusión (Merge Sort)

El algoritmo de ordenamiento por fusión (Merge Sort) es un método eficiente de ordenamiento que utiliza el paradigma de **divide y vencerás**.

## Funcionamiento

1. **División de la lista**:  
   Se divide la lista original en dos mitades de forma recursiva, hasta obtener listas de un solo elemento.

2. **Ordenamiento recursivo**:  
   Cada mitad es ordenada de forma independiente mediante llamadas recursivas al algoritmo.

3. **Fusión (merge)**:  
   Se combinan las mitades ordenadas en una sola lista ordenada utilizando el procedimiento de fusión.

## Ejemplo visual del proceso

Supongamos que partimos de la lista:

```
[26, 7, 77, 44, 55, 20]
```

1. Se divide en mitades:

```
[26, 7, 77] y [44, 55, 20]
```

2. Se ordenan recursivamente:

```
[7, 26, 77] y [20, 44, 55]
```

3. Se fusionan para obtener la lista ordenada final:

```
[7, 20, 26, 44, 55, 77]
```

## Condición de parada

El caso base de la recursividad se da cuando la lista a ordenar contiene solo un elemento (`n = 1`), ya que se considera ordenada.

---

## Complejidad

- Tiempo: **O(n log n)** en el peor caso, mejor caso y caso promedio.
- Espacio: **O(n)** debido al uso de arreglos auxiliares.

---


# Algoritmo Merge-Sort y Merge

## `MERGE-SORT(A, p, r)`

```
1.  if p >= r
2.      return
3.  q = ⌊(p + r) / 2⌋
4.  MERGE-SORT(A, p, q)
5.  MERGE-SORT(A, q + 1, r)
6.  MERGE(A, p, q, r)
```

## `MERGE(A, p, q, r)`

```
1.  n1 = q - p + 1
2.  n2 = r - q
3.  let L[0..n1-1] and R[0..n2-1] be new arrays
4.  for i = 0 to n1 - 1
5.      L[i] = A[p + i]
6.  for j = 0 to n2 - 1
7.      R[j] = A[q + 1 + j]
8.  i = 0
9.  j = 0
10. k = p
11. while i < n1 and j < n2
12.     if L[i] <= R[j]
13.         A[k] = L[i]
14.         i = i + 1
15.     else
16.         A[k] = R[j]
17.         j = j + 1
18.     k = k + 1
19. while i < n1
20.     A[k] = L[i]
21.     i = i + 1
22.     k = k + 1
23. while j < n2
24.     A[k] = R[j]
25.     j = j + 1
26.     k = k + 1
```

---

# Prueba de escritorio: Merge-Sort y Merge

**Arreglo original:**  
A = [54, 26, 93, 17, 77, 31, 44, 55, 20]

Índices:
```
p:  1  2  3  4  5  6  7  8  9
A: [54,26,93,17,77,31,44,55,20]
```

```
Merge-Sort(A, 1, 9)
  No retorna
  q = 5
  Merge-Sort(A, 1, 5)
    No retorna
    q = 3
    Merge-Sort(A, 1, 3)
      No retorna
      q = 2
      Merge-Sort(A, 1, 2)
        q = 1
        Merge-Sort(A, 1, 1)
          Return
        Merge-Sort(A, 2, 2)
          Return
        Merge(A, 1, 1, 2)        // Llamada 1
      Merge-Sort(A, 3, 3)
        Return
      Merge(A, 1, 2, 3)          // Llamada 2
    Merge-Sort(A, 4, 5)
      q = 4
      Merge-Sort(A, 4, 4)
        Return
      Merge-Sort(A, 5, 5)
        Return
      Merge(A, 4, 4, 5)          // Llamada 3
    Merge(A, 1, 3, 5)            // Llamada 4
  Merge-Sort(A, 6, 9)
    q = 7
    Merge-Sort(A, 6, 7)
      q = 6
      Merge-Sort(A, 6, 6)
        Return
      Merge-Sort(A, 7, 7)
        Return
      Merge(A, 6, 6, 7)          // Llamada 5
    Merge-Sort(A, 8, 9)
      q = 8
      Merge-Sort(A, 8, 8)
        Return
      Merge-Sort(A, 9, 9)
        Return
      Merge(A, 8, 8, 9)          // Llamada 6
    Merge(A, 6, 7, 9)            // Llamada 7
  Merge(A, 1, 5, 9)              // Llamada 8
```

**Resultado final:**  
A = [17, 20, 26, 31, 44, 54, 55, 77, 93]
