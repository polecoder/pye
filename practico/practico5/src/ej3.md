# Ejercicio 03 - Variables aleatorias continuas

**Fecha:** 27-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se considera la variable aleatoria $X$ absolutamente continua con densidad:

$$f_X(x)=\begin{cases}0 & \text{si }x<0\\bx & \text{si }x\in(0,1]\\ae^{-x} & \text{si }x>1\end{cases}$$

Hallar $a$ y $b$ sabiendo que $P(X\in[0,2])=2P(X\in[2,4])$.

## Resolución

Para empezar, vayamos a lo más fácil de calcular que tenemos, que es:

- $P(X\in[2,4])$

Esto porque es la integral de la misma función en todo el intervalo.

$$
\begin{aligned}
&P(X\in[2,4])=\int_{2}^{4}f_X(x)dx\\
&\iff\scriptstyle{(\text{reemplazando por la función conocida})}\\
&P(X\in[2,4])=\int_{2}^{4}ae^{-x}dx\\
&\iff\scriptstyle{(\text{propiedades de integrales})}\\
&P(X\in[2,4])=a\int_{2}^{4}e^{-x}dx\\
&\iff\scriptstyle{(\text{integrando ya con Barrow})}\\
&P(X\in[2,4])=a\left(-e^{-4}+e^{-2}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\in[2,4])=ae^{-2}\left(-e^{-2}+1\right)\\
\end{aligned}
$$

Ahora veamos que sucede con la otra integral:

$$
\begin{aligned}
&P(X\in[0,2])=\int_{0}^{2}f_X(x)dx\\
&\iff\scriptstyle{(\text{propiedades de integrales})}\\
&P(X\in[0,2])=\int_{0}^{1}f_X(x)dx+\int_{1}^{2}f_X(x)dx\\
&\iff\scriptstyle{(\text{definición de }f_X)}\\
&P(X\in[0,2])=\int_{0}^{1}bxdx+\int_{1}^{2}ae^{-x}dx\\
&\iff\scriptstyle{(\text{propiedades de integrales})}\\
&P(X\in[0,2])=b\int_{0}^{1}xdx+a\int_{1}^{2}e^{-x}dx\\
&\iff\scriptstyle{(\text{aplicando Barrow})}\\
&P(X\in[0,2])=b\cdot\left(\frac{1^2}{2}-0\right)+a\left(-e^{-2}+e^{-1}\right)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(X\in[0,2])=\frac{b}{2}+a\left(-e^{-2}+e^{-1}\right)\\
\end{aligned}
$$

Entonces tenemos una primera ecuación correspondiente a la igualdad planteada en la letra:

$$
\begin{aligned}
&P(X\in[0,2])=2P(X\in[2,4])\\
&\iff\scriptstyle{(\text{reemplazando lo conocido})}\\
&\frac{b}{2}+ae^{-1}(-e^{-1}+1)=2\cdot ae^{-2}(-e^{-2}+1)
\end{aligned}
$$

Por otra parte, podemos usar la condición de normalización, con lo que sabemos que:

$$
\begin{aligned}
&\int_{-\infty}^{+\infty}f_X(dx)=1\\
&\iff\scriptstyle{(\text{propiedades de integrales})}\\
&\int_{-\infty}^{0}f_X(dx)+\int_{0}^{1}f_X(dx)+\int_{1}^{+\infty}f_X(dx)=1\\
&\iff\scriptstyle{(\text{usando la definición de }f_X)}\\
&0+\int_{0}^{1}bxdx+\int_{1}^{+\infty}ae^{-x}dx=1\\
&\iff\scriptstyle{(\text{aplicando Barrow})}\\
&b\left(\frac{1^2}{2}+0\right)+a\left(\lim_{x\to+\infty}-e^{-x}+e^{-1}\right)=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{b}{2}+a\left(0+e^{-1}\right)=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{b}{2}+ae^{-1}=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{b}{2}=1-ae^{-1}\\
\end{aligned}
$$

Vamos a parar "estratégicamente" en este punto, ya que quién aparece en la igualdad planteada en la letra es $b/2$. Con esto podemos reemplazar todo en la igualdad mencionada.

$$
\begin{aligned}
&P(X\in[0,2])=2P(X\in[2,4])\\
&\iff\scriptstyle{(\text{reemplazando lo conocido})}\\
&\frac{b}{2}+ae^{-1}(-e^{-1}+1)=2\cdot ae^{-2}(-e^{-2}+1)\\
&\iff\scriptstyle{(\text{usando que }\frac{b}{2}=1-ae^{-1})}\\
&1-ae^{-1}+ae^{-1}(-e^{-1}+1)=2\cdot ae^{-2}(-e^{-2}+1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&1-ae^{-1}(-e^{-1}+\cancel{1}-\cancel{1})=2\cdot ae^{-2}(-e^{-2}+1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&1-ae^{-2}=2\cdot ae^{-2}(-e^{-2}+1)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&1-ae^{-2}=-2ae^{-4}+2ae^{-2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&1=-2ae^{-4}+3ae^{-2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{a}=-2e^{-4}+3e^{-2}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&a=\frac{1}{-2e^{-4}+3e^{-2}}\\
\end{aligned}
$$

Ahora podemos reemplazar $a$ en la segunda ecuación, para obtener que:

$$
\begin{aligned}
&\frac{b}{2}=1-ae^{-1}\\
&\iff\scriptstyle{(\text{reemplazando el valor conocido }a)}\\
&\frac{b}{2}=1-\frac{e^{-1}}{-2e^{-4}+3e^{-2}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&b=2-\frac{2}{-2e^{-3}+3e^{-1}}\\
\end{aligned}
$$

Esto concluye el ejercicio.
