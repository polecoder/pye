# Ejercicio 05 - Ley fuerte de los grandes números

**Fecha:** 03-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sea $\{X_n:n\in\mathbb{N}\}$ una sucesión de v.a. iid con $E(X_1)=a>0$. Probar que entonces

$$\sum_{i=1}^{n}X_i\xrightarrow[n]{\text{c.s.}}+\infty$$

## Resolución

Planteando la ley fuerte de los grandes números, tenemos que:

$$
\frac{1}{n}\sum_{i=1}^nX_i\xrightarrow[n]{c.s.}a\quad(*_1)
$$

Nosotros queremos ver que sucede con la misma sumatoria, pero sin la división por $1/n$. Estudiemos el límite de la sumatoria:

$$
\begin{aligned}
&\lim_{n\to+\infty}\left(\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\lim_{n\to+\infty}\left(n\cdot\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de límites de sucesiones})}\\
&\lim_{n\to+\infty} n\cdot\lim_{n\to+\infty}\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{por }*_1)}\\
&\lim_{n\to+\infty}n\cdot a\\
&=\scriptstyle{(\text{operatoria})}\\
&+\infty
\end{aligned}
$$

Esta es la definición de converger casi absolutamente a un valor, en particular:

$$
\sum_{i=1}^{n}X_i\xrightarrow[n]{\text{c.s.}}+\infty
$$

Esto concluye el ejercicio. $\blacksquare$