# Recurrencias

## ¿Qué es una recurrencia?

Una **relación de recurrencia** describe el tiempo de ejecución de un algoritmo recursivo en función del tamaño del problema y de llamadas recursivas a subproblemas más pequeños.

Por ejemplo, el factorial `n!` se puede expresar como:

```
n! = n * (n-1)!
```

Las recurrencias se utilizan para determinar **cotas asintóticas** del tiempo de ejecución de algoritmos recursivos.

---

## Métodos para resolver recurrencias

### 1. Suposiciones inteligentes

Pasos para resolver una recurrencia de esta manera:

1. Calcular los primeros valores.
2. Observar un patrón o regularidad.
3. Formular una conjetura.
4. Demostrar por **inducción matemática** u otro método.

### 2. Ecuación característica

Este método se usa cuando la recurrencia es lineal con coeficientes constantes. Se transforma en una ecuación algebraica cuyas raíces ayudan a describir la solución general.

---

## Ejemplos de resolución

### Ejemplo 1:

```
T(n) = T(n-1) + 1
```

Resolviendo:

```
T(n) = (n-1) + 1 = n
```

Resultado: T(n) = n

---

### Ejemplo 2:

```
T(n) = 3 * T(n/2) + n
```

Valores evaluados:

| n  | T(n)                          |
|----|-------------------------------|
| 1  | 1                             |
| 2  | 3*T(1) + 2 = 5                |
| 4  | 3*T(2) + 4 = 19               |
| 8  | 3*T(4) + 8 = 65               |
| 16 | 3*T(8) + 16 = 211             |
| 32 | 3*T(16) + 32 = 665            |

---

## Observaciones adicionales

Se puede notar una estructura repetitiva al expandir la recurrencia, por ejemplo:

```
T(2^k) = 3^k * T(1) + 3^(k-1)*2 + 3^(k-2)*2^2 + ... + 3*2^(k-1) + 2^k
```

Esto sugiere que:

```
T(2^k) = Σ (de i = 0 a k) de 3^(k-i) * 2^i
```

---

## Taller propuesto

Resolver la siguiente recurrencia:

```
T(n) = ?
```

(Sin datos adicionales, este ejercicio se deja como práctica para el alumno.)

---

## Taller

### Recurrencia dada:

```
T(n) = {
  0              si n = 0
  2T(n-1) + 1    si n > 0
}
```

### Valores observados:

| n | T(n)        |
|---|-------------|
| 1 | 1           |
| 2 | 3           |
| 3 | 7           |
| 4 | 15          |
| 5 | 31          |
| 6 | 63          |
| 7 | 127         |
| 8 | 255         |

### Patrón observado

```
T(n) = 2^n - 1
```

### Demostración por inducción matemática

**Hipótesis de inducción:**  
T(k) = 2^k - 1

**Paso inductivo:**

```
T(k+1) = 2T(k) + 1
       = 2(2^k - 1) + 1
       = 2^(k+1) - 2 + 1
       = 2^(k+1) - 1
```

**Conclusión:** La fórmula T(n) = 2^n - 1 es correcta por inducción matemática.
