# Ejercicio 08 - Propiedades de la probabilidad

**Fecha:** 14-04-2026
**Estado:** 🟡 Con ayuda

## Consigna

Sea $(\Omega, \mathcal{A}, P)$ un espacio de probabilidad. Demostrar que:

1. Si $A$ y $B$ son sucesos tales que $A \subset B$ entonces $P(B \setminus A) = P(B) - P(A)$

    **Sugerencia:** considerar que $B \setminus A = B \cap A^c$ y por otra parte $B = (B \cap A) \cup (B \cap A^c)$.

    Deducir que $P(A) \leq P(B)$.

2. Si $A$ y $B$ son sucesos entonces:

    - $P(A \cup B) \geq \max\{P(A), P(B)\}$
    - $P(A \cap B) \leq \min\{P(A), P(B)\}$

## Resolución

### Parte 1

- Si $A$ y $B$ son sucesos tales que $A \subset B$ entonces $P(B \setminus A) = P(B) - P(A)$

Para esta parte queremos usar la sugerencia que nos da la letra, es decir que:

- $(*_1)\quad B\setminus A=B\cap A^C$
- $(*_2)\quad B=(B\cap A)\cup(B\cap A^C)$

Si $B\cap A$ y $B\cap A^C$ son disjuntos, entonces podemos usar el **Ax.3** de Kolmogorov para encontrar la probabilidad de $B$.
Obviamente estos dos conjuntos son disjuntos, pues si algo está en $A$, entonces **NO** está en $A^C$ por la definición de complemento. Entonces, podemos desarrollar usando el **Ax.3**.

$$
\begin{aligned}
&B=(B\cap A)\cup(B\cap A^C)\\
&\iff\scriptstyle{(\text{Ax.3 de Kolmogorov})}\\
&P(B)=P(B\cap A)+P(B\cap A^C)\\
&\iff\scriptstyle{(\text{por la observación }*_1)}\\
&P(B)=P(B\cap A)+P(B\setminus A)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(B)-P(B\cap A)=P(B\setminus A)\\
&\iff\scriptstyle{(\text{como }A\subset B:\ P(B\cap A)=P(A))}\\
&P(B)-P(A)=P(B\setminus A)\\
\end{aligned}
$$

Esto concluye la prueba, de la cual se desprende que claramente $P(A)\leq P(B)$, esto pues el **Ax.1** nos dice que la probabilidad de cualquier evento es mayor que cero. Si $P(A)>P(B)$, entonces la probabilidad $P(B\setminus A)$ sería negativa, lo cual es **absurdo**.

### Parte 2

- Si $A$ y $B$ son sucesos entonces:

    - $P(A \cup B) \geq \max\{P(A), P(B)\}$
    - $P(A \cap B) \leq \min\{P(A), P(B)\}$

#### Afirmación 1

- $P(A \cup B) \geq \max\{P(A), P(B)\}$

Por teoría de conjuntos, sabemos que se dan las siguientes cosas:

- $A\subset (A\cup B)$
- $B\subset (A\cup B)$

Entonces por monotonía (lo que demostramos en la parte anterior), tenemos que:

- $P(A)\leq P(A\cup B)$
- $P(B)\leq P(A\cup B)$

Por lo que en particular tenemos que:

- $P(A\cup B)\geq\max\{P(A),P(B)\}$

Que es lo que queríamos demostrar.

#### Afirmación 2

- $P(A \cap B) \leq \min\{P(A), P(B)\}$

Por teoría de conjuntos, sabemos que se dan las siguientes cosas:

- $(A\cap B)\subset A$
- $(A\cap B)\subset B$

Entonces por monotonía (lo que demostramos en la parte anterior), tenemos que:

- $P(A\cap B)\leq P(A)$
- $P(A\cap B)\leq P(B)$

Por lo que en particular tenemos que:

- $P(A\cap B)\leq\min\{P(A),P(B)\}$

Que es lo que queríamos demostrar.