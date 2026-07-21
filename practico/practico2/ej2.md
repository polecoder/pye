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

- $|\Omega|=C^{36}_5=\frac{36!}{31!5!}=\frac{36\cdot35\cdot34\cdot33\cdot32}{5\cdot4\cdot3\cdot2}=217.147.392$

Otra observación es que estamos considerando que estamos trabajando con un espacio **equiprobable**, es decir que todas las jugadas posibles tienen la misma probabilidad de ocurrir.

Con esto ya podemos responder a la primera pregunta: **¿Cuál es la probabilidad de ganar?**. Llamemos $A$ al evento de ganar, entonces:

- $P(A)=\frac{1}{217.147.392}=4.6\times10^{-9}$

Para la segunda pregunta: **¿Cuál es la probabilidad de acertar en al menos 3 números (es decir, acertar exactamente 3, exactamente 4, o exactamente 5 números)?** necesitamos calcular la cantidad de jugadas que aciertan exactamente 3 números, exactamente 4 números y exactamente 5 números. También los calculamos con combinaciones.

- $\mathcal{C}_{\text{tres}}=C^{5}_3=\frac{5!}{3!2!}=10$
- $\mathcal{C}_{\text{cuatro}}=C^{5}_4=\frac{5!}{4!1!}=5$
- $\mathcal{C}_{\text{cinco}}=C^{5}_5=1$

Entonces llamando $B$ al evento de acerdar al menos tres números, entonces:

- $P(B)=\frac{16}{217.147.392}=7.4\times10^{-8}$

Para la cuarta pregunta: **Y si en lugar de 36, se elige sobre 20 números, ¿cuánto dan las probabilidades anteriores?** Lo único que tenemos que cambiar es el espacio muestral, que pasaría a ser:

- $|\Omega_2|=C^{20}_5=\frac{20!}{15!5!}=\frac{20\cdot19\cdot18\cdot17\cdot16}{5\cdot4\cdot3\cdot2}=19\cdot9\cdot17\cdot16=46512$

Como la cantidad de jugadas no cambia, tenemos que en este caso:

- $P(A)=\frac{1}{46512}=2.0\times10^{-5}$
- $P(B)=\frac{16}{46512}=3.4\times10^{-4}$

Esto concluye el ejercicio.