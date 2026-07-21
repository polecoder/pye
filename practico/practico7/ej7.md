# Ejercicio 07 - Esperanza y varianza de una v.a.

**Fecha:** 29-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Calcular esperanza y varianza de la distribución $\text{BN}(k,p)$ (binomial negativa).

Sugerencia: Utilizar que si $X_1,\ldots,X_k\ iid\sim\text{Geo}(p)$ entonces $X_1+\cdots+X_k\sim\text{BN}(k,p)$.

## Resolución

Recordemos que la distribución binomial negativa está dada por:

$$
X\sim BN(k,p)\iff P(X=x)=\binom{x-1}{k-1}p^k(1-p)^{x-k}
$$

Por otro lado, la distribución geométrica está dada por:

$$
X\sim Geo(p)\iff P(X=x)=(1-p)^{x-1}p
$$

Sabemos que $X_1,\ldots,X_k$ están idénticamente distribuidas, por lo que además de estar distribuidas en base a la distribución geométrica, comparten esperanza y varianza.

Sea entonces $Z=X_1+\ldots+X_k$ con $X_1,\ldots,X_k\ iid\sim\text{Geo}(p)$. Por la sugerencia entonces sabemos que $Z\sim BN(k,p)$. Por otro lado, también podemos usar que la esperanza de una suma es la suma de las esperanzas, entonces tenemos que:

$$
E(Z)=E(X_1)+\ldots+E(X_k)
$$

Recordando el ejercicio 6 de este práctico, hallando que si $X\sim Geo(p)$, entonces $E(X)=\frac{1}{p}$, obtenemos que:

$$
\begin{aligned}
&E(Z)=\frac{k}{p}
\end{aligned}
$$

Por otra parte, para la varianza recordemos también que las v.a. $X_1,\ldots,X_k$ son independientes también, lo que nos permite usar la propiedad de varianza que dice que si $X,Y$ son v.a. independientes, entonces:

$$
Var(X+Y)=Var(X)+Var(Y)
$$

Con esto en mente, tenemos que:

$$
Var(Z)=Var(X_1)+\ldots+Var(X_k)
$$

Recordando el ejercicio 6 de este práctico, hallando que si $X\sim Geo(p)$ entonces $Var(X)=\frac{1-p}{p^2}$, obtenemos que:

$$
Var(Z)=\frac{k(1-p)}{p^2}
$$

Esto concluye el ejercicio.
