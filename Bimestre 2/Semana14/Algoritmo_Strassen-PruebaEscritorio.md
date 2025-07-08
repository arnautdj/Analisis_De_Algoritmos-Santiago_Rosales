# Multiplicación de Matrices – Algoritmo de Strassen

## Ejercicio 1

**Multiplicar:**

    A = | 1 3 |
        | 5 7 |

    B = | 8 4 |
        | 6 2 |

**Submatrices:**

    A11 = 1    A12 = 3    B11 = 8    B12 = 4
    A21 = 5    A22 = 7    B21 = 6    B22 = 2

**Cálculo de productos:**

- M1 = (1 + 7)(8 + 2) = 8 * 10 = 80
- M2 = (5 + 7) * 8 = 12 * 8 = 96
- M3 = 1 * (4 - 2) = 1 * 2 = 2
- M4 = 7 * (6 - 8) = 7 * (-2) = -14
- M5 = (1 + 3) * 2 = 4 * 2 = 8
- M6 = (5 - 1)(8 + 4) = 4 * 12 = 48
- M7 = (3 - 7)(6 + 2) = -4 * 8 = -32

**Cálculo de submatrices de C:**

- C11 = M1 + M4 - M5 + M7 = 80 - 14 - 8 - 32 = 26
- C12 = M3 + M5 = 2 + 8 = 10
- C21 = M2 + M4 = 96 - 14 = 82
- C22 = M1 - M2 + M3 + M6 = 80 - 96 + 2 + 48 = 34

**Resultado final:**

    C = | 26 10 |
        | 82 34 |

---


## Ejercicio 2

Multiplicar las siguientes matrices usando Strassen:
````
A = | 7 6 9 4 |
    | 8 5 3 2 |
    | 7 7 9 9 |
    | 4 3 8 5 |

B = | 3 2 9 5 |
    | 7 5 6 4 |
    | 4 6 9 1 |
    | 9 3 8 7 |
````

---

### Paso 1: Dividir matrices en submatrices

Submatrices de A:

A11 = [[7, 6], [8, 5]]  
A12 = [[9, 4], [3, 2]]  
A21 = [[7, 7], [4, 3]]  
A22 = [[9, 9], [8, 5]]

Submatrices de B:

B11 = [[3, 2], [7, 5]]  
B12 = [[9, 5], [6, 4]]  
B21 = [[4, 6], [9, 3]]  
B22 = [[9, 1], [8, 7]]

---

### Paso 2: Calcular las 7 multiplicaciones de Strassen

Fórmulas:

- M1 = (A11 + A22)(B11 + B22) = [[417, 228], [342, 168]]
- M2 = (A21 + A22) * B11 = [[160, 112], [92, 64]]
- M3 = A11 * (B12 - B22) = [[-12, 10], [-10, 17]]
- M4 = A22 * (B21 - B11) = [[27, 18], [18, 22]]
- M5 = (A11 + A12) * B22 = [[224, 86], [155, 60]]
- M6 = (A21 - A11) * (B11 + B12) = [[13, 9], [-74, -46]]
- M7 = (A12 - A22) * (B21 + B22) = [[-85, -50], [-116, -65]]

---

### Paso 3: Calcular los valores de la matriz resultante C

Usando las combinaciones:

- C11 = M1 + M4 - M5 + M7 = [[135, 110], [89, 65]]
- C12 = M3 + M5 = [[212, 96], [145, 77]]
- C21 = M2 + M4 = [[187, 130], [110, 86]]
- C22 = M1 - M2 + M3 + M6 = [[258, 135], [166, 75]]

---

### Resultado final:
````
C = | 135  110  212   96 |
    |  89   65  145   77 |
    | 187  130  258  135 |
    | 110   86  166   75 |
````
