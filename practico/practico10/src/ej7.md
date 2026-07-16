# Ejercicio 07 - Intervalos de confianza

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Los contenidos de 7 recipientes similares de ácido sulfúrico son $9.8$, $10.2$, $10.4$, $9.8$, $10.0$, $10.2$ y $9.6$ litros. Encontrar un intervalo de confianza $0.95$ para la media de todos los recipientes, suponiendo una distribución normal.

## Resolución

Como ya vimos en los ejercicios anteriores, basta con identificar que estamos en el caso donde: **"Quiero hallar $\mu$ y $\sigma^2$ es desconocido"**. Para estos casos ya tenemos definida la forma del intervalo de confianza:

$$
\left[\overline{X}_n-\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}},\overline{X}_n+\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}}\right]
$$

La forma del intervalo de confianza, nos va guiando por su forma, hay dos valores que podemos calcular directamente, estos son:

- $\overline{X}_n$
- $S_n$, para quién primero calcularemos $S_n^2$

Separemos una pequeña sección de cálculos del ejercicio para una mejor lectura.

### Cálculos necesarios para hallar el intervalo

$$
\begin{aligned}
&\overline{X}_n\\
&=\scriptstyle{(\text{definición de promedio muestral})}\\
&\frac{1}{7}\cdot(9.8+10.2+10.4+9.8+10.0+10.2+9.6)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{70}{7}\\
&=\scriptstyle{(\text{operatoria})}\\
&10\\
\end{aligned}
$$

Ahora vayamos con $S_n^2$.

$$
\begin{aligned}
&S_n^2\\
&=\scriptstyle{(\text{definición de varianza muestral})}\\
&\frac{1}{6}\cdot\sum_{i=1}^7(X_i-10)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{6}\cdot(0.04+0.04+0.16+0.04+0+0.04+0.16)\\
&=\scriptstyle{(\text{operatoria})}\\
&0.08\\
\end{aligned}
$$

Y por lo tanto, tenemos que $S_n=\sqrt{0.08}\approx0.28$

---

Con esto, estamos en condiciones de hallar el intervalo de confianza. Reemplacemos lo que calculamos y operemos:

$$
\begin{aligned}
&\left[\overline{X}_n-\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}},\overline{X}_n+\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}}\right]\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\left[10-\frac{t_{0.025}(6)\cdot0.28}{\sqrt{7}},10+\frac{t_{0.025}(6)\cdot0.28}{\sqrt{7}}\right]\\
&\approx\scriptstyle{(\text{usando una tabla de }t-\text{student})}\\
&\left[10-\frac{2.447\cdot0.28}{\sqrt{7}},10+\frac{2.447\cdot0.28}{\sqrt{7}}\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[10-0.259,10+0.259\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[9.741,10.259\right]\\
\end{aligned}
$$

Esto concluye el ejercicio.