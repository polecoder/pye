# Ejercicio 08 - Probabilidad condicional

**Fecha:** 21-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se admite que entre los jugadores profesionales de ping pong un $5\%$ consume anfetaminas antes de cada partido. Durante un campeonato se les toma una muestra de orina a todos los jugadores. La muestra de cada jugador se divide en dos submuestras iguales a las que se les aplica un análisis clínico: si el resultado de aplicar el análisis a las dos submuestras da positivo, el jugador es sancionado; en cualquier otro caso el jugador no es sancionado.

Considere los eventos:

- $A_1=\{\text{el resultado de la primera submuestra es positivo}\}$
- $A_2=\{\text{el resultado de la segunda submuestra es positivo}\}$
- $B=\{\text{el jugador es sancionado}\}$
- $D=\{\text{el jugador consumió anfetaminas}\}$

Se asume que los eventos $A_1$ y $A_2$ condicionados a los eventos $D$ y a $D^c$ son independientes, esto es: $P(A_1\cap A_2|D)=P(A_1|D)P(A_2|D)$ y $P(A_1\cap A_2|D^c)=P(A_1|D^c)P(A_2|D^c)$.

Se sabe además que $P(A_i|D)=0.90$ y $P(A_i|D^c)=0.02$ para $i=1,2$.

1. Calcule $P(D|A_1)$, esto es, la probabilidad de que un jugador haya consumido anfetaminas dado que el resultado de la primera submuestra es positivo.
2. Calcule $P(B)$, esto es, la probabilidad de que un jugador sea sancionado. ¿Son $A_1$ y $A_2$ eventos independientes?
3. Calcule $P(D|B)$, esto es, la probabilidad de que un jugador sancionado haya consumido anfetaminas.

## Resolución

### Parte 1

- Calcule $P(D|A_1)$, esto es, la probabilidad de que un jugador haya consumido anfetaminas dado que el resultado de la primera submuestra es positivo.

Empecemos aplicando la fórmula de probabilidad condicional a lo que queremos hallar:

- $(*_1)\ P(D\mid A_1)=\frac{P(D\cap A_1)}{P(A_1)}$

A partir de esto, notemos que podemos hallar $P(D\cap A_1)$ si lo despejamos de la fórmula de la probabilidad condicional para $P(A_1\mid D)$ que ya conocemos su valor $0.90$:

$$
\begin{aligned}
&P(A_1\mid D)=\frac{P(A_1\cap D)}{P(D)}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&0.90=\frac{P(A_1\cap D)}{0.05}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.90\cdot0.05=P(A_1\cap D)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.045=P(A_1\cap D)\\
\end{aligned}
$$

Como la intersección de conjuntos es conmutativa, tenemos que:

- $P(D\cap A_1)=0.045$

Llegados a este punto, necesitamos hallar $P(A_1)$, no hay muchos caminos para hacerlo, de hecho creo que la siguiente observación nos lleva al único posible:

- $A_1=(A_1\cap D)\cup(A_1\cap D^C)$

Donde ambos eventos que componenen a $A_1$ son disjuntos (claramente), por lo que podemos usar aditividad:

- $(*_2)\ P(A_1)=P(A_1\cap D)+P(A_1\cap D^C)$

Y entonces nos faltaría hallar $P(A_1\cap D^C)$, que por suerte es bastante sencillo aplicando la fórmula de probabilidad condicional para $P(A_1\mid D^C)$:

$$
\begin{aligned}
&P(A_1\mid D^C)=\frac{P(A_1\cap D^C)}{P(D^C)}\\
&\iff\scriptstyle{(\text{reemplazando valores conocidos})}\\
&0.02=\frac{P(A_1\cap D^C)}{0.95}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.02\cdot0.95=P(A_1\cap D^C)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.019=P(A_1\cap D^C)\\
\end{aligned}
$$

Ahora podemos volver a $*_2$ y despejar para obtener $P(A_1)$:

- $P(A_1)=0.045+0.019=0.064$

Y ahora conocemos todo lo que necesitamos para volver a $*_1$ y calcular lo que necesitamos:

