# Clase 13 - Ley de los grandes números y estimación

**Fecha:** 30-06-2026

## Ley de los grandes números (LGN)

La ley de los grandes números es uno de los teoremas fundamentales de la probabilidad y la estadística. Establece que, a medida que aumenta el número de repeticiones de un experimento aleatorio, el promedio de los resultados observados tiende a acercarse al valor esperado de la variable aleatoria que describe ese experimento.

Dicho de manera intuitiva: si lanzamos una moneda muchas veces, la proporción de caras tenderá a estabilizarse cerca de $0.5$, aunque en unas pocas tiradas pueda haber desviaciones considerables.

### Formulación general

Sean $X_1,\ldots,X_n$ una secuencia de variables aleatorias iid, todas con la misma esperanza $\mu=E(X_i)$ y varianza $\sigma^2=Var(X_i)$. Se define la media muestral como:

$$
\overline{X_n}=\frac{1}{n}\sum_{i=1}^nX_i
$$

La ley de los grandes números afirma que $\overline{X_n}$ converge a $\mu$ cuando $n\to\infty$. Sin embargo, existen dos versiones diferentes de este resultado, según el tipo de convergencia que se considere.

### Ley débil de los grandes números

Establece que la media muestral converge en probabilidad a la media poblacional (es decir al valor esperado real):

$$
\boxed{
\lim_{n\to\infty}P(|\overline{X_n}-\mu|>\varepsilon)=0\quad\forall\varepsilon>0
}
$$

Esto significa que, para cualquier margen de error $\varepsilon$ que se elija, la probabilidad de que el promedio muestral se aleje de la media verdadera más que ese margen, se vuelve arbitrariamente pequeña a medida que $n$ crece.
Es una convergencia "en probabilidad": no garantiza que la desviación nunca ocurra, sino que se vuelve cada vez más improbable.

Hay otra formulación alternativa de la ley que simplemente consiste en tomar el complemento:

$$
\boxed{
\lim_{n\to\infty}P(|\overline{X_n}-\mu|<\varepsilon)=1\quad\forall\varepsilon>0
}
$$

Es decir que, para cualquier margen de error $\varepsilon$ que se elija, la probabilidad de que el promedio muestral se acerque a la media verdadera más que ese margen, se vuelve arbitrariamente grande a medida que $n$ crece.

#### Demostración

Probaremos la primera versión que enunciamos, siendo la segunda un equivalente.
Calculemos la varianza de $\overline{X_n}$ para poder utilizar la desigualdad de Chebyshev.

$$
\begin{aligned}
&Var(\overline{X_n})\\
&=\scriptstyle{(\text{definición de }\overline{X_n})}\\
&Var\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de varianza e independencia de las }X_i)}\\
&\frac{1}{n^2}\left(\sum_{i=1}^nVar(X_i)\right)\\
&=\scriptstyle{(\text{pues }Var(X_i)=\sigma^2)}\\
&\frac{1}{n^2}\cdot n\sigma^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{\sigma^2}{n}\\
\end{aligned}
$$

Recordemos que la desigualdad de Chebyshev dice que para todo $\varepsilon>0$ se cumple:

$$
P(|X-\mu|\geq\varepsilon)\leq\frac{\sigma^2}{\varepsilon^2}
$$

Ahora simplemente apliquemoslo a nuestro caso utilizando la varianza que recién calculamos.

$$
\begin{aligned}
&P(|X-\mu|\geq\varepsilon)\leq\frac{\sigma^2}{\varepsilon^2}\\
&=\scriptstyle{(\text{reemplazando con lo que queremos probar})}\\
&P(|\overline{X_n}-\mu|\geq\varepsilon)\leq\frac{\sigma^2}{n\varepsilon^2}\\
&=\scriptstyle{(\text{haciendo tender }n\text{ a infinito})}\\
&\lim_{n\to\infty}P(|\overline{X_n}-\mu|\geq\varepsilon)\leq0\\
\end{aligned}
$$

