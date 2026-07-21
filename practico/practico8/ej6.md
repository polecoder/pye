# Ejercicio 06 - Ley de los grandes números

**Fecha:** 03-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sea $X_1,X_2,\cdots,X_n$ una sucesión de variables aleatorias independientes e idénticamente distribuidas con distribución exponencial de parámetro $\lambda$.

1. Hallar el límite casi seguro de $\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)^2$.
2. Hallar el límite casi seguro de $\frac{1}{n}\sum_{i=1}^{n}X_i^2$.

## Resolución

Teniendo en cuenta que $X_i\sim exp(\lambda)$ y que calculamos el valor de la esperanza para esta distribución en el práctico anterior:

- $E(X_i)=\frac{1}{\lambda}$

Recordemos además que por ley fuerte de los grandes números:

$$
\frac{1}{n}\sum_{i=1}^{n}X_i\xrightarrow[n]{c.s.}\frac{1}{\lambda}\quad(*_1)
$$

### Parte 1

Queremos estudiar el comportamiento de $\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)^2$ en el infinito.

$$
\begin{aligned}
&\lim_{n\to\infty}\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\lim_{n\to\infty}\left(\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)\cdot\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)\right)\\
&=\scriptstyle{(\text{propiedades de límites de sucesiones})}\\
&\lim_{n\to\infty}\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)\cdot\lim_{n\to\infty}\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)\\
&=\scriptstyle{(\text{por }*_1)}\\
&\frac{1}{\lambda}\cdot\frac{1}{\lambda}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{\lambda^2}
\end{aligned}
$$

Este es el límite casi seguro de $\left(\frac{1}{n}\sum_{i=1}^{n}X_i\right)^2$, lo que concluye esta parte.

### Parte 2

- Hallar el límite casi seguro de $\frac{1}{n}\sum_{i=1}^{n}X_i^2$.

Solo necesitamos conocer la esperanza de $X_i^2$ con lo que aplicaremos directamente la ley fuerte de los grandes números para hallar la solución. Recordemos que:

$$
\text{Si }X\sim exp(\lambda),\text{ entonces }Var(X)=\frac{1}{\lambda^2}\quad(*_2)
$$

Operaremos con esto para hallar $E(X_i^2)$.

$$
\begin{aligned}
&E(X_i^2)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&Var(X_i)+E(X_i)^2\\
&=\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\frac{1}{\lambda^2}+\frac{1}{\lambda^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{2}{\lambda^2}
\end{aligned}
$$

Aplicando la ley fuerte de los grandes números, concluimos que:

$$
\begin{aligned}
&\overline{X^2}_n\xrightarrow[n]{c.s.}\frac{2}{\lambda^2}\\
&=\scriptstyle{(\text{definición de }\overline{X_i}^2)}\\
&\frac{1}{n}\cdot\sum_{i=1}^nX_i^2\xrightarrow[n]{c.s.}\frac{2}{\lambda^2}\\
\end{aligned}
$$

Que es lo que queríamos encontrar. Esto concluye el ejercicio.