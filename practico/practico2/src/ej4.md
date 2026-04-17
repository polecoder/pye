# Ejercicio 04 - Cálculo de probabilidades

**Fecha:** 16-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

1. Calcular la probabilidad de obtener una suma de puntos menor que 18 al tirar 3 dados.
2. Se elige un grupo de $n$ personas al azar. Descartando los años bisiestos y suponiendo por lo tanto años de 365 días, ¿cuál es la probabilidad de que al menos dos personas cumplan el mismo día? ¿Cuánto tiene que ser $n$ para que dicha probabilidad supere a $0.5$?

## Resolución

### Parte 1

- Calcular la probabilidad de obtener una suma de puntos menor que 18 al tirar 3 dados.

El espacio muestral que estamos considerando son las combinaciones que puede dar tirar tres dados. Esto se obtiene con la regla del producto fácilmente. Tengamos presente que nos da igual el orden de los dados, esto influye en el cálculo

- $|\Omega|=\frac{6\times6\times 6}{3!}=36$

Por otra parte, los casos favorables son aquellos en que la suma es menor que 18... Pero estos son todos menos el caso en que justamente los dados suman 18, entonces llamando $A$ a este evento:

- $P(A)=\frac{35}{36}=0.97$

### Parte 2

- Se elige un grupo de $n$ personas al azar. Descartando los años bisiestos y suponiendo por lo tanto años de 365 días, ¿cuál es la probabilidad de que al menos dos personas cumplan el mismo día? ¿Cuánto tiene que ser $n$ para que dicha probabilidad supere a $0.5$?

La estrategia para esta parte es bastante interesante, es de los problemas de probabilidad más interesantes y conocidos.

Contar en cuántos casos de $n$ personas al azar existen al menos dos que cumplan el mismo día es una tarea bastante díficil, llamemos $A$ a este evento.
No así, contar el complemento de este evento, $A^C$. Esto sería contar todos aquellos grupos de $n$ personas en los cuales ninguna cumple el mismo día.

Para contar esto, veamos que:

- Para la primer persona, tenemos $365$ posibilidades
- Para la segunda persona, tenemos $364$ posibilidades
- Y así sucesivamente...
- Para la enésima persona, tenemos $365-n+1$ posibilidades

Entonces:

- $|A^C|=365\cdot364\cdot\ldots\cdot(365-n+1)$

Para calcular la probabilidad, necesitamos encontrar el espacio muestral. Este es el espacio en el que simplemente elegimos $n$ cumpleaños en cualquiera de los 365 días del año, por lo que:

- $|\Omega|=365^n$

Entonces $P(A^C)=\frac{365\cdot364\cdot\ldots\cdot(365-n+1)}{365^n}$. Pero esto no es lo que queríamos hallar, sino el complemento del evento $A$, lo bueno es que los axiomas de Kolmogorov nos permiten decir que:

- $P(A^C)=1-P(A)$

Y por lo tanto:

- $P(A)=1-P(A^C)=1-\frac{365\cdot364\cdot\ldots\cdot(365-n+1)}{365^n}$

Para que la probabilidad supere a $0.5$, tenemos que ponernos a calcular uno por cada caso, lo cual es un poco engorroso, por lo que lo voy a saltear.
El número es $n=23$, lo cual contradice mucho la intuición que uno tiene sobre este problema.

Esto concluye el ejercicio.