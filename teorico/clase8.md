# Clase 08 - Valor esperado

**Fecha:** 09-06-2026

## Intuición de valor esperado

En probabilidad y estadística, el valor esperado (o esperanza) es el promedio a largo plazo de los resultados posibles de un experimento aleatorio.
En otras palabras, si realizaramos el mismo experimento aleatorio "infinitas veces", el valor esperado indica el resultado promedio que obtendríamos.

El concepto varía (como la mayoría de los conceptos del curso) según que índole tienen las variables aleatorias con las que trabajamos, veremos la distinción a continuación.

## Definición para variables discretas

Supongamos que $X$ es una variable discreta cuyos valores posibles son $R_X=\{x_1,x_2,\ldots\}$. Imaginemos que realizamos el experimento $n$ veces, y para cada una de ellas registramos el valor de $X$.
Llamemos a estos valores por $y_1,y_2,\ldots,y_n$. Cada uno de los $y_i$ puede ser igual a cualquiera de los valores posibles de $X$, o sea los valores del recorrido $R_X$.

El promedio de las $n$ realizaciones de $X$ es:

$$
\text{Promedio}(y_1,\ldots,y_n)=\frac{y_1+\ldots+y_n}{n}
$$

Por otra parte, podemos reordenar los valores $y_1,\ldots,y_n$ (que pueden repetirse) y agruparlos según su valor en términos del conjunto $R_X$, de modo que la suma:

$$
y_1+\ldots+y_n=n_1x_1+n_2x_2+\ldots
$$

Donde $n_j$ corresponde a la cantidad de veces que ha ocurrido el valor $x_j$. Con esta forma de escribir la suma, tenemos que:

$$
\text{Promedio}(y_1,\ldots,y_n)=x_1\left(\frac{n_1}{n}\right)+x_2\left(\frac{n_2}{n}\right)+\ldots
$$

Al realizar más veces el experimento, y hacer que $n$ tienda a infinito, las frecuencias relativas convergen a:

$$
\frac{n_j}{n}\to P(X=x_j)
$$

Con esto estamos en condiciones de dar la definición formal para variables aleatorias discretas.

### Definición de valor esperado (o esperanza)

Sea $X$ una variable aleatoria cuyo recorrido es $R_X$. Definimos el valor esperado de $X$ como

$$
E(X)=\sum_{x\in R_X}x\cdot P(X=x)
$$

## Variables de Bernoulli

Las variables de Bernoulli son los bloques fundamentales a partir de los cuales podemos construir una gran variedad de variables discretas. Las variables Bernoulli indican la ocurrencia o no de un determinado evento de interés. En general se usa la palabra "éxito" para indicar que el evento ocurre, y "fracaso" para indicar que no ocurre.
Decimos que una variable $X$ tiene distribución de Bernoulli si:

$$
X=\begin{cases}
1&\text{si éxito;}\\
0&\text{si fracaso}\\
\end{cases}
$$

Para conocer la distribución de la variable $X$, basta determinar el parámetro $p$, que representa la probabilidad de éxito, esto es $P(X=1)=p$. Escribimos que $X$ tiene distribución Bernoulli de parámetro $p$ de la siguiente forma: $X\sim Ber(p)$.
La esperanza de una variable Bernoulli es

$$
E(X)=1\cdot P(X=1)+0\cdot P(X=0)=p
$$

Esta fórmula tan simple es de mucha ayuda,ya que en muchas situaciones podemos descomponer una variable como suma de Bernoulli. Veamos un ejemplo típico.

### Ejemplo

En un grupo de $n$ personas distintas. ¿Cuántas coincidencias de cumpleaños esperamos ver?
Imaginemos a las personas numeradas de $1$ hasta $n$. Para cada par de personas $\{i,j\}$, consideremos la variable $X_{ij}$ que vale $1$ si $i$ y $j$ cumplen el mismo día, o $0$ en caso contrario.
Claramente $X_{ij}$ es una variable de Bernoulli, pues toma solamente los valores $0$ y $1$. Podemos calcular el parámetro $p$ de $X_{ij}$, que corresponde a la probabilidad de que valga $1$:

$$
\begin{aligned}
p&=P(X_{ij}=1)\\
&=P(i\text{ y }j\text{ cumplen el mismo día})\\
&=\frac{1}{365}
\end{aligned}
$$

Por lo tanto, $X_{ij}\sim Ber(1/365)$.
Llamemos $X$ a la suma de las $X_{ij}$ sobre todos los pares posibles. Esto es

$$
X=\sum_{\{i,j\}}X_{ij}
$$

De esta forma, $X$ cuenta la cantidad de coincidencias de cumpleaños que hay en el grupo de $n$ personas. Así que la probabilidad de que al menos dos personas cumplan el mismo día puede escribirse como $P(X\geq1)$.

Aceptemos por un momento que la esperanza de una suma, es la suma de sus esperanzas (lo demostraremos en la siguiente clase). Entonces el valor esperado de $X$ es:

