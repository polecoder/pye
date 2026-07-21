# Clase 15 - Métodos de estimación

**Fecha:** 06-07-2026

## Métodos de estimación

Finalizamos el tema de métodos de estimación introduciendo el segundo método que estaremos utilizando: el método de máxima verosimilitud.

### Método de máxima verosimilitud

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ discreta con función de probabilidad $p_X(x,\theta)$ (o absolutamente continua con función de densidad $f_X(x,\theta)$), se define la función de verosimilitud de la muestra a la función:

- $L(x_1,x_2,\ldots,x_n,\theta)=\prod_{i=1}^np_X(x_i,\theta)$ o,
- $L(x_1,x_2,\ldots,x_n,\theta)=\prod_{i=1}^nf_X(x_i,\theta)$

Según el tipo de variable aleatoria con el que estamos trabajando.
El método de máxima verosimilitud consiste en resolver un problema de optimización en el que buscamos hallar:

$$
\hat\theta=\arg\max_{\theta\in\Theta}L(x_1,x_2,\ldots,x_n,\theta)
$$

Donde $\arg$ indica que buscamos el valor de $\theta$ que maximiza la función $L$, no nos interesa el máximo en si.

Dado que la función $\ln$ es creciente, el valor de $\theta$ donde se maximiza $L(\theta)$ es el mismo valor de $\theta$ donde se maximiza $h(\theta)=\ln(L(\theta))$. Muchas veces es más fácil maximizar $h$ que maximizar la función $L$.

Supongamos que luego de realizado el muestreo, obtuvimos la muestra $(x_1,x_2,\ldots,x_n)$. Además suponemos que $X$ es discreta con función de probabilidad $p_X(x,\theta)$, entonces:

$$
\begin{aligned}
&L(x_1,x_2,\ldots,x_n)\\
&=\scriptstyle{(\text{definición de }L)}\\
&\prod_{i=1}^np_X(x_i,\theta)\\
&=\scriptstyle{(\text{definición de }p_X)}\\
&\prod_{i=1}^nP(X=x_i,\theta)\\
&=\scriptstyle{(\text{las }X_i\text{ son i.i.d.})}\\
&\prod_{i=1}^nP(X_i=x_i,\theta)\\
&=\scriptstyle{(\text{independencia de las }X_i)}\\
&P(X_1=x_1,X_2=x_2,\ldots,X_n=x_n,\theta)\\
&=\scriptstyle{(\text{definición})}\\
&P((X_1,X_2,\ldots,X_n)=(x_1,x_2,\ldots,x_n))
\end{aligned}
$$

Esto significa que la función de verosimilitud $L$, es la probabilidad (en función de $\theta$) de que la muestra $(X_1,X_2,\ldots,X_n)$ sea $(x_1,x_2,\ldots,x_n)$.
Entonces, intuitivamente podemos pensar que si se observó la muestra $(x_1,x_2,\ldots,x_n)$, entonces ésta debería tener una probabilidad alta de ocurrir, por lo tanto como método se busca aquel valor de $\theta$ que maximice esta probabilidad.

#### Ejemplo

Si $X_1,X_2,\ldots,X_n$ es una M.A.S. de $X\sim Ber(p)$, hallemos el estimador máximo verosímil de $p$.

- $L(p)=\prod_{i=1}^np_X(x_i,p)$
- $h(p)=\log(L(p))=\sum_{i=1}^n\log(p_X(x_i,p))$

En base a esto operamos para maximizar $\log(L(p))$:

$$
\begin{aligned}
&\log(L(p))\\
&=\scriptstyle{(\text{cálculo anterior})}\\
&\sum_{i=1}^n\log(p_X(x_i,p))\\
&=\scriptstyle{(\text{distribución de una Bernoulli})}\\
&\sum_{i=1}^n\log(p^{x_i}(1-p)^{1-x_i})\\
&=\scriptstyle{(\text{propiedades de logaritmo})}\\
&\sum_{i=1}^n[\log p^{x_i}+\log((1-p)^{1-x_i})]\\
&=\scriptstyle{(\text{propiedades de logaritmo})}\\
&\sum_{i=1}^n[x_i\log(p)+(1-x_i)\log(1-p)]\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{i=1}^nx_i\log(p)+\left(n-\sum_{i=1}^nx_i\right)\log(1-p)\\
\end{aligned}
$$

Luego, derivando la expresión obtenemos que:

$$
h'(p)=\sum_{i=1}^nx_i\cdot\frac{1}{p}-\left(n-\sum_{i=1}^nx_i\right)\cdot\frac{1}{1-p}\\
$$

Queremos analizar que sucede cuando $h'(p)=0$ para encontrar el máximo.

$$
\begin{aligned}
&h'(p)=0\\
&\iff\scriptstyle{(\text{derivada hallada anteriormente})}\\
&\sum_{i=1}^nx_i\cdot\frac{1}{p}-\left(n-\sum_{i=1}^nx_i\right)\cdot\frac{1}{1-p}=0\\
&\iff\scriptstyle{(\text{operatoria y facilitamos notación})}\\
&\sum x_i\cdot\frac{1}{p}=\left(n-\sum x_i\right)\cdot\frac{1}{1-p}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sum x_i(1-p)=\left(n-\sum x_i\right)p\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sum x_i-\cancel{p\sum x_i}=pn-\cancel{p\sum x_i}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\sum x_i=pn\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{n}\cdot\sum x_i=p\\
&\iff\scriptstyle{(\text{definición de promedio muestral})}\\
&\overline{x}=p\\
\end{aligned}
$$

Como hallamos, el punto crítico ocurre en $p=\overline{x}$

Dado que para todo $i$ se tiene que $x_i\in\{0,1\}$, entonces $\overline{X_n}\in[0,1]$ para todo $n$. Analizando el signo de $h'$, vemos que $h$ se maximiza para $\hat{p}=\overline{X_n}$.