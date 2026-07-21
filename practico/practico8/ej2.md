# Ejercicio 02 - Ley de los grandes números

**Fecha:** 02-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Este ejercicio describe el método de Montecarlo para el cálculo de integrales.

Sean $(U_i)_{i\in\mathbb{N}}\sim U[a,b]$ i.i.d. y $f\in R[a,b]$ ($f$ es integrable Riemann en $[a,b]$), mostrar que:

$$
\frac{1}{n}\sum_{i=1}^{n}f(U_i)\xrightarrow[n]{\text{c.s.}}\frac{1}{b-a}\int_a^b f(x)\,dx
$$

## Resolución

- Sean $(U_i)_{i\in\mathbb{N}}\sim U[a,b]$ i.i.d. y $f\in R[a,b]$ ($f$ es integrable Riemann en $[a,b]$), mostrar que:

$$
\frac{1}{n}\sum_{i=1}^{n}f(U_i)\xrightarrow[n]{\text{c.s.}}\frac{1}{b-a}\int_a^b f(x)\,dx
$$

Ahora bien, estamos en una situación donde estamos bajo las hipótesis de la ley fuerte de los grandes números, pues tenemos una sucesión de $n$ variables aleatorias independientes e idénticamente distribuidas. También tenemos el promedio muestral de estas v.a.

Un pequeño detalle, es que no nos interesa exactamente el promedio muestral de las $U_i$ por si solas, sino que nos interesa el que contempla a las $U_i$ pasadas por la función $f$. Consideramos entonces las v.a. $f(U_i)$ que también serán i.i.d., de modo que el promedio muestral que obtenemos es:

$$
\boxed{
\overline{U_i}=\frac{1}{n}\sum_{i=1}^nf(U_i)
}
$$

Esto es uno de los ingredientes que necesitamos, ahora tenemos que calcular la esperanza de $f(U_i)$ (será la misma para cualquier $i$ por ser i.i.d.). Operemos:

$$
\begin{aligned}
&E(f(U_i))\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}f(x)p(x)dx\\
&=\scriptstyle{(\text{considerando el intervalo relevante de la integral})}\\
&\int_{a}^{b}f(x)p(x)dx\\
&=\scriptstyle{(\text{reemplazando }p(x))}\\
&\int_{a}^{b}f(x)\cdot\frac{1}{b-a}dx\\
&=\scriptstyle{(\text{propiedades de integrales})}\\
&\frac{1}{b-a}\cdot\int_{a}^{b}f(x)dx\\
\end{aligned}
$$

Ahora si, entonces la esperanza de $f(U_i)$ es $\mu=\frac{1}{b-a}\cdot\int_{a}^{b}f(x)dx$.

Podemos utilizar la ley fuerte de los grandes números para afirmar que:

$$
\begin{aligned}
&\overline{X_n}\xrightarrow[n]{c.s}\mu\\
&\iff\scriptstyle{(\text{reemplazando el valor esperado conocido})}\\
&\overline{U_i}\xrightarrow[n]{c.s}\frac{1}{b-a}\cdot\int_{a}^{b}f(x)dx\\
&\iff\scriptstyle{(\text{definición de }\overline{U_i})}\\
&\frac{1}{n}\cdot\sum_{i=1}^nf(U_i)\xrightarrow[n]{c.s}\frac{1}{b-a}\cdot\int_{a}^{b}f(x)dx\\
\end{aligned}
$$

Esto es exactamente lo que queríamos probar. $\blacksquare$