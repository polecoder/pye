# Ejercicio 07 - Distribución conjunta. Variables independientes

**Fecha:** 08-06-2026
**Estado:** 🟡 Con ayuda

## Consigna

Se considera la siguiente función $f_{XY}:\mathbb{R}^2\to\mathbb{R}$:

$$f_{XY}(x,y)=\begin{cases}kxy & \text{si }x\in(0,4),\,y\in(1,5)\\0 & \text{en los otros casos}\end{cases}$$

1. Hallar $k$ para que $f_{XY}$ sea la función de densidad conjunta de dos variables aleatorias $X$, $Y$ absolutamente continuas.
2. Hallar las densidades (marginales) $f_X$ y $f_Y$.
3. Hallar la distribución conjunta $F_{XY}$ y las distribuciones (marginales) $F_X$ y $F_Y$.
4. ¿$X$ e $Y$ son independientes? Justifique la respuesta.
5. Calcular $P\{X\geq3,\,Y\leq2\}$ y $P\{X+Y>4\}$

## Recordatorio

Para este ejercicio necesitaremos resolver una integral doble. Por suerte trabajeremos con ejemplos relativamente sencillos, pero como no lo di en CDIVV es importante tener un paso a paso de como se hace.

**Paso 1 - Integral interior:** tratás la variable exterior como constante y resolvés normalmente.
**Paso 2 - Integral exterior:** sustituís el resultado y resolvés la segunda integral.

## Resolución

### Parte 1

- Hallar $k$ para que $f_{XY}$ sea la función de densidad conjunta de dos variables aleatorias $X$, $Y$ absolutamente continuas.

Para que la función $f_{XY}$ sea la densidad conjunta de $X$ e $Y$, tenemos que tener que la integral valga $1$. En particular en este caso podemos ignorar todas las regiones donde la función se anula, por lo que nos centramos en el rectángulo establecido por los valores posibles de $x$ e $y$. Queremos verificar que:

$$
\begin{aligned}
&\int_{0}^{4}\int_{1}^{5}kxy\ dydx=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\int_{0}^{4}\left[\frac{kxy^2}{2}\right]_1^5dx=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\int_{0}^{4}\frac{25kx-kx}{2}dx=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\int_{0}^{4}\frac{24kx}{2}dx=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\int_{0}^{4}12kx\ dx=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\left[\frac{12kx^2}{2}\right]_0^4=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\left[6kx^2\right]_0^4=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&96k=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&k=\frac{1}{96}\\
\end{aligned}
$$

### Parte 2

- Hallar las densidades (marginales) $f_X$ y $f_Y$.

De la misma forma que para las distribuciones discretas, sumábamos por fila y columna, en este caso integraremos respecto a la variable contraria, para sumar lo correspondiente a las filas y columnas en el caso de una distribución continua como esta. Entonces:

**Densidad marginal $f_X$:**

Integro respecto a $y$ en el intervalo que nos interesa, es decir $(1,5)$:

$$
\begin{aligned}
&f_X(x)=\int_{1}^{5}f_{XY}(x,y)dy\\
&\iff\scriptstyle{(\text{definición de }f_{XY})}\\
&f_X(x)=\int_{1}^{5}\frac{xy}{96}dy\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_X(x)=\frac{x}{96}\cdot\left[\frac{y^2}{2}\right]_1^5\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_X(x)=\frac{x}{96}\cdot\frac{25-1}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_X(x)=\frac{x}{96}\cdot\frac{24}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_X(x)=\frac{x}{96}\cdot12\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_X(x)=\frac{x}{8}\\
\end{aligned}
$$

**Densidad marginal $f_Y$:**

Integro respecto a $x$ en el intervalo que nos interesa, es decir $(0,4)$:

$$
\begin{aligned}
&f_Y(y)=\int_{0}^{4}f_{XY}(x,y)dx\\
&\iff\scriptstyle{(\text{definición de }f_{XY})}\\
&f_Y(y)=\int_{0}^{4}\frac{xy}{96}dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_Y(y)=\frac{y}{96}\cdot\left[\frac{x^2}{2}\right]_0^4\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_Y(y)=\frac{y}{96}\cdot\frac{16}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_Y(y)=\frac{y}{96}\cdot8\\
&\iff\scriptstyle{(\text{operatoria})}\\
&f_Y(y)=\frac{y}{12}\\
\end{aligned}
$$

### Parte 3

- Hallar la distribución conjunta $F_{XY}$ y las distribuciones (marginales) $F_X$ y $F_Y$.

Empecemos por las distribuciones marginales para las cuales solamente tenemos que integrar las densidades marginales que ya hallamos en la parte anterior:

**Distribución marginal $F_X$:**

$$
\begin{aligned}
&F_X(x)=\int_{0}^{x}\frac{u}{8}du\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_X(x)=\frac{1}{8}\cdot\left[\frac{u^2}{2}\right]_0^x\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_X(x)=\frac{1}{8}\cdot\frac{x^2}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_X(x)=\frac{x^2}{16}\\
\end{aligned}
$$

**Distribución marginal $F_Y$:**

$$
\begin{aligned}
&F_Y(y)=\int_{1}^{y}\frac{v}{12}dv\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_Y(y)=\frac{1}{12}\cdot\left[\frac{v^2}{2}\right]_1^y\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_Y(y)=\frac{1}{12}\cdot\frac{y^2-1}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_Y(y)=\frac{y^2-1}{24}\\
\end{aligned}
$$

**Distribución marginal $F_{XY}$:**

