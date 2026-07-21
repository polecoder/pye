# Ejercicio 01 - Consistencia de un estimador

**Fecha:** 07-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sean $(X_n)_{n\in\mathbb{N}}$ iid tales que $E(X_1)=\mu$ y $Var(X_1)=\sigma^2<\infty$ ($\sigma>0$).

1. Demostrar que $\overline{X}_n$ es un estimador consistente de $\mu$, esto es que $\overline{X}_n\xrightarrow[n]{\text{c.s.}}\mu$.

2. Demostrar que si $\sigma_n^2=\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2$ y $s_n^2=\frac{1}{n-1}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2$ entonces:

    $$
    \sigma_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2\qquad s_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2\qquad\sigma_n\xrightarrow[n]{\text{c.s.}}\sigma\qquad s_n\xrightarrow[n]{\text{c.s.}}\sigma
    $$

   Sugerencia: $\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2=\frac{1}{n}\sum_{i=1}^{n}(X_i)^2-\left(\overline{X}_n\right)^2$ y usar los siguientes resultados:

   - Si $X_n\xrightarrow[n]{\text{c.s.}}X$ y $g:\mathbb{R}\to\mathbb{R}$ es continua entonces $g(X_n)\xrightarrow[n]{\text{c.s.}}g(X)$.
   - Si $X_n\xrightarrow[n]{\text{c.s.}}X$ e $Y_n\xrightarrow[n]{\text{c.s.}}Y$ y $g:\mathbb{R}^2\to\mathbb{R}$ es continua entonces $g(X_n,Y_n)\xrightarrow[n]{\text{c.s.}}g(X,Y)$.

## Resolución

### Parte 1

- Demostrar que $\overline{X}_n$ es un estimador consistente de $\mu$, esto es que $\overline{X}_n\xrightarrow[n]{\text{c.s.}}\mu$

Esto se cumple directamente por el enunciado de la ley de los grandes números.

### Parte 2

- Demostrar que si $\sigma_n^2=\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2$ y $s_n^2=\frac{1}{n-1}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2$ entonces:

    $$
    \sigma_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2\qquad s_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2\qquad\sigma_n\xrightarrow[n]{\text{c.s.}}\sigma\qquad s_n\xrightarrow[n]{\text{c.s.}}\sigma
    $$

   Sugerencia: $\frac{1}{n}\sum_{i=1}^{n}\left(X_i-\overline{X}_n\right)^2=\frac{1}{n}\sum_{i=1}^{n}(X_i)^2-\left(\overline{X}_n\right)^2$ y usar los siguientes resultados:

   - Si $X_n\xrightarrow[n]{\text{c.s.}}X$ y $g:\mathbb{R}\to\mathbb{R}$ es continua entonces $g(X_n)\xrightarrow[n]{\text{c.s.}}g(X)$.
   - Si $X_n\xrightarrow[n]{\text{c.s.}}X$ e $Y_n\xrightarrow[n]{\text{c.s.}}Y$ y $g:\mathbb{R}^2\to\mathbb{R}$ es continua entonces $g(X_n,Y_n)\xrightarrow[n]{\text{c.s.}}g(X,Y)$.

Fragmentaremos esta parte por cada demostración que queremos hacer.

#### Demostración #1

- $\sigma_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2$

Desarrollamos con la sugerencia:

$$
\begin{aligned}
&\sigma_n^2\\
&=\scriptstyle{(\text{definición dada})}\\
&\frac{1}{n}\sum_{i=1}^n(X_i-\overline{X_n})^2\\
&=\scriptstyle{(\text{sugerencia})}\\
&\frac{1}{n}\sum_{i=1}^n(X_i)^2-(\overline{X_n})^2\\
&=\scriptstyle{(\text{definición de promedio muestral})}\\
&\overline{X_n^2}-(\overline{X_n})^2\\
&=\scriptstyle{(\text{tomando convergencia casi segura cuando }n\to\infty)}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&Var(X)\\
&=\scriptstyle{(\text{nomenclatura})}\\
&\sigma^2
\end{aligned}
$$

