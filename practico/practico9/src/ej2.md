# Ejercicio 02 - Método de los momentos

**Fecha:** 08-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sean $X_1,X_2,\ldots,X_n\sim F$ i.i.d. Encontrar estimadores para los siguientes parámetros por el método de los momentos:

1. $p$ si la distribución es $\text{Ber}(p)$
2. $\lambda$ si la distribución es $\mathcal{P}(\lambda)$
3. $p$ si la distribución es $\text{Geo}(p)$
4. $\mu$ y $\sigma^2$ si la distribución es $N(\mu,\sigma^2)$
5. $a$ y $b$ si la distribución es $U[a,b]$

## Resolución

### Lema #1

Necesitaremos un pequeño resultado del ejercicio 1, recordamos que la varianza muestral se define por:

$$
\sigma_n^2=\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2=\frac{1}{n}\sum_{i=1}^nX_i^2-(\overline{X_n})^2
$$

### Parte 1

- $p$ si la distribución es $\text{Ber}(p)$

Como queremos calcular un solo parámetro, el método de los momentos nos hace plantear un sistema de una sola ecuación, es decir:

$$
E(X)=\overline{X_n}
$$

Sabemos que la esperanza de una Bernoulli es el parámetro $p$, por lo tanto sustituyendo en la ecuación nos queda el estimador por momentos del parámetro $p$:

$$
\boxed{
\hat{p}=\overline{X_n}
}
$$

### Parte 2

- $\lambda$ si la distribución es $\mathcal{P}(\lambda)$

Como queremos calcular un solo parámetro, el método de los momentos nos hace plantear un sistema de una sola ecuación, es decir:

$$
E(X)=\overline{X_n}
$$

Sabemos que la esperanza de una distribución de Poisson es $\lambda$, por lo tanto sustituyendo en la ecuación nos queda el estimador por momentos del parámetro $\lambda$:

$$
\boxed{
\hat{\lambda}=\overline{X_n}
}
$$

### Parte 3

- $p$ si la distribución es $\text{Geo}(p)$

Como queremos calcular un solo parámetro, el método de los momentos nos hace plantear un sistema de una sola ecuación, es decir:

$$
E(X)=\overline{X_n}
$$

Sabemos que la esperanza de una distribución geométrica es $\frac{1}{p}$, por lo tanto sustituyendo en la ecuación nos queda:

$$
\begin{aligned}
&\frac{1}{p}=\overline{X_n}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p=\frac{1}{\overline{X}_n}\\
\end{aligned}
$$

Entonces el estimador por momentos del parámetro $p$ es:

$$
\boxed{
\hat{p}=\frac{1}{\overline{X}_n}
}
$$

### Parte 4

- $\mu$ y $\sigma^2$ si la distribución es $N(\mu,\sigma^2)$

En este caso tenemos dos parámetros, entonces el método de los momentos nos hace plantear el siguiente sistema:

$$
\begin{cases}
E(X)=\overline{X_n}\\
E(X^2)=\frac{1}{n}\sum_{i=1}^nX_i^2
\end{cases}
$$

Para sustituir en este caso, necesitamos un cálculo previo, que sería la esperanza de $E(X^2)$ que aún desconocemos:

$$
\begin{aligned}
&E(X^2)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&Var(X)+E(X)^2\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\sigma^2+\mu^2
\end{aligned}
$$

Podemos reemplazar esto en el sistema de ecuaciones:

$$
\begin{cases}
\mu=\overline{X_n}\\
\sigma^2+\mu^2=\frac{1}{n}\sum_{i=1}^nX_i^2
\end{cases}
$$

De donde obtenemos los estimadores por momentos de $\mu$ y $\sigma^2$ despejando:

$$
\boxed{
\hat{\mu}=\overline{X_n}
}
$$

$$
\hat{\sigma^2}=\frac{1}{n}\sum_{i=1}^nX_i^2-(\overline{X_n})^2
$$

Además, utilizando el lema #1, se simplifica considerablemente la notación pues esa es exactamente la varianza muestral:

$$
\boxed{
\hat{\sigma^2}=\sigma_n^2
}
$$

### Parte 5

- $a$ y $b$ si la distribución es $U[a,b]$

En este caso tenemos dos parámetros, entonces el método de los momentos nos hace plantear el siguiente sistema:

$$
\begin{cases}
E(X)=\overline{X_n}\\
E(X^2)=\frac{1}{n}\sum_{i=1}^nX_i^2
\end{cases}
$$

Para sustituir en este caso, necesitamos un cálculo previo, que sería la esperanza de $E(X^2)$ que aún desconocemos:

$$
\begin{aligned}
&E(X^2)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&Var(X)+E(X)^2\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\frac{(b-a)^2}{12}+\left(\frac{b+a}{2}\right)^2\\
\end{aligned}
$$

Podemos reemplazar esto en el sistema de ecuaciones:

$$
\begin{cases}
\frac{b+a}{2}=\overline{X_n}\\
\frac{(b-a)^2}{12}+\left(\frac{b+a}{2}\right)^2=\frac{1}{n}\sum_{i=1}^nX_i^2\\
\end{cases}
$$

Despejando en la primera ecuación obtenemos que:

- $b+a=2\overline{X_n}\quad(*_1)$

Ahora reemplazando en la segunda:

$$
\begin{aligned}
&\frac{(b-a)^2}{12}+\left(\frac{b+a}{2}\right)^2=\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{(b-a)^2}{12}=\frac{1}{n}\sum_{i=1}^nX_i^2-\left(\frac{b+a}{2}\right)^2\\
&\iff\scriptstyle{(\text{usando el despeje }*_1)}\\
&\frac{(b-a)^2}{12}=\frac{1}{n}\sum_{i=1}^nX_i^2-\left(\frac{2\overline{X_n}}{2}\right)^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{(b-a)^2}{12}=\frac{1}{n}\sum_{i=1}^nX_i^2-(\overline{X_n})^2\\
&\iff\scriptstyle{(\text{por lema \#1})}\\
&\frac{(b-a)^2}{12}=\sigma_n^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&(b-a)^2=12\sigma_n^2\\
&\iff\scriptstyle{(\text{operatoria, suponiendo que }b\geq a)}\\
&b-a=\sqrt{12\sigma_n^2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&b-a=2\sqrt{3}\sigma_n\\
\end{aligned}
$$

Podemos sumar lo obtenido en $*_1$ y $*_2$, obteniendo:

$$
\begin{aligned}
&(b-a)+(b+a)=2\sqrt{3}\sigma_n+2\overline{X_n}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&2b=2(\sqrt{3}\sigma_n+\overline{X_n})\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\boxed{\hat{b}=\overline{X_n}+\sqrt{3}\sigma_n}
\end{aligned}
$$

Reemplazando este resultado en $*_1$:

$$
\begin{aligned}
&b+a=2\overline{X_n}\\
&\iff\scriptstyle{(\text{efectuando el reemplazo de }b)}\\
&\sqrt{3}\sigma_n+\overline{X_n}+a=2\overline{X_n}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\boxed{\hat{a}=\overline{X_n}-\sqrt{3}\sigma_n}
\end{aligned}
$$

Estos son los estimadores de $a$ y $b$ respectivamente.