$$
\begin{aligned}
&F_{XY}(x,y)=\int_{0}^{x}\int_{1}^{y}\frac{uv}{96}\ dvdu\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\int_{0}^{x}\frac{u}{96}\cdot\left[\frac{v^2}{2}\right]_1^y\ du\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\int_{0}^{x}\frac{u}{96}\cdot\frac{y^2-1}{2}\ du\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\frac{y^2-1}{192}\cdot\int_{0}^{x}u du\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\frac{y^2-1}{192}\cdot\left[\frac{u^2}{2}\right]_0^x\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\frac{y^2-1}{192}\cdot\frac{x^2}{2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&F_{XY}(x,y)=\frac{x^2(y^2-1)}{384}\\
\end{aligned}
$$

### Parte 4

- ¿$X$ e $Y$ son independientes? Justifique la respuesta.

Recordemos que:

- $F_{XY}(x,y)=\frac{x^2(y^2-1)}{384}$
- $F_X(x)=\frac{x^2}{16}$
- $F_Y(y)=\frac{y^2-1}{24}$

Para que $X$ e $Y$ sean independientes, se tiene que cumplir que para todo par $x,y$ la siguiente igualdad es verdadera:

$$
\begin{aligned}
&F_{XY}(x,y)=^?F_X(x)\cdot F_Y(y)\\
&\iff\scriptstyle{(\text{reemplazando por las distribuciones conocidas})}\\
&\frac{x^2(y^2-1)}{384}=^?\frac{x^2}{16}\cdot\frac{y^2-1}{24}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{x^2(y^2-1)}{384}=^?\frac{x^2(y^2-1)}{384}\\
\end{aligned}
$$

Donde esto último es claramente cierto, por lo que concluimos que $X$ e $Y$ son variables independientes.

### Parte 5

- Calcular $P\{X\geq3,\,Y\leq2\}$ y $P\{X+Y>4\}$

Para la primer probabilidad podemos usar que $X$ e $Y$ son independientes, por lo que:

$$
\begin{aligned}
&P(X\geq3,Y\leq2)=P(X\geq3)\cdot P(Y\leq2)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq3,Y\leq2)=(1-P(X\leq3))\cdot P(Y\leq2)\\
&\iff\scriptstyle{(\text{reemplazando por las funciones conocidas})}\\
&P(X\geq3,Y\leq2)=\left(1-\frac{9}{16}\right)\cdot \frac{3}{24}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq3,Y\leq2)=\frac{7}{16}\cdot \frac{3}{24}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq3,Y\leq2)=\frac{21}{384}
\end{aligned}
$$

Ahora para la segunda, tenemos que trabajar un poco la desigualdad. Lo que queremos hacer es intersecar la región delimitada por la condición $X+Y>4$ con el rectángulo con el que venimos trabajando desde el inicio del ejercicio.

Veamos que un par $(x,y)$ que pertenezca a la intersección de estas regiones tiene que cumplir que:

- $x+y>4\implies y>4-x\implies 5>y>4-x$

Desde donde podemos despejar $x$:

- $5>4-x\implies x>-1$

De donde obtenemos que entonces no existen restricciones impuestas por la condición para $x$, se mantiene la región inicial:

- $4>x>0$

El tema es que para cuando $x>3$, tendremos que $1>4-x$, por lo que $y$ sale de su soporte.

**Nota:** No es necesario formalizar este razonamiento, pero es interesante ver el proceso mental al resolver el ejercicio, por eso lo dejo escrito.

Entonces para evitar partir la integral en dos, veamos que pasa si consideramos el complemento para facilitar el calculo. Tenemos que:

- $P(X+Y>4)=1-P(X+Y\leq4)$

Veamos entonces las condiciones que impone esto para un par $(x,y)$:

- $x+y\leq4\implies y\leq4-x\implies 1\leq y\leq4-x$
- $1\leq4-x\implies x\leq3\implies 0\leq x\leq3$

Por lo tanto con esto ya tenemos la región que queremos integrar, solamente resta operar.

$$
\begin{aligned}
&P(X+Y\leq 4)=\int_{0}^{3}\int_{1}^{4-x}\frac{xy}{96}\ dydx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\int_{0}^{3}\frac{x}{96}\int_{1}^{4-x}\ ydydx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\int_{0}^{3}\frac{x}{96}\cdot\left[\frac{y^2}{2}\right]_1^{4-x}dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\int_{0}^{3}\frac{x}{96}\cdot\frac{(4-x)^2-1}{2}dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\int_{0}^{3}\frac{x^3-8x^2+15x}{192}dx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\int_{0}^{3}x^3-8x^2+15xdx\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\left[\frac{x^4}{4}-\frac{8x^3}{3}+\frac{15x^2}{2}\right]^3_0\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\left(\frac{81}{4}-\frac{216}{3}+\frac{135}{2}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\left(\frac{81}{4}-\frac{216}{3}+\frac{270}{4}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\left(\frac{351}{4}-\frac{216}{3}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\left(\frac{1053-864}{12}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{1}{192}\cdot\frac{189}{12}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{189}{2304}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X+Y\leq 4)=\frac{21}{256}\\
\end{aligned}
$$

Recordemos que esta no es la región final para la que queremos saber la probabilidad, sino el complemento de esta, entonces:

- $P(X+Y>4)=1-P(X+Y\leq4)=1-\frac{21}{256}=\frac{235}{256}$

Esta es la probabilidad que queríamos hallar, lo que concluye el ejercicio.