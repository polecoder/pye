# Ejercicio 06 - Esperanza y varianza de una v.a.

**Fecha:** 28-06-2026
**Estado:** 🟡 Con ayuda

## Consigna

Calcular la esperanza y la varianza de las siguientes distribuciones:

1. $U\{1,\ldots,n\}$ (uniforme discreta)
2. $U[a,b]$ (uniforme continua)
3. $\mathcal{P}(\lambda)$ (Poisson)
4. $exp(\lambda)$ (exponencial)
5. $Geo(p)$ (geométrica)

## Resolución

### Distribución #1

- $U\{1,\ldots,n\}$ (uniforme discreta)

La distribución está dada por:

$$
P(X=k)=\frac{1}{n}\quad\text{para todo }k\in\{1,\ldots,n\}
$$

Entonces podemos operar para calcular la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{sustituyendo }p(x))}\\
&\sum_{x\in R_X}\frac{x}{n}\\
&=\scriptstyle{(\text{propiedades de sumatoria, sustituyendo el recorrido})}\\
&\frac{1}{n}\cdot\sum_{x=1}^n x\\
&=\scriptstyle{(\text{recordando que }\sum_1^nx=\frac{n(n+1)}{2})}\\
&\frac{1}{n}\cdot\frac{n(n+1)}{2}\\
&\scriptstyle{(\text{operatoria})}\\
&\frac{n+1}{2}
\end{aligned}
$$

Ahora operamos para calcular la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&E(X^2)-\left(\frac{n+1}{2}\right)^2\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)-\left(\frac{n+1}{2}\right)^2\\
&=\scriptstyle{(\text{mismo razonamiento que en el cálculo de }E(X))}\\
&\frac{1}{n}\cdot\sum_{x=1}^nx^2-\left(\frac{n+1}{2}\right)^2\\
&=\scriptstyle{(\text{sabiendo que }\sum_{x=1}^nx^2=\frac{n(n+1)(2n+1)}{6})}\\
&\frac{1}{n}\cdot\frac{n(n+1)(2n+1)}{6}-\left(\frac{n+1}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{(n+1)(2n+1)}{6}-\left(\frac{n+1}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&(n+1)\cdot\left(\frac{2n+1}{6}-\frac{n+1}{4}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&(n+1)\cdot\left(\frac{4n+2-3n-3}{12}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&(n+1)\cdot\left(\frac{n-1}{12}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{n^2-1}{12}\\
\end{aligned}
$$

Esto concluye el cálculo para esta distribución.

### Distribución #2

- $U[a,b]$ (uniforme continua)

La densidad de esta distribución está dada por:

$$
f(x)=\frac{1}{b-a}\quad\forall x\in[a,b]
$$

Entonces podemos operar para calcular la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}xp(x)dx\\
&=\scriptstyle{(\text{reemplazando por }p(x))}\\
&\int_{-\infty}^{+\infty}\frac{x}{b-a}dx\\
&=\scriptstyle{(\text{operatoria y considerar solo la parte relevante de la integral})}\\
&\frac{1}{b-a}\int_a^b xdx\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{b-a}\cdot\left[\frac{x^2}{2}\right]_a^b\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{b-a}\cdot\frac{b^2-a^2}{2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{b-a}\cdot\frac{(b+a)(b-a)}{2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{b+a}{2}\\
\end{aligned}
$$

Ahora operamos para calcular la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&E(X^2)-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}x^2p(x)dx-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{mismo razonamiento que en el cálculo de la esperanza})}\\
&\frac{1}{b-a}\int_a^b x^2dx-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{b-a}\cdot\left[\frac{x^3}{3}\right]_a^b-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{b-a}\cdot\frac{b^3-a^3}{3}-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{recordando que }b^3-a^3=(b-a)(b^2+ab+a^2))}\\
&\frac{1}{b-a}\cdot\frac{(b-a)(b^2+ab+a^2)}{3}-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{b^2+ab+a^2}{3}-\left(\frac{b+a}{2}\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{b^2+ab+a^2}{3}-\frac{b^2+2ab+a^2}{4}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{4b^2+4ab+4a^2-3b^2-6ab-3a^2}{12}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{b^2-2ab+a^2}{12}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{(b-a)^2}{12}\\
\end{aligned}
$$

Esto concluye el cálculo para esta distribución.

### Distribución #3

- $\mathcal{P}(\lambda)$ (Poisson)

La distribución está dada por:

$$
P(X=k)=\frac{\lambda^ke^{-\lambda}}{k!}
$$

Entonces podemos operar para calcular la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{reemplazando por los valores conocidos})}\\
&\sum_{x=1}^{+\infty}\frac{x\lambda^xe^{-\lambda}}{k!}\\
&=\scriptstyle{(\text{propiedades de sumatoria})}\\
&e^{-\lambda}\sum_{x=1}^{+\infty}\frac{x\lambda^x}{x!}\\
&=\scriptstyle{(\text{operatoria})}\\
&e^{-\lambda}\sum_{x=1}^{+\infty}\frac{\lambda^x}{x-1!}\\
&=\scriptstyle{(\text{operatoria})}\\
&\lambda e^{-\lambda}\sum_{x=1}^{+\infty}\frac{\lambda^{x-1}}{x-1!}\quad(*_1)\\
\end{aligned}
$$

