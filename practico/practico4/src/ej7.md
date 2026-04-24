# Ejercicio 07 - Distribuciones discretas

**Fecha:** 24-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

La distribución introducida en este ejercicio se denomina distribución hipergeométrica.

1. Se consideran los números naturales $N$, $D$ y $n$ tales que $N\geq D$. Sea también $A=\{0,1,\ldots,n\}$. Para $r>0$, se define $\binom{r}{s}=0$ si $s<0$ o si $s>r$.
   1. Probar que $$\sum_{k=0}^{n}\binom{N-D}{n-k}\binom{D}{k}=\binom{N}{n}$$ Sugerencia: observe que $(1+x)^N=(1+x)^{N-D}(1+x)^D$ y utilice el desarrollo de Newton $\left((1+x)^N=\sum_{n=0}^{\infty}\binom{N}{n}x^n\right)$ para hallar el coeficiente de $x^n$ a ambos lados de la igualdad.
   2. Probar que la función $p:A\to\mathbb{R}$ tal que $p(k)=\dfrac{\binom{N-D}{n-k}\binom{D}{k}}{\binom{N}{n}}$ con $k\in A$ define una probabilidad en $A$.

2. Una empresa quiere comprar cajas que contienen 40 herramientas cada una. El procedimiento de control de calidad de cada caja consiste en tomar una muestra de 5 herramientas al azar de dicha caja y rechazarla si se encuentra una herramienta defectuosa. Si la caja a inspeccionar tiene 3 defectuosas, ¿cuál es la probabilidad de rechazar la caja?

3. Ahora de un lote de 10 herramientas se seleccionan 4 al azar. Si el lote contiene 3 herramientas con defectos de fabricación, calcular la probabilidad de que:
   1. las 4 funcionen.
   2. al menos 2 no funcionen.
   3. sólo una funciona.
   4. por lo menos una funciona.

## Resolución

### Parte 1

- Se consideran los números naturales $N$, $D$ y $n$ tales que $N\geq D$. Sea también $A=\{0,1,\ldots,n\}$. Para $r>0$, se define $\binom{r}{s}=0$ si $s<0$ o si $s>r$.
   1. Probar que $$\sum_{k=0}^{n}\binom{N-D}{n-k}\binom{D}{k}=\binom{N}{n}$$ Sugerencia: observe que $(1+x)^N=(1+x)^{N-D}(1+x)^D$ y utilice el desarrollo de Newton $\left((1+x)^N=\sum_{n=0}^{\infty}\binom{N}{n}x^n\right)$ para hallar el coeficiente de $x^n$ a ambos lados de la igualdad.
   2. Probar que la función $p:A\to\mathbb{R}$ tal que $p(k)=\dfrac{\binom{N-D}{n-k}\binom{D}{k}}{\binom{N}{n}}$ con $k\in A$ define una probabilidad en $A$.

#### Subparte 1

- Probar que $$\sum_{k=0}^{n}\binom{N-D}{n-k}\binom{D}{k}=\binom{N}{n}$$ Sugerencia: observe que $(1+x)^N=(1+x)^{N-D}(1+x)^D$ y utilice el desarrollo de Newton $\left((1+x)^N=\sum_{n=0}^{\infty}\binom{N}{n}x^n\right)$ para hallar el coeficiente de $x^n$ a ambos lados de la igualdad.

Utilizaremos la sugerencia para operar y probar lo que mencionan en la letra.

$$
\begin{aligned}
&(1+x)^N=(1+x)^{N-D}(1+x)^D\\
&\iff\scriptstyle{(\text{binomio de Newton})}\\
&\sum^N_{n=0}\binom{N}{n}x^n=\sum^{N-D}_{i=0}\binom{N-D}{i}x^i\cdot\sum^{D}_{j=0}\binom{D}{j}x^j\\
&\iff\scriptstyle{(\text{comparando el coeficiente de }x^n\text{; se tiene que dar que }i+j=n)}\\
&\binom{N}{n}x^n=\binom{N-D}{n-j}\binom{D}{j}x^n\\
&\iff\scriptstyle{(\text{operatoria y cambio de variable})}\\
&\binom{N}{n}=\binom{N-D}{n-k}\binom{D}{k}\\
\end{aligned}
$$

