# Clase 09 - Cambio de variable

**Fecha:** 23-06-2026

## Esperanza de una función de variables discretas

En general, el proceso para calcular el valor esperado de una variable consiste en, primero hallar su f.p.p. y luego aplicar la definición. Sin embargo, cuando la variable de interés se escribe en función de otras, esto puede volverse un poco engorroso.

### Ejemplo

Se apuesta en el lanzamiento de dos dados de la siguiente manera: $Z=XY-10$, en donde $X$ e $Y$ son el resultado de cada uno de los dados. ¿Cuál es la ganancia esperada?
Como cada resultado tiene probabilidad $1/36$, la f.p.p. de $Z$ la podemos obtener usando la siguiente tabla:

![Figura 1](../img/clase9fig1.png)

Contando la aparición de cada uno de los valores del recorrido obtenemos:

![Figura 2](../img/clase9fig2.png)

Obtenemos la f.p.p. simplemente dividiendo cada uno de estos valores por $36$. A partir de esto podemos calcular la esperanza con la definición.

**Nota:** Lo calculamos usando que $E(Z)=\sum_{z\in R_Z}z\cdot p(z)$

Ignorando los calculos que son irrelevantes, llegamos a que $E(Z)=81/36=2.25$.

Esto se puede generalizar ampliamente. Si denotamos $g:\mathbb{R}^2\to\mathbb{R}$ la función $g(x,y)=xy-10$, entonces $Z=g(X,Y)$.

### Teorema

Sean $X$ e $Y$ dos variables aleatorias discretas, y $g:\mathbb{R}^2\to\mathbb{R}$ una función. Entonces

$$
E(g(X,Y))=\sum_{x\in R_X,y\in R_Y}g(x,y)p(x,y)
$$

Donde $p(x,y)$ es la f.p.p. conjunta de $X$ e $Y$.

#### Demostración

El recorrido de $Z=g(x,y)$ es el siguiente:

- $R_Z=\{g(x,y):x\in R_X, y\in R_Y\}$

Que es claramente numerable, por lo tanto $g(X,Y)$ también es discreta. Notemos que estos valores $g(x,y)$ se pueden repetir, de hecho esto sucedió bastante en el ejemplo 1.
Sin embargo, para cada valor posible $z$ de $g(x,y)$, el evento $\{g(X,Y)=z\}$ se descompone como la siguiente unión disjunta:

- $\{g(X,Y)=z\}=\bigcup_{g(x,y)=z}\{X=x, Y=y\}$

Que es básicamente la unión de todas las formas distintas de escribir $z$ como $g(x,y)$ para algún $x$ e $y$. Tomando probabilidades obtenemos:

- $P(g(X,Y)=z)=\sum_{g(x,y)=z}P(X=x,Y=y)$

Nos resta ahora aplicar la definición de esperanza, y contemplar todas las $z$ posibles:

$$
\begin{aligned}
&E(g(X,Y))\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{z\in R_Z}z\cdot P(g(X,Y)=z)\\
&=\scriptstyle{(\text{razonamiento anterior})}\\
&\sum_{z\in R_Z}z\cdot\sum_{g(x,y)=z}P(X=x,Y=y)\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{z\in R_Z}\sum_{g(x,y)=z}z\cdot P(X=x,Y=y)\\
&=\scriptstyle{(z=g(x,y))}\\
&\sum_{z\in R_Z}\sum_{g(x,y)=z}g(x,y)\cdot P(X=x,Y=y)\\
\end{aligned}
$$

Aquí viene un punto sutil de la demostración. Este consiste en notar que sumar en aquellos $x$ e $y$ con $g(x,y)=z$, y luego sumar todos los valores posibles de $z$, es lo mismo que sumar en todos los valores posibles de $x$ e $y$.
De aquí terminamos la igualdad anterior resultando que:

$$
E(g(X,Y))=\sum_{x\in R_X,y\in R_Y}g(x,y)\cdot p(x,y)
$$

Esto concluye la demostración. $\blacksquare$

## Esperanza de una función de variables continuas

Sean $X$ e $Y$ dos variables aleatorias continuas, y $g:\mathbb{R}^2\to\mathbb{R}$ una función. Entonces:

$$
E(g(X,Y))=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}g(x,y)p(x,y)dxdy
$$

Donde $p(x,y)$ es la densidad conjunta de $X$ e $Y$.

**Nota:** La demostración requiere de varios bloques relacionados a cambios de variable que si bien están en el teórico, no son necesarios para la resolución de los ejercicios del práctico. Asumiremos la fórmula como cierta para no generar dolores de cabeza innecesarios con temas que no se van a estar evaluando.

## Propiedades básicas de la esperanza