**Nota:** En el paso #4 utilizamos implicitamente que la convergencia segura se "porta bien" para funciones continuas. En este caso la función continua es $g(x)=x^2$.

Esto demuestra lo que queríamos probar. $\blacksquare$.

#### Demostración #2

- $s_n^2\xrightarrow[n]{\text{c.s.}}\sigma^2$

Notemos que $s^2_n$ tiene una forma muy similar a $\sigma^2_n$, de quién ya probamos convergencia casi segura a $\sigma^2$. Desarrollemos sobre este punto:

$$
\begin{aligned}
&s_n^2=\frac{1}{n-1}\sum_{i=1}^n(X_i-\overline{X_n})^2\\
&\iff\scriptstyle{(\text{multiplicando por }\frac{n-1}{n})}\\
&\frac{n-1}{n}\cdot s_n^2=\frac{1}{n}\cdot\sum_{i=1}^n(X_i-\overline{X_n})^2\\
&\iff\scriptstyle{(\text{definición de }\sigma_n^2)}\\
&\frac{n-1}{n}\cdot s_n^2=\sigma_n^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&s_n^2=\frac{n}{n-1}\cdot\sigma_n^2\\
\end{aligned}
$$

Queremos estudiar entonces la convergencia casi segura de $s_n^2=\frac{n}{n-1}\cdot\sigma_n^2$.

$$
\begin{aligned}
&s_n^2=\frac{n}{n-1}\cdot\sigma_n^2\\
&\iff\scriptstyle{(\text{estudiando el comportamiento cuando }n\to\infty)}\\
&s_n^2\xrightarrow[n]{c.s.}\lim_{n\to\infty}\frac{n}{n-1}\cdot\sigma^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&s_n^2\xrightarrow[n]{c.s.}\sigma^2\\
\end{aligned}
$$

Esto demuestra lo que queríamos probar. $\blacksquare$.

#### Demostración #3

- $\sigma_n\xrightarrow[n]{\text{c.s.}}\sigma$

Notemos que $\sigma_n=\sqrt{\sigma_n^2}$. Ya probamos anteriormente que $\sigma_n^2\xrightarrow[n]{c.s.}\sigma^2$. Podemos usar esta afirmación en conjunto con la siguiente propiedad de convergencia casi segura:

- Si $X_n\xrightarrow[n]{\text{c.s.}}X$ y $g:\mathbb{R}\to\mathbb{R}$ es continua entonces $g(X_n)\xrightarrow[n]{\text{c.s.}}g(X)$.

Consideramos $g(X)=\sqrt{x}$, una función continua y observamos que $\sigma_n=g(\sigma^2_n)$ con esta nueva notación. Aplicando la propiedad concluimos que:

$$
\sigma_n\xrightarrow[n]{c.s.}\sqrt{\sigma^2}=\sigma
$$

Esto demuestra lo que queríamos probar. $\blacksquare$.

#### Demostración #4

- $s_n\xrightarrow[n]{\text{c.s.}}\sigma$

El razonamiento es totalmente análogo a la demostración anterior. Sabemos que:

- $s^2_n\xrightarrow[n]{c.s.}\sigma^2$ y
- Si $X_n\xrightarrow[n]{\text{c.s.}}X$ y $g:\mathbb{R}\to\mathbb{R}$ es continua entonces $g(X_n)\xrightarrow[n]{\text{c.s.}}g(X)$.

Consideramos $g(X)=\sqrt{x}$, una función continua y observamos que $s_n=g(s^2_n)$ con esta nueva notación. Aplicando la propiedad concluimos que:

$$
s_n\xrightarrow[n]{c.s.}\sqrt{\sigma^2}=\sigma
$$

Esto demuestra lo que queríamos probar. $\blacksquare$.