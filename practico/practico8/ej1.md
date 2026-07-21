# Ejercicio 01 - Estimación

**Fecha:** 01-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se realiza una encuesta para tratar de estimar el porcentaje de votos de determinado candidato. Al final de la misma se tendrán $n$ respuestas, representadas en la muestra $X_1,X_2,\cdots,X_n$ de realizaciones de la variable de Bernoulli de parámetro $p$ (la probabilidad de que una persona elegida al azar en la población vote por el candidato en cuestión).

1. A partir de la mencionada muestra ¿Qué valor usaría usted para estimar $p$?
2. Usando la Desigualdad de Chebyshev (y antes de tomar la muestra) ¿Cuántos datos tomaría para que, con una probabilidad de al menos $0.95$, el estimador no distara del valor de $p$ más de un $0.03$? (Sugerencia: Demuestre y use que para cualquier valor de $p\in[0,1]$ se cumple $p(1-p)\leq1/4$).

## Resolución

### Recordatorio #1

Antes de empezar, recordemos la definición de un estimador para ver como la aplicamos para resolver el ejercicio.

Sean $X_1,\ldots,X_n$ es una M.A.S. de cierta $X$ con distribución $F_X(x,\theta)$ con $\theta\in\Theta\subset\mathbb{R}^k$.
Se dice que $\hat{\theta}:\Omega\to\Theta$ es un **estimador** de $\theta$ si y sólo si $\hat{\theta}(X_1,\ldots,X_n)$ es un **estadístico** que puede usarse para "estimar" el verdadero valor de $\theta$.

### Parte 1

- A partir de la mencionada muestra ¿Qué valor usaría usted para estimar $p$?

En definitiva lo que buscamos es una función $\hat{p}(X_1,X_2,\ldots,X_n)$ que sea una v.a. y que podamos usar para aproximar $p$.
Recordemos que para cualquier v.a. de la muestra, al ser variables de Bernoulli se cumple que:

- $E(X_i)=p$

Una buena estimación podría ser tomar el promedio muestral $\overline{X_n}$, esto pues su esperanza es exactamente a $p$:

$$
\begin{aligned}
&E(\overline{X_n})\\
&=\scriptstyle{(\text{definición del promedio muestral y propiedades de la esperanza})}\\
&\frac{1}{n}\sum_{i=1}^nE(X_i)\\
&=\scriptstyle{(E(X_i)=p)}\\
&\frac{1}{n}\cdot np\\
&=\scriptstyle{(\text{operatoria})}\\
&p\\
\end{aligned}
$$

Usar este estimador tiene mucho sentido, pues al hacer tender $n$ a infinito, por la ley de los grandes números nos acercamos más al valor real de $p$.

### Parte 2

- Usando la Desigualdad de Chebyshev (y antes de tomar la muestra) ¿Cuántos datos tomaría para que, con una probabilidad de al menos $0.95$, el estimador no distara del valor de $p$ más de un $0.03$? (Sugerencia: Demuestre y use que para cualquier valor de $p\in[0,1]$ se cumple $p(1-p)\leq1/4$).

#### Recordatorio - Desigualdad de Chebyshev

Sea $X$ una v.a. de esperanza $\mu=E(X)$ y varianza $\sigma^2=Var(X)$. Entonces, para todo $\varepsilon>0$ vale que:

$$
P(|X-\mu|\geq\varepsilon)\leq\frac{\sigma^2}{\varepsilon^2}
$$

#### Continuación

Tengamos en cuenta que por como elegimos el estimador en la parte anterior, tenemos que su valor esperado es exactamente $p$. Por otro lado, correspondería también hallar la varianza de $\overline{X_n}$ para poder sustituirla dentro de la fórmula.

$$
\begin{aligned}
&Var(\overline{X_n})\\
&=\scriptstyle{(\text{definición de }\overline{X_n})}\\
&Var\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de varianza e independencia de las }X_i)}\\
&\frac{1}{n^2}\left(\sum_{i=1}^nVar(X_i)\right)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&\frac{1}{n^2}\left(\sum_{i=1}^nE(X_i^2)-E(X_i)^2\right)\\
&=\scriptstyle{(\text{esperanza de una Bernoulli})}\\
&\frac{1}{n^2}\left(\sum_{i=1}^np-p^2\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{np(1-p)}{n^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{p(1-p)}{n}\\
\end{aligned}
$$

Entonces, la desigualdad de Chebyshev para los datos que tenemos es la siguiente:

$$
P(|\overline{X_n}-p|\geq\varepsilon)\leq\frac{p(1-p)}{n\varepsilon^2}
$$

Recordemos que queremos hallar lo siguiente: *¿Cuántos datos tomaría para que, con una probabilidad de al menos $0.95$, el estimador no distara del valor de $p$ más de un $0.03$?*.
Esto se corresponde al siguiente razonamiento.

$$
P(|\overline{X_n}-p|\geq0.03)\leq\frac{p(1-p)}{n\cdot 0.03^2}
$$

En donde buscamos que se cumpla la siguiente desigualdad:

$$
\frac{p(1-p)}{n\cdot 0.03^2}\leq0.05
$$

Pues queremos calcular la probabilidad de que el estimador **NO** diste de $p$ más de un $0.03$.

Operando sobre esta desigualdad, vemos que se cumple sii:

$$
\begin{aligned}
&\frac{p(1-p)}{n\cdot 0.03^2}\leq0.05\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(1-p)\leq0.05\cdot n\cdot 0.03^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&p(1-p)\leq0.000045n\quad(*_1)\\
\end{aligned}
$$

Llegados a este punto nos gustaría usar la sugerencia para reemplazar en la última desigualdad y encontrar el valor de $n$ que buscamos.

#### Sugerencia

- Demuestre y use que para cualquier valor de $p\in[0,1]$ se cumple $p(1-p)\leq1/4$

Consideremos la función $f(p)=p(1-p)$. Calculemos sus derivadas para hallar los puntos críticos.

- $f(p)=p(1-p)=p-p^2$
- $f'(p)=1-2p$
- $f''(p)=-2$

Observemos que la derivada primera tiene raíz en $p=\frac{1}{2}$, y como la derivada segunda es negativa en ese punto, sabemos que la función es cóncava hacia abajo (formando una colina). Esto significa que en la función original $f$ tiene un máximo relativo en $p=\frac{1}{2}$.

Sustituimos esto en la función:

- $f(\frac{1}{2})=\frac{1}{2}\cdot\frac{1}{2}=\frac{1}{4}$

Entonces la función $f(p)=p(1-p)$ tiene un máximo relativo de $\frac{1}{4}$ en el intervalo $[0,1]$. Esto demuestra la sugerencia. $\blacksquare$

#### Continuación

Ahora que tenemos probada la sugerencia, podemos usarla en la última desigualdad de $*_1$ para operar más hasta hallar el $n$ que buscamos.

$$
\begin{aligned}
&p(1-p)\leq0.000045n\quad(*_1)\\
&\iff\scriptstyle{(\text{por la sugerencia recién probada})}\\
&\frac{1}{4}\leq0.000045n\quad(*_1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{4\cdot 0.000045}\leq n\quad(*_1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&n\geq 5555.\overline{5}
\end{aligned}
$$

Entonces, respondiendo a la pregunta: *¿Cuántos datos tomaría para que, con una probabilidad de al menos $0.95$, el estimador no distara del valor de $p$ más de un $0.03$?*

Tomaría $5556$ datos para asegurar que esta afirmación se cumple, usando la desigualdad de Chebyshev.