# Ejercicio 05 - Esperanza de una v.a.

**Fecha:** 26-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Si a usted le dicen que el $12\%$ de la población está desempleada, el $48\%$ tiene un solo empleo, el $35\%$ tiene dos empleos y el $5\%$ tiene tres, y por otra parte en una muestra tomada al azar, de manera independiente, de 1400 personas resulta que el promedio de empleos por persona es $2.04$. ¿Usted qué diría? ¿Le parece que algún dato puede estar mal, o no? Si algún dato puede estar mal, ¿de cuáles sospecharía? ¿Qué tipos de errores podría contener la información? Si además, entre esas 1400 personas hay 312 desempleados, ¿qué respondería a las preguntas anteriores?

## Resolución

Llamemos $X$ a la v.a. que cuenta la cantidad de empleos que tiene una persona de la población mencionada. Según los datos de la letra tenemos que:

- $P(X=0)=0.12$
- $P(X=1)=0.48$
- $P(X=2)=0.35$
- $P(X=3)=0.05$

Podemos calcular la esperanza de $X$ para comparar con el valor de $2.04$ que brinda la letra.

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{reemplazando por los sumandos conocidos})}\\
&0+0.48+2\cdot0.35+3\cdot0.05\\
&=\scriptstyle{(\text{operatoria})}\\
&1.33
\end{aligned}
$$

Como vemos, hay una diferencia importante entre $2.04$ y la esperanza de $X$ según los datos.
Ahora, como dato adicional, podemos hallar también la varianza de $X$, para determinar que tan lejos de la esperanza tienden a encontrarse los valores de la v.a.

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedad de }Var(X))}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&E(X^2)-1.33^2\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&0+0.48+2^2\cdot0.35+3^2\cdot0.05-1.33^2\\
&=\scriptstyle{(\text{operatoria})}\\
&2.33-1.33^2\\
&=\scriptstyle{(\text{operatoria})}\\
&0.5611\\
\end{aligned}
$$

Observamos que la varianza además es relativamente pequeña, por lo que los valores tienen que tender a estar altamente concentrados en la esperanza de $X$.
En base a esto, podemos concluir que hay una chance alta de que **hay algún error en los datos brindados**.

Por otra parte, si además, entre esas 1400 personas hay 312 desempleados, podemos decir algo más, observemos que en este caso:

- $P(X=0)=312/1400\approx0.2229$

Esto es casi el doble del dato brindado inicialmente $(0.12)$. Con esta información podemos decir que el principal sospechoso del error que estamos encontrando es la información respecto a los desempleados de la población.
Puede existir algún error de muestreo, es decir que la muestra de las $1400$ personas no es representativa con respecto al total de la población.
