# Clase 17 - Intervalos de confianza

**Fecha:** 14-07-2026

## Definición - Intervalos de confianza

### Introducción

Dada una M.A.S. $X_1,\ldots,X_n$ de $X$, cuya función de distribución es $F_X(x,\theta)$ siendo $\theta\in\Theta\subset\mathbb{R}$, en lugar de estimar un valor numérico a partir de los datos de la muestra, daremos una región (en general un intervalo) con "probabilidad tan alta como se desee" de que el verdadero parámetro pertenezca a dicha región (intervalo).

### Definición formal 11.1

Si $X_1,\ldots,X_n$ es una M.A.S. de $X$ cuya función de distribución es $F_X(x,\theta)$ siendo $\theta\in\Theta\subset\mathbb{R}$.
Dado $\alpha\in(0,1)$, supongamos que $a(X_1,\ldots,X_n)$ y $b(X_1,\ldots,X_n)$ son dos estadísticos tales que:

- $P(\theta\in[a(X_1,\ldots,X_n),b(X_1,\ldots,X_n)])=1-\alpha$

Diremos entonces que $I=[a(X_1,\ldots,X_n),b(X_1,\ldots,X_n)]$ es un intervalo de confianza de nivel $1-\alpha$ para el parámetro $\theta$.

### Observación 11.2

En la práctica el valor de $\alpha$ (o equivalentemente el nivel de confianza $1-\alpha$) está determinado por el investigador, por lo que es un valor fijo.

## Construcción de intervalos de confianza en algunos casos particulares

### Intervalo de confianza para $\mu$ con distribución normal con $\sigma^2$ conocido

Sea $X_1,X_2,\ldots,X_n$ es una M.A.S. de $X\sim N(\mu,\sigma^2)$. Supongamos que conocemos $\sigma^2$, queremos construir un intervalo de confianza para el parámetro desconocido $\mu$.
Sabemos que por LFGN que $\overline{X}_n\xrightarrow[n]{c.s.}\mu$, por lo que tiene sentido formar un intervalo de la forma:

- $[\overline{X}_n-k,\overline{X}_n+k]$ para algún $k$ que no dependa de parámetros desconocidos.

Siempre y cuando podamos hallar $k$ de modo que $P(\mu\in[\overline{X}_n-k,\overline{X}_n+k])=1-\alpha$.
Notemos que $\overline{X}_n\sim N(\mu,\sigma^2/n)$ por ser combinación lineal de normales. Entonces:

$$
\begin{aligned}
&P(\mu\in[\overline{X}_n-k;\overline{X}_n+k])\\
&=\scriptstyle{(\text{definición de inclusión en un intervalo})}\\
&P(\overline{X}_n-k\leq\mu\leq\overline{X}_n+k)\\
&=\scriptstyle{(\text{restando }\overline{X}_n\text{ y }\mu)}\\
&P(-\mu-k\leq-\overline{X}_n\leq-\mu+k)\\
&=\scriptstyle{(\text{multiplicando por }-1)}\\
&P(\mu+k\geq\overline{X}_n\geq\mu-k)\\
&=\scriptstyle{(\text{reordenando})}\\
&P(\mu-k\leq\overline{X}_n\leq\mu+k)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(\frac{\mu-k-\mu}{\sigma/\sqrt{n}}\leq Z_n\leq\frac{\mu+k-\mu}{\sigma/\sqrt{n}}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P\left(\frac{-k\sqrt{n}}{\sigma}\leq Z_n\leq\frac{k\sqrt{n}}{\sigma}\right)\\
&=\scriptstyle{(\text{recordando que }Z_n\sim N(0,1))}\\
&\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)-\Phi\left(-\frac{k\sqrt{n}}{\sigma}\right)\\
&=\scriptstyle{(\text{propiedades de }\Phi)}\\
&\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)-\left(1-\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&2\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)-1\\
&=\scriptstyle{(\text{lo que queremos que se cumpla})}\\
&1-\alpha
\end{aligned}
$$

