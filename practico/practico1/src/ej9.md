# Ejercicio 09 - Propiedades de la probabilidad

**Fecha:** 14-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

Sea $(\Omega, \mathcal{A}, P)$ un espacio de probabilidad. Se consideran dos sucesos $A$ y $B$ tales que $P(A) = \frac{1}{3}$ y $P(B) = \frac{1}{2}$. Determinar el valor de $P(A^C \cap B)$ en los siguientes casos:

1. $A$ y $B$ incompatibles (mutuamente excluyentes)
2. $A \subset B$
3. $P(A \cap B) = \frac{1}{8}$

## Resolución

Recordemos que $A^C\cap B=B\setminus A$ como vimos en el ejercicio anterior, y podemos deducir usando diagramas. Esto es importante para varias de las partes.

### Parte 1

- $A$ y $B$ incompatibles (mutuamente excluyentes)

Para esta parte y la tres, tenemos que hacer una observación importante, y es que:

- $B=(B\cap A)\cup(B\cap A^C)$

Es decir, $B$ tiene los elementos de $B$ que se encuentran en $A$ y en $A^C$. Sabemos que los dos conjuntos que mencionamos son mutualmente excluyentes (pues lo que está en $A$ no está en $A^C$ por definición), por lo que corresponde usar la regla de la suma.

- $P(B)=P(B\cap A)+P(B\cap A^C)$

Y como conocemos $P(B)=\frac{1}{2}$ y $P(B\cap A)=0$ (pues $A$ y $B$ son excluyentes), despejamos obteniendo:

- $P(B\cap A^C)=\frac{1}{2}$

### Parte 2

- $A \subset B$

Cuando $A$ es un subconjunto de $B$, sabemos que $P(B\setminus A)=P(B)-P(A)$, por lo tanto la respuesta es que:

- $P(A^C\cap B)=P(B\setminus A)=P(B)-P(A)=\frac{1}{2}-\frac{1}{3}=\frac{1}{6}$

### Parte 3

- $P(A \cap B) = \frac{1}{8}$

Para esta parte nuevamente podemos usar la observación de la parte uno, entonces:

- $P(B)=P(B\cap A)+P(B\cap A^C)$

Y despejando con los valores que conocemos:

- $P(B\cap A^C)=\frac{1}{2}-\frac{1}{8}=\frac{3}{8}$

Esto concluye el ejercicio.