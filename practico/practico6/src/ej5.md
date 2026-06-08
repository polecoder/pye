# Ejercicio 05 - Distribución conjunta. Variables independientes

**Fecha:** 26-05-2026
**Estado:** 🟢 Resuelto solo

## Consigna

1. Sean $X$ e $Y$ dos variables aleatorias cuya distribución conjunta es

    $$F_{XY}(x,y)=\begin{cases}1 & \text{si }x\geq1,\,y\geq1\\y & \text{si }y\in[0,1),\,x\geq y\\x & \text{si }x\in[0,1),\,y\geq x\\0 & \text{en los otros casos}\end{cases}$$

   Hallar las distribuciones marginales $F_X$ y $F_Y$.

2. Sean $X$ e $Y$ dos variables aleatorias cuya distribución conjunta es

    $$F_{XY}(x,y)=\begin{cases}1 & \text{si }x\geq1,\,y\geq1\\y & \text{si }x\geq1,\,y\in[0,1)\\x & \text{si }x\in[0,1),\,y\geq1\\xy & \text{si }x\in[0,1),\,y\in[0,1)\\0 & \text{en los otros casos}\end{cases}$$

   Hallar la distribución (marginal) $F_X$ y la distribución (marginal) $F_Y$.

3. Si $X$ e $Y$ son variables aleatorias, ¿las distribuciones marginales $F_X$ y $F_Y$ determinan la distribución conjunta $F_{XY}$? ¿En qué caso $F_X$ y $F_Y$ determinan la distribución conjunta?

## Resolución

### Parte 1

- Sean $X$ e $Y$ dos variables aleatorias cuya distribución conjunta es

    $$F_{XY}(x,y)=\begin{cases}1 & \text{si }x\geq1,\,y\geq1\\y & \text{si }y\in[0,1),\,x\geq y\\x & \text{si }x\in[0,1),\,y\geq x\\0 & \text{en los otros casos}\end{cases}$$

    Hallar las distribuciones marginales $F_X$ y $F_Y$.

Hasta ahora, trabajamos con casos discretos y teniendo la función de distribución puntual.
En esta parte tenemos la función de distribución acumulada. Si queremos los marginales tenemos que hacer algo similar a lo que hicimos en los casos anteriores que eran discretos: fijar una de las dos variables y sumar todos los valores de la otra.
En este caso lo hacemos con el límite por la naturaleza continua del problema, obteniendo:

- $F_X(x)=\lim_{y\to\infty}F_{XY}(x,y)$
- $F_Y(y)=\lim_{x\to\infty}F_{XY}(x,y)$

Por lo que llegados a esta conclusión, solo tenemos que hallar los límites:

**Distribución marginal $F_X$**

$$
\begin{aligned}
&F_X(x)=\lim_{y\to\infty}F_{XY}(x,y)\\
&\iff\scriptstyle{(\text{definición de }F_{XY})}\\
&F_X(x)=\begin{cases}
0&\text{si }x<0\\
x&\text{si }x\in[0,1)\\
1&\text{si }x\geq1
\end{cases}
\end{aligned}
$$

**Distribución marginal $F_Y$**

$$
\begin{aligned}
&F_Y(y)=\lim_{x\to\infty}F_{XY}(x,y)\\
&\iff\scriptstyle{(\text{definición de }F_{XY})}\\
&F_Y(y)=\begin{cases}
0&\text{si }y<0\\
y&\text{si }y\in[0,1)\\
1&\text{si }y\geq1
\end{cases}
\end{aligned}
$$

Esto concluye esta parte.

### Parte 2

- Sean $X$ e $Y$ dos variables aleatorias cuya distribución conjunta es

    $$F_{XY}(x,y)=\begin{cases}1 & \text{si }x\geq1,\,y\geq1\\y & \text{si }x\geq1,\,y\in[0,1)\\x & \text{si }x\in[0,1),\,y\geq1\\xy & \text{si }x\in[0,1),\,y\in[0,1)\\0 & \text{en los otros casos}\end{cases}$$

   Hallar la distribución (marginal) $F_X$ y la distribución (marginal) $F_Y$.

Esta parte es análoga a la anterior, procedemos de la misma forma:

**Distribución marginal $F_X$**

$$
\begin{aligned}
&F_X(x)=\lim_{y\to\infty}F_{XY}(x,y)\\
&\iff\scriptstyle{(\text{definición de }F_{XY})}\\
&F_X(x)=\begin{cases}
0&\text{si }x\leq0\\
x&\text{si }x\in[0,1)\\
1&\text{si }x\geq 1
\end{cases}
\end{aligned}
$$

**Distribución marginal $F_Y$**

$$
\begin{aligned}
&F_Y(y)=\lim_{x\to\infty}F_{XY}(x,y)\\
&\iff\scriptstyle{(\text{definición de }F_{XY})}\\
&F_Y(y)=\begin{cases}
0&\text{si }y\leq0\\
y&\text{si }y\in[0,1)\\
1&\text{si }y\geq 1
\end{cases}
\end{aligned}
$$

Esto concluye esta parte.

### Parte 3

- Si $X$ e $Y$ son variables aleatorias, ¿las distribuciones marginales $F_X$ y $F_Y$ determinan la distribución conjunta $F_{XY}$? ¿En qué caso $F_X$ y $F_Y$ determinan la distribución conjunta?

La respuesta a esta pregunta se encuentra en la teoría básicamente. Sabemos que la distribución conjunta $F_{XY}$ va a estar dada por $F_X$ y $F_Y$ solamente si $X$ e $Y$ son independientes.

Y por definición, esto sucede solamente si $F_{XY}(x,y)=F_X(x)\cdot F_Y(y)$.
Los dos ejemplos que vimos en este ejercicio sirven para visualizar esto.

1. La primera distribución conjunta $F_{XY}$ no está determinada por las distribuciones marginales, pues $X$ e $Y$ no son independientes en este caso.
2. La segunda distribución conjunta $F_{XY}$ está determinada por las distribuciones marginales, pues en todos los casos $F_{XY}(x,y)=F_X(x)\cdot F_Y(y)$

Esto concluye el ejercicio