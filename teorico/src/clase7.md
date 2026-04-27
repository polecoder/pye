# Clase 07 - Variables aleatorias continuas

**Fecha:** 27-04-2026

## Introducción

En nuestra anterior clase, abordamos el estudio de las **variables aleatorias discretas**, cuyo núcleo reside en el acto de contar resultados dentro de un recorrido numerable. Sin embargo, al enfrentarnos a fenómenos de la naturaleza o la ingeniería (como el tiempo de falla de un componente o la concentración de un contaminante), el enfoque tiene que mutar necesariamente hacia la **medición de magnitudes**.
Es imperativo subrayar que la transición del dominio discreto al continuo, no es meramente una cuestión de escala, sino un cambio de paradigma matemático. 

En un intervalo real $[a,b]$, la cantidad de puntos no es numerable. Si intentáramos asignar una probabilidad positiva a cada punto individual, la suma de estas (el axioma de aditividad) nos conduciría a una contradicción lógica, excediendo la unidad. Por lo tanto, en el modelo continuo, **la probabilidad puntual se desvanece** $(P(X=0)=0)$, y el foco de estudio se desplaza de los puntos aislados a la acumulación de "masa" probabilística sobre intervalos.

## La función de densidad de probabilidad $f_X$

Para las **variables absolutamente continuas** el pilar analítico es la **función de densidad de probabilidad** $(f_X)$. A diferencia del caso discreto, $f_X(x)$ no es una probabilidad en si misma; es una función cuya integral representa la probabilidad.

**Nota:** Las variables aleatorias absolutamente continuas son aquellas cuya distribución se puede describir usando **la función de densidad de probabilidad**. En el curso no nos interesan otros casos donde esto no suceda.

De lo anterior se desprende que una función solo puede ser considerada una densidad legítima si satisface los requisitos derivados de la adaptación de los **Axiomas de Kolgomorov** al cálculo de la integral de Riemann:

### Requisitos axiomáticos de la función de densidad

1. **Positividad (Ax.1):** Para todo $x\in\mathbb{R}$, se debe cumplir que $f_X(x)\geq0$. Esto garantiza que no existan densidades negativas, lo cual invalidaría cualquier medida de probabilidad.
2. **Normalización (Ax.2):** El área total bajo la curva, considerando todo el espacio muestral $\mathbb{R}$, debe ser exactamente 1:

$$
\int_{-\infty}^{+\infty}f_X(x)dx=1
$$

### Visualización y el concepto de "soporte"

Desde una perspectiva geométrica, para que una gráfica represente una densidad, debe cumplir dos criterios estrictos: permanecer siempre por encima del eje $x$ y encerrar un área unitaria. Es común que las funciones densidad estén definidas por tramos, siendo nulas fuera de un intervalo de interés; a éste intervalo donde $f_X(x)>0$ lo denominamos **soporte** de la variable.

## Intuición

Para el estudiante de ingeniería, la comprensión de $f_X(x)$ se simplifica mediante la **analogía de la densidad de la masa**. Consideremos una barra física de longitud $L$:

1. **Masa vs. Densidad:** La "masa" en un punto exacto de la barra es nula, pues un punto carece de extensión.
2. **Concentración infinitesimal:** El término de $f_X(x)$ representa la concentración de probabilidad por unidad de longitud. Matemáticamente, el producto $f_X(x)dx$ representa la **masa infinitesimal** (probabilidad) contenida en un diferencial de largo $dx$.
3. **Integración como suma:** La probabilidad de un intervalo no es más que la suma (integral) de esas masas infinitesimales. Sin un "ancho" de intervalo, no hay probabilidad acumulada.

## Cálculo de probabilidades mediante integración

La probabilidad de que una variable aleatoria continua $X$ se encuentre entre dos valores $a$ y $b$ se calcula mediante la integral definida de su densidad.

$$
P(a<X\leq b)=\int_{a}^{b}f_X(x)dx
$$

### La inevitabilidad de la probabilidad puntual nula

Dado que el área bajo una curva en un solo punto es nula, se deduce una propiedad fundamental: $P(X=c)=0$ para cualquier $c\in\mathbb{R}$.
Esta característica implica que, en el cálculo de probabilidades, la inclusión o exclusión en un intervalo es irrelevante. Los símbolos $<,\leq,>,\geq$ son intercambiables, una libertad que no existe en el mundo discreto.

$$
P(a\leq X\leq b)=P(a<X\leq b)=P(a\leq X<b)=P(a<X<b)
$$

## Función de distribución acumulada

La **función de distribución acumulada (f.d.a.)** conserva su definición conceptual, $F_X(x)=P(X\leq x)$, pero su construcción matemática es ahora integral:

- $F_X(x)=\int_{-\infty}^{x}f_X(t)dt$

### Propiedades y continuidad

La f.d.a. en el caso absolutamente continuo presenta propiedades distintivas:

1. **Monotonía y límites:** Es no decreciente, con $\lim_{x\to-\infty}=0$  y $\lim_{x\to+\infty}=1$.
2. **Continuidad absoluta:** A diferencia de la "escalera" de saltos del caso discreto, aquí $F_X(x)$ es una función continua en **todo su dominio**.

Esta suavidad de $F_X$ es una consecuencia directa de que $P(X=c)=0$. Al no haber puntos que concentren masa de probabilidad, no existen saltos o discontinuidades en la acumulación de la misma.

## Distribución uniforme

Para la resolución de problemas técnicos, es necesario dominar la expresión analítica de los modelos presentados en el práctico. Estudiaremos específicamente la distribución "uniforme" en esta clase, mientras las demás se detallarán con los ejercicios del práctico.

### Definición $X\sim U(a,b)$

Representa el escenario de máxima incertidumbre, donde la probabilidad se distribuye de forma equitativa sobre un intervalo $[a,b]$. Su densidad es constante en su soporte:

- $f_X(x)=\begin{cases}\frac{1}{b-a}&\text{si }a\leq x\leq b\\0&\text{en otro caso}\end{cases}$

Por lo general se entiende en el ejercicio que queremos resolver si se utiliza esta distribución.