**Observación:** Notemos que lo que tenemos en $*_1$ es exactamente la serie de Taylor para $e^{\lambda}$. Podemos simplificar con esto en mente:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{retomando desde }*_1)}\\
&\lambda e^{-\lambda}\sum_{x=1}^{+\infty}\frac{\lambda^{x-1}}{x-1!}\\
&=\scriptstyle{(\text{por la observación})}\\
&\lambda e^{-\lambda}e^{\lambda}\\
&=\scriptstyle{(\text{operatoria})}\\
&\lambda\\
\end{aligned}
$$

Ahora operamos para calcular la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando los valores conocidos y operatoria})}\\
&E(X(X-1))+E(X)-\lambda^2\\
&=\scriptstyle{(\text{definición de esperanza y reemplazando los valores conocidos})}\\
&\sum_{i=1}^{+\infty}(x(x-1)p(x))+\lambda-\lambda^2\\
&=\scriptstyle{(\text{reemplazando por }p(x))}\\
&\sum_{i=1}^{+\infty}\left(\frac{x(x-1)\lambda^xe^{-\lambda}}{x!}\right)+\lambda-\lambda^2\\
&=\scriptstyle{(\text{operatoria})}\\
&e^{-\lambda}\sum_{i=1}^{+\infty}\left(\frac{\lambda^x}{(x-2)!}\right)+\lambda-\lambda^2\\
&=\scriptstyle{(\text{operatoria})}\\
&e^{-\lambda}\lambda^2\sum_{i=1}^{+\infty}\left(\frac{\lambda^{x-2}}{(x-2)!}\right)+\lambda-\lambda^2\\
&=\scriptstyle{(\text{desarrollo de Taylor})}\\
&e^{-\lambda}\lambda^2e^{\lambda}+\lambda-\lambda^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\lambda\\
\end{aligned}
$$

Esto concluye el cálculo para esta distribución.

### Distribución #4

- $exp(\lambda)$ (exponencial)

La densidad de distribución exponencial está dada por:

$$
X\sim exp(\lambda)\iff f(x)=\lambda e^{-\lambda x},\ x\geq0
$$

Con esto ya podemos operar para calcular la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{-\infty}^{+\infty}x\lambda e^{-\lambda x}dx\\
&=\scriptstyle{(\text{contemplando solo la parte relevante de la integral})}\\
&\int_0^{+\infty}x\lambda e^{-\lambda x}dx\\
&=\scriptstyle{(\text{operatoria})}\\
&(-1)\cdot\left[\int_0^{+\infty}-x\lambda e^{-\lambda x}dx\right]\\
&=\scriptstyle{(\text{integración por partes: }du=1dx;u=x;\ v=e^{-\lambda x};dv=-\lambda e^{-\lambda x}dx)}\\
&(-1)\cdot\left[xe^{-\lambda x}\Big|_0^{+\infty}-\int_0^{+\infty}e^{-\lambda x}dx\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&(-1)\cdot\left[0-\left(-\frac{e^{-\lambda x}}{\lambda}\right)\Big|_0^{+\infty}\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&(-1)\cdot\left[0-\left(0+\frac{1}{\lambda}\right)\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{\lambda}\\
\end{aligned}
$$

Con esto estamos en condiciones de hallar la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{definición de esperanza y reemplazando lo conocido})}\\
&\int_{-\infty}^{+\infty}x^2p(x)dx-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{considerando la parte relevante de la integral y reemplazando }p(x))}\\
&\int_0^{+\infty}x^2\lambda e^{-\lambda x}dx-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&(-1)\cdot\left(\int_0^{+\infty}-x^2\lambda e^{-\lambda x}dx\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{integración por partes: }u=x^2;du=2xdx;\ dv=-\lambda e^{-\lambda x};v=e^{-\lambda x}dx)}\\
&(-1)\cdot\left(-x^2\lambda e^{-\lambda x}\Big|_0^{+\infty}-\int_0^{+\infty}e^{-\lambda x}2xdx\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&(-1)\cdot\left(0-2\left(\int_0^{+\infty}e^{-\lambda x}xdx\right)\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{integración por partes: }u=x;du=1dx;\ dv=e^{-\lambda x};v=-\frac{e^{-\lambda x}}{\lambda}dx)}\\
&(-1)\cdot\left(-2\left(xe^{-\lambda x}\Big|_0^{+\infty}-\int_0^{+\infty}-\frac{e^{-\lambda x}}{\lambda}dx\right)\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&2\left(0-\left(-\frac{1}{\lambda}\cdot\left[-\frac{e^{-\lambda x}}{\lambda}\right]_0^{+\infty}\right)\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&2\left(\frac{1}{\lambda}\cdot\left[0+\frac{1}{\lambda}\right]\right)-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2}{\lambda^2}-\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&-\frac{1}{\lambda^2}\\
\end{aligned}
$$

Esto concluye el cálculo para esta distribución.

### Distribución #5

- $\text{Geo}(p)$ (geométrica)

La distribución geométrica está dada por:

$$
X\sim Geo(p)\iff P(X=x)=(1-p)^{x-1}p
$$

Con esto ya podemos operar para calcular la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{reemplazando por }(x))}\\
&\sum_{x\in R_X}x(1-p)^{x-1}p\\
&=\scriptstyle{(\text{propiedades de sumatoria})}\\
&p\sum_{x\in R_X}x(1-p)^{x-1}\\
\end{aligned}
$$

