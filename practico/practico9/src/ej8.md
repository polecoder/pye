# Ejercicio 08 - Sesgo de un estimador

**Fecha:** 10-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sean $X_1,\ldots,X_n\sim\mathcal{P}(\lambda)$ i.i.d. Entonces:

1. Estimar $\lambda$ por el método de los momentos. Observar que es insesgado.
2. Probar que $s_n^2$ también es un estimador insesgado para $\lambda$.
3. Encontrar el estimador de máxima verosimilitud para $\lambda$ y observar que coincide con el estimador obtenido por el método de los momentos.

## Resolución

### Parte 1

- Estimar $\lambda$ por el método de los momentos. Observar que es insesgado.

Aplicar el método de los momentos, nos devuelve la siguiente ecuación, si recordamos que la esperanza de una distribución de Poisson es $E(X)=\lambda$.

$$
\hat\lambda=\overline{X_n}
$$

Desarrollamos para demostrar que el estimador hallado es insesgado.

$$
\begin{aligned}
&E(\hat\lambda)\\
&=\scriptstyle{(\text{definción de }\hat\lambda)}\\
&E(\overline{X_n})\\
&=\scriptstyle{(\text{definición de promedio muestral})}\\
&E\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\frac{1}{n}\sum_{i=1}^nE(X_i)\\
&=\scriptstyle{(E(X_i)=\lambda)}\\
&\frac{1}{n}\cdot n\lambda\\
&=\scriptstyle{(\text{operatoria})}\\
&\lambda\\
\end{aligned}
$$

Esto demuestra que $\hat\lambda$ es un estimador insesgado para $\lambda$. $\blacksquare$

### Parte 2

- Probar que $s_n^2$ también es un estimador insesgado para $\lambda$.

Recordemos que la varianza para una distribución de Poisson es $Var(X)=\lambda$. Esto prueba directamente que $s_n^2$ es insesgado para $\lambda$, pues ya vimos en los ejercicios anteriores que:

- $s_n^2$ es insesgado para $\sigma^2$

Y como en este caso $\sigma^2=\lambda$, queda probada esta parte también.

### Parte 3

- Encontrar el estimador de máxima verosimilitud para $\lambda$ y observar que coincide con el estimador obtenido por el método de los momentos.

Recordemos que el método de máxima verosimilitud consiste en maximizar la función $L(\lambda)=\prod_{i=1}^n p_x(x_i,\lambda)$. Hallemos esta función y sigamos los pasos del método.

$$
L(\lambda)=\prod_{i=1}^n\frac{\lambda^{x_i}e^{-\lambda}}{x_i!}
$$

Hallemos también $h(\lambda)=\log(L(\lambda))$ ya que la función se ve bastante compleja de manejar:

$$
\begin{aligned}
&\log(L(\lambda))\\
&=\scriptstyle{(\text{definición de }L)}\\
&\sum_{i=1}^n\log\left(\frac{\lambda^{x_i}e^{-\lambda}}{x_i!}\right)\\
&=\scriptstyle{(\text{propiedades de logarítmo})}\\
&\sum_{i=1}^n(\log(\lambda^{x_i})+\log(e^{-\lambda})-\log(x_i!))\\
&=\scriptstyle{(\text{propiedades de logaritmo})}\\
&\sum_{i=1}^n(x_i\log(\lambda)-\lambda-\log(x_i!))\\
&=\scriptstyle{(\text{operatoria})}\\
&-n\lambda+\sum_{i=1}^nx_i\log(\lambda)-\log(x_i!)\\
\end{aligned}
$$

Perfecto, ahora derivamos la expresión para maximizarla.

$$
\begin{aligned}
&h'(\lambda)\\
&=\scriptstyle{(\text{derivando})}\\
&-n+\sum_{i=1}^n\frac{x_i}{\lambda}\\
&=\scriptstyle{(\text{operatoria})}\\
&-n+\frac{1}{\lambda}\cdot\sum_{i=1}^nx_i\\
\end{aligned}
$$

Ahora queremos hallar cuando $h'(\lambda)=0$ para encontrar los puntos críticos.

$$
\begin{aligned}
&h'(\lambda)=0\\
&\iff\scriptstyle{(\text{derivada hallada anteriormente})}\\
&-n+\frac{1}{\lambda}\cdot\sum_{i=1}^nx_i=0\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{\lambda}\cdot\sum_{i=1}^nx_i=n\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sum_{i=1}^nx_i=n\lambda\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{n}\sum_{i=1}^nx_i=\lambda\\
&\iff\scriptstyle{(\text{definción de promedio muestral})}\\
&\boxed{\hat\lambda=\overline{X}_n}\\
\end{aligned}
$$

Este último paso ya nos deja con el estimador que buscabamos $\hat\lambda$.
Efectivamente este último coincide con el que hallamos mediante el método de los momentos.

Esto concluye el ejercicio.