# Ejercicio 06 - Probabilidad condicional

**Fecha:** 20-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

1. Tres jugadores tiran al blanco. La probabilidad de que el jugador 1 dé en el blanco es $\frac{1}{6}$, la probabilidad de que el jugador 2 dé en el blanco es $\frac{1}{4}$ y la probabilidad de que el jugador 3 dé en el blanco es $\frac{1}{3}$. Cada uno dispara una vez.
   1. ¿Cuál es la probabilidad de que el blanco sea alcanzado solamente una vez?
   2. Si sólo uno da en el blanco, ¿cuál es la probabilidad que haya sido el jugador 1?

2. La probabilidad de que el jugador 1 dé en el blanco es $\frac{1}{4}$ y la probabilidad de que el jugador 2 dé en el blanco es $\frac{1}{3}$.
   1. Si cada uno dispara dos veces, ¿cuál es la probabilidad de que el blanco sea alcanzado por lo menos una vez?
   2. Supongamos ahora que cada uno dispara una vez. Dado que el blanco fue alcanzado solamente una vez, ¿cuál es la probabilidad que haya sido el jugador 1?

## Resolución

### Parte 1

- Tres jugadores tiran al blanco. La probabilidad de que el jugador 1 dé en el blanco es $\frac{1}{6}$, la probabilidad de que el jugador 2 dé en el blanco es $\frac{1}{4}$ y la probabilidad de que el jugador 3 dé en el blanco es $\frac{1}{3}$. Cada uno dispara una vez.
  1.  ¿Cuál es la probabilidad de que el blanco sea alcanzado solamente una vez?
  2.  Si sólo uno da en el blanco, ¿cuál es la probabilidad que haya sido el jugador 1?

Para esta parte, consideraremos el siguiente nombre para los siguientes eventos:

- $A:$ El jugador 1 le da al blanco
- $B:$ El jugador 2 le da al blanco
- $C:$ El jugador 3 le da al blanco
- $O:$ El blanco es alcanzado por exactamente un jugador

#### Subparte 1

- ¿Cuál es la probabilidad de que el blanco sea alcanzado solamente una vez?

Para esta parte definimos (y calculamos) los complementos de los eventos $A,B$ y $C$.

- $P(A^C)=1-P(A)=1-\frac{1}{6}=\frac{5}{6}$
- $P(B^C)=1-P(B)=1-\frac{1}{4}=\frac{3}{4}$
- $P(C^C)=1-P(C)=1-\frac{1}{3}=\frac{2}{3}$

Ahora, la clave para esta parte es usar que la independencia de estos eventos dos a dos. Esto es claro, ya que sabemos que si el jugador 1 acierta al blanco, las probabilidades de que el jugador 2 acierte no cambian, esto significa que son independientes, es decir que $A$ es independiente de $B$.

Queremos calcular aquellos eventos donde el blanco es alcanzado por exactamente un jugador, es decir:

- $A\cup B^C\cup C^C$
- $A^C\cup B\cup C^C$
- $A^C\cup B^C\cup C$

Ahora para calcular sus probabilidades, usamos que todos estos son independientes entre si, por lo que podemos usar que:

- $P(A\cup B^C\cup C^C)=P(A)P(B^C)P(C^C)=\frac{1}{6}\cdot\frac{3}{4}\cdot\frac{2}{3}=\frac{6}{72}=\frac{1}{12}$
- $P(A^C\cup B\cup C^C)=P(A^C)P(B)P(C^C)=\frac{5}{6}\cdot\frac{1}{4}\cdot\frac{2}{3}=\frac{10}{72}=\frac{5}{36}$
- $P(A^C\cup B^C\cup C)=P(A^C)P(B^C)P(C)=\frac{5}{6}\cdot\frac{3}{4}\cdot\frac{1}{3}=\frac{15}{72}=\frac{5}{24}$

Ahora, el evento $O$ es la unión de estos tres eventos que vimos, los cuales claramente son disjuntos dos a dos, por lo que usando la regla de aditividad tenemos que:

- $P(O)=\frac{1}{12}+\frac{5}{36}+\frac{5}{24}=\frac{6+10+15}{72}=\frac{31}{72}$

