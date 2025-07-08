# Algoritmo de Ordenación Rápida (Quicksort)

--- 
## Prueba de escritorio: quicksort(T[1..7]) con T = [3, 1, 4, 1, 5, 9, 2]

```plaintext
quicksort(T[1..7])
    p = T[1] = 3
    k = 1; i = 8

    Repetir k = k + 1 hasta que T[k] > p
        k = 2 → T[2] = 1 ≤ 3 → sigue
        k = 3 → T[3] = 4 > 3 → se detiene

    Repetir i = i - 1 hasta que T[i] ≤ p
        i = 7 → T[7] = 2 ≤ 3 → se detiene

    Como k < i (3 < 7), intercambiar T[3] y T[7]
        T = [3, 1, 2, 1, 5, 9, 4]

    Repetir k = k + 1 hasta que T[k] > p
        k = 4 → T[4] = 1 ≤ 3 → sigue
        k = 5 → T[5] = 5 > 3 → se detiene

    Repetir i = i - 1 hasta que T[i] ≤ p
        i = 6 → T[6] = 9 > 3 → sigue
        i = 5 → T[5] = 5 > 3 → sigue
        i = 4 → T[4] = 1 ≤ 3 → se detiene

    Como k > i (5 > 4), intercambiar T[1] con T[4]
        T = [1, 1, 2, 3, 5, 9, 4]

    Sublistas: quicksort(T[1..3]) y quicksort(T[5..7])

---

quicksort(T[1..3])
    p = T[1] = 1
    k = 1; i = 4

    Repetir k = k + 1 hasta que T[k] > p
        k = 2 → T[2] = 1 ≤ 1 → sigue
        k = 3 → T[3] = 2 > 1 → se detiene

    Repetir i = i - 1 hasta que T[i] ≤ p
        i = 3 → T[3] = 2 > 1 → sigue
        i = 2 → T[2] = 1 ≤ 1 → se detiene

    Como k > i (3 > 2), intercambiar T[1] y T[2]
        T = [1, 1, 2, 3, 5, 9, 4]

    Sublistas: quicksort(T[1..1]) y quicksort(T[3..3]) (ambas ya ordenadas)

---

quicksort(T[5..7])
    p = T[5] = 5
    k = 5; i = 8

    Repetir k = k + 1 hasta que T[k] > p
        k = 6 → T[6] = 9 > 5 → se detiene

    Repetir i = i - 1 hasta que T[i] ≤ p
        i = 7 → T[7] = 4 ≤ 5 → se detiene

    Como k < i (6 < 7), intercambiar T[6] y T[7]
        T = [1, 1, 2, 3, 5, 4, 9]

    Repetir k = k + 1 hasta que T[k] > p
        k = 7 → T[7] = 9 > 5 → se detiene

    Repetir i = i - 1 hasta que T[i] ≤ p
        i = 6 → T[6] = 4 ≤ 5 → se detiene

    Como k > i (7 > 6), intercambiar T[5] y T[6]
        T = [1, 1, 2, 3, 4, 5, 9]

    Sublistas: quicksort(T[5..5]) y quicksort(T[7..7]) (ambas de un solo elemento)

---

Resultado final:
T = [1, 1, 2, 3, 4, 5, 9]
```
