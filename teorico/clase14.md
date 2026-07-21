# Clase 14 - Estimación puntual y métodos de estimación

**Fecha:** 06-07-2026

## Estimación puntual

En esta sección continuamos con lo que vimos hasta ahora sobre estimadores, definiendo dos nuevos conceptos para ellos.

### Definición 10.4 - Estimador consistente

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$, se dice que $\hat\theta=\hat\theta(X_1,\ldots,X_n)$:

- Es un estimador débilmente consistente si y sólo si $\hat\theta\xrightarrow{P}\theta$
- Es un estimador fuertemente consistente si y sólo si $\hat\theta\xrightarrow[n]{c.s.}\theta$

En el caso de un estimador débilmente consistente, la notación nos dice que $\hat\theta$ está cada vez más cerca de $\theta$ en probabilidad a medida que aumenta el tamaño de la muestra $n$.

### Definición 10.5 - Estimador insesgado

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$, se dice que $\hat\theta=\hat\theta(X_1,\ldots,X_n)$:

- Es un estimador insesgado si y sólo si $E(\hat\theta)=\theta$
- Es un estimador asintóticamente insesgado si y sólo si $\lim_{n\to\infty}E(\hat\theta)=\theta$

#### Observación

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X\in L^1$, por ley fuerte de los grandes números, sabemos que $\overline{X_n}\xrightarrow[n]{c.s}\mu=E(X)$, lo cual nos dice que $\hat\mu=\overline{X_n}$ es un estimador fuertemente consistente de $\mu$.
Además sabemos que $E(\overline{X_n})=\mu$, lo que demuestra que el estimador también es insesgado.

Existe también un estimador natural para la varianza de $X$, que se verá en uno de los ejercicios del práctico.

## Métodos de estimación

Ya vamos que podemos estimar de manera fuertemente consistente e insesgada, a la esperanza y varianza de una variable aleatoria (ejercicio de práctico). Ahora ¿cómo se estima otro tipo de parámetros? Sería importante tener métodos que nos permitan obtener estimadores, por lo que veremos los dos más populares, el método de los momentos y el de máxima verosimilitud.

### Método de los momentos

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X\in L^k$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$ entonces se plantean las siguientes $k$ ecuaciones:

$$
\begin{cases}
E(X)=\overline{X_n}\\
E(X^2)=\frac{1}{n}\sum_{i=1}^nX_i^2\\
\quad\quad\quad\quad\vdots\\
E(X^k)=\frac{1}{n}\sum_{i=1}^nX_i^k\\
\end{cases}
$$

Observemos que las $k$ igualdades se pueden ver como un sistema de $k$ ecuaciones con $k$ incógnitas, donde las incógnitas son $\theta_1,\theta_2,\ldots,\theta_k$ que aparecen del lado izquierdo en las igualdades, ya que al depender de la distribución de $X$ de los parámetros $\theta_1,\theta_2,\ldots,\theta_k$, entonces sus momentos $E(X),E(X^2),\ldots,E(X^k)$ quedan en función de $\theta_1,\theta_2,\ldots,\theta_k$.

Se observa que este método está fuertemente basado en la ley de los grandes números, ya que la misma nos afirma que $\overline{X_n}$ converge casi seguramente a $E(X)$, $\frac{1}{n}\sum_{i=1}^nX_i^2$ converge casi seguramente a $E(X^2)$ y así sucesivamente.
Por este razonamiento, parece natural que si este sistema admite solución, entonces la misma se debería esperar que sea fuertemente consistente.

#### Ejemplo

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X\sim U(0,b)$, entonces para hallar el estimador por el método de los momentos planteamos un sistema de una sola ecuación, ya que hay un solo parámetro que estimar. Este es:

$$
E(X)=\overline{X_n}
$$

Al calcular la esperanza, la misma nos queda $\frac{b}{2}=\overline{X_n}$, por lo que el estimador por momentos de $b$ nos queda $\hat{b}=2\overline{X_n}$. Notemos que el estimador nos queda fuertemente consistente ya que:

$$
\overline{X_n}\xrightarrow[n]{c.s.}E(X)=\frac{b}{2}\quad\text{entonces: }2\overline{X_n}\xrightarrow[n]{c.s.}2\frac{b}{2}=b
$$

Además, es insesgado porque:

$$
E(\hat{b})=E(2\overline{X_n})=2E(\overline{X_n})=2\frac{b}{2}=b
$$

Bajo ciertas hipótesis de regularidad, se puede probar que el estimador de un parámetro $\theta=(\theta_1,\theta_2,\ldots,\theta_k)$ por momentos, en caso de existir, es fuertemente consistente y asintóticamente insesgado.