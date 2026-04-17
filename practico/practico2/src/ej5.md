# Ejercicio 05 - Cálculo de probabilidades

**Fecha:** 17-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Si un dado está cargado de modo tal que $P(\{i\}) = \alpha i, \quad \forall i = 1, 2, \dots, 6$

1. Determinar el valor de $\alpha$.
2. ¿Cuál es la probabilidad de sacar 5?
3. ¿Cuál es la probabilidad de sacar par?

## Resolución

### Parte 1

- Determinar el valor de $\alpha$.

Los axiomas de Kolmogorov nos dicen que:

- $P(\Omega)=1$

Y sabemos que $\Omega=\{1\}\cup\{2\}\cup\{3\}\cup\{4\}\cup\{5\}\cup\{6\}$ pues el dado va a caer en alguna de las 6 caras.

Considerando que los eventos son independientes dos a dos, podemos usar la regla de aditividad:

$$
\begin{aligned}
&P(\Omega)=P(\{1\})+P(\{2\})+P(\{3\})+P(\{4\})+P(\{5\})+P(\{6\})\\
&\iff\scriptstyle{(\text{reemplazando valores conocidos})}\\
&1=\alpha+2\alpha+3\alpha+4\alpha+5\alpha+6\alpha\\
&\iff\scriptstyle{(\text{operatoria})}\\
&1=21\alpha\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\alpha=\frac{1}{21}
\end{aligned}
$$

### Parte 2

- ¿Cuál es la probabilidad de sacar 5?

La respuesta es concreta y se deriva de la parte anterior:

- $P(\{5\})=\frac{5}{21}$

### Parte 3

- ¿Cuál es la probabilidad de sacar par?

Para esta parte tenemos que usar la aditividad (siempre recordando que todos los eventos en este ejercicio son independientes), llamando $A$ al evento de que salga par:

$$
\begin{aligned}
&P(A)=P(\{2\})+P(\{4\})+P(\{6\})\\
&\iff\scriptstyle{(\text{reemplazando lo conocido})}\\
&P(A)=\frac{2}{21}+\frac{4}{21}+\frac{6}{21}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(A)=\frac{12}{21}\\
\end{aligned}
$$

Por lo que es más probable que el dado salga par que impar.

Esto concluye el ejercicio.