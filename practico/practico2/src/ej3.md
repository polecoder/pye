# Ejercicio 03 - Cálculo de probabilidades

**Fecha:** 15-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Si a un ómnibus con $n$ asientos suben $i$ personas con $i \leq n$.

1. ¿De cuántas maneras pueden elegirse los asientos en los que se sentará la gente?
2. ¿De cuántas maneras distintas puede disponerse la gente en el ómnibus?
3. Asumamos ahora que la gente se dispone al azar y que cada disposición particular tiene la misma probabilidad (equiprobabilidad).
Supongamos que $n = 4m$ y que el ómnibus tiene un pasillo en el medio; y que a cada costado del pasillo hay $m$ filas de 2 asientos.
Para darle un toque romántico, suponga ahora que sube al ómnibus Keanu Reeves o Angelina Jolie (según la opción de cada uno), ¿qué probabilidad tiene Ud. de quedar sentado al lado del personaje en cuestión?

## Resolución

### Parte 1

- ¿De cuántas maneras pueden elegirse los asientos en los que se sentará la gente?

Para esta parte la respuesta es bastante sencilla, ya que solo queremos elegir los asientos, por lo que el orden no importa, y esto nos hace elegir a las combinaciones para obtener la cantidad.

- $\mathcal{C}_{\text{asientos}}=C^n_i$

### Parte 2

- ¿De cuántas maneras distintas puede disponerse la gente en el ómnibus?

Para esta parte, tenemos una dificultad agregada, y es que tenemos que considerar una forma de representar las disposiciones... Esto parece complicado pero en realidad basta con numerar cada posición de 1 hasta n. Con esto podemos ver que una disposición equivale a un Arreglo de $i$ elementos tomados de $n$ totales. Entonces tenemos que:

- $\mathcal{C}_{\text{disposiciones}}=A^n_i$

### Parte 3

- Asumamos ahora que la gente se dispone al azar y que cada disposición particular tiene la misma probabilidad (equiprobabilidad).
Supongamos que $n = 4m$ y que el ómnibus tiene un pasillo en el medio; y que a cada costado del pasillo hay $m$ filas de 2 asientos.
Para darle un toque romántico, suponga ahora que sube al ómnibus Keanu Reeves o Angelina Jolie (según la opción de cada uno), ¿qué probabilidad tiene Ud. de quedar sentado al lado del personaje en cuestión?

Para esta parte tenemos varias formas de realizar el conteo para encontrar la probabilidad. La que más entiendo tiene que ver con el espacio muestral definido por:

- $\Omega$: Formas de acomodar a dos personas en el ómnibus (en mi caso Angelina Jolie y yo).

Entonces el cardinal de nuestro espacio muestral es:

- $|\Omega|=A^n_2=\frac{n!}{n-2!}=n(n+1)$

Notemos que este razonamiento es totalmente independiente de las $i$ personas que se suben al ómnibus. Y esto tiene sentido para la letra del problema que queremos resolver (pues la letra no aclara que, por ejemplo, las otras personas $i-2$ se suben antes que nosotros).

Segumios con los casos favorables, que son bastante fáciles de encontrar, ya que tenemos 4 por cada fila, por ejemplo para la fila 1:

- (1,2), (2,1), (3,4), (4,3)

Este razonamiento es idéntico para las demás filas, por lo que tenemos $4m$ casos favorables. Llamando $A$ al evento de que estemos sentados al lado, tenemos que:

- $P(A)=\frac{4m}{n(n+1)}=\frac{1}{n+1}$

Esto concluye el ejercicio.