Queda demostrada la igualdad de esta parte entonces.

#### Subparte 2

- Probar que la función $p:A\to\mathbb{R}$ tal que $p(k)=\dfrac{\binom{N-D}{n-k}\binom{D}{k}}{\binom{N}{n}}$ con $k\in A$ define una probabilidad en $A$.

Probaremos los dos axiomas relevantes para probabilidades en contextos discretos, es decir la no negatividad y la normalización.

##### No negatividad

Este axioma es bastante directo, tenemos un producto entre todos factores positivos:

- $\binom{N-D}{n-k}$ es siempre positivo por la definición de las combinaciones
- $\binom{D}{k}$ es siempre positivo por la definición de las combinaciones
- $\frac{1}{\binom{N}{n}}$ es siempre positivo por la definición de las combinaciones

Esto prueba que la función es siempre positiva.

##### Normalización

Queremos probar que la suma de todas las probabilidades individuales sean exactamente 1, expresemos la suma y operemos para demostrar que esto es cierto.

$$
\begin{aligned}
&\sum_{k=0}^n\frac{\binom{N-D}{n-k}\binom{D}{k}}{\binom{N}{n}}\\
&=\scriptstyle{(\text{sacando factores comunes de la sumatoria})}\\
&\frac{1}{\binom{N}{n}}\sum_{k=0}^n\binom{N-D}{n-k}\binom{D}{k}\\
&=\scriptstyle{(\text{resultado de la parte 1})}\\
&\frac{1}{\binom{N}{n}}\cdot\binom{N}{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&1
\end{aligned}
$$

Por lo tanto la función $p$ definida en esta parte efectivamente es una probabilidad para $A$

### Parte 2

Una empresa quiere comprar cajas que contienen 40 herramientas cada una. El procedimiento de control de calidad de cada caja consiste en tomar una muestra de 5 herramientas al azar de dicha caja y rechazarla si se encuentra una herramienta defectuosa. Si la caja a inspeccionar tiene 3 defectuosas, ¿cuál es la probabilidad de rechazar la caja?

Bueno, de forma similar al ejercicio anterior tenemos que identificar que rol cumple cada dato, vayamos uno a uno:

- $n=5$ el tamaño de la muestra de herramientas.
- $D=3$ es el número de herramientas defectuosas en la caja.
- $N=40$ la cantidad de herramientas que contiene cada caja.
- $X$ es nuestra variable aleatoria que cuenta cuántas herramientas defectuosas hay en la muestra de 5.

Entonces, lo que queremos calcular es $P(X\geq 1)$ para lo que podemos usar la propiedad del complemento para simplificar el cálculo:

- $P(X\geq 1)=1-P(X=0)$

Y esto lo podemos calcular simplemente usando la fórmula:

$$
\begin{aligned}
&P(X\geq 1)=1-P(X=0)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&P(X\geq 1)=1-p(3)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&P(X\geq 1)=1-\frac{\binom{40-3}{5}\binom{3}{0}}{\binom{40}{5}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\frac{\binom{37}{5}}{\binom{40}{5}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\frac{\frac{37!}{32!5!}}{\frac{40!}{35!5!}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\left(\frac{37!}{32!5!}\cdot\frac{35!5!}{40!}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\left(\frac{\cancel{37!}}{\cancel{32!}\cancel{5!}}\cdot\frac{35\cdot34\cdot33\cdot\cancel{(32)!}\cancel{5!}}{40\cdot39\cdot38\cdot\cancel{(37)!}}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\left(\frac{35\cdot34\cdot33}{40\cdot39\cdot38}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)=1-\left(\frac{7\cdot17\cdot11}{8\cdot13\cdot19}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)\approx1-0.66\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq 1)\approx0.34\\
\end{aligned}
$$

Entonces, la probabilidad de que se rechaze una caja, al encontrar al menos una herramienta defectuosa es aproximadamente $0.34$.

### Parte 3

- Ahora de un lote de 10 herramientas se seleccionan 4 al azar. Si el lote contiene 3 herramientas con defectos de fabricación, calcular la probabilidad de que:
   1. las 4 funcionen.
   2. al menos 2 no funcionen.
   3. sólo una funciona.
   4. por lo menos una funciona.

Bueno, de forma similar a la parte anterior tenemos que identificar que rol cumple cada dato, vayamos uno a uno:

- $n=4$ el tamaño de la muestra de herramientas.
- $D=3$ es el número de herramientas defectuosas en el lote.
- $N=10$ la cantidad de herramientas que contiene el lote.
- $X$ es nuestra variable aleatoria que cuenta cuántas herramientas defectuosas hay en la muestra de 4.

#### Subparte 1

- que las 4 funcionen.

Entonces lo que queremos calcular es la probabilidad de que no haya herramientas defectuosas, es decir queremos calcular $P(X=0)$.
Esto se hace directo con la fórmula:

$$
\begin{aligned}
&P(X=0)=p(0)\\
&\iff\scriptstyle{(\text{definición de }p)}\\
&P(X=0)=\frac{\binom{10-3}{4}\binom{3}{0}}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{\binom{7}{4}}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{\frac{7!}{4!3!}}{\frac{10!}{6!4!}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{\cancel{7!}}{\cancel{4!}\cancel{3!}}\cdot\frac{6\cdot5\cdot4\cdot\cancel{3!}\cancel{4!}}{10\cdot9\cdot8\cdot\cancel{7!}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{6\cdot5\cdot4}{10\cdot9\cdot8}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{6}{2\cdot9\cdot2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{6}{36}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=0)=\frac{1}{6}\\
\end{aligned}
$$

#### Subparte 2

- que al menos 2 no funcionen.

Entonces queremos calcular $P(X\geq2)$.
En este caso no podemos trabajar directo con la fórmula, nos conviene usar el complemento y separar por eventos disjuntos:

- $(X\geq2)^C=X\leq1$
- $(X\leq1)=(X=0)\cup(X=1)$

Entonces la probabilidad que buscamos es:

- $P(X\geq2)=1-P(X=0)-P(X=1)$

Operemos:

$$
\begin{aligned}
&P(X\geq2)=1-P(X=0)-P(X=1)\\
&\iff\scriptstyle{(\text{definición de }p)}\\
&P(X\geq2)=1-p(X=0)-p(X=1)\\
&\iff\scriptstyle{(\text{definición de }p)}\\
&P(X\geq2)=1-\frac{1}{6}-\frac{\binom{10-3}{4-1}\binom{3}{1}}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq2)=\frac{5}{6}-\frac{\binom{7}{3}}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq2)=\frac{5}{6}-\frac{1}{6}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq2)=\frac{2}{3}\\
\end{aligned}
$$

#### Subparte 3

- que sólo una funciona.

Entonces lo que queremos calcular es la probabilidad de que haya exactamente 3 herramientas defectuosas, es decir queremos calcular $P(X=3)$, pues entonces tendremos que una sola funciona.
En este caso podemos trabajar directamente con la fórmula.

$$
\begin{aligned}
&P(X=3)=p(3)\\
&\iff\scriptstyle{(\text{definición de }p)}\\
&P(X=3)=\frac{\binom{7}{1}\cdot\binom{3}{3}}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=3)=\frac{7}{\binom{10}{4}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X=3)=\frac{1}{30}\\
\end{aligned}
$$

#### Subparte 4

- que por lo menos una funciona.

Recordemos que tenemos una muestra de cuatro herramientas en total, donde hay solo tres herramientas defectuosas. Por lo tanto este evento siempre sucede, su probabilidad es $1$.

Esto concluye el ejercicio.