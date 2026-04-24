# Ejercicio 06 - Distribuciones discretas

**Fecha:** 23-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

La distribución introducida en este ejercicio se denomina distribución binomial.

1. Se considera el natural $n\geq1$, $0<p<1$ y el conjunto $A=\{0,1,\ldots,n\}$. Probar que la función $p:A\to\mathbb{R}$ tal que $p(k)=\binom{n}{k}p^k(1-p)^{n-k}$ con $k\in A$ define una probabilidad en $A$. Sugerencia: utilizar el binomio de Newton.

2. La probabilidad de que una cierta clase de componente pase con éxito una determinada prueba de impacto es $3/4$. Hallar la probabilidad de que exactamente 2 de los siguientes 4 componentes que se prueban pasen la prueba.

3. El sistema electrónico de dirección de un cohete funciona correctamente con una probabilidad $p$ cuando se pone a funcionar. Se quiere instalar $n$ sistemas de respaldo independientes, pero idénticas, en el cohete de modo que la probabilidad de que al menos un sistema trabaje en forma correcta no sea menor que $0.99$. Hallar la cantidad $n$ de sistemas electrónicos de dirección que se necesitan para satisfacer los requerimientos si $p=0.9$ y si $p=0.8$.

## Resolución

### Parte 1

- Se considera el natural $n\geq1$, $0<p<1$ y el conjunto $A=\{0,1,\ldots,n\}$. Probar que la función $p:A\to\mathbb{R}$ tal que $p(k)=\binom{n}{k}p^k(1-p)^{n-k}$ con $k\in A$ define una probabilidad en $A$. Sugerencia: utilizar el binomio de Newton.

Para demostrar que la función mencionada es una probabilidad, queremos demostrar básicamente los axiomas de Kolgomorov, así que vayamos uno por uno.

#### No negatividad

Queremos probar que la función $p$ es no negativa para todo $k\in A$. Esto es directo ya que sin importar el valor de $k$, la función es la multiplicación de tres valores siempre positivos:

- $\binom{n}{k}$ es siempre positivo.
- $p^k$ es siempre positivo cuando $0<p<1$ que está establecido por letra.
- $(1-p)^{n-k}$ es siempre positivo pues $p<1$ también por letra

Por este motivo se cumple la no negatividad.

#### Normalización

Queremos probar que la suma de todas las probabilidades individuales sean exactamente 1, para esto recordemos la fórmula del binomio de Newton nos dice que:

$$
(a+b)^n=\sum_{k=0}^n\binom{n}{k}a^kb^{n-k}
$$

Notemos que al plantear la suma de las probabilidades para todos los elementos $k\in A$, obtenemos que:

$$
\sum_{k=0}^n\binom{n}{k}p^k(1-p)^{n-k}
$$

Que es lo mismo que la fórmula del binomio de Newton para $a=p$ y $b=1-p$, por lo tanto tenemos que:

$$
\begin{aligned}
&\sum_{k=0}^n\binom{n}{k}p^k(1-p)^{n-k}\\
&=\scriptstyle{(\text{binomio de Newton})}\\
&(p+1-p)^n\\
&=\scriptstyle{(\text{operatoria})}\\
&1^n\\
&=\scriptstyle{(\text{operatoria})}\\
&1\\
\end{aligned}
$$

#### Aditividad y continuidad

Al ser un modelo de probabilidad discreta, no necesitamos probar ninguno de estos axiomas ya que "vienen dados" por como definimos la probabilidad en casos discretos como este.

Con esto, concluimos que la función $p$ es una probabilidad en $A$.

### Parte 2

- La probabilidad de que una cierta clase de componente pase con éxito una determinada prueba de impacto es $3/4$. Hallar la probabilidad de que exactamente 2 de los siguientes 4 componentes que se prueban pasen la prueba.

Bueno esta parte se trata solamente de interpretar que valor va en que lugar de la fórmula que hallamos en la parte 1. Tenemos que:

- $n=4$
- $k=2$
- $p=3/4$

Por lo tanto, tenemos que:

$$
\begin{aligned}
&p(2)=\binom{4}{2}\cdot\left(\frac{3}{4}\right)^2\cdot\left(\frac{1}{4}\right)^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(2)=\frac{4!}{2!2!}\cdot\frac{9}{16}\cdot\frac{1}{16}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(2)=6\cdot\frac{9}{144}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(2)=\frac{54}{144}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(2)=\frac{13}{36}\\
\end{aligned}
$$

Esto concluye esta parte.

### Parte 3

- El sistema electrónico de dirección de un cohete funciona correctamente con una probabilidad $p$ cuando se pone a funcionar. Se quiere instalar $n$ sistemas de respaldo independientes, pero idénticas, en el cohete de modo que la probabilidad de que al menos un sistema trabaje en forma correcta no sea menor que $0.99$. Hallar la cantidad $n$ de sistemas electrónicos de dirección que se necesitan para satisfacer los requerimientos si $p=0.9$ y si $p=0.8$.

Queremos que la probabilidad de al menos un sistema trabaje sea mayor a $0.99$. Notemos que podemos usar el complemento, para determinar cuál es la probabilidad de que ningún sistema trabaje y luego usarlo para obtener la probabilidad que nos interesa. De este modo:

- $P(\text{al menos uno})=1-P(\text{ninguno funciona})$

La letra nos dice que los sistemas son **independientes**, esto es importante pues nos dice que la probabilidad de fallo de todos los sistemas, equivale a la probabilidad de fallo del producto de todos ellos. Con esto podemos afirmar que:

- $p$ es la probabilidad de que un sistema trabaje
- $1-p$ entonces es la probabilidad de que un sistema falle.
- Como tenemos $n$ sistemas, la probabilidad de que todos fallen es $(1-p)^n$


Con esto ya tenemos una fórmula para la probabilidad que nos interesa:

- $P(\text{al menos uno})=1-(1-p)^n$

Y como queremos que la probabilidad sea de al menos $0.99$:

- $1-(1-p)^n\geq 0.99$, es decir:
- $(1-p)^n\leq 0.01$

Operemos para obtener el resultado que buscamos:

$$
\begin{aligned}
&(1-p)^n\leq 0.01\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\log((1-p)^n)\leq\log(0.01)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&n\log(1-p)\leq\log(0.01)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&n\leq\frac{\log(0.01)}{\log(1-p)}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&n\leq\log(0.01-1+p)\\
\end{aligned}
$$
