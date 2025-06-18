
# Divide y Vencerás

El principio de “Divide y vencerás” se aplica a muchos algoritmos eficientes, donde el problema se divide en subproblemas más pequeños, se resuelven de manera recursiva y luego se combinan sus resultados.

---

## Ejemplo: Multiplicación de grandes números

Se quiere calcular el producto:

```
981 × 1234
```

Este se puede descomponer como:

```
981 × 1234 = (10²w + x)(10²y + z)
           = 10⁴wy + 10²(wz + xy) + xz
```

Para reducir la cantidad de multiplicaciones necesarias, se analiza la expresión:

```
r = (w + x)(y + z) = wy + wz + xy + xz
```

Por lo tanto, se puede deducir:

```
wz + xy = r - wy - xz
```

---

## Ejemplo aplicado

Valores asignados:

```
p = wy = 09 × 12 = 108
q = xz = 81 × 34 = 2754
r = (w + x)(y + z) = 90 × 46 = 4140
```

Sustituyendo en la fórmula original:

```
981 × 1234 = 10⁴p + 10²(r - p - q) + q
           = 10⁴(108) + 10²(4140 - 108 - 2754) + 2754
           = 1210554
```

Este ejemplo muestra cómo disminuir el número de multiplicaciones directas usando la estrategia de dividir y vencer.

---

## Búsqueda Secuencial

### Código en Java

```java
public static int Secuencial(int[] T, int x) {
    int Encontrado = -1;
    int i = 0;
    while (Encontrado == -1 && i < T.length) {
        if (T[i] == x)
            Encontrado = i;
        i++;
    }
    return Encontrado;
}
```

- **Complejidad:** θ(n)
- **Caso peor:** se recorre todo el arreglo.
- **Caso promedio:** n/2 comparaciones.

---

## Búsqueda Binaria (Iterativa)

### Código en Java

```java
public static int BinIter(int[] T, int x) {
    int n = T.length;
    if (x > T[n-1]) return n + 1;
    int i = 0, j = n;
    while (i < j) {
        int k = (i + j) / 2;
        if (x <= T[k])
            j = k;
        else
            i = k + 1;
    }
    return i;
}
```

- **Complejidad:** θ(log n)

---

## Búsqueda Binaria (Recursiva)

### Código en Java

```java
public static int BinRec(int[] T, int i, int j, int x) {
    if (i == j) return i;
    int k = (i + j) / 2;
    if (x <= T[k])
        return BinRec(T, i, k, x);
    else
        return BinRec(T, k + 1, j, x);
}

public static int BusquedaBin(int[] T, int x) {
    int n = T.length;
    if (n == 0 || x > T[n - 1]) return n + 1;
    return BinRec(T, 0, n, x);
}
```

---

## Complejidad y Eficiencia de Búsqueda Binaria

- **Mejor caso:** 1 comparación (el elemento está en el centro).
- **Peor caso:** log₂(n) comparaciones.
- **Promedio:** log₂(n/2)

> La velocidad de ejecución depende logarítmicamente del tamaño del arreglo.