# Ejercicio 01 - Variables aleatorias continuas

**Fecha:** 27-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sea $X$ una variable aleatoria real continua y $a<b$ reales.

1. Demostrar que:
$P(a<X\leq b)=P(a\leq X\leq b)=P(a<X<b)=F_X(b)-F_X(a)$

2. Si además $X$ es absolutamente continua con densidad $f_X$ deducir que:
$P(a<X\leq b)=P(a\leq X\leq b)=P(a<X<b)=\int_a^b f_X(x)\,dx$

## Resolución

### Parte 1

- Demostrar que $P(a<X\leq b)=P(a\leq X\leq b)=P(a<X<b)=F_X(b)-F_X(a)$

Sabemos que por propiedades de la función distribución que:

- $P(a<X\leq b)=F_X(b)-F_X(a)$

Sabiendo esto, usemos propiedades de la probabilidad para descomponer los demás casos:

**Caso #1**

$$
\begin{aligned}
&P(a\leq X\leq b)=P(X=a)+P(a<X\leq b)\\
&\iff\scriptstyle{(\text{probabilidad puntual nula y definición})}\\
&P(a\leq X\leq b)=0+F_X(b)-F_X(a)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(a\leq X\leq b)=F_X(b)-F_X(a)\\
\end{aligned}
$$

**Caso #2**

$$
\begin{aligned}
&P(a<X<b)+P(X=b)=P(a<X\leq b)\\
&\iff\scriptstyle{(\text{probabilidad puntual nula y definición})}\\
&P(a<X<b)+0=F_X(b)-F_X(a)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(a<X<b)=F_X(b)-F_X(a)\\
\end{aligned}
$$

Queda demostrada entonces la parte 1.

### Parte 2

- Si además $X$ es absolutamente continua con densidad $f_X$ deducir que:
$P(a<X\leq b)=P(a\leq X\leq b)=P(a<X<b)=\int_a^b f_X(x)\,dx$

Recordemos que para las variables aleatorias absolutamente continuas, lo único que tenemos definido es que:

- $P(a<X\leq b)=\int_{a}^{b}f_X(x)dx$

Sabiendo esto, usemos propiedades de la probabilidad para descomponer los demás casos:

**Caso #1**

$$
\begin{aligned}
&P(a\leq X\leq b)=P(X=a)+P(a<X\leq b)\\
&\iff\scriptstyle{(\text{probabilidad puntual nula y definición})}\\
&P(a\leq X\leq b)=0+\int_{a}^{b}f_X(x)dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(a\leq X\leq b)=\int_{a}^{b}f_X(x)dx\\
\end{aligned}
$$

**Caso #2**

$$
\begin{aligned}
&P(a<X<b)+P(X=b)=P(a<X\leq b)\\
&\iff\scriptstyle{(\text{probabilidad puntual nula y definición})}\\
&P(a<X<b)+0=\int_{a}^{b}f_X(x)dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(a<X<b)=\int_{a}^{b}f_X(x)dx\\
\end{aligned}
$$

Queda demostrada entonces la parte 2.
