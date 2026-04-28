# Ejercicio 07 - Variables aleatorias continuas

**Fecha:** 28-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

1. En la densidad normal estándar, encuentre el área bajo la curva que está:
   1. a la derecha de $z=1.84$.
   2. entre $z=-1.97$ y $z=0.86$.

2. Si $Z\sim N(0,1)$, encuentre los valores de $k$ de tal forma que:
   1. $P(Z>k)=0.3015$
   2. $P(k<Z<-0.18)=0.4197$

3. En una distribución normal con $\mu=40$ y $\sigma=6$, encuentre el valor de $x$ que tiene:
   1. $45\%$ del área a la izquierda.
   2. $14\%$ del área a la derecha.

## Resolución

### Parte 1

- En la densidad normal estándar, encuentre el área bajo la curva que está:
   1. a la derecha de $z=1.84$.
   2. entre $z=-1.97$ y $z=0.86$.

#### Subparte 1

- a la derecha de $z=1.84$.

Esto es $P(Z\geq1.84)$. Para este caso podemos usar que la integral entera suma uno, por lo que:

- $P(Z\geq1.84)=1-P(Z\leq1.84)$

Y $P(Z\leq1.84)$ es un valor que tenemos en la tabla de la distribución normal, por lo que:

$$
\begin{aligned}
&P(Z\geq1.84)=1-P(Z\leq1.84)\\
&\iff\scriptstyle{(\text{valores de la distribución normal})}\\
&P(Z\geq1.84)=1-0.9671\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(Z\geq1.84)=0.0329\\
\end{aligned}
$$

Esto concluye la subparte 1.

#### Subparte 2

- entre $z=-1.97$ y $z=0.86$.

Esto es $P(-1.97\leq Z\leq0.86)$. Recordemos que por propiedades de las funciones de distribución acumulada, tenemos que:

- $P(-1.97\leq Z\leq0.86)=\Phi(0.86)-\Phi(-1.97)$

Donde $\Phi$ es la letra que representa a la f.d.a. para la distribución normal.

$$
\begin{aligned}
&P(-1.97\leq Z\leq0.86)=\Phi(0.86)-\Phi(-1.97)\\
&\iff\scriptstyle{(\text{valores de la distribución normal y propiedades})}\\
&P(-1.97\leq Z\leq0.86)=0.8051-(1-\Phi(1.97))\\
&\iff\scriptstyle{(\text{valores de la distribución normal})}\\
&P(-1.97\leq Z\leq0.86)=0.8051-(1-0.9756)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-1.97\leq Z\leq0.86)=0.8051-0.0244\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(-1.97\leq Z\leq0.86)=0.7807\\
\end{aligned}
$$

Esto concluye la subparte 2.

### Parte 2

- Si $Z\sim N(0,1)$, encuentre los valores de $k$ de tal forma que:
   1. $P(Z>k)=0.3015$
   2. $P(k<Z<-0.18)=0.4197$

**Nota:** Que $Z\sim N(0,1)$ significa que estamos trabajando con la distribución normal estándar. En la parte tres veremos las consecuencias de que esto no pase.

#### Subparte 1

- $P(Z>k)=0.3015$

Recordemos la propiedad que usamos en la primera parte, usando que la integral suma en total 1, con esto la probabilidad que queremos calcular es:

- $P(Z>k)=1-P(Z\leq k)$

Y con esto podemos ya podemos usar la tabla:

$$
\begin{aligned}
&P(Z>k)=1-P(Z\leq k)\\
&\iff\scriptstyle{(\text{sabiendo que }P(Z>k)=0.3015)}\\
&0.3015=1-P(Z\leq k)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(Z\leq k)=1-0.3015\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(Z\leq k)=0.6985\\
\end{aligned}
$$

Y ahora queremos hallar $k$ para que esto sea cierto en la tabla:

- $k=0.52$

Esto concluye la subparte 1.

#### Subparte 2

- $P(k<Z<-0.18)=0.4197$

Recordemos que por propiedades de las funciones de distribución acumulada, tenemos que:

- $P(k<Z<-0.18)=\Phi(-0.18)-\Phi(k)$

Ahora operemos para despejar $\Phi(k)$:

