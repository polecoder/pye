# Ejercicio 02 - Título

**Fecha:** 16-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Los resistores de cierto tipo tienen resistencias que en promedio son de $\mu=200$ ohms, con una desviación estándar de $\sigma=10$ ohms. Se toman (al azar) 25 de estos resistores y se conectan (en forma independiente) en un circuito.

1. Calcular la probabilidad (aproximada) de que la resistencia promedio de los 25 resistores esté entre $199$ y $202$ ohms.
2. Calcular la probabilidad (aproximada) de que la resistencia total de los 25 resistores no sea mayor que $5100$ ohms.

## Resolución

### Parte 1

- Calcular la probabilidad (aproximada) de que la resistencia promedio de los 25 resistores esté entre $199$ y $202$ ohms.

Esta parte es una aplicación muy directa del TCL. Tenemos que estandarizar, y para esto recordemos que:

- $\overline{X}_{25}\overset{d}{\approx} N(\mu,\sigma^2/n)$

Esto nos dice que el desvío por el que tenemos que dividir es justamente $10/\sqrt{25}$.

$$
\begin{aligned}
&P(199\leq \overline{X}_{25}\leq202)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(\frac{199-200}{10/\sqrt{25}}\leq Z_{25}\leq\frac{202-200}{10/\sqrt{25}}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P(-0.5\leq Z_{25}\leq1)\\
&=\scriptstyle{(Z_{25}\sim N(0,1))}\\
&\Phi(1)-\Phi(-0.5)\\
&=\scriptstyle{(\text{propiedades de }\Phi)}\\
&\Phi(1)+\Phi(0.5)-1\\
&\approx\scriptstyle{(\text{usando una tabla de la normal})}\\
&0.8413+0.6915-1\\
&\approx\scriptstyle{(\text{operatoria})}\\
&0.5328
\end{aligned}
$$

### Parte 2

- Calcular la probabilidad (aproximada) de que la resistencia total de los 25 resistores no sea mayor que $5100$ ohms.

Esta parte también es una aplicación muy directa del TCL como el caso anterior. Tiene un pequeño detalle y es que en este caso estaremos considerando la suma total, no el promedio. Esto cambia los valores de la esperanza y el desvío.

- $S_{25}\overset{d}{\approx}N(25\mu,25\sigma^2)$

Basándonos en esto podemos operar para estandarizar y obtener el resultado final

$$
\begin{aligned}
&P(S_{25}\leq5100)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(Z_{25}\leq\frac{5100-25\cdot200}{10\sqrt{25}}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P\left(Z_{25}\leq2\right)\\
&=\scriptstyle{(Z_{25}\sim N(0,1))}\\
&\Phi(2)\\
&\approx\scriptstyle{(\text{usando una tabla de la normal})}\\
&0.9772
\end{aligned}
$$

Esto concluye el ejercicio.