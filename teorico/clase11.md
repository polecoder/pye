# Clase 11 - Desigualdad de Chebyshev y v.a. idénticamente distribuidas

**Fecha:** 25-06-2026

## Desigualdades de Markov y Chebyshev

Las desigualdades de Markov y Chebyshev establecen cotas superiores para las colas de una distribución de una variable en función de sus momentos.

### Desigualdad de Markov

Sea $X$ una variable aleatoria positiva. Entonces, para todo $t>0$ vale que:

$$
P(X\geq t)\leq\frac{E(X)}{t}
$$

#### Demostración

Fijemos $t>0$ y consideremos la variable aleatoria de Bernoulli $Y$ que vale $1$ si $X\geq t$ y $0$ si no. La probabilidad de éxito de $Y$ es:

$$
p=P(Y=1)=P(X\geq t)
$$

Notemos que $tY\leq X$ pues:

- Si $Y=0$ la desigualdad se cumple trivialmente.
- Si $Y=1$ también se cumple pues $X\geq t$ por definición de $Y$.

Entonces podemos decir que $E(tY)\leq E(X)$. Por otro lado, la esperanza de $Y$ es $p$, juntando con la desigualdad obtenemos que:

$$
\begin{aligned}
&tP(X\geq t)\leq E(X)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq t)\leq \frac{E(X)}{t}\\
\end{aligned}
$$

Que es lo que queríamos demostrar.

### Desigualdad de Chebyshev

Sea $X$ una v.a. de esperanza $\mu=E(X)$ y varianza $\sigma^2=Var(X)$. Entonces, para todo $\varepsilon>0$ vale que:

$$
P(|X-\mu|\geq\varepsilon)\leq\frac{\sigma^2}{\varepsilon^2}
$$

#### Demostración

Consideremos la variable $Y=(X-\mu)^2$. Claramente $Y\geq0$ y su esperanza es:

$$
E(Y)=E((X-\mu)^2)=Var(X)=\sigma^2
$$

Si aplicamos la desigualdad de Markov a $Y=(X-\mu)^2$ con $\varepsilon^2$ obtenemos que:

$$
P(Y\geq\varepsilon^2)\leq\frac{E(X)}{\varepsilon^2}=\frac{\sigma^2}{\varepsilon^2}
$$

Concluimos la demostración al notar que el evento $\{Y\geq\varepsilon^2\}=\{(X-\mu)^2\geq\varepsilon^2\}=\{|X-\mu|\geq\varepsilon\}$. $\blacksquare$

## Variables aleatorias idénticamente distribuidas

**Nota:** No encontré la bibliografía para este tema, por lo que voy a tomar esta sección desde Wikipedia.

Sean dos v.a. $X$ e $Y$ y sus f.d.a. respectivas y la conjunta:

- $F_X(x)=P(X\leq x)$
- $F_Y(y)=P(Y\leq y)$
- $F_{X,Y}(x,y)=P(X\leq x,Y\leq y)$

Decimos que $X$ e $Y$ son **idénticamente distribuidas** sii:

$$
F_X(x)=F_Y(x)\quad\forall x\in R
$$

Donde denotamos $R$ como el recorrido de ambas $X$ e $Y$ (que claramente tiene que ser igual para que sean idénticamente distribuidas).

Este concepto se puede generalizar a más de dos v.a.