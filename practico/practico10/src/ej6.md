# Ejercicio 06 - Intervalos de confianza

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se ha llevado a cabo un experimento para determinar la vida útil de un cierto tipo de mecha (en condiciones extremas). Para esto se tomaron 50 mechas al azar de un stock mayor de mechas, y se les midió el tiempo de vida (en cientos de horas) obteniéndose un promedio muestral $\overline{X}_n=2.266$. Por estudios previos se sabe que el tiempo de vida de las mechas de ese tipo tiene una distribución $N(\mu,\sigma^2)$ con $\sigma=1.935$. Determinar un intervalo de confianza para la vida útil promedio $\mu$ de las mechas de ese tipo, con una confianza igual a $0.95$.

## Resolución

Como ya vimos en el ejercicio anterior, basta con identificar que estamos en el caso donde: **"Quiero hallar $\mu$ y $\sigma^2$ es conocido"**. Para estos casos ya tenemos definida la forma del intervalo de confianza:

$$
\left[\overline{X}_n-\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}},\overline{X}_n+\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\right]
$$

Con esto en mente podemos operar para encontrar la forma del intervalo de confianza solicitado.

$$
\begin{aligned}
&\left[\overline{X}_n-\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}},\overline{X}_n+\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\right]\\
&=\scriptstyle{(\text{reemplazando lo conocido})}\\
&\left[2.266-\frac{1.935\cdot\Phi^{-1}(1-0.025)}{\sqrt{50}},2.266+\frac{1.935\cdot\Phi^{-1}(1-0.025)}{\sqrt{50}}\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&\left[2.266-\frac{1.935\cdot\Phi^{-1}(0.975)}{\sqrt{50}},2.266+\frac{1.935\cdot\Phi^{-1}(0.975)}{\sqrt{50}}\right]\\
&\approx\scriptstyle{(\text{usando una tabla de la normal})}\\
&\left[2.266-\frac{1.935\cdot1.96}{\sqrt{50}},2.266+\frac{1.935\cdot1.96}{\sqrt{50}}\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[2.266-0.5364,2.266+0.5364\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[1.7296,2.8024\right]\\
\end{aligned}
$$

Este es el intervalo de confianza que buscabamos para $\mu$, lo que concluye el ejercicio.