$$
E(X)=\sum_{\{i,j\}}E(X_{ij})=\sum_{\{i,j\}}\frac{1}{365}=C_2^n\cdot\frac{1}{365}=\frac{n(n-1)}{730}
$$

Notar que $E(X)\geq1$ si $n=28$. Esto sugiere que con $28$ personas es altamente probable que haya al menos una coincidencia.

## Valor esperado de variables continuas

Veamos ahora como trasladar este concepto a las variables aleatorias continuas. Imaginemos que dividimos la recta real en intervalos de longitud $\Delta x_k$ centrados en puntos $x_k$. Llamemos $X_0$ a la variable discreta que vale $x_k$ cuando $X$ cae en el intervalo centrado en $x_k$ (de largo $\Delta x_k$). Notar que la probabilidad de que $X_0$ valga $x_k$ es apróximadamente igual a $p(x_k)\Delta x_k$.

La esperanza de $X_0$ es por definición:

$$
E(X_0)=\sum_k x_k\cdot P(X_0=x_k)=\sum_k x_k\cdot p(x_k)\Delta x_k
$$

Si los intervalos $\Delta x_k$ son todos pequeños, entonces la suma es aproximádamente igual a la integral de $x\cdot p(x)$.
En base a esto, definimos la esperanza de una variable continua $X$ con densidad $p(x)$ como:

$$
\int_{-\infty}^{+\infty}x\cdot p(x)dx
$$

### Ejemplo

- Dos puntos se eligen al azar de manera uniforme e independiente en un segmento de longitud unidad, y dividen al segmento en tres piezas. ¿Cuál es la longitud promedio del segmento izquierdo?

Llamemos $X$ e $Y$ a las coordenadas de los dos puntos en el intervalo $[0,1]$. El segmento izquierdo es el que va desde $0$ hasta $Z=\min\{X,Y\}$ y su longitud es precisamente $Z$. Debemos hallar la densidad de $Z$.

En la siguiente figura, se muestra el evento $\{z\leq Z\leq z+dz\}$, que en definitiva representa el evento en el que $Z$ cae en el intervalo $[z,z+dz]$ de largo $dz$.

![Figura 1](../img/clase8fig1.png)

El área de este evento es:

$$
\begin{aligned}
&A\{z\leq Z\leq z+dz\}\\
&=\scriptstyle{(\text{basado en la figura})}\\
&(1-z)^2-(1-z-dz)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\cancel{1}-\cancel{2z}+\cancel{z^2}-\cancel{1}+\cancel{z}+dz+\cancel{z}-\cancel{z^2}-zdz+dz-zdz-(dz)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&(2-2z)dz-(dz)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&2(1-z)dz-(dz)^2\\
\end{aligned}
$$

Luego la densidad de $Z$ (para $0<z>1$) está dada por:

$$
p(z)=\lim_{dz\to0}\frac{P(z\leq Z\leq z+dz)}{dz}=\lim_{dz\to0}2(1-z)-dz=2(1-z)
$$

Entonces la esperanza de $Z$ es:

$$
\begin{aligned}
&E(Z)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\int_{0}^{1}zp(z)dz\\
&=\scriptstyle{(\text{definición de }p(z))}\\
&2\int_{0}^{1}z(1-z)dz\\
&=\scriptstyle{(\text{operatoria})}\\
&2\int_{0}^{1}z-z^2dz\\
&=\scriptstyle{(\text{operatoria})}\\
&2\left[\frac{z^2}{2}-\frac{z^3}{3}\right]_0^1\\
&=\scriptstyle{(\text{operatoria})}\\
&2\cdot\frac{1}{6}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{3}\\
\end{aligned}
$$

## Una fórmula para variables positivas

Cuando trabajamos con variables enteras y positivas, existe una fórmula que a veces simplifica las cuentas.

Sea $X$ una variable discreta que toma valores enteros mayores o iguales a cero. Entonces:

- $E(X)=\sum_{k=0}^{+\infty}P(X>k)$

**Demostración:**

Por definición tenemos que:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{k=0}^{+\infty}kP(X=k)\\
&=\scriptstyle{(\text{pues el primer término es }0)}\\
&\sum_{k=1}^{+\infty}kP(X=k)\\
\end{aligned}
$$

Podemos poner estos términos en un arreglo triangular:

$$
\begin{aligned}
E(X)&=P(X=1)\\
&=P(X=2)+P(X=2)\\
&=P(X=3)+P(X=3)+P(X=3)+\cdots\\
\end{aligned}
$$

Al sumar las columnas, obtenemos:

- $E(X)=P(X>0)+P(X>1)+P(X>2)+\cdots=\sum_{k=0}^{+\infty}P(X>k)$

Que es lo que queríamos probar. $\blacksquare$

### Variable continua positiva

Veamos (sin tanto detalle) el caso de una variable continua siempre positiva.

Sea $X$ una variable aleatoria mayor o igual a cero. Entonces:

- $E(X)=\int_{0}^{+\infty}(1-F(x))dx$

Este resultado es análogo al que tenemos para las variables discretas (recordando las propiedades que  teníamos para las probabilidades usando la función de distribución acumulada).