
# Multiplicación de Matrices – Algoritmo de Strassen

## Algoritmo clásico de multiplicación de matrices

**Código Java:**
```java
public static void multiplicar(int [][] a, int [][] b, int [][] c) {
    int n = a.length;
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            c[i][j] = 0;
            for (int k = 0; k < n; k++) {
                c[i][j] += a[i][k] * b[k][j];
            }
        }
    }
}
```

**Fórmula matemática:**

    C[i][j] = ∑ A[i][k] * B[k][j]

**Complejidad:**

    O(n³)

---

## Algoritmo de Strassen

Dado matrices divididas en submatrices:

    A = | A11 A12 |      B = | B11 B12 |
        | A21 A22 |          | B21 B22 |

Se definen las siguientes 7 multiplicaciones:

- M1 = (A11 + A22)(B11 + B22)
- M2 = (A21 + A22) * B11
- M3 = A11 * (B12 - B22)
- M4 = A22 * (B21 - B11)
- M5 = (A11 + A12) * B22
- M6 = (A21 - A11) * (B11 + B12)
- M7 = (A12 - A22) * (B21 + B22)

Se combinan los resultados:

- C11 = M1 + M4 - M5 + M7
- C12 = M3 + M5
- C21 = M2 + M4
- C22 = M1 - M2 + M3 + M6

**Complejidad:**

    O(n^log₂7) ≈ O(n^2.81)

---

## Instrucciones del algoritmo de Strassen

1. Dividir las matrices A y B en submatrices de tamaño n/2 x n/2.
2. Realizar O(n²) operaciones de suma/resta para obtener matrices intermedias.
3. Calcular las 7 multiplicaciones recursivamente.
4. Combinar los productos con sumas/restas para obtener el resultado.

---


