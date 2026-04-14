# Clase 02 - Axiomas de Kolmogorov

**Fecha:** 14-04-2026

## Fundamentos de la teoría de la probabilidad

### Definición de probabilidad

La probabilidad es una función $P$ que asigna a cada evento de un espacio muestral $\Omega$ un número real en el intervalo $[0,1]$. Formalmente $P:\mathcal{A}\to[0,1]$ donde $\mathcal{A}$ es la familia de eventos.

### Axiomas de Kolmogorov

Para que una función $P$ de las características que vimos anteriormente, sea efectivamente una medida de probabilidad, debe satisfacer los cuatro "mandamientos" del sistema axiomático.

- $(*_1)$ **Positividad**: $P(A)\geq0$. La probabilidad de cualquier evento $A$ es no negativa.
- $(*_2)$ **Normalización**: $P(\Omega)=1$. La probabilidad del "evento seguro" es la unidad.
- $(*_3)$ **Aditividad finita**: Si $A\cap B=\emptyset$, entonces $P(A\cup B)=P(A)+P(B)$. Si dos eventos son disjuntos, entonces la probabilidad de la suma, es igual a la suma de sus probabilidades.
- $(*_4)$ **Continuidad**: Si ${A_k}$ es una sucesión creciente de eventos (es decir si $A_k\subset A_{k+1}$), entonces $P(\lim A_k)=\lim P(A_k)$.

En la práctica solemos utilizar una forma equivalente a los axiomas $*_3,*_4$ que los une en uno solo.

- $*_3(\infty)$ **Aditividad numerable**: Si ${A_k}$ es una sucesión de eventos incompatibles dos a dos, entonces:

    $$
    P\left(\bigcup^{\infty}_{k=1}A_k\right)=\sum^{\infty}_{k=1}P(A_k)
    $$

    Esta expresión como dijimos es equivalente a la suma de los axiomas $*_3$ y $*_4$. Es una herramienta fundamental para trabajar con procesos infinitos, permitiendo tratar el límite de una sucesión de eventos como una suma infinita de probabilidades.

### Propiedades derivadas de los axiomas

Estas propiedades son básicamente la caja de herramientas para resolver los ejercicios el práctico.

- **Complemento**: $P(A^C)=1-P(A)$
- **Regla de la resta**: Si $A\subset B$, entonces $P(B\setminus A)=P(B)-P(A)$
- **Monotonía**: Si $A\subset B\implies P(A)\leq P(B)$
- **Inclusión-Exclusión**: $P(A\cup B)=P(A)+P(B)-P(A\cap B)$. Se extiende como la regla de combinatoria para más eventos.
- **Cota de la unión**: $P(A\cup B)\leq P(A)+P(B)$
- **División en casos**: Si podemos dividir el espacio muestral $\Omega$ en subconjuntos $C_1,\ldots,C_n$ disjuntos dos a dos, entonces la probabilidad de cualquier evento $A$ es:

    $$
    P(A)=\sum^n_{i=1} P(A\cap C_i)
    $$

## Modelos de probabilidad discreta

Decimos que un espacio es discreto si $\Omega$ es finito o numerable, es decir $\Omega=\{\omega_1,\omega_2,\ldots,\omega_n\}$. Queriendo definir las probabilidades de los eventos de $\Omega$, primero tenemos que definir las probabilidades $p_i\in[0,1]$ de cada evento simple $\omega_i$.
No cualquier elección de los números $p_i$ resultará en que la probabilidad del espacio muestral sea uno. Para que esto suceda debemos imponer la condición de normalización:

$$
\sum_{i=1}^{\infty}p_i=1
$$

Con esto en mente, definimos la probabilidad de un evento en $A$ como el agregado de las probabilidades de sus eventos simples, de modo que:

$$
P(A)=\sum_{\omega_i\in A}p_i
$$

**Espacio equiprobable**: en el caso especial donde $p_i=\frac{1}{n}$ para todo $i$, tenemos que:

$$
P(A)=\sum_{\omega_i\in A}p_i=\sum_{i=1}^{|A|}\frac{1}{n}=\frac{|A|}{n}=\frac{|A|}{|\Omega|}
$$