## Inducción Matemática

La **inducción matemática** es una técnica de demostración lógica para afirmar propiedades sobre los números naturales.

### Pasos del Principio de Inducción

1. **Caso base**: Demostrar que la afirmación es válida para \( n = 1 \).
2. **Hipótesis de inducción**: Suponer que se cumple para \( n = k \).
3. **Paso inductivo**: Probar que si se cumple para \( n = k \), entonces se cumple para \( n = k + 1 \).

### Ejemplo de demostración

Demostrar que:

\[
1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2}
\]

- **Caso base (n=1)**:
  \[
  1 = \frac{1(1+1)}{2} = 1
  \]
- **Hipótesis (n=k)**:
  \[
  1 + 2 + 3 + \dots + k = \frac{k(k+1)}{2}
  \]
- **Paso inductivo (n=k+1)**:
  \[
  (1 + 2 + 3 + \dots + k) + (k+1) = \frac{(k+1)(k+2)}{2}
  \]

---

## Procedimientos y Algoritmos

### Ordenamiento de un Arreglo

**Algoritmo tipo burbuja**:

```pseudo
for i ← 1 to n-1
  for j ← i+1 to n
    if A[i] > A[j]
      aux ← A[i]
      A[i] ← A[j]
      A[j] ← aux
```

---

### Verificación de Números Primos

Algoritmo para verificar si un número es primo:

```pseudo
if n ≤ 1
  return False
i ← 2
while i ≤ n/2
  if n mod i = 0
    return False
  i ← i + 1
return True
```

