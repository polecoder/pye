# Ejercicio 04 - Estimación puntual

**Fecha:** 08-07-2026
**Estado:** 🟡 Con ayuda

## Consigna

Sea una sucesión de variables aleatorias $X_1,X_2,\ldots,X_n$ iid tal que $P\{X_1=1\}=P\{X_1=-1\}=a$ y $P\{X_1=0\}=1-2a$ donde $0<a<1/2$. Dar por el método de los momentos un estimador consistente del parámetro $a$.

## Resolución

Para empezar tendremos que notar que la letra ya nos da el recorrido completo de la función de probabilidad. Esto es fundamental para poder calcular la esperanza y así trabajar con el método de los momentos. Esto es así pues:

$$
a+a+(1-2a)=1
$$

Calculemos la esperanza de $X$ usando la definición:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{expandiendo la suma})}\\
&a-a\\
&=\scriptstyle{(\text{operatoria})}\\
&0\\
\end{aligned}
$$

Como vimos, la esperanza de $X$ no depende de $a$. Por esta razón, no podemos usar simplemente la primera ecuación para hallar el estimador que buscamos. Esto nos lleva a plantear la segunda ecuación:

$$
\begin{aligned}
&E(X^2)=\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}x^2p(x)=\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{expandiendo la suma})}\\
&a+a=\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&2a=\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&a=\frac{1}{2}\cdot\frac{1}{n}\sum_{i=1}^nX_i^2\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\boxed{\hat{a}=\frac{1}{2}\cdot\overline{X_n^2}}\\
\end{aligned}
$$

Probamos que $\hat{a}$ es consistente basándonos en la ley fuerte de los grandes números:

$$
\begin{aligned}
&\hat{a}\xrightarrow[n]{c.s.}a\\
&\iff\scriptstyle{(\text{reemplazando }\hat{a})}\\
&\frac{1}{2}\cdot\overline{X_n^2}\xrightarrow[n]{c.s.}a\\
&\iff\scriptstyle{(\text{ley fuerte de los grandes números para }\overline{X_n^2})}\\
&\frac{1}{2}\cdot E(X^2)\xrightarrow[n]{c.s.}a\\
&\iff\scriptstyle{(\text{propiedades de convergencia casi segura})}\\
&E(X^2)\xrightarrow[n]{c.s.}2a\\
\end{aligned}
$$

Y esto último ya sabemos que se cumple pues lo calculamos en los pasos anteriores. Con lo que queda demostrado que $\hat{a}$ es consistente.
