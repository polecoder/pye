# Ejercicio 08 - Intervalos de confianza

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Una máquina produce piezas metálicas de forma cilíndrica. Se toma una muestra de piezas cuyos diámetros son $1.01$, $0.97$, $1.03$, $1.04$, $0.99$, $0.98$, $0.99$, $1.01$ y $1.03$ centímetros. Encontrar un intervalo de confianza $0.99$ para el diámetro promedio de piezas de esta máquina, si se supone una distribución aproximadamente normal.

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
&\frac{1}{9}\cdot(1.01+0.97+1.03+1.04+0.99+0.98+0.99+1.01+1.03)\\
&\approx\scriptstyle{(\text{operatoria})}\\
&1.01\\
\end{aligned}
$$

Ahora vayamos con $S_n^2$.

$$
\begin{aligned}
&S_n^2\\
&=\scriptstyle{(\text{definición de varianza muestral})}\\
&\frac{1}{8}\sum_{i=1}^9(X_i-1.01)^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{8}\cdot(0+0.0016+0.0004+0.0009+0.0004+0.0009+0.0004+0+0.0004)\\
&\approx\scriptstyle{(\text{operatoria})}\\
&0.0006
\end{aligned}
$$

Y por lo tanto, tenemos que $S_n=\sqrt{0.0006}\approx0.025$.

---

Con esto, estamos en condiciones de hallar el intervalo de confianza. Reemplacemos lo que calculamos y operemos:

$$
\begin{aligned}
&\left[\overline{X}_n-\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}},\overline{X}_n+\frac{t_{\alpha/2}(n-1)S_n}{\sqrt{n}}\right]\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\left[1.01-\frac{t_{0.005}(8)\cdot0.025}{\sqrt{9}},1.01+\frac{t_{0.005}(8)\cdot0.025}{\sqrt{9}}\right]\\
&=\scriptstyle{(\text{operatoria y usando una tabla de }t-\text{student})}\\
&\left[1.01-\frac{3.355\cdot0.025}{3},1.01+\frac{3.355\cdot0.025}{3}\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[1.01-0.028,1.01+0.028\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[0.982,1.038\right]\\
\end{aligned}
$$

Esto concluye el ejercicio.