$$
\begin{aligned}
&P(D\mid A_1)=\frac{P(D\cap A_1)}{P(A_1)}\\
&\iff\scriptstyle{(\text{reemplazando por los valores conocidos})}\\
&P(D\mid A_1)=\frac{0.045}{0.064}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(D\mid A_1)\approx0.703
\end{aligned}
$$

Esto concluye esta parte.

### Parte 2

- Calcule $P(B)$, esto es, la probabilidad de que un jugador sea sancionado. ¿Son $A_1$ y $A_2$ eventos independientes?

Para empezar, notemos que $B=A_1\cap A_2$, es decir que el resultado de las dos muestras es positivo. Recordemos que:

- $P(A_1\cap A_2|D)=P(A_1|D)P(A_2|D)$ y
- $P(A_1\cap A_2|D^c)=P(A_1|D^c)P(A_2|D^c)$

Sumado a esto, observemos que:

- $(*_3)\ A_1\cap A_2=(A_1\cap A_2\cap D)\cup(A_1\cap A_2\cap D^C)$

Esto nos da todos los ingredientes para calcular $A_1\cap A_2$, pues podemos plantear la fórmula de probabilidad condicional para $P(A_1\cap A_2\mid D)$ y $P(A_1\cap A_2\mid D)$ respectivamente:

**Paso #1:** Calcular $P(A_1\cap A_2\mid D)$ y $P(A_1\cap A_2\mid D)$ usando la fórmula dada por la letra:

- $P(A_1\cap A_2\mid D)=0.90^2=0.81$
- $P(A_1\cap A_2\mid D^C)=0.02^2=0.0004$

**Paso #2:** Plantear la fórmula de probabilidad condicional para $P(A_1\cap A_2\mid D)$:

$$
\begin{aligned}
&P(A_1\cap A_2\mid D)=\frac{P(A_1\cap A_2\cap D)}{P(D)}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&0.81=\frac{P(A_1\cap A_2\cap D)}{0.05}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.81\cdot 0.05=P(A_1\cap A_2\cap D)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.0405=P(A_1\cap A_2\cap D)\\
\end{aligned}
$$

**Paso #3:** Plantear la fórmula de probabilidad condicional para $P(A_1\cap A_2\mid D^C)$:

$$
\begin{aligned}
&P(A_1\cap A_2\mid D^C)=\frac{P(A_1\cap A_2\cap D^C)}{P(D^C)}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&0.0004=\frac{P(A_1\cap A_2\cap D^C)}{0.95}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.0004\cdot 0.95=P(A_1\cap A_2\cap D^C)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.00038=P(A_1\cap A_2\cap D^C)\\
\end{aligned}
$$

**Paso #4:** Sumar lo calculado para obtener $P(A_1\cap A_2)$ usando $*_3$:

- $P(B)=P(A_1\cap A_2)=P(A_1\cap A_2\cap D)+P(A_1\cap A_2\cap D^C)=0.0405+0.00038=0.04088$

Nos quedaría responder a si $A_1$ y $A_2$ son eventos independientes, por definición esto sucede sii:

- $P(A_1\cap A_2)=P(A_1)\cdot P(A_2)$

Sustituyamos y veamos si esto es cierto:

$$
\begin{aligned}
&P(A_1\cap A_2)=^{?}P(A_1)\cdot P(A_2)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&0.04088=^{?}0.061\cdot0.061\\
&\iff\scriptstyle{(\text{operatoria})}\\
&0.04088=^{?}0.003721
\end{aligned}
$$

Donde la última igualdad es claramente falso. Por lo tanto **$A_1$ y $A_2$ no son eventos independientes**.

### Parte 3

- Calcule $P(D|B)$, esto es, la probabilidad de que un jugador sancionado haya consumido anfetaminas.

Ya calculamos todo lo que necesitamos en la parte anterior, así que solo tenemos que plantear
la definición de probabilidad condicional recordando que $B=A_1\cap A_2$.

$$
\begin{aligned}
&P(D\mid B)=\frac{P(D\cap A_1\cap A_2)}{P(A_1\cap A_2)}\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&P(D\mid B)=\frac{0.0405}{0.04088}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(D\mid B)\approx0.99
\end{aligned}
$$

Esto concluye el ejercicio.