# Ejercicio 04 - Esperanza de una v.a.

**Fecha:** 26-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Consideremos dos juegos de azar.

1. Se eligen 5 números entre 1 y 20 y se sortea mediante bolilleros 5 números entre 1 y 20 (suponemos equiprobabilidad). Si salen los 5 números elegidos por nosotros (aunque sea en otro orden), ganamos 20 veces lo apostado; si salen 4 de los 5, ganamos 4 veces lo apostado; si salen 3 de los 5, ganamos el doble de lo apostado, y en cualquier otro caso perdemos lo apostado. (**Atención:** cuando decimos 'ganar' nos referimos a cuánto se nos paga, y no a la ganancia neta. En realidad, la ganancia neta se obtiene luego de restar lo apostado, por ej.: si acertamos los 5 números, la ganancia neta es 19 veces lo apostado.)

2. Se eligen 5 cartas de un mazo de 32, si las 5 son del mismo color y en escalera (supongamos las cartas numeradas del 1 al 8; las escaleras son cuatro: 1 a 5, 2 a 6, 3 a 7, 4 a 8) ganamos 8 veces lo apostado, si obtenemos 5 cartas del mismo color pero no en escalera, ganamos 2 veces lo apostado; si obtenemos cartas en escalera pero no del mismo color, recuperamos lo apostado; en cualquier otro caso se pierde lo apostado. (**Atención:** vale la misma precisión que en el juego anterior respecto de la ganancia y también suponemos equiprobabilidad.)

Queremos jugar una vez por semana uno de estos juegos, con las siguientes reglas:

- Jugaremos siempre una suma fija $S$,
- Jugaremos siempre el mismo juego,
- Las distintas jugadas son totalmente independientes, no hay influencia de una jugada en la otra,
- Jugaremos por un tiempo indefinido, muy largo.

¿Cuál de los juegos elegiría usted? Al cabo de 1000 semanas, ¿cuánto estimaría usted que es la ganancia neta que se obtendría jugando siempre al primer juego? ¿Y al segundo?

## Resolución

Para empezar, necesitamos traducir la consigna en conceptos de probabilidad, para poder aplicar la definición de esperanza y determinar que juego es más rentable jugar.

### Juego #1

- Se eligen 5 números entre 1 y 20 y se sortea mediante bolilleros 5 números entre 1 y 20 (suponemos equiprobabilidad). Si salen los 5 números elegidos por nosotros (aunque sea en otro orden), ganamos 20 veces lo apostado; si salen 4 de los 5, ganamos 4 veces lo apostado; si salen 3 de los 5, ganamos el doble de lo apostado, y en cualquier otro caso perdemos lo apostado. (**Atención:** cuando decimos 'ganar' nos referimos a cuánto se nos paga, y no a la ganancia neta. En realidad, la ganancia neta se obtiene luego de restar lo apostado, por ej.: si acertamos los 5 números, la ganancia neta es 19 veces lo apostado.)

Consideremos $X$ la variable aleatoria que cuenta la ganancia que tiene el jugador. Necesitamos calcular algunos detalles del espacio de probabilidad en el que estamos trabajando:

- $|\Omega|=\text{elecciones posibles de 5 números entre 1 y 20}=C_5^{20}$
- $P(\text{5 aciertos})=\frac{1}{C_5^{20}}=\frac{1}{15304}\approx0.00006$
- $P(\text{4 aciertos})=\frac{C_4^5\cdot C_1^{15}}{C_5^{20}}\approx0.00484$
- $P(\text{3 aciertos})=\frac{C_3^5\cdot C_2^{15}}{C_5^{20}}\approx0.06772$
- $P(\text{perder apuesta})=1-(P(\text{5 aciertos}+P(\text{4 aciertos})+P(\text{3 aciertos})))\approx1-(0.00006+0.00484+0.06772)=1-0.07262=0.92738$

Con esto, estamos en condiciones de calcular la esperanza de $X$, y ver la ganancia esperada al jugar a este juego, sea $S$ la apuesta inicial del jugador, entonces:

- $P(X=19S)=0.00006$
- $P(X=3S)=0.00484$
- $P(X=S)=0.06772$
- $P(X=-S)=0.92738$

Podemos aplicar la definición de esperanza, donde obtenemos que:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{expandiendo la suma})}\\
&0.00006\cdot19S+0.00484\cdot3S+0.06772\cdot S+0.92738\cdot(-S)\\
&=\scriptstyle{(\text{operatoria})}\\
&-0.84400S
\end{aligned}
$$

Por lo tanto, este juego tiene una esperanza negativa respecto a la apuesta inicial del jugador. Veamos que sucede con el otro juego.

### Juego #2

- Se eligen 5 cartas de un mazo de 32, si las 5 son del mismo color y en escalera (supongamos las cartas numeradas del 1 al 8; las escaleras son cuatro: 1 a 5, 2 a 6, 3 a 7, 4 a 8) ganamos 8 veces lo apostado, si obtenemos 5 cartas del mismo color pero no en escalera, ganamos 2 veces lo apostado; si obtenemos cartas en escalera pero no del mismo color, recuperamos lo apostado; en cualquier otro caso se pierde lo apostado. (**Atención:** vale la misma precisión que en el juego anterior respecto de la ganancia y también suponemos equiprobabilidad.)

Consideremos $X$ la variable aleatoria que cuenta la ganancia que tiene el jugador. Necesitamos calcular algunos detalles del espacio de probabilidad en el que estamos trabajando:

- $|\Omega|=C_5^{32}=201376$
- $P(\text{escalera y mismo color})=\frac{4+4+4+4}{201376}=\frac{16}{201376}\approx0.00008$
- $P(\text{mismo color})=\frac{C_1^4\cdot C_5^8}{201376}\approx0.00111$
- $P(\text{escalera})=\frac{4\cdot4^5}{201376}\approx0.02034$
- $P(\text{perder apuesta})\approx1-(0.00008+0.00111+0.02034)=0.97847$

Donde el evento donde tenemos una escalera con cualquier color, se obtiene pensando en que tenemos $4$ escaleras posibles, y para cada uno de los $5$ números tenemos $4$ colores posibles.

Con esto, estamos en condiciones de calcular la esperanza de $X$, y ver la ganancia esperada al jugar a este juego, sea $S$ la apuesta inicial del jugador, entonces:

- $P(X=7S)=0.00008$
- $P(X=S)=0.00111$
- $P(X=0)=0.02034$
- $P(X=-S)=0.97847$

Podemos aplicar la definición de esperanza, donde obtenemos que:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{reemplazando por los valores de los sumandos})}\\
&7S\cdot0.00008+S\cdot0.00111+0+(-S)\cdot0.97847\\
&=\scriptstyle{(\text{operatoria})}\\
&-0.97680S
\end{aligned}
$$

Por lo tanto, este juego también tiene una esperanza negativa respecto a la apuesta inicial del jugador.

### Conclusión

- Queremos jugar una vez por semana uno de estos juegos, con las siguientes reglas:

    - Jugaremos siempre una suma fija $S$,
    - Jugaremos siempre el mismo juego,
    - Las distintas jugadas son totalmente independientes, no hay influencia de una jugada en la otra,
    - Jugaremos por un tiempo indefinido, muy largo.

    ¿Cuál de los juegos elegiría usted? Al cabo de 1000 semanas, ¿cuánto estimaría usted que es la ganancia neta que se obtendría jugando siempre al primer juego? ¿Y al segundo?

Si tuviera que elegir a que juego jugaría, no eligiría ninguno de los dos, aunque el primero es el "mejor" de ellos. Recordando que la esperanza de $X$ representa la ganancia promedio por jugada, podemos calcular la ganancia estimada al cabo de $1000$ semanas con:

- **Juego #1:** $G_1=1000\cdot E(X)=1000\cdot-0.84400S=-844.00S$
- **Juego #2:** $G_2=1000\cdot E(X)=1000\cdot-0.97680S=-976.80S$

En definitiva, no es recomendable jugar a ninguno de estos juegos, ya que en promedio terminaremos perdiendo (aunque menos con el juego #1).