Y como $P$ es una probabilidad, necesariamente el menor o igual tiene que ser un igual. Esto concluye la demostración. $\blacksquare$

### Ley fuerte de los grandes números

Antes de definir que es la ley fuerte de los grandes números, vayamos por un resultado intermedio que nos da una forma alternativa del enunciado de la ley.

#### Convergencia casi segura

Sea una sucesión de v.a. $X_1,\ldots,X_n$ y $a\in\mathbb{R}$. Decimos que $X_n$ converge casi seguramente a $a$ si se cumple que:

$$
\{X_n\}_{n\in N}\xrightarrow[n]{c.s.}a\iff P(\{X_n\to a\})=1
$$

#### Continuación

Este es un resultado más potente. Establece que la media muestral converge casi seguramente (probabilidad 1) a la media poblacional.

$$
\boxed{
P\left(\lim_{n\to\infty}\overline{X_n}=\mu\right)=1
}
$$

Podemos usar el concepto de convergencia casi segura para dar un enunciado alternativo:

$$
\boxed{
\overline{X_n}\xrightarrow[n]{c.s}\mu
}
$$

En definitiva lo que significa es que, salvo en un conjunto de casos con probabilidad nula, la trayectoria completa de promedios muestrales efectivamente converge al valor $\mu$, no solo que la probabilidad de desviarse se reduzca (como en el caso de la ley débil).

No demostraremos este teorema pues no aparece en las notas.

## Estadísticos y estimadores

Cuando $X_1,X_2,\ldots X_n$ son variables aleatorias i.i.d. con distribución como la de cierta $X$, se dice que $X_1,X_2,\ldots,X_n$ es una **muestra aleatoria simple (o M.A.S.)** de tamaño $n$ de $X$.
En estadística aplicada, es frecuente encontrarse con números $x_1,x_2,\ldots,x_n$ producto de un muestreo sobre alguna característica de cierta población, por ejemplo, ingreso de los hogares de cierta ciudad, diámetro de las células de cierta población observada al microscopio, altura o peso de ciertos animales, etc. En todas estas situaciones, de la variable a estudiar, no se conoce su distribución, por lo que interesa manipular la información que nos brinda la muestra $x_1,x_2,\ldots,x_n$ para poder estimar diversos parámetros de interés.

### Definición 10.1 - Estadístico

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ para un determinado $n$, se le llama estadístico a la función $T(X_1,\ldots,X_n):\Omega\to \mathbb{R}^{k}$ para cierto $k$, donde $T:\mathbb{R}^n\to\mathbb{R}^k$ es una v.a. que no depende de parámetros desconocidos.

**Nota:** Se pide que no depende de parámetros desconocidos para que dada una muestra $x_1,\ldots,x_n$ el valor $T(x_1,\ldots,x_n)$ pueda ser utilizado para estimar parámetros desconocidos por ejemplo.

### Definición 10.2 - Estadística paramétrica

Si $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$. Al conjunto $\Theta$ se le denomina **espacio paramétrico**.

Vemos que en este caso la distribución de $X$ es completamente conocida, salvo por un parámetro $\theta$. En esta situación se dice que estamos en **estadística paramétrica**, mientras que si la distribución de $X$ es totalmente desconocida, estamos en presencia de **estadística no paramétrica**.

### Definición 10.3 - Estimador

Sean $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$.
Se dice que $\hat{\theta}:\Omega\to\Theta$ es un estimador de $\theta$ si y sólo si $\hat{\theta}(X_1,\ldots,X_n)$ es un **estadístico** que puede usarse para "estimar" el verdadero valor de $\theta$.

En general, para abreviar nos referiremos a $\hat{\theta}(X_1,\ldots,X_n)$ como $\hat{\theta}$.
Observemos que $\hat{\theta}$ depende de $n$ y es importante tener un estimador que cumpla propiedades de convergencia al verdadero valor de $\theta$ cuando el tamaño de muestra $n$ tiende a infinito.