# Ejercicio 04 - Probabilidad condicional

**Fecha:** 20-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se consideran los eventos $A$ y $B$ tales que

1. $P(A)=\frac{1}{2}$, $P(B)=\frac{1}{3}$ y $P(A\cap B)=\frac{1}{4}$. Calcular
   1. $P(A\mid B)$
   2. $P(B\mid A)$
   3. $P(A^C\mid B)$
   4. $P(B^C\mid A)$
   5. $P(A^C\mid B^C)$
   6. $P(B^C\mid A^C)$

2. $P(A)=\frac{3}{8}$, $P(B)=\frac{5}{8}$ y $P(A\cup B)=\frac{3}{4}$. Calcular
   1. $P(A\mid B)$
   2. $P(B\mid A)$

3. $B\subseteq A$. Calcular $P(A\mid B)$

4. $A$ y $B$ son disjuntos (o excluyentes), esto es $A\cap B=\emptyset$. Suponiendo $P(B)\neq0$, calcular $P(A\mid B)$. ¿Son $A$ y $B$ independientes? ¿Qué pasa si $P(B)=0$?

## Resolución

### Parte 1

- $P(A)=\frac{1}{2}$, $P(B)=\frac{1}{3}$ y $P(A\cap B)=\frac{1}{4}$. Calcular

    1. $P(A\mid B)$
    2. $P(B\mid A)$
    3. $P(A^C\mid B)$
    4. $P(B^C\mid A)$
    5. $P(A^C\mid B^C)$
    6. $P(B^C\mid A^C)$

Las primeras cuatro probabilidades se calculan directamente:

1. $P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{1}{4}\cdot3=\frac{3}{4}$
2. $P(B\mid A)=\frac{P(A\cap B)}{P(A)}=\frac{1}{4}\cdot2=\frac{2}{4}=\frac{1}{2}$
3. $P(A^C\mid B)=1-P(A\mid B)=1-\frac{3}{4}=\frac{1}{4}$
4. $P(B^C\mid A)=1-P(B\mid A)=1-\frac{1}{2}=\frac{1}{2}$

Para las subpartes cinco y seis, necesitamos algo más. En particular necesitamos saber cuánto vale $P(A^C\cap B^C)$.
Para esto tendremos presente la siguiente observación que viene de las leyes de De Morgan (se puede deducir con un diagrama simple):

- $(A^C\cap B^C)=(A\cup B)^C$

Entonces si calculamos $A\cup B$, podemos obtener $(A\cup B)^C$ que es importante para el cálculo de la probabilidad que nos piden.

- $P(A\cup B)=P(A)+P(B)-P(A\cap B)=\frac{1}{2}+\frac{1}{3}-\frac{1}{4}=\frac{5}{6}-\frac{1}{4}=\frac{7}{12}$

Y por lo tanto, usando la regla del complemento:

- $P((A\cup B)^C)=1-P(A\cup B)=1-\frac{7}{12}=\frac{5}{12}$

Sumando a esto, necesitamos también las probabilidades individuales de los complementos:

- $P(A^C)=1-\frac{1}{2}=\frac{1}{2}$
- $P(B^C)=1-\frac{1}{3}=\frac{2}{3}$

Y ahora si, podemos calcular las probabilidades que nos piden la parte 5 y 6:

5. $P(A^C\mid B^C)=\frac{P(A^C\cap B^C)}{P(B^C)}=\frac{5}{12}\cdot\frac{3}{2}=\frac{15}{24}=\frac{5}{8}$
6. $P(B^C\mid A^C)=\frac{P(A^C\cap B^C)}{P(A^C)}=\frac{5}{12}\cdot2=\frac{10}{12}=\frac{5}{6}$

Esto concluye la parte 1.

### Parte 2

- $P(A)=\frac{3}{8}$, $P(B)=\frac{5}{8}$ y $P(A\cup B)=\frac{3}{4}$. Calcular
   1. $P(A\mid B)$
   2. $P(B\mid A)$

Esta parte tiene una muy pequeña dificultad agregada, necesitamos conocer $P(A\cap B)$, lo que podemos hacer con la propiedad de inclusión-exclusión antes de calcular las probabilidades.

$$
\begin{aligned}
&P(A\cup B)=P(A)+P(B)-P(A\cap B)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\frac{3}{4}=\frac{3}{8}+\frac{5}{8}-P(A\cap B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{3}{4}-1=-P(A\cap B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(A\cap B)=\frac{1}{4}
\end{aligned}
$$

Y ahora si, podemos obtener las probabilidades que nos solicitan:

1. $P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{1}{4}\cdot\frac{8}{5}=\frac{8}{20}=\frac{2}{5}$
2. $P(B\mid A)=\frac{P(A\cap B)}{P(A)}=\frac{1}{4}\cdot\frac{8}{3}=\frac{8}{12}=\frac{2}{3}$

Esto concluye la parte 2.

### Parte 3

- $B\subseteq A$. Calcular $P(A\mid B)$

Si $B\subseteq A$, entonces $P(A\cap B)=P(B)$.Con esto en mente:

- $P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{P(B)}{P(B)}=1$

Este razonamiento es independiente de quienes son $A$ y $B$.
Esto concluye la parte 3.

### Parte 4

- $A$ y $B$ son disjuntos (o excluyentes), esto es $A\cap B=\emptyset$. Suponiendo $P(B)\neq0$, calcular $P(A\mid B)$. ¿Son $A$ y $B$ independientes? ¿Qué pasa si $P(B)=0$?

Recordemos que $P(\emptyset)=0$, por lo tanto al utilizar la fórmula tenemos que:

- $P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{0}{P(B)}=0$

Como vemos, es fundamental que $P(B)\neq0$, si esto no fuera cierto entonces estamos dividiendo por cero. Por lo tanto esta propiedad no se cumple en dicho caso.