# Notación Asintótica

## ¿Qué es la Notación Asintótica?

La notación asintótica describe cómo crece el tiempo de ejecución de un algoritmo a medida que aumenta el tamaño de la entrada. Es una medida de **eficiencia asintótica**, enfocada en el **comportamiento de las funciones en el límite**, es decir, cuando *n* tiende a infinito.

- Se representa con funciones cuyo dominio es el conjunto de los números naturales.
- Permite comparar algoritmos ignorando factores como el lenguaje, compilador o la velocidad del hardware.

---

## Crecimiento y tasa de ejecución

El tiempo de ejecución se evalúa con base en:

1. ¿Cuánto tiempo tarda el algoritmo según el tamaño de la entrada?
2. ¿Qué tan rápido crece esa función?

> Ejemplo: Si un algoritmo tarda `6n² + 100n + 300` operaciones, el término dominante es `6n²`, que se vuelve más relevante a medida que n crece (aproximadamente desde n=20).

---

## Descartar términos y coeficientes

Para simplificar análisis, **se ignoran coeficientes constantes** y los términos de menor crecimiento. Así:

- `6n² + 100n + 300` → se considera como `O(n²)`

---

## Tipos de Notación

### Notación O (Orden superior)

Describe una **cota superior** al tiempo de ejecución de un algoritmo. Se usa para analizar el **peor caso**.

Ejemplos comunes:
- O(1): constante
- O(log n): logarítmica
- O(n): lineal
- O(n²): cuadrática
- O(aⁿ): exponencial
- O(n!): factorial

**Regla del máximo**:  
Si T(n) = T₁(n) + T₂(n) → entonces T(n) ∈ O(max(f(n), g(n)))

---

### Notación Ω (Omega)

Define una **cota inferior** asintótica. Representa el mejor caso de eficiencia.

Formalmente:
- T(n) ∈ Ω(f(n)) si existen constantes positivas d y n₀ tales que:
  - T(n) ≥ d * f(n) para todo n ≥ n₀

---

### Notación Θ (Theta)

Establece una **cota ajustada** (por arriba y por abajo). Representa el **orden exacto** de crecimiento.

Formalmente:
- T(n) ∈ Θ(f(n)) si existen constantes c y d tales que:
  - d * f(n) ≤ T(n) ≤ c * f(n), para todo n ≥ n₀

---

## Reglas de comparación

### Regla del límite

Permite determinar la relación asintótica entre dos funciones:

- Si lim (f(n)/g(n)) = 0 → f(n) ∈ O(g(n))
- Si lim (f(n)/g(n)) = ∞ → f(n) ∉ O(g(n)), pero g(n) ∈ O(f(n))
- Si lim (f(n)/g(n)) = constante ≠ 0 → f(n) ∈ Θ(g(n))

---

## Consideraciones prácticas

- La eficiencia de un algoritmo es relevante especialmente para entradas grandes o programas que se ejecutan frecuentemente.
- En algoritmos numéricos, precisión y estimación pueden ser tan importantes como eficiencia.

---

## Ejercicio de análisis de código

```pseudo
n = 2
contador = 0
numero = 2

while (contador < n)
    sumaDivisores = 1
    for i = 2 to numero/2
        if numero % i == 0
            sumaDivisores = sumaDivisores + i
    if sumaDivisores == numero
        imprimir(numero)
        contador = contador + 1
    numero = numero + 1
```

Este pseudocódigo busca los primeros dos **números perfectos**.

---

