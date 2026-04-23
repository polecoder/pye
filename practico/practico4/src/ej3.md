# Ejercicio 03 - Variables aleatorias discretas

**Fecha:** 23-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

Se considera la función de distribución $F_X:\mathbb{R}\to\mathbb{R}$ de la variable aleatoria $X$. Probar que:

1. $P(a<X\leq b)=F_X(b)-F_X(a)$
2. $P(X=a)=F_X(a)-\lim_{x\to a^-}F_X(x)$
3. $P(a\leq X\leq b)=F_X(b)-\lim_{x\to a^-}F_X(x)$
4. $P(a<X<b)=\lim_{x\to b^-}F_X(x)-F_X(a)$
5. $P(a\leq X<b)=\lim_{x\to b^-}F_X(x)-\lim_{x\to a^-}F_X(x)$
6. $P(X>a)=1-F_X(a)$
7. $P(X\geq a)=1-\lim_{x\to a^-}F_X(x)$

## Resolución

### Parte 1

- $P(a<X\leq b)=F_X(b)-F_X(a)$

Consideremos los siguientes eventos:

- $A=\{X\leq a\}$
- $B=\{X\leq b\}$

Como tenemos que $a<b$, podemos concluir que $A\subset B$. Además notemos que el evento $a<X\leq b$ es exactamente lo mismo que el evento $B\setminus A$, es decir lo que está en $B$ que **no está** en $A$.
Con esto estamos en condiciones de usar la regla de la resta para concluir que:

- $P(a<X\leq b)=P(X\leq b)-P(X\leq a)$

Y utilizando la definición de $F_X$:

- $P(a<X\leq B)=F_X(b)-F_X(a)$

Esto concluye la demostración.

### Parte 2

- $P(X=a)=F_X(a)-\lim_{x\to a^-}F_X(x)$

Notemos que el evento $X\leq a$ se puede partir en dos eventos incompatibles $X<a$ y $X=a$, por lo tanto usando aditividad tenemos que:

- $P(X=a)=P(X\leq a)-P(X<a)$

Y usando la definición de $F_X$ y la propiedad de **saltos** vista en el teórico respectivamente, esta igualdad es:

- $P(X=a)=F_X(a)-\lim_{x\to a^-}F_X(x)$

Esto concluye la demostración

### Parte 3

- $P(a\leq X\leq b)=F_X(b)-\lim_{x\to a^-}F_X(x)$

Consideremos los siguientes eventos:

- $A=\{X<a\}$
- $B=\{X\leq b\}$

Como tenemos que $a\leq b$, podemos concluir que $A\subset B$.
Además notemos que el evento $a\leq X\leq b$ es exactamente lo mismo que el evento $B\setminus A$, es decir lo que está en $B$ que **no está** en $A$.
Con esto estamos en condiciones de usar la regla de la resta para concluir que:

- $P(a\leq X\leq b)=P(X\leq b)-P(X<a)$

Donde usando la definición de $F_X$ y la propiedad de **saltos** vista en el teórico respectivamente, concluimos que:

- $P(a\leq X\leq b)=F_X(b)-\lim_{x\to a^-}F_X(x)$

Esto concluye la demostración.

### Parte 4

- $P(a<X<b)=\lim_{x\to b^-}F_X(x)-F_X(a)$

Consideremos los siguientes eventos:

- $A=\{X\leq a\}$
- $B=\{X<b\}$

Como tenemos que $a<b$, podemos concluir que $A\subset B$.
Además notemos que el evento $a<X<b$ es exactamente lo mismo que el evento $B\setminus A$, es decir lo que está en $B$ que **no está** en $A$.
Con esto estamos en condiciones de usar la regla de la resta para concluir que:

- $P(a<X<b)=P(X<b)-P(X\leq a)$

Donde usando la definición de $F_X$ y la propiedad de **saltos** vista en el teórico respectivamente, concluimos que:

- $P(a<X<b)=\lim_{x\to b^-}F(x)-F_X(a)$

Esto concluye la demostración.

### Parte 5

- $P(a\leq X<b)=\lim_{x\to b^-}F_X(x)-\lim_{x\to a^-}F_X(x)$

Consideremos los siguientes eventos:

- $A=\{X<a\}$
- $B=\{X<b\}$

Como tenemos que $a<b$, podemos concluir que $A\subset B$.
Además notemos que el evento $a\leq X<b$ es exactamente lo mismo que el evento $B\setminus A$, es decir lo que está en $B$ que **no está** en $A$.
Con esto estamos en condiciones de usar la regla de la resta para concluir que:

- $P(a\leq X<b)=P(X<b)-P(X<a)$

Donde usando la definición de $F_X$ y la propiedad de **saltos** vista en el teórico respectivamente, concluimos que:

- $P(a\leq X<b)=\lim_{x\to b^-}F(x)-\lim_{x\to a^-}F_X(x)$

Esto concluye la demostración.

### Parte 6

- $P(X>a)=1-F_X(a)$

Podemos considerar el complemento del evento $X>a$, es decir:

- $A^C=\{X\leq a\}$

Y utilizando la propiedad del complemento tenemos que:

- $P(X>a)=1-P(X\leq a)$

Donde usando la definición de $F_X$ concluimos que:

- $P(X>a)=1-F_X(a)$

Esto concluye la demostración.

### Parte 7

- $P(X\geq a)=1-\lim_{x\to a^-}F_X(x)$

Podemos considerar el complemento del evento $X\geq a$, es decir:

- $A^C=\{X<a\}$

Y utilizando la propiedad del complemento tenemos que:

- $P(X\geq a)=1-P(X<a)$

Donde usando la definición de $F_X$ concluimos que:

- $P(X\geq a)=1-\lim_{x\to a^-}F_X(x)$

Esto concluye la demostración.