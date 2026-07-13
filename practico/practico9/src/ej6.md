# Ejercicio 06 - Sesgo de un estimador

**Fecha:** 09-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sean $(X_n)_{n\in\mathbb{N}}$ iid tales que $E(X_1)=\mu$ y $\text{Var}(X_1)=\sigma^2<\infty$ ($\sigma>0$).

Mostrar que $\overline{X}_n$ es insesgado como estimador de $\mu$, que $\sigma_n^2$ no es insesgado como estimador de $\sigma^2$ y que $s_n^2$ es insesgado para $\sigma^2$.

## Resolución

### Recordatorio: definición de estimador insesgado

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$, se dice que $\hat\theta=\hat\theta(X_1,\ldots,X_n)$:

- Es un estimador insesgado si y sólo si $E(\hat\theta)=\theta$
- Es un estimador asintóticamente insesgado si y sólo si $\lim_{n\to\infty}E(\hat\theta)=\theta$

### Continuación

Usando la definición, probamos primero que $\overline{X_n}$ es un estimador insesgado de $\mu$.

$$
\begin{aligned}
&E(\overline{X_n})\\
&=\scriptstyle{(\text{definición de }\overline{X_n})}\\
&E\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{linealidad de esperanza})}\\
&\frac{1}{n}\sum_{i=1}^nE(X_i)\\
&=\scriptstyle{(\text{sabiendo que para todo }i:\ E(X_i)=\mu)}\\
&\frac{1}{n}\cdot n\mu\\
&=\scriptstyle{(\text{operatoria})}\\
&\mu
\end{aligned}
$$

Esto prueba que $\overline{X_n}$ es un estimador insesgado de $\mu$.
**Nota:** Esto vale para cualquier sucesión de variables aleatorias i.i.d. cómo lo utilizaremos más adelante en el ejercicio la llamaremos **propiedad #1**.

Por otra parte, queremos probar que $\sigma_n^2$ no es un estimador insesgado de $\sigma^2$. Seguimos el mismo razonamiento:

$$
\begin{aligned}
&E(\sigma_n^2)\\
&=\scriptstyle{(\text{definición de }\sigma_n^2)}\\
&E\left(\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2\right)\\
&=\scriptstyle{(\text{sugerencia vista en el ejercicio 1})}\\
&E\left(\frac{1}{n}\sum_{i=1}^{n}X_i^2-(\overline{X_n})^2\right)\\
&=\scriptstyle{(\text{promedio muestral para }X_i^2)}\\
&E(\overline{X_n^2}-(\overline{X_n})^2)\\
&=\scriptstyle{(\text{linealidad de esperanza})}\\
&E(\overline{X_n^2})-E((\overline{X_n})^2)\\
&=\scriptstyle{(\text{como el promedio muestral es un estimador insesgado})}\\
&E(X^2)-E((\overline{X_n})^2)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&Var(X)+E(X)^2-(Var(\overline{X_n})+E(\overline{X_n})^2)\\
&=\scriptstyle{(\text{reemplazando valores conocidos, y }\overline{X_n}\text{ es insesgado})}\\
&\sigma^2+\cancel{\mu^2}-(Var(\overline{X_n})+\cancel{\mu^2})\\
&=\scriptstyle{(\text{definición de }\overline{X_n})}\\
&\sigma^2-Var\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de varianza cuando las variables son independientes})}\\
&\sigma^2-\frac{1}{n^2}\sum_{i=1}^nVar(X_i)\\
&=\scriptstyle{(Var(X_i)=\sigma^2)}\\
&\sigma^2-\frac{1}{n^2}\cdot n\sigma^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\sigma^2-\frac{\sigma^2}{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{n\sigma^2-\sigma^2}{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{n-1}{n}\cdot \sigma^2\\
\end{aligned}
$$

Por lo tanto $\sigma_n^2$ no es un estimador insesgado, pues su esperanza no es $\sigma^2$.
Esto nos va a servir para la última parte, que consiste en calcular la esperanza de $s_n^2$ para demostrar que es insesgado.

$$
\begin{aligned}
&E(s_n^2)\\
&=\scriptstyle{(\text{observación del ejercicio 1 sobre }s_n^2)}\\
&E\left(\frac{n}{n-1}\cdot\sigma_n^2\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\frac{n}{n-1}\cdot E\left(\sigma_n^2\right)\\
&=\scriptstyle{(\text{esperanza que ya calculamos})}\\
&\frac{n}{n-1}\cdot\frac{n-1}{n}\cdot \sigma^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\sigma^2
\end{aligned}
$$

Esto prueba que $s_n^2$ es insesgado. Esto concluye el ejercicio. $\blacksquare$