Luego, de este último punto que obtuvimos desarrollando, podemos despejar $k$ de la expresión para saber que valor tiene que tener:

$$
\begin{aligned}
&2\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)-1=1-\alpha\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\Phi\left(\frac{k\sqrt{n}}{\sigma}\right)=1-\alpha/2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{k\sqrt{n}}{\sigma}=\Phi^{-1}(1-\alpha/2)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&k=\frac{\Phi^{-1}(1-\alpha/2)\cdot\sigma}{\sqrt{n}}\\
\end{aligned}
$$

Además, llamando $z_p=\Phi^{-1}(1-p)$ para todo $p\in(0,1)$, podemos definir el intervalo de confianza para este caso como:

$$
\boxed{
\left[\overline{X}_n-\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}},\overline{X}_n+\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\right]
}
$$

Esto sale bastante lindo, pero lamentablemente para el caso donde no conocemos $\sigma^2$ no tenemos tanta suerte. Si bien los cálculos son igualmente válidos, esto que hallamos no sería un estadístico, ya que $k$ dependería de un parámetro desconocido. Por lo tanto este razonamiento no es suficiente para construir un intervalo de confianza.
Esto nos lleva a introducir dos nuevas familias de v.a.

### Definición 11.4

Se dice que $X$ tiene una distribución $t$-student con $n$ grados de libertad, y se escribe $X\sim t_n$, cuando tiene la siguiente densidad:

$$
f_X(x)=\frac{\Gamma\left(\frac{n+1}{2}\right)}{\sqrt{n\pi}\Gamma\left(\frac{n}{2}\right)}\cdot\frac{1}{\left(1+\frac{x^2}{n}\right)^{\frac{n+1}{2}}}
$$

Observemos que si $X\sim t_n$, entonces se puede verificar que:

- $E(X)=0$ para $n>1$ (si $n\leq1$ entonces no existe la esperanza)
- $Var(X)=\frac{n}{n-2}$ para $n>2$ $($si $n\leq2$, no admite momentos de orden $2)$

### Definición 11.5

Se dice que $X$ tiene una distribución $\chi^2$ con $n$ grados de libertad, y se escribe $X\sim\chi_n^2$ cuando tiene la siguiente densidad:

$$
f_X(x)=\begin{cases}
\frac{1}{2^{n/2}\Gamma(n/2)}x^{(n/2)-1}e^{-x/2}&\text{si }x>0\\
0&\text{en otro caso}
\end{cases}
$$

Observemos que si $X\sim\chi_n^2$, entonces se puede verificar que:

- $E(X)=n$
- $Var(X)=2n$

---

Ahora que definimos las dos nuevas familias de variables aleatorias, enunciemos un teorema que vamos a utilizar (pero no demostrar) para poder determinar que hacemos en el caso donde la varianza $\sigma^2$ es desconocida.

### Teorema 11.6

Si $X_1,\ldots,X_n$ es una M.A.S. de $X\sim N(\mu,\sigma^2)$ entonces:

$$
\frac{\sqrt{n}(\overline{X}_n-\mu)}{S_n}\sim T(n-1)
$$

Donde: 

- $T(n-1)$ es $t-$student con $n-1$ grados de libertad.
- $S_n^2=\frac{1}{n-1}\sum_{i=1}^n(X_i-\overline{X}_n)^2$, es decir la varianza muestral.

### Intervalo de confianza para $\mu$ con distribución normal con $\sigma^2$ desconocido

Y ahora si, estamos en condiciones de usar todo lo que estudiamos para encontrar un intervalo de confianza de nivel $1-\alpha$ para $\mu$.
Buscamos un intervalo de la forma $[\overline{X}_n-kS_n,\overline{X}_n+kS_n]$, operamos entonces para encontrar lo que buscamos.

