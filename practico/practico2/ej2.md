# Ejercicio 02 - Cálculo de probabilidades

**Fecha:** 15-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

1. Se juega a un juego del tipo 5 de Oro: hay que acertar 5 números, elegidos dentro de 36 posibilidades.

    1. ¿Cuál es la probabilidad de ganar?
    2. ¿Cuál es la probabilidad de acertar en al menos 3 números (es decir, acertar exactamente 3, exactamente 4, o exactamente 5 números)?
    3. Construir un espacio muestral para este experimento.
    4. Y si en lugar de 36, se elige sobre 20 números, ¿cuánto dan las probabilidades anteriores?

2. Se juega a la baraja con 40 cartas, 10 de cada palo. Si uno toma 3 cartas, ¿cuál es la probabilidad de elegirlas todas del mismo palo?

## Resolución

### Parte 1

- Se juega a un juego del tipo 5 de Oro: hay que acertar 5 números, elegidos dentro de 36 posibilidades.

    1. ¿Cuál es la probabilidad de ganar?
    2. ¿Cuál es la probabilidad de acertar en al menos 3 números (es decir, acertar exactamente 3, exactamente 4, o exactamente 5 números)?
    3. Construir un espacio muestral para este experimento.
    4. Y si en lugar de 36, se elige sobre 20 números, ¿cuánto dan las probabilidades anteriores?

Para empezar con esta parte, queremos definir el cardinal del espacio muestral, contando todas las jugadas posibles, del estilo de:

- $\{31,2,6,12,11\}$ es una jugada posible.

Esto se hace fácilmente con combinaciones, ya que el orden entre los números no es importante:

- $|\Omega|=C^{36}_5=\frac{36!}{31!5!}=\frac{36\cdot35\cdot34\cdot33\cdot32}{5\cdot4\cdot3\cdot2}=376992$

Otra observación es que estamos considerando que estamos trabajando con un espacio **equiprobable**, es decir que todas las jugadas posibles tienen la misma probabilidad de ocurrir.

Con esto ya podemos responder a la primera pregunta: **¿Cuál es la probabilidad de ganar?**. Llamemos $A$ al evento de ganar, entonces:

- $P(A)=\frac{1}{376992}=2.6\times10^{-6}$

Para la segunda pregunta: **¿Cuál es la probabilidad de acertar en al menos 3 números (es decir, acertar exactamente 3, exactamente 4, o exactamente 5 números)?** necesitamos calcular la cantidad de jugadas que aciertan exactamente 3 números, exactamente 4 números y exactamente 5 números. También los calculamos con combinaciones.

- $\mathcal{C}_{\text{tres}}=C^{5}_3\times C^{31}_2=\frac{5!}{3!2!}\times\frac{31!}{29!2!}=10\times31\cdot15=4650$
- $\mathcal{C}_{\text{cuatro}}=C^{5}_4\times C^{31}_1=\frac{5!}{4!1!}\times \frac{31!}{30!1!}=5\times31=155$
- $\mathcal{C}_{\text{cinco}}=C^{5}_5=1$

Entonces llamando $B$ al evento de acerdar al menos tres números, entonces:

- $P(B)=\frac{4806}{376992}=1.3\times10^{-2}$

Para la cuarta pregunta: **Y si en lugar de 36, se elige sobre 20 números, ¿cuánto dan las probabilidades anteriores?** Lo único que tenemos que cambiar es el espacio muestral, que pasaría a ser:

- $|\Omega_2|=C^{20}_5=\frac{20!}{15!5!}=\frac{20\cdot19\cdot18\cdot17\cdot16}{5\cdot4\cdot3\cdot2}=19\cdot3\cdot17\cdot16=15504$

Como la cantidad de jugadas no cambia, tenemos que en este caso la probabilidad de ganar es:

- $P(A)=\frac{1}{15504}=6.4\times10^{-5}$

Por otra parte, para la probabilidad de adivinar al menos 3 cartas, tenemos que recalcular las posibilidades para cada caso:

- $\mathcal{C}_{\text{tres}}=C^{5}_3\times C^{15}_2=\frac{5!}{3!2!}\times\frac{15!}{13!2!}=10\times15\cdot7=1050$
- $\mathcal{C}_{\text{cuatro}}=C^{5}_4\times C^{15}_1=\frac{5!}{4!1!}\times \frac{15!}{14!1!}=5\times15=75$
- $\mathcal{C}_{\text{cinco}}=C^{5}_5=1$

Por lo tanto, tenemos que:

- $P(B)=\frac{1126}{15504}=7.3\times10^{-2}$

Esto concluye esta parte.

### Parte 2

- Se juega a la baraja con 40 cartas, 10 de cada palo. Si uno toma 3 cartas, ¿cuál es la probabilidad de elegirlas todas del mismo palo?

El espacio muestral es una "jugada" de tres cartas, por lo que su cardinal es:

- $|\Omega|=C^{40}_3=\frac{40!}{37!3!}=\frac{40\cdot39\cdot38}{3\cdot2}=20\cdot13\cdot38=9880$

Ahora, determinaremos la cantidad de jugadas en las que las cartas sean de todas del mismo palo usando la regla del producto, a continuación explicamos los pasos de la tarea:

- elegir una carta cualquiera (40 posibilidades)
- elegir una carta del mismo palo, eliminando la que ya elegimos (9 posibilidades)
- elegir otra carta del mismo palo, eliminando las dos elegidas (8 posibilidades)

Pero esto contempla el orden de las cartas que elegimos, esto no nos interesa, por lo que queremos dividir por la cantidad de formas de ordenar tres cartas $(3!)$. Llamando $A$ al evento de que las tres cartas sean del mismo palo, tenemos que:

- $P(A)=\frac{40\cdot9\cdot8}{9880}\cdot\frac{1}{3!}\approx4.9\times 10^{-2}$

Esto concluye el ejercicio.