# Ejercicio 01 - Teorema central del límite

**Fecha:** 15-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se realiza una encuesta para tratar de estimar el porcentaje de votos de determinado candidato. Al final de la misma se tendrán $n$ respuestas, representadas en la muestra $X_1,X_2,\cdots,X_n$ de realizaciones de la variable de Bernoulli de parámetro $p$ (la probabilidad de que una persona elegida al azar en la población vote por el candidato en cuestión).

1. A partir de la mencionada muestra ¿Qué valor usaría usted para estimar $p$?
2. Usando la Desigualdad de Chevishoff (y antes de tomar la muestra) ¿Cuántos datos tomaría para que, con una probabilidad de al menos $0{,}95$, el estimador no distara del valor de $p$ más de un $0{,}03$? (Sugerencia: Demuestre y use que para cualquier valor de $p\in[0,1]$ se cumple $p(1-p)\leq1/4$).
3. Usando el Teorema del Límite Central resolver la parte anterior y comparar con el resultado obtenido por la Desigualdad de Chevishoff. (Las dos primeras partes de este ejercicio fueron resueltas en el práctico 8).

## Resolución

### Partes 1 y 2

1. A partir de la mencionada muestra ¿Qué valor usaría usted para estimar $p$?
2. Usando la Desigualdad de Chevishoff (y antes de tomar la muestra) ¿Cuántos datos tomaría para que, con una probabilidad de al menos $0{,}95$, el estimador no distara del valor de $p$ más de un $0{,}03$? (Sugerencia: Demuestre y use que para cualquier valor de $p\in[0,1]$ se cumple $p(1-p)\leq1/4$).

Estas partes fueron resueltas en el mismo ejercicio del práctico 8.

### Parte 3

- Usando el Teorema del Límite Central resolver la parte anterior y comparar con el resultado obtenido por la Desigualdad de Chevishoff. (Las dos primeras partes de este ejercicio fueron resueltas en el práctico 8).

Esta parte hace referencia a resolver el problema de la parte 2. Traduciendo la consigna a una desigualdad matemática, lo que queremos resolver es, para que $p$ se cumple que:

$$
P(|\overline{X}_n-p|\leq0.03)\geq0.95\quad(*_1)
$$

Este es el punto de partida que tenemos. Recordemos que por lo general cuando se aplica el TCL se debe estandarizar, este caso es igual, solo que la variable que estandarizamos es $\overline{X}_n$. El TCL para esta variable establece que para $n$ grande:

- $\overline{X}_n\overset{d}\approx N(\mu,\sigma^2/n)$

En este caso, reemplazando por $E(X)=p$ y $Var(X)=p(1-p)$, tenemos que:

- $\overline{X}_n\overset{d}\approx N(p,p(1-p)/n)$

Ahora, nuestra condición inicial de probabilidad se traduce en:

$$
\begin{aligned}
&P(|\overline{X}_n-p|\leq0.03)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(\frac{|\overline{X}_n-p|}{\sqrt{p(1-p)/n}}\leq\frac{0.03}{\sqrt{p(1-p)/n}}\right)\\
&=\scriptstyle{(\text{aplicando el TCL})}\\
&P\left(|Z_n|\leq\frac{0.03}{\sqrt{p(1-p)/n}}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P\left(|Z_n|\leq\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\right)\\
&=\scriptstyle{(Z_n\sim N(0,1))}\\
&2\Phi\left(\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\right)-1
\end{aligned}
$$

Ahora que tenemos una expresión bien concreta sobre la condición inicial de probabilidad, podemos operar volviendo a $*_1$ para despejar $\sqrt{n}$

$$
\begin{aligned}
&P(|\overline{X}_n-p|\leq0.03)\geq0.95\\
&\iff\scriptstyle{(\text{razonamiento anterior})}\\
&2\Phi\left(\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\right)-1\geq0.95\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\Phi\left(\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\right)\geq\frac{1.95}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\Phi\left(\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\right)\geq0.975\\
&\iff\scriptstyle{(\text{usando una tabla de la distribución normal})}\\
&\frac{0.03\sqrt{n}}{\sqrt{p(1-p)}}\geq1.96\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{0.03\sqrt{n}}{1.96}\geq\sqrt{p(1-p)}\\
&\iff\scriptstyle{(\text{usando la sugerencia de la parte 2: }p(1-p)\leq1/4)}\\
&\frac{0.03\sqrt{n}}{1.96}\geq\sqrt{\frac{1}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sqrt{n}\geq\frac{1.96}{0.03\cdot2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sqrt{n}\geq32.\overline{6}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&n\gtrsim1067.1
\end{aligned}
$$

Por lo tanto, considerando un $n\geq1068$, el teorema central del límite nos dice que esa desigualdad se cumple. Esta cota es mucho mejor que la que hallamos en el práctico 8, y esto se debe a que el TCL aprovecha que sabemos que a medida que $n$ crece, el promedio tiende cada vez más a una distribución normal, mientras que la desigualdad de Chebyshev es una cota más restrictiva que no considera la forma de la distribución.