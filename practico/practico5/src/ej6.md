# Ejercicio 06 - Variables aleatorias continuas

**Fecha:** 28-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Suponga que la concentración de cierto contaminante se encuentra distribuida uniformemente en el intervalo de 4 a 20 $ppm$ (partes por millón). Si se considera tóxica una concentración de 15 $ppm$ o más, ¿cuál es la probabilidad de que al tomar una muestra la concentración sea tóxica?

## Resolución

Como la concentración está distribuida uniformemente en el intervalo, y además conocemos los extremos, tenemos la función densidad definida por:

$$
f_X(x)=\begin{cases}
\frac{1}{16}&\text{si }4\leq x\leq 20\\
0&\text{en otro caso}
\end{cases}
$$

**Nota:** Solo para aclarar, el $16$ del denominador corresponde a $20-4=16$.

Y bueno, queremos considerar la probabilidad de que la concentración sea tóxica, es decir $P(X\geq15)$, operando:

$$
\begin{aligned}
&P(X\geq15)=\int_{15}^{20}f_X(x)dx\\
&\iff\scriptstyle{(\text{definición de }f_X)}\\
&P(X\geq15)=\int_{15}^{20}\frac{1}{16}dx\\
&\iff\scriptstyle{(\text{operatoria y Barrow})}\\
&P(X\geq15)=\frac{20}{16}-\frac{15}{16}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\geq15)=\frac{5}{16}\\
\end{aligned}
$$

Esto concluye el ejercicio.
