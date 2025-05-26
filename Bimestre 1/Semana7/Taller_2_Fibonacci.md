# Taller 2 - Sucesión de Fibonacci

## 1. Fibonacci en Java

Se presenta a continuación la versión recursiva del algoritmo que calcula el n-ésimo número de la sucesión de Fibonacci:

```java
public class Fibonacci {
    public static int fibonacci(int n) {
        if (n <= 1) return n;
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        int n = 10;
        System.out.println("Fibonacci de " + n + " es: " + fibonacci(n));
    }
}
```

---

## 2. Identificar la recurrencia

La función `fibonacci(n)` tiene la siguiente recurrencia:

```
T(n) = T(n-1) + T(n-2) + c
```

donde `c` es una constante que representa las operaciones básicas.  
Esto se debe a que la función llama a sí misma dos veces en cada ejecución para `n > 1`.

---

## 3. Obtener la ecuación general

La sucesión de Fibonacci se define como:

```
F(0) = 0  
F(1) = 1  
F(n) = F(n-1) + F(n-2)  para n ≥ 2
```

La fórmula cerrada (conocida como **fórmula de Binet**) es:

```
F(n) = (φ^n - ψ^n) / √5
```

donde:

- φ = (1 + √5) / 2  
- ψ = (1 - √5) / 2

---

## 4. Demostración por inducción matemática

Queremos demostrar que:

```
F(n) = (φ^n - ψ^n) / √5
```

### Base

Para `n = 0`:

```
F(0) = (φ^0 - ψ^0) / √5 = (1 - 1) / √5 = 0 ✅
```

Para `n = 1`:

```
F(1) = (φ - ψ) / √5 = √5 / √5 = 1 ✅
```

### Paso inductivo

Suponiendo que la fórmula es válida para `n = k` y `n = k-1`, demostrar que también lo es para `n = k+1`.

```
F(k+1) = F(k) + F(k-1)

Usando la fórmula:

F(k+1) = [(φ^k - ψ^k) + (φ^(k-1) - ψ^(k-1))] / √5
       = (φ^(k+1) - ψ^(k+1)) / √5
```

Por lo tanto, se cumple la fórmula cerrada por inducción matemática.