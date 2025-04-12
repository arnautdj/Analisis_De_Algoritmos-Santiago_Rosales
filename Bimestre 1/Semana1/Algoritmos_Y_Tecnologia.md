# Tema 1.2 - Los algoritmos como tecnología

## ¿Por qué estudiar algoritmos si las computadoras son rápidas?

Aunque las computadoras actuales son veloces y la memoria es barata, **el tiempo y los recursos siguen siendo limitados**. Estudiar algoritmos permite:

- Asegurar que el método termine correctamente
- Optimizar tiempo y espacio de ejecución
- Resolver problemas de gran escala de forma práctica


---

## Eficiencia algorítmica

Diferentes algoritmos para el mismo problema pueden tener eficiencias muy distintas.

### Ejemplo: Insertion Sort vs. Merge Sort

- **Insertion Sort:** Tiempo ≈ `c₁ * n²`
- **Merge Sort:** Tiempo ≈ `c₂ * n log n`

Aunque Insertion Sort tiene menor constante (`c₁ < c₂`), **para entradas grandes**, Merge Sort se vuelve mucho más rápido debido a su crecimiento logarítmico.

---

## Comparación práctica

### Caso extremo:

- **Computadora A:** Muy rápida (10 mil millones instrucciones/segundo), ejecuta Insertion Sort
- **Computadora B:** Muy lenta (10 millones instrucciones/segundo), ejecuta Merge Sort

Para ordenar 10 millones de elementos:

- A (Insertion Sort): ~5.5 horas
- B (Merge Sort): ~20 minutos

**Conclusión:** Un algoritmo eficiente puede superar en rendimiento a una computadora mucho más potente con un algoritmo ineficiente.

---

## Algoritmos y otras tecnologías

Los algoritmos son tan importantes como:

- Arquitectura y hardware avanzado
- Interfaces gráficas de usuario (GUI)
- Programación orientada a objetos
- Redes rápidas
- Aprendizaje automático
- Aplicaciones móviles

Incluso cuando un programa no parece depender de algoritmos, **estos están presentes en su compilador, sistema operativo, red, hardware, etc.**

---

## ¿Y el aprendizaje automático?

El **machine learning** parece prescindir de algoritmos manuales, pero en realidad:

- Está basado en **colecciones de algoritmos**
- Se usa cuando no se conoce el algoritmo exacto para resolver un problema (como visión por computadora o traducción automática)
- No reemplaza a los algoritmos diseñados específicamente, que son más eficientes cuando el problema está bien definido

---

## Relación con la ciencia de datos

La **ciencia de datos** combina estadística, computación y optimización para extraer conocimiento de los datos. Los algoritmos son parte central en:

- Clasificación y regresión
- Agrupamiento (clustering)
- Optimización
- Limpieza y análisis de datos

---

## Conclusión

Los algoritmos son una tecnología esencial. No solo permiten resolver problemas eficientemente, sino que son la base oculta de casi todo en la computación moderna. Cuanto mayor es el tamaño del problema, mayor es el valor de un algoritmo bien diseñado.

