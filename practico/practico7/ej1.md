# Ejercicio 01 - Esperanza de una v.a.

**Fecha:** 26-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Al invertir en la bolsa de valores, una persona puede lograr una ganancia de 4000 dólares en un año con una probabilidad de $0.3$ o bien tener una pérdida de 1000 dólares con probabilidad $0.7$. ¿Cuál sería la ganancia esperada de esta persona?

## Resolución

Este ejercicio es super simple, como para entender la noción de esperanza a nivel teórico. Consideremos $X$ la v.a. que cuenta la ganancia de una persona al invertir en la bolsa de valores.

Entonces la f.p.p. de $X$ se puede describir mediante:

- $P(X=4000)=0.3$
- $P(X=-1000)=0.7$

Entonces el recorrido de $X$ cuenta con solamente dos valores. Apliquemos la definición de esperanza para obtener el resultado:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{expandiendo la suma con los valores conocidos})}\\
&4000\cdot0.3+(-1000)\cdot0.7\\
&=\scriptstyle{(\text{operatoria})}\\
&1200-700\\
&=\scriptstyle{(\text{operatoria})}\\
&500\\
\end{aligned}
$$

Por lo tanto, la ganancia esperada de la persona es $500$.