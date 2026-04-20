# Ejercicio 05 - Probabilidad condicional

**Fecha:** 20-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

1. Se considera una caja que contiene 6 bolillas rojas, 4 blancas y 5 azules. Se extraen tres bolillas en forma sucesiva (sin reposición). Calcular la probabilidad que la primera sea roja, la segunda blanca y la tercera azul.

2. Se consideran dos cajas con bolas. La caja 1 contiene 3 bolas rojas y 2 azules, la caja 2 contiene 2 bolas rojas y 8 azules. Se lanza una moneda, si se obtiene cara se saca una bola de la caja 1, y si se obtiene cruz se saca una bola de la caja 2.
   1. Hallar la probabilidad que la bola extraída sea roja.
   2. Si se sabe que la bola extraída es roja, ¿cuál es la probabilidad que provenga de la caja 1?

## Resolución

### Parte 1

- Se considera una caja que contiene 6 bolillas rojas, 4 blancas y 5 azules. Se extraen tres bolillas en forma sucesiva (sin reposición). Calcular la probabilidad que la primera sea roja, la segunda blanca y la tercera azul.

Este ejercicio es bien sencillo. Simplemente aplicamos combinatoria partiendo desde el espacio muestral de bolillas:

- $|\Omega|=6+4+5=15$

En base a esto, tenemos que la probabilidad del evento $A$ descrito es:

- $P(A)=\frac{6}{15}\cdot\frac{4}{14}\cdot\frac{5}{13}=\frac{120}{2730}\approx0.04$

Lo que hace que este ejercicio sea de probabilidad condicional, es el cambio en el espacio muestral, pero no es nada que no hayamos visto antes.

### Parte 2

- Se consideran dos cajas con bolas. La caja 1 contiene 3 bolas rojas y 2 azules, la caja 2 contiene 2 bolas rojas y 8 azules. Se lanza una moneda, si se obtiene cara se saca una bola de la caja 1, y si se obtiene cruz se saca una bola de la caja 2.
   1. Hallar la probabilidad que la bola extraída sea roja.
   2. Si se sabe que la bola extraída es roja, ¿cuál es la probabilidad que provenga de la caja 1?

Para esta parte, llamemos de la siguiente forma a los siguientes eventos:

- $C:$ Se obtiene cara de la moneda
- $X:$ Se obtiene cruz de la moneda
- $R:$ Se extrae una bola roja

#### Subparte 1

- Hallar la probabilidad que la bola extraída sea roja.

Con esta nomenclatura, sabemos la probabilidad de algunos eventos, en particular de:

- $P(R\mid C)=\frac{3}{5}$ que es la probabilidad de sacar una bola roja de la caja uno (sale cara en la moneda).
- $P(R\mid X)=\frac{2}{10}=\frac{1}{5}$ que es la probabilidad de sacar una bola roja de la caja dos (sale cruz en la moneda).

Sabemos que estos dos casos son disjuntos (o sale cara o sale cruz), entonces podemos dividir en casos:

- $P(R)=P(R\cap X)+P(R\cap C)$

Y usando la regla del producto podemos operar, obteniendo:

$$
\begin{aligned}
&P(R)=P(R\cap X)+P(R\cap C)\\
&\iff\scriptstyle{(\text{regla del producto})}\\
&P(R)=P(X)\cdot P(R\mid X)+P(C)\cdot P(R\mid C)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&P(R)=\frac{1}{2}\cdot\frac{1}{5}+\frac{1}{2}\cdot\frac{3}{5}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(R)=\frac{1}{10}+\frac{3}{10}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(R)=\frac{4}{10}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(R)=\frac{2}{5}\\
\end{aligned}
$$

#### Subparte 2

- Si se sabe que la bola extraída es roja, ¿cuál es la probabilidad que provenga de la caja 1?

Recordemos que "extraer de la caja 1" básicamente significa que la moneda sea cara. Con esto en mente, queremos hallar la probabilidad del siguiente evento:

- $P(C\mid R)$ que es *la probabilidad de que salga cara, una vez que sabemos que la bola extraída es roja*.

Planteemos entonces la fórmula:

$$
\begin{aligned}
&P(C\mid R)=\frac{P(C\cap R)}{P(R)}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&P(C\mid R)=\frac{3/10}{2/5}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(C\mid R)=\frac{15}{20}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(C\mid R)=\frac{3}{4}\\
\end{aligned}
$$

Esto concluye el ejercicio.