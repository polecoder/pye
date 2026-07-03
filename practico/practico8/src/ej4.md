# Ejercicio 04 - Ley fuerte de los grandes números

**Fecha:** 03-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Demostrar que si $X_n\xrightarrow[n]{c.s.}a$ e $Y_n\xrightarrow[n]{c.s.}b$ y $g:\mathbb{R}\to\mathbb{R}$ continua entonces:

1. $X_n+Y_n\xrightarrow[n]{c.s.}a+b$
2. $X_nY_n\xrightarrow[n]{c.s.}ab$
3. $g(X_n)\xrightarrow[n]{c.s.}g(a)$

## Resolución

### Preámbulo

Para este ejercicio usaremos la definición de converger casi seguramente a un número. Ésta es la siguiente:

Sea una sucesión de v.a. $X_1,\ldots,X_n$ y $a\in\mathbb{R}$. Decimos que $X_n$ converge casi seguramente a $a$ si se cumple que:

$$
\{X_n\}_{n\in N}\xrightarrow[n]{c.s.}a\iff P(\{X_n\to a\})=1
$$

### Parte 1

- $X_n+Y_n\xrightarrow[n]{c.s.}a+b$

Lo que queremos hacer para estas demostraciones, es esencialmente estudiar que pasa en el infinito con las v.a. dadas. Entonces:

$$
\begin{aligned}
&\lim_{n\to\infty}(X_n+Y_n)\\
&=\scriptstyle{(\text{propiedades de límite de sucesiones})}\\
&\lim_{n\to\infty}X_n+\lim_{n\to\infty}Y_n\\
&=\scriptstyle{(\text{definición de convergencia casi segura para }X_n,Y_n)}\\
&a+b
\end{aligned}
$$

Hallamos entonces que:

$$
\boxed{
\lim_{n\to\infty}(X_n+Y_n)=a+b
}
$$

Esta es exactamente la definición de converger casi seguramente a un valor, por lo que queda demostrada la propiedad. $\blacksquare$

### Parte 2

- $X_nY_n\xrightarrow[n]{c.s.}ab$

Siguiendo el mismo razonamiento que el caso anterior:

$$
\begin{aligned}
&\lim_{n\to\infty}(X_nY_n)\\
&=\scriptstyle{(\text{propiedades de límite de sucesiones})}\\
&\lim_{n\to\infty}X_n\cdot\lim_{n\to\infty}Y_n\\
&=\scriptstyle{(\text{definición de convergencia casi segura para }X_n,Y_n)}\\
&ab
\end{aligned}
$$

Hallamos entonces que:

$$
\boxed{
\lim_{n\to\infty}(X_nY_n)=ab
}
$$

Esta es exactamente la definición de converger casi seguramente a un valor, por lo que queda demostrada la propiedad. $\blacksquare$

### Parte 3

- $g(X_n)\xrightarrow[n]{c.s.}g(a)$

Siguiendo el mismo razonamiento que el caso anterior:

$$
\begin{aligned}
&\lim_{n\to\infty}g(X_n)\\
&=\scriptstyle{(\text{límite de funciones continuas})}\\
&g\left(\lim_{n\to\infty}X_n\right)\\
&=\scriptstyle{(\text{definición de convergencia casi segura para }X_n)}\\
&g(a)
\end{aligned}
$$

Hallamos entonces que:

$$
\boxed{
\lim_{n\to\infty}g(X_n)=g(a)
}
$$

Esta es exactamente la definición de converger casi seguramente a un valor, por lo que queda demostrada la propiedad. $\blacksquare$