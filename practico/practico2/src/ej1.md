# Ejercicio 01 - Cálculo de probabilidades

**Fecha:** 15-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Determinar el espacio muestral asociado a cada uno de los siguientes experimentos aleatorios, y en el caso que sea finito, indicar su cardinal.

1. Lanzar al aire una moneda tres veces.
2. Extraer dos fichas sucesivamente y sin reposición de una bolsa que contiene fichas numeradas con los 5 dígitos pares.
3. Lanzar una moneda finalizando el experimento si sale número; si sale cara, tirar además un dado.
4. Seleccionar al azar dos alumnos de una clase de 30.
5. Valor de la tasa de inflación para este año.

## Resolución

### Parte 1

- Lanzar al aire una moneda tres veces.

El espacio muestral es aquel que contiene todas las combinaciones posibles de cara o cruz con tres lanzamientos, un ejemplo de esto sería el lanzamiento:

- $XCX$

El cardinal del espacio muestral está dado por la regla del producto.

- $|\Omega|=2\times 2\times 2=8$

### Parte 2

- Extraer dos fichas sucesivamente y sin reposición de una bolsa que contiene fichas numeradas con los 5 dígitos pares.

Como la parte anterior, demos un ejemplo para entender cuales son los casos con los que trabajamos:

- $(0,2)$

El cardinal depende de si el orden en el que extraemos los dígitos importa o no. Nosotros consideraremos que importa, entonces el cardinal está dado por:

- $|\Omega|=A^5_2=\frac{5!}{5-2!}=5\cdot4=20$

### Parte 3

- Lanzar una moneda finalizando el experimento si sale número; si sale cara, tirar además un dado.

Veamos algunos ejemplos para entender cuales son los casos con los que trabajamos.

- $X$.
- $C$ y $3$ en el dado.
- $C$ y $2$ en el dado.

Entonces el cardinal está dado básicamente por la regla de la suma, sabiendo que tenemos un solo caso donde la moneda sale cruz, y 6 casos donde la moneda sale cara.

- $|\Omega|=C_X+C_C=1+6=7$

### Parte 4

- Seleccionar al azar dos alumnos de una clase de 30.

Para este caso ni hace falta ver un ejemplo del espacio muestral, calculamos directamente usando combinaciones pues no nos importa el orden.

- $C^{30}_2=\frac{30!}{30-2!2!}=15\cdot29=435$

### Parte 5

- Valor de la tasa de inflación para este año.

Es el único caso del práctico que tiene que ver con probabilidades geométricas, donde el cardinal no es finito.
Hay una sección de teórico que tiene que ver con esto, pero no está marcado en el cronograma por lo que vista la poca cantidad que se usa en el práctico lo voy a ignorar.