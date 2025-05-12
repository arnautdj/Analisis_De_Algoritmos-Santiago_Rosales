# Análisis de Algoritmos – Resolución del Ejercicio

Dado:

- f(n) = n³ + 9n² * log(n)
- g(n) = n² * log(n)

Se pide:

Parte 1.
- Comprobar si f(n) ∈ O(g(n))
- Comprobar si f(n) ∉ O(n²)

Parte 2.
- Demostrar formalmente si existe relación de pertenencia:
  - Entre f(n) y O(g(n))
  - Y también entre g(n) y O(f(n))
  
    Considerando:
    - f(n) = 2ⁿ
    - g(n) = 2^(2n)


---

## Parte 1

### Dado:

- f(n) = n^3 + 9n^2 * log(n)
- g(n) = n^2 * log(n)

---

### ¿f(n) pertenece a O(g(n))?

Evaluamos el cociente:

f(n) / g(n) = (n^3 + 9n^2 * log(n)) / (n^2 * log(n))  
= n / log(n) + 9

Al aplicar el límite cuando n tiende a infinito:

lim (n → ∞) [n / log(n) + 9] = ∞

**Conclusión:**

Como el cociente tiende a infinito, esto indica que f(n) crece más rápido que g(n) = n^2 * log(n).  
Por lo tanto, **f(n) NO pertenece a O(g(n))**.  

---

### ¿f(n) pertenece a O(n^2)?

Evaluamos:

f(n) / n^2 = (n^3 + 9n^2 * log(n)) / n^2  
= n + 9 * log(n)

lim (n → ∞) [n + 9 * log(n)] = ∞

**Conclusión:**

El cociente tiende a infinito, lo que significa que f(n) crece más rápido que n^2.  
Por lo tanto, **f(n) NO pertenece a O(n^2)**.

---

## Parte 2

### Dado:

- f(n) = 2^n
- g(n) = 2^(2n) = 4^n

---

### ¿Existe una relación de pertenencia entre f(n) y O(g(n))?

Evaluamos:

f(n) / g(n) = 2^n / 4^n = 2^n / (2^2)^n = 2^n / 2^(2n) = 2^(-n)

lim (n → ∞) [2^(-n)] = 0

**Conclusión:**

Como el cociente tiende a 0, f(n) crece mucho más lento que g(n).  
Por lo tanto, **sí existe una relación de pertenencia: f(n) pertenece a O(g(n))**.

---

### ¿Existe una relación de pertenencia entre g(n) y O(f(n))?

Evaluamos:

g(n) / f(n) = 4^n / 2^n = 2^(2n) / 2^n = 2^n

lim (n → ∞) [2^n] = ∞

**Conclusión:**

Como el cociente tiende a infinito, g(n) crece más rápido que f(n).  
Por lo tanto, **NO existe una relación de pertenencia: g(n) NO pertenece a O(f(n))**.