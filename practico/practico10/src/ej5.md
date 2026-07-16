# Ejercicio 05 - Intervalos de confianza

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

1. Una máquina de refrescos está ajustada de tal manera que la cantidad de líquido despachada se distribuye aproximadamente en forma normal con una desviación estándar igual a $0.15$ decilitros. Encontrar un intervalo de confianza $0.95$ para la media de todos los refrescos que sirve esta máquina si una muestra aleatoria de 36 refrescos tiene un contenido promedio de $2.25$ decilitros.
2. ¿Qué tan grande tiene que ser la muestra si se desea tener una confianza del $95\%$ de que la media muestral no difiera en más de $0.03$ decilitros de la media real $\mu$?

## Resolución

### Parte 1

- Una máquina de refrescos está ajustada de tal manera que la cantidad de líquido despachada se distribuye aproximadamente en forma normal con una desviación estándar igual a $0.15$ decilitros. Encontrar un intervalo de confianza $0.95$ para la media de todos los refrescos que sirve esta máquina si una muestra aleatoria de 36 refrescos tiene un contenido promedio de $2.25$ decilitros.

Analizando los datos, tenemos que:

1. $X\sim N(\mu,0.15^2)$
2. $\alpha=1-0.95=0.05$
3. $\overline{X}_{36}=2.25$

Queremos hallar *la media de todos los refrescos*, es decir la esperanza $\mu$.
Estos ejercicios consisten en identificar en que caso estamos, que sería: **"Quiero hallar $\mu$ con $\sigma^2$ conocido**", el teórico nos dice que estos casos tienen el siguiente intervalo de confianza definido:

$$
\left[\overline{X}_n-\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}},\overline{X}_n+\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\right]
$$

Entonces, reemplacemos los datos que conocemos en este intervalo.

$$
\begin{aligned}
&\left[\overline{X}_n-\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}},\overline{X}_n+\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\right]\\
&=\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\left[2.25-\frac{0.15\cdot\Phi^{-1}(1-0.025)}{6},2.25+\frac{0.15\cdot\Phi^{-1}(1-0.025)}{6}\right]\\
&=\scriptstyle{(\text{operatoria})}\\
&\left[2.25-\frac{0.15\cdot\Phi^{-1}(0.975)}{6},2.25+\frac{0.15\cdot\Phi^{-1}(0.975)}{6}\right]\\
&\approx\scriptstyle{(\text{usando una tabla de la normal})}\\
&\left[2.25-\frac{0.15\cdot1.96}{6},2.25+\frac{0.15\cdot1.96}{6}\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[2.25-0.049,2.25+0.049\right]\\
&\approx\scriptstyle{(\text{operatoria})}\\
&\left[2.201,2.299\right]\\
\end{aligned}
$$

Esto concluye la parte 1.

### Parte 2

- ¿Qué tan grande tiene que ser la muestra si se desea tener una confianza del $95\%$ de que la media muestral no difiera en más de $0.03$ decilitros de la media real $\mu$?

Esta parte se complementa muy bien de la primera parte, ya que en esta ya calculamos el intervalo de confianza $0.95$, que es igual al que nos piden acá.
Lo único que cambia es la variación del "error" digamos, que sería el término por el cual restamos y sumamos para encontrar el intervalo de confianza.

Queremos que este término sea menor o igual a $0.03$, así que con esta premisa operamos.

$$
\begin{aligned}
&\frac{\sigma z_{(\alpha/2)}}{\sqrt{n}}\leq0.03\\
&\iff\scriptstyle{(\text{cálculo anterior})}\\
&\frac{0.15\cdot1.96}{\sqrt{n}}\leq0.03\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{0.15\cdot1.96}{0.03}\leq\sqrt{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&5\cdot1.96\leq\sqrt{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&9.8\leq\sqrt{n}\\
&=\scriptstyle{(\text{operatoria})}\\
&n\geq96.04
\end{aligned}
$$

Por lo tanto, con una muestra de al menos $97$ refrescos, nos aseguramos que la media muestral no difiera más de $0.03$ decilitros de la media real $\mu$.
Esto concluye el ejercicio.