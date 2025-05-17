
# Estructuras de Control

## ¿Qué son las estructuras de control?

- Conjunto de instrucciones que permiten modificar el flujo de ejecución de un algoritmo.
- Permiten que el algoritmo tome decisiones, repita procesos o siga una secuencia ordenada.
- Se clasifican en:
  - **Secuenciales**
  - **Condicionales**
  - **Repetitivas**

---

## Estructuras Secuenciales

- Instrucciones que se ejecutan una tras otra en el orden en que se escriben.
- No requieren decisiones ni condiciones.
- Base para estructuras más complejas.

**Ejemplo:**
```plaintext
Leer A
Leer B
C ← A + B
Imprimir C
```

---

## Estructuras Repetitivas: Bucles (para)

- Repiten un bloque de instrucciones un número determinado de veces.
- Se usa cuando se conoce de antemano cuántas veces se repetirá el ciclo.

**Sintaxis:**
```plaintext
Para i ← 1 hasta n hacer
    Instrucción(es)
FinPara
```

---

## Llamadas Recursivas

### ¿Qué es la recursión?

- Técnica en la que una función se llama a sí misma para resolver un problema.
- Útil cuando el problema puede dividirse en subproblemas más pequeños.

**Elementos:**
- **Caso base:** Condición para detener la recursión.
- **Caso recursivo:** La función se llama a sí misma con una entrada modificada.

### Ejemplo:
```plaintext
Función factorial(n)
    Si n = 0 entonces
        retornar 1
    Sino
        retornar n * factorial(n - 1)
FinFunción
```

---

## Ejemplo de ciclo `for` (análisis de complejidad)

```java
public static void CicloFor1(int n) {
    for (int i = 0; i < n; i++) {
        int x = i;
        x = x * 2;
    }
}
```

- Complejidad: **O(n)**
- Operaciones constantes dentro del ciclo.

---

## Ejemplo con incremento exponencial

```java
public static void CicloFor2(int n) {
    int contador = 0;
    for (int i = 1; i <= n; i = i * 2) {
        contador++;
    }
}
```

- Se incrementa el contador solo cuando `i = 2^k`, donde `k = log₂(n)`
- Complejidad: **O(log n)**

---

## Algoritmo de Burbuja

**Descripción:** Ordena un arreglo `A` de menor a mayor.

```pascal
procedure burbuja(var A: array [1..n] of integer);
var
    i, j, temp: integer;
begin
    for i := 1 to n-1 do
        for j := n downto i + 1 do
            if A[j-1] > A[j] then begin
                temp := A[j-1];
                A[j-1] := A[j];
                A[j] := temp;
            end;
end;
```

- Complejidad aproximada: **O(n²)**

---

## Análisis de complejidad de algoritmo anidado

```pascal
procedure misterio(n: integer);
var
    contador, i, j, k: integer;
begin
    contador := 0;
    for i := 1 to n-1 do
        for j := i + 1 to n do
            for k := 1 to j do
                contador := contador + 1;
end;
```

- Tres bucles anidados.
- Complejidad: **O(n³)** en el peor caso.
