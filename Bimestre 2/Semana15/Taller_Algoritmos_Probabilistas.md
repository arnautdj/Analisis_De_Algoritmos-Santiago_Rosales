# Algoritmos Probabilistas

## Taller:



1. Implementar el generador pseudoaleatorio con el método congruencial lineal en Java.
2. Generar una secuencia de 100 números normalizados en [0, 1).
3. Mostrar los primeros 10 valores generados.
4. Analizar la distribución:
   - ¿Es aproximadamente uniforme?
   - ¿Qué efecto tiene cambiar la semilla?

---

# Generador Lineal Congruencial

---

## 1. Parámetros del generador

| Parámetro | Valor |
|-----------|-------|
| a (multiplicador) | 1664525 |
| c (incremento) | 1013904223 |
| m (módulo) | 2^32 = 4294967296 |
| Semilla X0 | 987654321 |

---

## 2. Implementación en Java
Generador congruencial lineal de 32 bits normalizado a [0,1).

```java
public class LinearCongruentialGenerator {

    private static final long A = 1_664_525L;
    private static final long C = 1_013_904_223L;
    private static final long M = 1L << 32; // 2^32
    private long state;

    public LinearCongruentialGenerator(long seed) {
        state = seed;
    }

    private long nextUInt() {
        state = (A * state + C) % M;
        return state;
    }

    public double nextDouble() {
        return (nextUInt() & 0xFFFFFFFFL) / (double) M;
    }

    public static void main(String[] args) {
        long seed = 987654321L;
        LinearCongruentialGenerator lcg = new LinearCongruentialGenerator(seed);

        for (int i = 0; i < 10; i++) {
            System.out.printf("%.10f%n", lcg.nextDouble());
        }
    }
}
```

---

## 3. Secuencia generada

Se obtuvieron 100 números `u_i` en el intervalo [0, 1). Los primeros 10 son:

| i | u_i |
|---|----------------|
| 1 | 0.0653349375 |
| 2 | 0.8729687955 |
| 3 | 0.6203584629 |
| 4 | 0.4065450702 |
| 5 | 0.6690972634 |
| 6 | 0.3583722373 |
| 7 | 0.7843605881 |
| 8 | 0.0439127965 |
| 9 | 0.1837228248 |
| 10 | 0.4710008546 |

---

## 4. Distribución por intervalos

| Intervalo | Frecuencia |
|-----------|------------|
| 0.0 – 0.2 | 13 |
| 0.2 – 0.4 | 20 |
| 0.4 – 0.6 | 24 |
| 0.6 – 0.8 | 22 |
| 0.8 – 1.0 | 21 |

Con 100 muestras esperaríamos unas 20 por intervalo si la distribución fuera perfectamente uniforme.
Las frecuencias observadas están próximas a ese valor, lo que respalda la uniformidad para este tamaño de muestra.

---

## 5. Preguntas

1. **¿La distribución es aproximadamente uniforme?**

   Sí. Las frecuencias por intervalo son cercanas a la expectativa de 20.


2. **¿Qué efecto tiene cambiar la semilla?**

   Cambia completamente la secuencia generada.
