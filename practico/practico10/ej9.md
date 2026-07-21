# Ejercicio 09 - Intervalos de confianza

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Los siguientes son los pesos, en decagramos, de 10 paquetes de semillas de pasto distribuidos por determinada compañía: $46.4$, $46.1$, $45.8$, $47.0$, $46.1$, $45.9$, $45.8$, $46.9$, $45.2$ y $46.0$. Encontrar un intervalo de confianza $0.95$ para la varianza de todos los paquetes de semillas de pasto que distribuyó esta compañía, suponiendo una población normal.

## Resolución

Como ya vimos en los ejercicios anteriores, basta con identificar que estamos en el caso donde: **"Quiero hallar $\sigma^2$ con una distribución normal"**. Para estos casos ya tenemos definida la forma del intervalo de confianza:

$$
\left[\frac{(n-1)S_n^2}{\chi^2_{\alpha/2}(n-1)},\frac{(n-1)S_n^2}{\chi^2_{1-\alpha/2}(n-1)}\right]
$$

La forma del intervalo de confianza, nos va guiando por su forma, hay dos valores que podemos calcular directamente, estos son:

- $\overline{X}_n$
- $S_n^2$

Separemos una pequeña sección de cálculos del ejercicio para una mejor lectura.

### Cálculos necesarios para hallar el intervalo

$$
\begin{aligned}
&\overline{X}_{10}\\
&=\scriptstyle{(\text{definición de promedio muestral})}\\
&\frac{1}{10}\cdot(46.4+46.1+45.8+47.0+46.1+45.9+45.8+46.9+45.2+46.0)\\
&=\scriptstyle{(\text{operatoria})}\\
&46.12
\end{aligned}
$$

Ahora vayamos con $S_{10}^2$:

$$
\begin{aligned}
&S_{10}^2\\
&=\scriptstyle{(\text{definición de varianza muestral})}\\
&\frac{1}{9}\sum_{i=1}^{10}(X_i-46.12)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{9}\cdot(0.0784+0.0004+0.1024+0.7744+0.0004+0.0484+0.1024+0.6084+0.8464+0.0144)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{9}\cdot2.576\\
&\approx\scriptstyle{(\text{operatoria})}\\
&0.2862
\end{aligned}
$$

---

Con esto, estamos en condiciones de hallar el intervalo de confianza. Reemplacemos lo que calculamos y operemos:

$$
\begin{aligned}
&\left[\frac{(n-1)S_n^2}{\chi^2_{\alpha/2}(n-1)},\frac{(n-1)S_n^2}{\chi^2_{1-\alpha/2}(n-1)}\right]\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\left[\frac{9\cdot0.2862}{\chi^2_{0.025}(9)},\frac{9\cdot0.2862}{\chi^2_{1-0.025}(9)}\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&\left[\frac{9\cdot0.2862}{\chi^2_{0.025}(9)},\frac{9\cdot0.2862}{\chi^2_{0.975}(9)}\right]\\
&\approx\scriptstyle{(\text{usando una tabla de Chi cuadrado})}\\
&\left[\frac{9\cdot0.2862}{19.02},\frac{9\cdot0.2862}{2.700}\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&[0.1354,0.9540]
\end{aligned}
$$

Esto concluye el ejercicio.