# Clase 03 - Probabilidad condicional

**Fecha:** 20-04-2026

## Introducción a la probabilidad condicional y dependencia

En la teoría de la probabilidad, la incertidumbre no es un valor estático; se transforma dinámicamente ante la presencia de nueva información. El concepto fundamental que articula este cambio es la **reducción del espacio muestral**. Cuando sabemos que un evento $B$ ha ocurrido, los resultados que ocurren fuera de $B$ dejan de ser posibles, y nuestro universo de análisis se contrae de $\Omega$ a $B$.

Consideremos el experimento de las tres cartas. Tenemos tres cartas diferentes, una roja en ambos lados $(RR)$, otra roja en un lado y blanca en el otro $(RB)$, y la última blanca en ambos lados $(BB)$.
Queremos estudiar la probabilidad que hay de que el lado de la carta que da a la mesa sea rojo, sabemos que hay tres lados rojos y tres lados blancos, por lo que la probabilidad de que salga rojo es $1/2$ sin información adicional.

Si elegimos una carta al azar y observamos que el lado superior es rojo, la situación cambia. Nuestro espacio muestral en este caso se reduciría a los tres lados rojos, de los cuales ambos dos lados de la carta $(RR)$ cumplirían con que el reverso de la carta sería rojo. Por lo tanto una vez hecha la observación del lado superior, la probabilidad cambia a $2/3$.

## Definición formal y normalización

Para dos eventos cualesquiera $A$ y $B$ en un espacio muestral $\Omega$, definimos la probabilidad de $A$ dado $B$ como:

$$
\begin{aligned}
&P(A\mid B)=\frac{P(A\cap B)}{P(B)}
\end{aligned}
$$

Esta definición es válida solamente si $P(B)>0$.
Desde el rigor matemático, esta fórmula representa una normalización. Al ocurrir $B$, todos los resultados en $B^C$ adquieren probabilidad cero. Para que la nueva medida de probabilidad siga sumando uno, los valores de probabilidad de los eventos dentro de $B$ deben reescalarse proporcionalmente por el factor $1/P(B)$. De este modo, $P(B)$ actúa como la nueva unidad de medida del espacio reducido.

## Propiedades axiomáticas de la probabilidad condicional

Es fundamental comprender que la probabilidad condicional $P(\cdot\mid B)$ no es meramente un cálculo derivado, sino una **medida de probabilidad genuina** que satisface los axiomas de Kolmogorov sobre el espacio muestral reducido.

### Demostraciones

$(*_1)$ **Certidumbre del nuevo espacio:** $P(\Omega\mid B)=1$

$$
\begin{aligned}
P(\Omega\mid B)=\frac{P(\Omega\cap B)}{P(B)}=\frac{P(B)}{P(B)}=1
\end{aligned}
$$

$(*_2)$ **Aditividad para eventos incompatibles:** Si $A_1,A_2,\ldots,A_n$ es una sucesión de eventos disjuntos dos a dos $(A_i\cap A_j)=\emptyset$, entonces $A_i\cap B$ también son disjuntos.

$$
\begin{aligned}
&P(\bigcup A_n\mid B)\\
&=\scriptstyle{(\text{definición de probabilidad condicional})}\\
&\frac{P(\bigcup A_n\cap B)}{P(B)}\\
&=\scriptstyle{(\text{propiedades de conjuntos})}\\
&\frac{P(\bigcup (A_n\cap B))}{P(B)}\\
&=\scriptstyle{(\text{por Axiomas de Kolgomorov})}\\
&\frac{\sum P(A_i\cap B)}{P(B)}\\
&=\scriptstyle{(\text{definición de probabilidad condicional})}\\
&\sum P(A_i\mid B)
\end{aligned}
$$

$(*_3)$ **Probabilidad del complemento:**

$$
\begin{aligned}
&P(A^C\mid B)\\
&=\scriptstyle{(\text{definición de probabilidad condicional})}\\
&\frac{P(A^C\cap B)}{P(B)}\\
&=\scriptstyle{(\text{propiedades de conjuntos})}\\
&\frac{P(B\setminus A)}{P(B)}\\
&=\scriptstyle{(\text{pro   piedades de conjuntos})}\\
&\frac{P(B)-P(A\cap B)}{P(B)}\\
&=\scriptstyle{(\text{operatoria})}\\
&1-P(A\mid B)
\end{aligned}
$$

Además de esta última, todas las que ya hemos visto son válidas al cumplirse los axiomas de Kolmogorov.

## Regla del producto

Reordenando la definición de probabilidad condicional, obtenemos la **regla del producto**, que permite calcular la probabilidad de la ocurrencia simultánea de eventos:

- $P(A\cap B)=P(B)P(A\mid B)$

### Ejemplo

Si extraemos dos cartas de un mazo de $52$ cartas (donde hay $13$ cartas de cada palo), la probabilidad de que ambas sean picas $(S_1\cap S_2)$ es:

$$
\begin{aligned}
&P(S_1\cap S_2)\\
&=\scriptstyle{(\text{por la regla del producto})}\\
&P(S_1)\cdot P(S_2\mid S_1)\\
&=\scriptstyle{(\text{cambiando cada probablidad por su valor})}\\
&\frac{13}{52}\cdot\frac{12}{51}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{4}\cdot\frac{12}{51}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{3}{51}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{17}\\
\end{aligned}
$$

Este resultado es el mismo que obtendríamos usando combinatoria.

## Independencia de eventos

Decimos que dos eventos $A$ y $B$ son independientes si la ocurrencia de uno, no altera la ocurrencia del otro. Podemos decir esto usando la probabilidad condicional:

- $P(A\mid B)=P(A)$

Esto nos deja con la siguiente condición (usando la fórmula de probabilidad condicional):

- $P(A\cap B)=P(A)P(B)$

Por lo tanto, si esta última igualdad no se cumple, podemos afirmar que los eventos son dependientes.