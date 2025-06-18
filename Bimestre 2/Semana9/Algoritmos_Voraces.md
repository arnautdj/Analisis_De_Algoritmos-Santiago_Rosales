
# Algoritmos Voraces

## ¿Qué son los algoritmos voraces?

Los algoritmos voraces construyen una solución paso a paso, eligiendo la opción que parece ser la mejor en cada etapa. Esta técnica no garantiza siempre la solución óptima, pero es eficiente y adecuada para ciertos problemas específicos.

---

## Características principales

- Se construye la solución de forma incremental.
- En cada paso se toma la mejor decisión local posible.
- No se reconsideran decisiones previas.
- Son rápidos y simples en comparación con otros enfoques más exhaustivos.

---

## Aplicaciones de algoritmos voraces en grafos

### Grafos no dirigidos

- **Matriz de adyacencia**: Se utiliza para representar conexiones entre vértices. Es una matriz cuadrada, donde cada celda indica si existe o no una arista entre dos vértices.

- **Vértices adyacentes**: Dos vértices son adyacentes si están conectados directamente por una arista.

- **Grafos conexos y no conexos**: 
  - Un grafo es **conexo** si se puede llegar de cualquier vértice a otro.
  - Es **no conexo** si existe al menos un vértice que no puede ser alcanzado desde otro.

- **Grafos ponderados**: Las aristas tienen pesos que representan un valor, como distancia, costo o tiempo.

---

### Grafos dirigidos

- **Definición**: Las aristas tienen una dirección, es decir, van de un vértice origen a un vértice destino.

- **Representación**: También pueden representarse mediante matrices de adyacencia, pero los valores indican la dirección del flujo.

- **Ejemplo de aplicación**: Rutas de entrega, flujos de tráfico, tareas con orden de ejecución.

---

## Ejemplo práctico de aplicación voraz

Los algoritmos voraces se aplican comúnmente a problemas como:

- **Árboles de expansión mínima** (ej. algoritmo de Kruskal, Prim)
- **Problema de la mochila fraccionaria**
- **Selección de actividades**
- **Códigos Huffman** para compresión de datos

