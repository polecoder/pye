# Ejercicio 03 - Ley fuerte de los grandes números

**Fecha:** 02-07-2026
**Estado:** 🟡 Con ayuda

## Consigna

Sean $(X_i)_{i\in\mathbb{N}}$ variables independientes e idénticamente distribuidas. Suponga que $E(X_1)=0$ y sea $Y_i=\dfrac{X_i+X_{i+1}}{2}$.

Demostrar que $\overline{Y}_n\xrightarrow[n]{\text{c.s.}}0$, aunque $Y_n,Y_{n+1}$ pueden ser dependientes para todo $n$.

## Resolución

Yendo directo a lo que queremos demostrar, tratemos de hallar quién es $\overline{Y_n}$.

$$
\begin{aligned}
&\overline{Y_n}\\
&=\scriptstyle{(\text{definición de promedio muestral})}\\
&\frac{1}{n}\cdot\sum_{i=1}^nY_i\\
&=\scriptstyle{(\text{definición de }Y_i)}\\
&\frac{1}{n}\cdot\sum_{i=1}^n\frac{X_i+X_{i+1}}{2}\\
&=\scriptstyle{(\text{desarrollando la sumatoria})}\\
&\frac{1}{n}\cdot\left(\frac{X_1+X_2}{2}+\frac{X_2+X_3}{2}+\frac{X_3+X_4}{2}+\ldots+\frac{X_{n-1}+X_n}{2}+\frac{X_n+X_{n+1}}{2}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{n}\cdot\left(\frac{X_1+X_{n+1}}{2}+\sum_{i=2}^nX_i\right)\\
\end{aligned}
$$

Por otra parte, los datos nos dicen que $(X_i)_{i\in\mathbb{N}}$ son variables aleatorias i.i.d. y que $E(X_1)=0$. De esto podemos sacar que todas tienen esperanza cero, es decir que:

- $E(X_i)=0$ para todo $i\in\mathbb{N}$

Tomando la esperanza del promedio muestral obtenemos que:

$$
\begin{aligned}
&E(\overline{Y_n})\\
&=\scriptstyle{(\text{reemplazando por el promedio muestral})}\\
&E\left(\frac{1}{n}\cdot\left(\frac{X_1+X_{n+1}}{2}+\sum_{i=2}^nX_i\right)\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\frac{1}{n}\cdot E\left(\frac{X_1+X_{n+1}}{2}+\sum_{i=2}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\frac{1}{n}\cdot\left(\frac{1}{2}(E(X_1)+E(X_{n+1}))+\sum_{i=2}^nE(X_i)\right)\\
&=\scriptstyle{(E(X_i)=0)}\\
&\frac{1}{n}\cdot0\\
&=\scriptstyle{(\text{operatoria})}\\
&0
\end{aligned}
$$

Por lo tanto, la esperanza de $\overline{Y_i}$ es $\mu=0$. Por la ley de los grandes números, podemos concluir que:

- $\overline{Y_i}\xrightarrow[n]{c.s.}0$

Que es lo que queríamos probar.