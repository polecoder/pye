# Clase 06 - Variables aleatorias discretas

**Fecha:** 21-04-2026

## Introducción y definición de variable aleatoria

En el análisis de sistemas complejos, como el crecimiento de la planta leguminosa *Onobrychis viciifolia*, los ingenieros enfrentamos fenómenos donde el azar surge de una multiplicidad de factores (genéticos, climáticos y edafológicos). Resulta analíticamente inviable describir de forma exhaustiva el espacio muestral $(\Omega)$ que contenga todas las posibilidades "historias" de desarrollo de cada espécimen.

La **variable aleatoria (v.a.)** surge como la herramienta fundamental para modelar estos experimentos sin requerir un conocimiento absoluto de $\Omega$. Actúa como una función que traduce resultados experimentales en valores numéricos procesables. Desde una perspectiva de ingeniería, este concepto es vital para la transición de señales analógicas (continuas) a representaciones digitales (discretas) mediante el redondeo y la cuantización.

### Definición formal

Una variable aleatoria es una función $X:\Omega\to\mathbb{R}$ que asigna un número real $X(\omega)$ a cada resultado elemental $\omega\in\Omega$
Es importante también para las variables aleatorias, que propiedades cumple el recorrido de la función $R_X$. Decimos que **una función $X$ es una variable aleatoria discreta** si su recorrido $R_X$ es **numerable**.

En el ejemplo mencionado en las notas de las alturas de las plantas Onobrychis viciifolia, aunque la altura es intrínsecamente continua, la medición redondeada a centímetros la convierte en una variable discreta con $R_X=\{14,16,17,\ldots,32\}$.
La frecuencia relativa de cada valor constituye nuestra primera aproximación empírica a su distribución.

## Función de probabilidad puntual

La distribución de una variable aleatoria discreta queda unívocamente determinada por su **función de probabilidad puntual (f.p.p.)** denotada $p(x)$ o $p_X(x)$, y queda definida como:

- $p(x)=P(X=x)$

Donde $(X=x)$ es un evento que significa *la función $X$ vale $x$*. En definitiva $p(x)$ vale la probabilidad de que $X$ valga $x$ para todo $x$ en el dominio.

### Probabilidades y condiciones de existencia

Para que una función $p(x)$ sea una f.p.p válida, debe satisacer las siguientes condiciones necesarias y suficientes:

1. $0\leq p(x)\leq 1$ para todo $x\in\mathbb{R}$
2. $\sum_{x\in R_X}p(x)=1$

### Ejemplo

Consideremos el ejemplo de lanzar dos dados equilibrados y definir una variable aleatoria que devuelve el máximo de los dos resultados:

- $M(i,j)=\max\{i,j\}$

Por ejemplo, si sacas $(3,5)$, el máximo es $5$, i.e. $M(3,5)=5$.
Podemos representar la f.p.p. analíticamente o mediante una tabla de valores:

|  $x$     |   $1$    |   $2$    |   $3$    |   $4$    |   $5$    |   $6$    |
| -------- | ------ | ------ | ------ | ------ | ------ | ------ |
|**f.p.p** | $1/36$ | $3/36$ | $5/36$ | $7/36$ | $9/36$ | $11/36$ |

Gráficamente, la f.p.p. se visualiza mediante diagramas de barras o puntos, donde la altura de la barra en el punto $x$ del soporte es exactamente $p(x)$.

## Función de distribución acumulada

La **función de distribución acumulada (f.d.a.)** de una variable aleatoria $X$ es la función $X:\mathbb{R}\to[0,1]$ definida por:

- $F(x)=P(X\leq x)$

La función lleva este nombre porque $F(x)$ da la probabilidad acumulada al sumar las probabilidades $p(y)$ con $y\leq x$.
Notemos que el signo es menor o igual, esto es fundamental para no confundir los cálculos y excluir el punto por error.

### Ejemplo

Volviendo al caso anterior de los dados, podemos agregar a la tabla el valor de la f.d.a.

|  $x$     |   $1$    |   $2$    |   $3$    |   $4$    |   $5$    |   $6$    |
| -------- | ------ | ------ | ------ | ------ | ------ | ------ |
|**f.p.p** | $1/36$ | $3/36$ | $5/36$ | $7/36$ | $9/36$ | $11/36$ |
|**f.d.a** | $1/36$ | $4/36$ | $9/36$ | $16/36$ | $25/36$ | $36/36$

### Propiedades axiomáticas

Todo f.d.a. debe cumplir con los siguientes axiomas:

- **Monotonía:** Es no decreciente. Si $x\leq y$ entonces $F(x)\leq F(y)$
- **Límites en el infinito:** $\lim_{x\to-\infty}F(x)=0$ y $\lim_{x\to+\infty}F(x)=1$
- **Continuidad por derecha:** En cada punto $x$, se cumple que $\lim_{y\to x^+}F(y)=F(x)$
- **Saltos y probabilidad puntual:** El valor del "salto" vertical en la gráfica en un punto $x$ es exactamente la probabilidad $P(X=x)$. Si no hay salto (la función es continua en ese punto), la probabilidad puntual es cero. Además el límite por izquierda es:
    
    - $\lim_{y\to x^-}F(y)=P(X<x)$

## Distribución conjunta e independencia

Cuando estudiamos dos variables $X$ e $Y$ simultáneamente, definimos **la función de probabilidad conjunta**:

- $p(x,y)=P(X=x,Y=y)$

A partir de una tabla de contingencia, podemos calcular las **distribuciones marginales** $p_X(x)$ y $p_Y(y)$ se obtienen sumando los valores de las filas y las columnas respectivamente.

### Ejemplo

Consideremos un ejemplo para poder interpetar mejor este concepto. Queremos considerar la distribución aleatoria de tres bolas distinguibles en tres celdas también distinguibles.
El espacio muestral consiste en $3^3=27$ elementos, por lo que cada resultado tiene probabilidad $1/27$. Consideraremos las siguientes variables aleatorias:

- $N$ el número de celdas ocupadas.
- $X$ el número de bolas en la primer celda.
- $Y$ el número de bolas en la segunda celda.

Las distribuciones respectivas de $N,X$ e $Y$ son:

![Figura 1](../img/clase6fig1.png)

Tenemos un tema con este cuadro, que es que no nos proporciona información suficiente para calcular, por ejemplo, la probabilidad de que $\{X=1\}$ y $\{Y=2\}$. Aquí interviene la distribución conjunta de las variables, esto lo hacemos con una *tabla de contingencia* como se muestra a continuación:

![Figura 2](../img/clase6fig2.png)

Con lo que tenemos las probabilidades que estabamos buscando al principio.

### Independencia

Dos variables son independientes si y solo si la probabilidad conjunta es el producto de sus marginales:

- $p_{X,Y}(x,y)=p_X(x)\cdot p_Y(y)$

Este concepto es básicamente el mismo que estudiamos cuando estudiamos la probabilidad condicional.

## Aritmética con variables aleatorias

Las variables aleatorias pueden operarse aritméticamente. Un caso frecuente es calcular la f.p.p. de una suma $S=X+Y$ de variables independientes.

El método más efectivo es la **tabla de contingencia y sumas diagonales**. Si construimos una tabla donde las filas son los valores de $X$ y las columnas los de $Y$, las celdas interiores contienen la probabilidad conjunta (producto de marginales por independencia). 
Para hallar $P(X+Y=s)$ sumamos todas las celdas ubicadas en la **diagonal** donde la suma de los índices $x+y$ sea igual a $s$. Este procedimiento agrupa todos los eventos del espacio muestral que satisfacen la condición de la suma total.