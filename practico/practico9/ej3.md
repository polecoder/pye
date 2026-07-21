# Ejercicio 03 - Estimación puntual

**Fecha:** 08-07-2026
**Estado:** 🟡 Con ayuda

## Consigna

Una pieza de una máquina se verifica al final de cada hora de producción y se cambia por una nueva en caso de encontrarse rota. El tiempo de vida en horas de la pieza se puede modelar con una variable aleatoria $T$ con distribución exponencial de parámetro $\lambda\ (T\sim\text{exp}(\lambda))$, por lo tanto el tiempo en horas que transcurre hasta el recambio de la pieza se puede modelar con una variable aleatoria $X=[T]+1$, donde $[T]$ es la parte entera de $T$ (esto es, $X=n$ si y sólo si $n-1\leq T<n$).

1. Hallar la función de probabilidad de la variable aleatoria $X$ y probar que tiene distribución geométrica de parámetro $1-e^{-\lambda}$ ($X\sim\text{Geo}(1-e^{-\lambda})$).

2. A partir de los tiempos en los que se realiza el recambio de las piezas se desea estimar el parámetro $\lambda$ del tiempo de vida de dichas piezas.
   1. Calcular $\lambda$ en función de $\mu$ siendo $\mu=E(X)$.
   2. ¿Cómo estimaría $\mu$ a partir de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas?
   3. Construir un estimador consistente para $\lambda$ en función de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas.

## Resolución

### Parte 1

- Hallar la función de probabilidad de la variable aleatoria $X$ y probar que tiene distribución geométrica de parámetro $1-e^{-\lambda}$, es decir que $X\sim Geo(1-e^{-\lambda})$

Antes de empezar, recordemos que la distribución geométrica es discreta y está dada por la siguiente función de probabilidad puntual:

- $p(x)=(1-p)^{x-1}p$

Como especifica la letra, tenemos que $X=n$ si y sólo si $n-1\leq T<n$. Esto nos indica que podemos calcular la probabilidad puntual para $X=n$ desarrollando de la siguiente manera:

$$
\begin{aligned}
&P(X=n)\\
&=\scriptstyle{(\text{observación de la letra})}\\
&P(n-1\leq T<n)\\
&=\scriptstyle{(\text{probabilidad en v.a. continuas})}\\
&\int_{n-1}^{n}p_T(x)dx\\
&=\scriptstyle{(T\sim exp(\lambda))}\\
&\int_{n-1}^{n}\lambda e^{-\lambda x}dx\\
&=\scriptstyle{(\text{operatoria})}\\
&\left(-e^{-\lambda x}\right)\Big|_{n-1}^n\\
&=\scriptstyle{(\text{operatoria})}\\
&-e^{-\lambda n}+e^{-\lambda(n-1)}\\
&=\scriptstyle{(\text{operatoria})}\\
&e^{-\lambda(n-1)}(-e^{-\lambda}+1)\\
&=\scriptstyle{(\text{operatoria})}\\
&e^{-\lambda(n-1)}(1-e^{-\lambda})\\
&=\scriptstyle{(\text{operatoria})}\\
&(e^{-\lambda})^{n-1}(1-e^{-\lambda})\\
&=\scriptstyle{(\text{llamando }p=1-e^{-\lambda})}\\
&(1-p)^{n-1}p
\end{aligned}
$$

Esto prueba que $X\sim Geo(p)$ con $p=1-e^{-\lambda}$ que es lo que queríamos probar. $\blacksquare$

### Parte 2

- A partir de los tiempos en los que se realiza el recambio de las piezas se desea estimar el parámetro $\lambda$ del tiempo de vida de dichas piezas.
   1. Calcular $\lambda$ en función de $\mu$ siendo $\mu=E(X)$.
   2. ¿Cómo estimaría $\mu$ a partir de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas?
   3. Construir un estimador consistente para $\lambda$ en función de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas.

#### Subparte 1

- Calcular $\lambda$ en función de $\mu$ siendo $\mu=E(X)$.

Al $X$ tener distribución geométrica de parámetro $p=1-e^{-\lambda}$, sabemos que su esperanza es $\mu=E(X)=\frac{1}{p}=\frac{1}{1-e^{-\lambda}}$. Podemos operar con esto para despejar $\lambda$.

$$
\begin{aligned}
&\mu=\frac{1}{1-e^{-\lambda}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{\mu}=1-e^{-\lambda}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&-\frac{1}{\mu}+1=e^{-\lambda}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\ln\left(-\frac{1}{\mu}+1\right)=\ln e^{-\lambda}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\ln\left(-\frac{1}{\mu}+1\right)=-\lambda\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\lambda=-\ln\left(-\frac{1}{\mu}+1\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\lambda=-\ln\left(\frac{\mu-1}{\mu}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\lambda=-\ln(\mu-1)+\ln(\mu)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\lambda=\ln(\mu)-\ln(\mu-1)\\
\end{aligned}
$$

Esto concluye el cálculo para esta subparte.

#### Subparte 2

- ¿Cómo estimaría $\mu$ a partir de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas?

Estimaría $\mu$ utilizando el método de los momentos, el mismo nos devuelve la ecuación:

$$
\hat{\mu}=\overline{X_n}
$$

Que no podemos simplificar más.

#### Subparte 3

- Construir un estimador consistente para $\lambda$ en función de las observaciones $X_1,X_2,\ldots,X_n$ de los tiempos de recambio de las piezas.

Esta parte consiste en juntar lo que hicimos en la parte 1 y 2. Recordemos que:

- $\lambda=\ln(\mu)-\ln(\mu-1)\quad(*_1)$
- $\hat{\mu}=\overline{X_n}\quad(*_2)$

Juntando todo, podemos concluir que:

$$
\boxed{\hat{\lambda}=\ln(\overline{X_n})-\ln(\overline{X_n}-1)}
$$

Queremos verificar que es consistente, y esto es sumamente sencillo pues:

1. $\hat{\mu}$ es un estimador fuertemente consistente de $\mu$ por la ley de los grandes números.
2. La función $g(x)=\ln(x)-\ln(x-1)$ es una función continua.

Por lo tanto la convergencia casi segura se mantiene y efectivamente $\hat{\lambda}$ es un estimador fuertemente consistente.