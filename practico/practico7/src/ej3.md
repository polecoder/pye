# Ejercicio 03 - Esperanza de una v.a.

**Fecha:** 26-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

La función de densidad de la variable aleatoria $X$ que mide los diámetros de paso de los hilos de la rosca de una pieza está dada por:

$$
f(x)=\begin{cases}\dfrac{4}{\pi(1+x^2)} & \text{si }x\in[0,1]\\0 & \text{en cualquier otro caso}\end{cases}
$$

1. ¿Cuál es el valor esperado de $X$?
2. Si ahora definimos una variable aleatoria $Y$ tal que $Y=3X+1$, ¿cuál es el valor esperado de $Y$?

## Resolución

### Parte 1

- ¿Cuál es el valor esperado de $X$?

Esta parte es directa usando la definición de esperanza sobre la función $f(x)$ que sabemos que es la función densidad de $X$.

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}xp(x)dx\\
&=\scriptstyle{(\text{reemplazando por }p(x))}\\
&\int_{-\infty}^{+\infty}\frac{4x}{\pi(1+x^2)}dx\\
&=\scriptstyle{(\text{sacando constantes y considerando el intervalo relevante})}\\
&\frac{4}{\pi}\cdot\int_{0}^{1}\frac{x}{1+x^2}dx\\
&=\scriptstyle{(u=1+x^2;du=2xdx)}\\
&\frac{4}{\pi}\cdot\frac{1}{2}\cdot\int_{1}^{2}\frac{du}{u}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2}{\pi}\cdot\log(u)\Big|_1^2\\
&=\scriptstyle{(\text{deshaciendo el cambio de variable})}\\
&\frac{2}{\pi}\cdot\log(1+x^2)\Big|_0^1\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2\log(2)}{\pi}\\
\end{aligned}
$$

Este es el valor esperado de $X$.

### Parte 2

- Si ahora definimos una variable aleatoria $Y$ tal que $Y=3X+1$, ¿cuál es el valor esperado de $Y$?

Para esta parte tenemos que usar la definición de $E(h(X))$ con $h(X)=3X+1$. Recordemosla antes de usarla.

#### Recordatorio

Sean $X$ e $Y$ dos variables aleatorias discretas, y $g:\mathbb{R}^2\to\mathbb{R}$ una función. Entonces

$$
E(g(X,Y))=\sum_{x\in R_X,y\in R_Y}g(x,y)p(x,y)
$$

Donde $p(x,y)$ es la f.p.p. conjunta de $X$ e $Y$.

#### Continuación del ejercicio

Notemos que estamos en el caso de una variable, por lo que es incluso más fácil. Operemos con el recordatorio en mente.

$$
\begin{aligned}
&E(3X+1)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}g(x)p(x)dx\\
&=\scriptstyle{(\text{reemplazando }g(x)\text{ y }p(x))}\\
&\int_{-\infty}^{+\infty}\frac{4(3x+1)}{\pi(1+x^2)}dx\\
&=\scriptstyle{(\text{considerando el intervalo relevante y sacando las constantes})}\\
&\frac{4}{\pi}\int_{0}^{1}\frac{3x}{1+x^2}+\frac{1}{1+x^2}dx\\
&=\scriptstyle{(\text{linealidad de integrales})}\\
&\frac{4}{\pi}\left(\int_{0}^{1}\frac{3x}{1+x^2}dx+\int_{0}^{1}\frac{1}{1+x^2}dx\right)\\
&=\scriptstyle{(\text{sacando constantes de la primera integral y evaluando la segunda})}\\
&\frac{12}{\pi}\cdot\int_{0}^{1}\frac{x}{1+x^2}dx+\frac{4}{\pi}\cdot arctan(x)\Big|_0^1\\
&=\scriptstyle{(\text{preparando el cambio de variable})}\\
&\frac{12}{\pi}\cdot\frac{1}{2}\cdot\int_{0}^{1}\frac{2x}{1+x^2}dx+\frac{4}{\pi}\cdot arctan(x)\Big|_0^1\\
&=\scriptstyle{(\text{evaluando y c.v. }u=1+x^2;du=2xdx)}\\
&\frac{6}{\pi}\cdot\int_{1}^{2}\frac{du}{u}+\frac{4}{\pi}\cdot arctan(1)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{6}{\pi}\cdot\log(u)\Big|_1^2+1\\
&=\scriptstyle{(\text{evaluando})}\\
&\frac{6\log(2)}{\pi}+1\\
\end{aligned}
$$

Este es el valor esperado de $3X+1$.

**Nota importante:** Ya sabemos que la esperanza cumple con la linealidad, por lo tanto podríamos haber ido por el camino **mucho más** sencillo de escribir $E(3X+1)=3E(X)+1$. Donde ya conocíamos $E(X)$ además.