Y en este punto, tenemos que reconocer que la sumatoria del último paso no es cualquier sumatoria, es la derivada de una serie geométrica:

$$
\begin{aligned}
&\sum_{x\in R_X}x(1-p)^{x-1}\\
&=\scriptstyle{(\text{sea }q=1-p)}\\
&\sum_{x\in R_X}xq^{x-1}\\
&=\scriptstyle{(\text{derivada respecto de }q)}\\
&\sum_{x\in R_X}\frac{d}{dq}(q^x)\\
&=\scriptstyle{(\text{propiedades de derivada})}\\
&\frac{d}{dq}\left(\sum_{x\in R_X}(q^x)\right)\\
&=\scriptstyle{(\text{resultado de serie geométrica})}\\
&\frac{d}{dq}\left(\frac{1}{1-q}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{d}{dq}(1-q)^{-1}\\
&=\scriptstyle{(\text{derivando respecto de }q)}\\
&-1\cdot(1-q)^{-2}\cdot(-1)\\
&=\scriptstyle{(\text{derivando respecto de }q)}\\
&\frac{1}{(1-q)^2}\\
&=\scriptstyle{(\text{recordando que }q=1-p)}\\
&\frac{1}{(1-1+p)^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{p^2}\\
\end{aligned}
$$

Con esto ya podemos reemplazar en el cálculo de esperanza para finalizar:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{retomando el cálculo inicial})}\\
&p\sum_{x\in R_X}x(1-p)^{x-1}\\
&=\scriptstyle{(\text{razonamiento anterior})}\\
&p\cdot\frac{1}{p^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{p}\\
\end{aligned}
$$

Con esto estamos en condiciones de hallar la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando por los valores conocidos})}\\
&E(X^2)-\frac{1}{p^2}\\
&=\scriptstyle{(\text{usando que }E(X^2)=E(X(X-1))+E(X))}\\
&E(X(X-1))+E(X)-\frac{1}{p^2}\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&E(X(X-1))+\frac{1}{p}-\frac{1}{p^2}\quad(*_1)\\
\end{aligned}
$$

Para no complicar excesivamente el razonamiento, trabajamos sobre $E(X(X-1))$:

$$
\begin{aligned}
&E(X(X-1))\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{x\in R_X}x(x-1)(1-p)^{x-1}p\\
&=\scriptstyle{(\text{propiedades de la sumatoria})}\\
&p(1-p)\sum_{x\in R_X}x(x-1)(1-p)^{x-2}\\
&=\scriptstyle{(\text{llamando }q=(1-p)\text{ donde es relevante})}\\
&p(1-p)\sum_{x\in R_X}x(x-1)q^{x-2}\\
&=\scriptstyle{(\text{derivando respecto a }q)}\\
&p(1-p)\sum_{x\in R_X}\frac{d}{dq}(xq^{x-1})\\
&=\scriptstyle{(\text{derivando respecto a }q)}\\
&p(1-p)\sum_{x\in R_X}\frac{d^2}{dq^2}(q^{x})\\
&=\scriptstyle{(\text{propiedades de derivadas})}\\
&p(1-p)\frac{d^2}{dq^2}\left(\sum_{x\in R_X}q^{x}\right)\\
&=\scriptstyle{(\text{resultado de serie geométrica})}\\
&p(1-p)\frac{d^2}{dq^2}\left(\frac{1}{1-q}\right)\\
&=\scriptstyle{(\text{calculando la derivada})}\\
&p(1-p)\cdot\frac{2}{(1-q)^3}\\
&=\scriptstyle{(\text{recordando que }q=1-p)}\\
&p(1-p)\cdot\frac{2}{(1-1+p)^3}\\
&=\scriptstyle{(\text{operatoria})}\\
&p(1-p)\cdot\frac{2}{p^3}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2(1-p)}{p^2}\quad(*_2)\\
\end{aligned}
$$

Volvemos ahora a $*_1$:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{retomando el razonamiento de }*_1)}\\
&E(X(X-1))+\frac{1}{p}\left(1-\frac{1}{p}\right)\\
&=\scriptstyle{(\text{por lo visto en }*_2)}\\
&\frac{2(1-p)}{p^2}+\frac{1}{p}-\frac{1}{p^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2(1-p)+p-1}{p^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1-p}{p^2}
\end{aligned}
$$

Esto concluye el cálculo para esta distribución.