Veremos ahora un conjunto de propiedades básicas de la esperanza, la mayoría de las cuales deducidas de las fórmulas que vimos en esta clase para variables discretas y continuas respectivamente.

### Esperanza de la suma

Para $X,Y$ variables aleatorias cualesquiera, se cumple que:

- $E(X+Y)=E(X)+E(Y)$

#### Demostración

Tendremos que separar en dos casos, según si las variables son discretas o continuas.

**Si son discretas:**

Tomamos $g(x,y)=x+y$ en la siguiente fórmula:

- $E(g(X,Y))=\sum_{x\in R_X,y\in R_Y}g(x,y)p(x,y)$

Entonces, tenemos que:

$$
\begin{aligned}
&E(X+Y)\\
&=\scriptstyle{(g(x,y)=x+y)}\\
&\sum_{x\in R_X,y\in R_Y}(x+y)p(x,y)\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{x\in R_X,y\in R_Y}xp(x,y)+yp(x,y)\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{x\in R_X,y\in R_Y}xp(x,y)+\sum_{x\in R_X,y\in R_Y}yp(x,y)\\
&=\scriptstyle{(\text{operatoria})}\\
&\sum_{x\in R_X,y\in R_Y}xP(X=x,Y=y)+\sum_{x\in R_X,y\in R_Y}yP(X=x,Y=y)\\
\end{aligned}
$$

En este punto, notemos que si fijamos $x$, tenemos que $\sum_{y\in R_Y}P(X=x,Y=y)=P(X=x)$ para cualquier $x$ (esto es básicamente una suma como cuando calculamos las marginales). Entonces podemos reescribir la primer sumatoria de la siguiente forma:

$$
\begin{aligned}
&\sum_{x\in R_X,y\in R_Y}xP(X=x,Y=y)\\
&=\scriptstyle{(\text{propiedades de la sumatoria})}\\
&\sum_{x\in R_X}\sum_{y\in R_Y}xP(X=x,Y=y)\\
&=\scriptstyle{(\text{por la observación anterior})}\\
&\sum_{x\in R_X}xP(X=x)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&E(X)\\
\end{aligned}
$$

Se puede hacer un análisis análogo para el segundo término de la suma, por lo tanto podemos concluir que:

$$
\begin{aligned}
&E(X+Y)\\
&=\scriptstyle{(\text{análisis inicial})}\\
&\sum_{x\in R_X,y\in R_Y}xP(X=x,Y=y)+\sum_{x\in R_X,y\in R_Y}yP(X=x,Y=y)\\
&=\scriptstyle{(\text{razonamiento anterior})}\\
&E(X)+E(Y)
\end{aligned}
$$

Esto concluye la demostración para el caso donde son discretas, ahora veamos el caso en el que son continuas

**Si son continuas:**

Tomamos el mismo $g(x,y)=x+y$ pero ahora usamos la fórmula para variables aleatorias continuas:

- $E(g(X,Y))=\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}g(x,y)p(x,y)dxdy$

Con esto ya podemos operar para ver a que llegamos:

$$
\begin{aligned}
&E(X+Y)\\
&=\scriptstyle{(g(x,y)=x+y)}\\
&\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}(x+y)p(x,y)dxdy\\
&=\scriptstyle{(\text{propiedades de integrales})}\\
&\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}xp(x,y)dxdy+\int_{-\infty}^{+\infty}\int_{-\infty}^{+\infty}yp(x,y)dxdy\\
&=\scriptstyle{(\text{Fubini y propiedades de integrales})}\\
&\int_{-\infty}^{+\infty}x\left(\int_{-\infty}^{+\infty}p(x,y)dy\right)dx+\int_{-\infty}^{+\infty}y\left(\int_{-\infty}^{+\infty}p(x,y)dx\right)dy\\
&=\scriptstyle{(\text{distribuciones marginales en v.a. continuas})}\\
&\int_{-\infty}^{+\infty}xp(x)dx+\int_{-\infty}^{+\infty}yp(y)dy\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&E(X)+E(Y)
\end{aligned}
$$

Con esto queda demostrada la propiedad de la suma de esperanzas.

### Esperanza del producto

Si $X$ e $Y$ son dos v.a. independientes, entonces:

- $E(XY)=E(X)E(Y)$.

### Esperanza de una función de una variable discreta

Si $h:\mathbb{R}\to\mathbb{R}$ y $X$ es discreta, entonces:

- $E(h(X))=\sum_xh(x)p(x)$

### Esperanza de una función de variable continua

Si $h:\mathbb{R}\to\mathbb{R}$ y $X$ es continua, entonces $E(h(X))=\int_{-\infty}^{+\infty}h(x)p(x)dx$

### Constantes en la esperanza

Si $c$ es una constante, entonces $E(cX)=cE(X)$