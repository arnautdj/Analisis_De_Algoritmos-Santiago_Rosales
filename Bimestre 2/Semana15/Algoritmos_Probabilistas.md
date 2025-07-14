# Algoritmos Probabilistas

## Introducción a los algoritmos probabilistas

Un algoritmo probabilista incorpora decisiones aleatorias en su ejecución, lo que puede influir en su resultado o en su eficiencia. Su uso se justifica cuando:

- Se desea evitar el alto costo de evaluar todas las opciones posibles.
- Se aceptan resultados aproximados o soluciones variables.
- Se busca resolver problemas donde las decisiones óptimas no son evidentes de forma determinista.

---

## Ejemplo narrativo (fábula)

- Hay un tesoro con `x` lingotes en una de dos ubicaciones: A o B.
- Tras cada noche, un dragón roba `y` lingotes.
- Desplazarse a A o B toma 5 días.
- En el punto O puedo descubrir la ubicación correcta en 4 días usando una computadora.
- Un elfo ofrece la solución inmediata a cambio del equivalente a 3 noches de saqueo del dragón (3y).

### Opciones:
- Quedarse en O y esperar 4 días: se obtienen `x - 9y`.
- Aceptar el trato del elfo: se obtienen `x - 8y`.
- Tirar una moneda:
  - Si se acierta: `x - 5y`
  - Si se falla: `x - 10y`
  - Valor esperado: `x - 7.5y`

**Conclusión:** A veces la mejor decisión es probabilística, no determinista.

---

## Fundamentos teóricos

### Comportamiento de algoritmos probabilistas vs deterministas

- Un **algoritmo determinista**:
  - Siempre produce el mismo resultado con la misma entrada.
  - No permite errores ni ciclos infinitos.
- Un **algoritmo probabilista**:
  - Puede generar distintos resultados con la misma entrada.
  - Puede producir errores con baja probabilidad.
  - Puede abortar y repetirse en caso de error.

---

## Definiciones clave

| Concepto         | Tiempo Promedio (Determinista)             | Tiempo Esperado (Probabilista)                      |
|------------------|---------------------------------------------|-----------------------------------------------------|
| Variabilidad     | En la entrada                                | En el comportamiento interno del algoritmo          |
| Promedio sobre   | Todas las entradas posibles                  | Todas las ejecuciones posibles con la misma entrada |
| Entrada          | Varía                                        | Fija                                                |
| Uso principal    | Evaluar el rendimiento general               | Evaluar la eficiencia promedio con aleatoriedad     |

---

## Probabilidades básicas

La probabilidad de un evento es:

```
P = (número de casos favorables) / (número total de casos)
```

Por definición: `0.0 ≤ P ≤ 1.0`

### Ejemplo:

Dado el conjunto {1, 2, 3, 4, 5, 6}:
- Probabilidad de sacar 1 o 6: 2/6 = 0.33
- Probabilidad de sacar un número par: 3/6 = 0.5

---

## Generación de números pseudoaleatorios

Los números pseudoaleatorios son generados mediante algoritmos deterministas que simulan aleatoriedad.

### Método congruencial lineal

Fórmula general:

```
X_(n+1) = (a * X_n + c) mod m
```

Donde:
- `X_0`: Semilla inicial
- `a`, `c`, `m`: Constantes enteras cuidadosamente seleccionadas

### Ejemplo:

```Java
public class GeneradorPseudoaleatorio {

    public static void main(String[] args) {
        int cantidad = 10;
        long semilla = 12345;

        double[] numeros = generarPseudoaleatorios(semilla, cantidad);

        System.out.println("Números pseudoaleatorios generados:");
        for (double num : numeros) {
            System.out.println(num);
        }
    }

    public static double[] generarPseudoaleatorios(long semilla, int cantidad) {
        // Parámetros del generador (Numerical Recipes)
        long a = 1664525;
        long c = 1013904223;
        long m = (long) Math.pow(2, 32);

        double[] resultados = new double[cantidad];
        long x = semilla;

        for (int i = 0; i < cantidad; i++) {
            x = (a * x + c) % m;
            resultados[i] = (double) x / m;  // Normalización a [0, 1)
        }

        return resultados;
    }
}

```

## Tipos de algoritmos probabilistas

- **Monte Carlo**: Puede devolver resultados incorrectos pero con probabilidad controlada.
- **Las Vegas**: Siempre devuelve un resultado correcto, pero su tiempo de ejecución es aleatorio.