$$
\begin{aligned}
&P(\mu\in[\overline{X}_n-kS_n,\overline{X}_n+kS_n])\\
&=\scriptstyle{(\text{definición de entorno})}\\
&P(|\overline{X}_n-\mu|\leq kS_n)\\
&=\scriptstyle{(\text{multiplicando por }\frac{\sqrt{n}}{S_n}>0)}\\
&P\left(\frac{\sqrt{n}|\overline{X}_n-\mu|}{S_n}\leq k\sqrt{n}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P\left(-k\sqrt{n}\leq\frac{\sqrt{n}(\overline{X}_n-\mu)}{S_n}\leq k\sqrt{n}\right)\\
&=\scriptstyle{(\text{teorema anterior})}\\
&P\left(-k\sqrt{n}\leq T(n-1)\leq k\sqrt{n}\right)\\
&=\scriptstyle{(\text{distribución de }t-\text{student})}\\
&F_T(k\sqrt{n})-F_T(-k\sqrt{n})\\
&=\scriptstyle{(\text{simetría de }t-\text{student})}\\
&2F_T(k\sqrt{n})-1\\
&=\scriptstyle{(\text{la igualdad que queremos alcanzar})}\\
&1-\alpha\\
\end{aligned}
$$

Luego, de este último punto que obtuvimos desarrollando, podemos despejar $k$ de la expresión para saber que valor tiene que tener:

$$
\begin{aligned}
&2F_T(k\sqrt{n})-1=1-\alpha\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_T(k\sqrt{n})=1-\alpha/2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&k\sqrt{n}=F_T^{-1}(1-\alpha/2)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&k=\frac{F_T^{-1}(1-\alpha/2)}{\sqrt{n}}
\end{aligned}
$$

Llegados a este punto, podemos aliviar la notación llamando:

$$
t_p(n)=F^{-1}(1-p)
$$

Donde $F$ es la función de distribución correspondiente a una variable $t-$student con $n$ grados de libertad. De esta forma nos queda el intervalo de confianza como:

$$
\boxed{
\left[\overline{X}_n-\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}},\overline{X}_n+\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}}\right]
}
$$

---

Después de esto, el teórico abarca otros casos que tienen un análisis similar a estos, solo que son muy extensos.
A continuación daremos intervalos de confianza para casos particulares, sin hacer el análisis que hicimos para estos casos.

### Intervalo de confianza para $\mu$ con $\sigma^2$ desconocido para $n$ grande

Si $X\in L^2$ y $n$ es suficientemente grande, un intervalo aproximado es:

$$
\boxed{
\left[\overline{X}_n-\frac{S_nz_{\alpha/2}}{\sqrt{n}},\overline{X}_n+\frac{S_nz_{\alpha/2}}{\sqrt{n}}\right]
}
$$

**Nota:** Notemos que en este caso, a diferencia de los anteriores, la distribución no tiene porque ser la normal.

### Intervalo de confianza para $p$ cuando $X\sim Ber(p)$ para $n$ grande

Si $X\sim Ber(p)$, entonces un intervalo de confianza aproximado para $p$ al nivel de confianza de $1-\alpha$ cuando $X\sim Ber(p)$.

$$
\boxed{
\left[\overline{X}_n-\frac{\sqrt{\overline{X}_n(1-\overline{X}_n)}z_{\alpha/2}}{\sqrt{n}},\overline{X}_n+\frac{\sqrt{\overline{X}_n(1-\overline{X}_n)}z_{\alpha/2}}{\sqrt{n}}\right]
}
$$

### Intervalo de confianza para $\sigma^2$ en el caso en que $X\sim N(\mu,\sigma^2)$

En este caso, un intervalo de confianza aproximado para $\sigma^2$ al nivel de confianza de $1-\alpha$ es:

$$
\boxed{
\left[
\frac{(n-1)S_n^2}{\chi^2_{\alpha/2}(n-1)},\frac{(n-1)S_n^2}{\chi^2_{1-\alpha/2}(n-1)}
\right]
}
$$

Donde $\chi_p^2(n)=F^{-1}(1-p)$, con $F$ es la función de distribución que corresponde a una distribución $\chi_n^2$.