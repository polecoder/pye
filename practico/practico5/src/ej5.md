# Ejercicio 05 - Variables aleatorias discretas

**Fecha:** 27-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

En pruebas de medición de distancia de frenado de automóviles, los vehículos que viajan a determinada velocidad tienden a recorrer distancias de frenado que están distribuidas uniformemente entre dos puntos $a$ y $b$. Calcular la probabilidad de que uno de estos automóviles:

1. se detenga más cerca de $a$ que de $b$.
2. se detenga de tal modo que la distancia a $a$ sea por lo menos 3 veces mayor que la distancia a $b$.

## Resolución

Como las distancias de frenado están distribuidas uniformemente entre los puntos $a$ y $b$, podemos definirlo con una función que justamente distribuya toda la probabilidad equitativamente en el intervalo $[a,b]$, esta función densidad es:

$$
f_X(x)=\begin{cases}
\frac{1}{b-a}&\text{si } a\leq x\leq b\\
0&\text{en otro caso}
\end{cases}
$$

Con esta información podemos trabajar en las siguientes partes.

### Parte 1

- que se detenga más cerca de $a$ que de $b$.

Queremos calcular $P(a\leq X<\frac{b+a}{2})$, es decir la probabilidad de que $X$ esté más cerca de $a$ que de $b$.
Esto lo hacemos simplemente integrando:

$$
\begin{aligned}
&P\left(a\leq X<\frac{b+a}{2}\right)=\int_{a}^{(b+a)/2}f_X(x)dx\\
&\iff\scriptstyle{(\text{definición de la función }f_X)}\\
&P\left(a\leq X<\frac{b+a}{2}\right)=\int_{a}^{(b+a)/2}\frac{1}{b-a}dx\\
&\iff\scriptstyle{(\text{regla de Barrow})}\\
&P\left(a\leq X<\frac{b-a}{2}\right)=\frac{(b+a)/2}{b-a}-\frac{a}{b-a}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P\left(a\leq X<\frac{b-a}{2}\right)=\frac{(b-a)/2}{b-a}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P\left(a\leq X<\frac{b-a}{2}\right)=\frac{1}{2}\\
\end{aligned}
$$

Lo cual tiene mucho sentido ya que la distribución es uniforme.

### Parte 2

- que se detenga de tal modo que la distancia a $a$ sea por lo menos 3 veces mayor que la distancia a $b$.