Esto concluye la subparte 1.

#### Subparte 2

- Si sólo uno da en el blanco, ¿cuál es la probabilidad que haya sido el jugador 1?

Nombremos alguno de los eventos de la parte anterior:

- $J_1=A\cup B^C\cup C^C:$ Solo el jugador $A$ acierta al blanco.

Ahora si, queremos hallar la probabilidad condicional que nos devuelve cuántas son las probabilidades de que suceda $J_1$ si sabemos que sucedió $O$.

- $P(J_1\mid O)=\frac{6/72}{31/72}=\frac{6}{31}$

Esto concluye la subparte 2.

### Parte 2

- La probabilidad de que el jugador 1 dé en el blanco es $\frac{1}{4}$ y la probabilidad de que el jugador 2 dé en el blanco es $\frac{1}{3}$.
  1. Si cada uno dispara dos veces, ¿cuál es la probabilidad de que el blanco sea alcanzado por lo menos una vez?
  2. Supongamos ahora que cada uno dispara una vez. Dado que el blanco fue alcanzado solamente una vez, ¿cuál es la probabilidad que haya sido el jugador 1?

#### Subparte 1

- Si cada uno dispara dos veces, ¿cuál es la probabilidad de que el blanco sea alcanzado por lo menos una vez?

Para este caso, tenemos las siguientes probabilidades para los siguientes eventos:

- $P(A)=\frac{1}{4}$
- $P(B)=\frac{1}{3}$

Por lo tanto, tenemos que:

- $P(A^C)=1-\frac{1}{4}=\frac{3}{4}$
- $P(B^C)=1-\frac{1}{3}=\frac{2}{3}$

Llamemos $O_2$ al evento que queremos encontrar. Lo más fácil va a ser encontrar $(O_2)^C$, es decir la probabilidad de que ningún disparo alcance al blanco después de dos disparos cada uno.

- $P((O_2)^C)=P(A^C\cap A^C\cap B^C\cap B^C)=P(A^C)^2\cdot P(B^C)^2=\frac{9}{16}\cdot\frac{4}{9}=\frac{36}{144}=\frac{1}{4}$

Entonces usando la propiedad del complemento, tenemos que:

- $P(O_2)=1-P((O_2)^C)=1-\frac{1}{4}=\frac{3}{4}$

Por lo tanto, la respuesta para esta parte es que la probabilidad de que el blanco sea alcanzado por lo menos una vez bajo las condiciones dadas, es de $0.75$

#### Subparte 2

- Supongamos ahora que cada uno dispara una vez. Dado que el blanco fue alcanzado solamente una vez, ¿cuál es la probabilidad que haya sido el jugador 1?

Para esta parte tenemos que recalcular las probabilidades ya que cambiaron con respecto a la parte 1 y tenemos un jugador menos.
Llamemos $O$ al evento que describe que el blanco fue alcanzado exactamente una vez.

Para calcular su probabilidad tenemos que hallar primero (recordemos que los eventos que veremos son independientes el uno del otro):

- $P(A\cap B^C)=P(A)\cdot P(B^C)=\frac{1}{4}\cdot\frac{2}{3}=\frac{1}{6}$
- $P(A^C\cap B)=P(A^C)\cdot P(B)=\frac{3}{4}\cdot\frac{1}{3}=\frac{1}{4}$

Entonces podemos hallar $P(O)$, sabiendo que ambos estos eventos son disjuntos y podemos aplicar aditividad.

- $P(O)=P(A\cap B^C)+P(A^C\cap B)=\frac{1}{6}+\frac{1}{4}=\frac{2+3}{12}=\frac{5}{12}$

Llamemos $J_1=A\cap B^C$ al evento que describe que el blanco fue alcanzado exactamente una vez por el jugador 1, con esto la probabilidad condicional que queremos calcular es:

- $P(J_1\mid O)=\frac{1/6}{5/12}=\frac{2}{5}$

**Nota:** Ambas las veces que usamos la fórmula de la probabilidad condicional se dió que la probabilidad de una intersección de conjuntos era equivalente a la probabilidad de una de sus partes. Ojo con generalizar esto.
