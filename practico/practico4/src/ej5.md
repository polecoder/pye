# Ejercicio 05 - Variables aleatorias discretas

**Fecha:** 23-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se considera una variable aleatoria $X$ cuya función de distribución es:

1. $$F_X(x)=\begin{cases}0 & \text{si }x<-3\\1/4 & \text{si }-3\leq x<1\\3/4 & \text{si }1\leq x<2\\1 & \text{si }2\leq x\end{cases}$$

   Calcular:
   1. $P(-3\leq X\leq1)$
   2. $P(-3<X\leq1)$
   3. $P(-3\leq X<1)$
   4. $P(-3<X<1)$
   5. $P(-2<X<2)$
   6. $P(-1<X<0)$

2. $$F_X(x)=\begin{cases}0 & \text{si }x<0\\1/4 & \text{si }0\leq x<1\\1/3 & \text{si }1\leq x<2\\x/6 & \text{si }2\leq x<4\\x/8+1/4 & \text{si }4\leq x<6\\1 & \text{si }6\leq x\end{cases}$$

   Calcular:
   1. $P(1\leq X\leq5)$
   2. $P(2<X\leq4)$
   3. $P(0<X<1)$
   4. $P(4\leq X<6)$

## Resolución

### Recordatorio

Estas propiedades serán muy utiles para resolver este ejercicio.

1. $P(a<X\leq b)=F_X(b)-F_X(a)$
2. $P(X=a)=F_X(a)-\lim_{x\to a^-}F_X(x)$
3. $P(a\leq X\leq b)=F_X(b)-\lim_{x\to a^-}F_X(x)$
4. $P(a<X<b)=\lim_{x\to b^-}F_X(x)-F_X(a)$
5. $P(a\leq X<b)=\lim_{x\to b^-}F_X(x)-\lim_{x\to a^-}F_X(x)$
6. $P(X>a)=1-F_X(a)$
7. $P(X\geq a)=1-\lim_{x\to a^-}F_X(x)$

### Parte 1

- $$F_X(x)=\begin{cases}0 & \text{si }x<-3\\1/4 & \text{si }-3\leq x<1\\3/4 & \text{si }1\leq x<2\\1 & \text{si }2\leq x\end{cases}$$

   Calcular:
   1. $P(-3\leq X\leq1)$
   2. $P(-3<X\leq1)$
   3. $P(-3\leq X<1)$
   4. $P(-3<X<1)$
   5. $P(-2<X<2)$
   6. $P(-1<X<0)$

Vamos uno por uno, recordemos que estamos usando las propiedades listadas en el recordatorio (ejercicio tres del práctico).

**Probabilidad #1:**

$$
\begin{aligned}
&P(-3\leq X\leq1)=F_X(1)-\lim_{x\to-3^-}F_X(x)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-3\leq X\leq1)=\frac{3}{4}-0\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-3\leq X\leq1)=\frac{3}{4}\\
\end{aligned}
$$

**Probabilidad #2:**

$$
\begin{aligned}
&P(-3<X\leq1)=F_X(1)-F_X(-3)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-3<X\leq1)=\frac{3}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-3<X\leq1)=\frac{1}{2}\\
\end{aligned}
$$

**Probabilidad #3:**

$$
\begin{aligned}
&P(-3\leq X<1)=\lim_{x\to1^-}F_X(x)-\lim_{x\to-3^-}F_X(-3)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-3\leq X<1)=\frac{1}{4}-0\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-3\leq X<1)=\frac{1}{4}\\
\end{aligned}
$$

**Probabilidad #4:**

$$
\begin{aligned}
&P(-3<X<1)=\lim_{x\to 1^-}F_X(x)-F_X(-3)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-3<X<1)=\frac{1}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-3<X<1)=0\\
\end{aligned}
$$

**Probabilidad #5:**

$$
\begin{aligned}
&P(-2<X<2)=\lim_{x\to 2^-}F_X(x)-F_X(-2)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-2<X<2)=\frac{3}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-2<X<2)=\frac{1}{2}\\
\end{aligned}
$$

**Probabilidad #6:**

$$
\begin{aligned}
&P(-1<X<0)=\lim_{x\to 0^-}F_X(x)-F_X(-1)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(-1<X<0)=\frac{1}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-1<X<0)=0\\
\end{aligned}
$$

### Parte 2

- $$F_X(x)=\begin{cases}0 & \text{si }x<0\\1/4 & \text{si }0\leq x<1\\1/3 & \text{si }1\leq x<2\\x/6 & \text{si }2\leq x<4\\x/8+1/4 & \text{si }4\leq x<6\\1 & \text{si }6\leq x\end{cases}$$

   Calcular:
   1. $P(1\leq X\leq5)$
   2. $P(2<X\leq4)$
   3. $P(0<X<1)$
   4. $P(4\leq X<6)$

Vamos uno por uno, recordemos que estamos usando las propiedades listadas en el recordatorio (ejercicio tres del práctico).

**Probabilidad #1:**

$$
\begin{aligned}
&P(1\leq X\leq5)=F_X(5)-\lim_{x\to1^-}F_X(x)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(1\leq X\leq5)=\frac{5}{8}+\frac{1}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(1\leq X\leq5)=\frac{5}{8}\\
\end{aligned}
$$

**Probabilidad #2:**

$$
\begin{aligned}
&P(2<X\leq4)=F_X(4)-F_X(2)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(2<X\leq4)=\frac{1}{2}+\frac{1}{4}-\frac{1}{3}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(2<X\leq4)=\frac{3}{4}-\frac{1}{3}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(2<X\leq4)=\frac{5}{12}\\
\end{aligned}
$$

**Probabilidad #3:**

$$
\begin{aligned}
&P(0<X<1)=\lim_{x\to 1^-}F_X(x)-F_X(0)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(0<X<1)=\frac{1}{4}-\frac{1}{4}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(0<X<1)=0\\
\end{aligned}
$$

**Probabilidad #4:**

$$
\begin{aligned}
&P(4\leq X<6)=\lim_{x\to 6^-}F_X(x)-\lim_{x\to 4^-}F_X(x)\\
&\iff\scriptstyle{(\text{definición de }F_X)}\\
&P(4\leq X<6)=\frac{3}{4}+\frac{1}{4}-\frac{2}{3}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(4\leq X<6)=\frac{1}{3}\\
\end{aligned}
$$