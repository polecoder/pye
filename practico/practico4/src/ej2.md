# Ejercicio 02 - Variables aleatorias

**Fecha:** 22-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se consideran las funciones $F:\mathbb{R}\to\mathbb{R}$ tales que:

1. $$F(x)=\begin{cases}\beta e^x & \text{si }x<0\\\beta & \text{si }x=0\\1/4 & \text{si }0<x<1\\\alpha\dfrac{x}{1+x} & \text{si }1\leq x\end{cases}$$

   Hallar $\alpha$ y $\beta$ para que $F$ sea una función de distribución.

2. $$F(x)=\begin{cases}\alpha+e^x & \text{si }x\leq-1\\\beta x+\gamma & \text{si }-1<x\leq1\\\delta+\varepsilon x & \text{si }1<x\end{cases}$$

   Hallar $\alpha,\beta,\gamma,\delta,\varepsilon$ para que $F$ sea una función de distribución.

## Resolución

### Recordatorio

Recordemos que para que una función sea efectivamente una de distribución, tiene que cumplir con las siguientes propiedades:

- **Monotonía:** Es no decreciente. Si $x\leq y$ entonces $F(x)\leq F(y)$
- **Límites en el infinito:** $\lim_{x\to-\infty}F(x)=0$ y $\lim_{x\to+\infty}F(x)=1$
- **Continuidad por derecha:** En cada punto $x$, se cumple que $\lim_{y\to x^+}F(y)=F(x)$
- **Saltos y probabilidad puntual:** El valor del "salto" vertical en la gráfica en un punto $x$ es exactamente la probabilidad $P(X=x)$. Si no hay salto (la función es continua en ese punto), la probabilidad puntual es cero.

### Parte 1

- $$F(x)=\begin{cases}\beta e^x & \text{si }x<0\\\beta & \text{si }x=0\\1/4 & \text{si }0<x<1\\\alpha\dfrac{x}{1+x} & \text{si }1\leq x\end{cases}$$

   Hallar $\alpha$ y $\beta$ para que $F$ sea una función de distribución.

En este caso es bastante sencillo, empecemos por los límites en el infinito, sabemos que:

- $\lim_{x\to-\infty}F(x)=0$ y $\lim_{x\to+\infty}F(x)=1$

Entonces desarrollemos estos límites:

$$
\begin{aligned}
&\lim_{x\to-\infty}F(x)=0\\
&\iff\scriptstyle{(\text{reemplazando con la definición de }F)}\\
&\lim_{x\to-\infty}\beta e^x=0\\
&\iff\scriptstyle{(\text{sabiendo que }x\to-\infty\implies e^x\to0)}\\
&\beta\cdot 0=0\\
\end{aligned}
$$

Y esto último es cierto para cualquier $\beta$.
Vayamos con el otro límite:

$$
\begin{aligned}
&\lim_{x\to+\infty}F(x)=1\\
&\iff\scriptstyle{(\text{reemplazando con la definición de }F)}\\
&\lim_{x\to+\infty}\alpha\cdot\frac{x}{1+x}=1\\
&\iff\scriptstyle{(\text{propiedades del límite en el infinito})}\\
&\lim_{x\to+\infty}\alpha\cdot\frac{x}{x}=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\alpha=1\\
\end{aligned}
$$

Por lo tanto, $\alpha=1$ para poder satisfacer con esa condición.

Para concluir, tenemos que ver que pasa cuando $x=0$ ya que ahí $F(0)=\beta$.
Notemos que para respetar la monotonía, $\beta\in[0,\frac{1}{4}]$, de modo que no sea mayor que el caso cuando $0<x<1$.

Para que además la función cumpla con la **continuidad por derecha**, se va a tener que dar que en $x=0$ la imagen tendrá que ser $\frac{1}{4}$.

Concluimos diciendo que los valores de $\alpha$ y $\beta$ para que $F$ sea una función de distribución son:

- $\alpha=1$
- $\beta=\frac{1}{4}$

### Parte 2

- $$F(x)=\begin{cases}\alpha+e^x & \text{si }x\leq-1\\\beta x+\gamma & \text{si }-1<x\leq1\\\delta+\varepsilon x & \text{si }1<x\end{cases}$$

   Hallar $\alpha,\beta,\gamma,\delta,\varepsilon$ para que $F$ sea una función de distribución.

Como el caso anterior, empecemos por los límites en el infinito:

- $\lim_{x\to-\infty}F(x)=0$ y $\lim_{x\to+\infty}F(x)=1$

Entonces:

$$
\begin{aligned}
&\lim_{x\to-\infty}F(x)=0\\
&\iff\scriptstyle{(\text{reemplazando con la definición de }F)}\\
&\lim_{x\to-\infty}\alpha+e^x=0\\
&\iff\scriptstyle{(\text{sabiendo que }x\to-\infty\implies e^x\to0)}\\
&\alpha=0
\end{aligned}
$$

Por lo que $\alpha=0$. Por otra parte:

$$
\begin{aligned}
&\lim_{x\to+\infty}F(x)=1\\
&\iff\scriptstyle{(\text{reemplazando con la definición de F})}\\
&\lim_{x\to+\infty}\delta+\varepsilon x=1\\
\end{aligned}
$$

Donde la única forma de que esta igualdad sea cierta es que:

- $\varepsilon=0$
- $\delta=1$

Por otra parte, sabemos que la función tiene que cumplir con la continuidad por derecha, entonces se tienen que dar las siguientes igualdades:

$$
\begin{aligned}
&\lim_{x\to-1^+}F(x)=F(x)\\
&\iff\scriptstyle{(\text{definición de la función }F)}\\
&-\beta+\gamma=\alpha+\frac{1}{e}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&-\beta+\gamma=\frac{1}{e}\\
\end{aligned}
$$

Y también:

$$
\begin{aligned}
&\lim_{x\to1^+}F(x)=F(x)\\
&\iff\scriptstyle{(\text{definición de la función F})}\\
&\beta+\gamma=\delta+\varepsilon x\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\beta+\gamma=1\\
\end{aligned}
$$

Esto nos deja con el sistema:

$$
\begin{cases}
-\beta+\gamma=\frac{1}{e}\\
\beta+\gamma=1\\
\end{cases}
$$

Donde podemos sumar las ecuaciones y obtener:

$$
\begin{aligned}
&2\gamma=\frac{1}{e}+1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&2\gamma=\frac{1+e}{e}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\gamma=\frac{1+e}{2e}
\end{aligned}
$$

Sustituyendo en la segunda ecuación:

$$
\begin{aligned}
&\beta+\gamma=1\\
&\iff\scriptstyle{(\text{reemplazando }\gamma)}\\
&\beta+\frac{1+e}{2e}=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\beta=1-\frac{1+e}{2e}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\beta=\frac{1-e}{2e}\\
\end{aligned}
$$

Resumiendo, la función $F$ es una función de distribución sii:

- $\alpha=0$
- $\varepsilon=0$
- $\delta=1$
- $\gamma=\frac{1+e}{2e}$
- $\beta=\frac{1-e}{2e}$
