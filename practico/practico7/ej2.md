# Ejercicio 02 - Esperanza de una v.a.

**Fecha:** 26-06-2026
**Estado:** 🟢 Resuelto solo

## Consigna

La función de probabilidad de una variable aleatoria discreta $X$ está dada por:

$$p_X(x)=K\binom{3}{x}\left(\frac{1}{4}\right)^x\left(\frac{3}{4}\right)^{3-x}\qquad\text{con }x=1,2,3$$

Hallar $K$ y la esperanza de $X$.

## Resolución

Este ejercicio se va a separar en dos partes, primero tenemos que hallar $K$, para esto nos conviene simplemente usar propiedades de funciones de probabilidad. Luego hallaremos la esperanza de $X$.

### Hallar $K$

Solo tenemos tres elementos en $R_X$, por lo que la estrategia que usaremos será sumar las probabilidades de los tres, y verificar que de 1, formalmente verificaremos que la f.d.a. cumpla con la propiedad de valer 1 al hacerla tender a infinito.

$$
\begin{aligned}
&\sum_{x\in R_X}p_X(x)=1\\
&\iff\scriptstyle{(\text{reemplazando por }p_X)}\\
&\sum_{x\in R_X}K\binom{3}{x}\left(\frac{1}{4}\right)^x\left(\frac{3}{4}\right)^{3-x}=1\\
&\iff\scriptstyle{(\text{expandiendo la suma})}\\
&K\left(\binom{3}{1}\left(\frac{1}{4}\right)^1\left(\frac{3}{4}\right)^{3-1}+\binom{3}{2}\left(\frac{1}{4}\right)^2\left(\frac{3}{4}\right)^{3-2}+\binom{3}{3}\left(\frac{1}{4}\right)^3\left(\frac{3}{4}\right)^{3-3}\right)=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&K\left(3\cdot\frac{1}{4}\cdot\frac{9}{16}+3\cdot\frac{1}{16}\cdot\frac{3}{4}+1\cdot\frac{1}{64}\cdot1\right)=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&K\left(\frac{27}{64}+\frac{9}{64}+\frac{1}{64}\right)=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&K\cdot\frac{37}{64}=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&K=\frac{64}{37}\\
\end{aligned}
$$

Aprovechando que ya hicimos la suma para calcular $K$, podemos reutilizarla en la definición de esperanza para encontrar la respuesta.

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{usando el desarrollo anterior})}\\
&\frac{64}{37}\left(\frac{27}{64}+2\cdot\frac{9}{64}+3\cdot\frac{1}{64}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{64}{37}\left(\frac{27}{64}+\frac{18}{64}+\frac{3}{64}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{64}{37}\cdot\frac{48}{64}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{48}{37}\\
\end{aligned}
$$

Por lo tanto, concluimos que la esperanza de $X$ vale $48/37\approx1.29730$.