$$
\begin{aligned}
&P(k<Z<-0.18)=\Phi(-0.18)-\Phi(k)\\
&\iff\scriptstyle{(\text{propiedades de }\Phi)}\\
&P(k<Z<-0.18)=1-\Phi(0.18)-\Phi(k)\\
&\iff\scriptstyle{(\text{valores de distribución normal})}\\
&P(k<Z<-0.18)=1-0.5714-\Phi(k)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(k<Z<-0.18)=0.4286-\Phi(k)\\
&\iff\scriptstyle{(\text{usando que }P(k<Z<-0.18)=0.4197)}\\
&0.4197=0.4286-\Phi(k)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\Phi(k)=0.4286-0.4197\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\Phi(k)=0.0089\\
\end{aligned}
$$

Como vemos este es un valor muy pequeño... Y no figura en la tabla, pero esto tiene sentido pues no aparecen los valores negativos, y $k$ claramente lo es. Recordemos entonces que:

- $\Phi(-k)=1-\Phi(k)$

Por lo tanto, $\Phi(-k)=1-0.0089=0.9911$, y este valor si estará en la tabla, de donde sacamos que:

- $k=-2.37$

Esto concluye la subparte 2.

### Parte 3

- En una distribución normal con $\mu=40$ y $\sigma=6$, encuentre el valor de $x$ que tiene:
   1. $45\%$ del área a la izquierda.
   2. $14\%$ del área a la derecha.

Para esta parte, necesitamos la introducción de algunos conceptos más "teóricos" sobre la distribución normal. Lo que sucede es que a veces la distribución está ligeramente modificada por dos parámetros.

- **Media $\mu$:** Representa el valor de $x$ donde está ubicado el centro de la campana.
- **Desviación $\sigma$:** Es el valor que ajusta el "ancho" de la campana.

Pero claro... Al cambiar estos valores la tabla que tenemos ya no sirve por si sola. Tendremos que hacer un proceso llamado desestandarización, que básicamente consiste en entender que:

- $Z=\frac{X-\mu}{\sigma}$

Y entonces podremos hallar cualquier valor de $X$ despejando:

- $X=\sigma Z+\mu$

Donde $X$ representa la variable aleatoria medida por la distribución normal con los parámetros $\sigma$ y $\mu$, mientras que $Z$ es la variable aleatoria medida por la distribución normal con los parámetros estándar.
Con esto estamos en condiciones de encarar el ejercicio.

#### Subparte 1

- $45\%$ del área a la izquierda.

Esto es $P(X\leq x)=0.45$. Nos interesa hallar el $x$ que cumpla con esto, pero no podemos hacerlo directamente. Como vimos en la previa a las subpartes, primero hallaremos el valor para la distribución normal estándar, y luego lo ajustaremos para encontrar el $x$.

Recordemos que como la probabilidad es menor que $0.5$, no hallaremos la probabilidad en la tabla, entonces trabajamos con el complemento:

- $\Phi(-z)=1-\Phi(z)=0.55$

Utilizando la tabla, llegamos a que el valor aproximado de $z$ es $-0.13$.
Ahora tendríamos que estandarizar, para esto utilizamos la fórmula que vimos anteriormente:

$$
\begin{aligned}
&x=\sigma z+\mu\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&x=6\cdot(-0.13)+40\\
&\iff\scriptstyle{(\text{operatoria})}\\
&x=-0.78+40\\
&\iff\scriptstyle{(\text{operatoria})}\\
&x=39.22\\
\end{aligned}
$$

#### Subparte 2

- $14\%$ del área a la derecha.

Esto es $P(X\geq x)=0.14$ de la misma forma que antes, buscaremos primero el $z$ que cumpla con esto.
En este caso el valor si figura directamente en la tabla:

- $P(Z\geq z)=0.14$

La tabla nos dice que $z=2.2$, ajustando mediante la estandarización podemos hallar $x$:

$$
\begin{aligned}
&x=\sigma z+\mu\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&x=6\cdot1.08+40\\
&\iff\scriptstyle{(\text{operatoria})}\\
&x=6.48+40\\
&\iff\scriptstyle{(\text{operatoria})}\\
&x=46.48\\
\end{aligned}
$$