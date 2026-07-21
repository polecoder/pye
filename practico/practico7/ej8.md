# Ejercicio 08 - Esperanza y varianza de una v.a.

**Fecha:** 29-06-2026
**Estado:** 🟡 Con ayuda

## Consigna

Calcular esperanza y varianza de la distribución $H(n;N;D)$ (hipergeométrica).

## Resolución

Recordemos que la distribución hipergeométrica está dada por:

$$
X\sim H(n;N;D)\iff P(X=k)=\frac{\binom{N-D}{n-k}\binom{D}{k}}{\binom{N}{n}}
$$

### Lema #1

Para resolver este ejercicio necesitaremos una identidad para facilizar los cálculos. En particular observemos que:

$$
\begin{aligned}
&x\binom{D}{x}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&\frac{x\cdot D!}{(D-x)!x!}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{D!}{(D-x)!(x-1)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&D\cdot\frac{(D-1)!}{(D-x)!(x-1)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&D\cdot\frac{(D-1)!}{((D-\cancel{1})-(x-\cancel{1}))!(x-1)!}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&D\binom{D-1}{x-1}\\
\end{aligned}
$$

Este razonamiento es válido para cualquier $x\geq1$.

### Lema #2: Identidad de Vandermonde

Necesitaremos también comprender la siguiente identidad para poder resolver el ejercicio:

$$
\binom{m+n}{r}=\sum_{k=0}^r\binom{m}{k}\binom{n}{r-k}
$$

No entraremos al detalle matemática de porque funciona, pero lo explicaremos con una analogía sencilla.

Imaginemos que tenemos una bolsa con $m$ manzanas rojas y $n$ manzanas verdes. Queremos elegir $r$ manzanas en total sin importar el color.
- El lado izquierdo de la igualdad representa la parte más fácil, simplemente ignoro los colores y elijo usando combinaciones tomando del total de manzanas $(m+n)$.
- El lado derecho representa lo mismo, pero pensado en partes: sumas todas las formas de elegir $k$ manzanas rojas y luego completar el resto eligiendo manzanas verdes.

### Lema #3

Veamos otra identidad que usaremos para el cálculo de la varianza.

$$
\begin{aligned}
&x(x-1)\binom{D}{x}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&x(x-1)\frac{D!}{(D-x)!x!}\\
&=\scriptstyle{(\text{operatoria})}\\
&\cancel{x(x-1)}\frac{D!}{(D-x)!\cancel{x(x-1)}(x-2)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{D!}{(D-x)!(x-2)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&D(D-1)\frac{(D-2)!}{(D-x)!(x-2)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&D(D-1)\frac{(D-2)!}{((D-2)-(x-2))!(x-2)!}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&D(D-1)\binom{D-2}{x-2}\\
\end{aligned}
$$

### Continuación

Con esto podemos operar para obtener la esperanza:

$$
\begin{aligned}
&E(X)\\
&=\scriptstyle{(\text{definición de esperanza})}\\
&\sum_{x\in R_X}xp(x)\\
&=\scriptstyle{(\text{operatoria y reemplazando por }p(x))}\\
&\frac{1}{\binom{N}{n}}\sum_{x\in R_X}x\cdot\binom{N-D}{n-x}\binom{D}{x}\\
&=\scriptstyle{(\text{por el lema \#1})}\\
&\frac{1}{\binom{N}{n}}\sum_{x\in R_X}D\binom{D-1}{x-1}\binom{N-D}{n-x}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{D}{\binom{N}{n}}\sum_{x\in R_X}\binom{D-1}{x-1}\binom{(N-1)-(D-1)}{(n-1)-(x-1)}\\
&=\scriptstyle{(\text{identidad de Vandermonde})}\\
&\frac{D}{\binom{N}{n}}\cdot\binom{N-1}{n-1}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&D\cdot\frac{\cancel{(N-n)!}n!}{N!}\cdot\frac{(N-1)!}{\cancel{(N-n)!}(n-1)!}\\
&=\scriptstyle{(\text{operatoria})}\\
&D\cdot\frac{n\cdot \cancel{(n-1)!}}{N\cdot \cancel{(N-1)!}}\cdot\frac{\cancel{(N-1)!}}{\cancel{(n-1)!}}\\
&=\scriptstyle{(\text{operatoria})}\\
&D\cdot\frac{n}{N}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\\
\end{aligned}
$$

Con esto, estamos en condiciones de calcular la varianza:

$$
\begin{aligned}
&Var(X)\\
&=\scriptstyle{(\text{propiedades de varianza})}\\
&E(X^2)-E(X)^2\\
&=\scriptstyle{(\text{reemplazando los valores conocidos y operatoria})}\\
&E(X(X-1))+E(X)-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{definición de esperanza y reemplazando los valores conocidos})}\\
&\sum_{x\in R_X}(x(x-1)p(x))+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{definición de }p(x))}\\
&\frac{1}{\binom{N}{n}}\sum_{x\in R_X}\left(x(x-1)\binom{N-D}{n-x}\binom{D}{x}\right)+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{por lema \#3})}\\
&\frac{1}{\binom{N}{n}}\sum_{x\in R_X}\left(D(D-1)\binom{D-2}{x-2}\binom{N-D}{n-x}\right)+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{D(D-1)}{\binom{N}{n}}\sum_{x\in R_X}\left(\binom{D-2}{x-2}\binom{(N-2)-(D-2)}{(n-2)-(x-2)}\right)+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{identidad de Vandermonde})}\\
&\frac{D(D-1)}{\binom{N}{n}}\binom{N-2}{n-2}+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{definición de combinaciones})}\\
&D(D-1)\cdot\frac{(N-n)!n!}{N!}\cdot\frac{N-2!}{(N-n)!(n-2)!}+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&D(D-1)\cdot\frac{n(n-1)}{N(N-1)}+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{D(D-1)\cdot n(n-1)}{N(N-1)}+\frac{Dn}{N}-\frac{D^2n^2}{N^2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{(D-1)(n-1)}{N-1}+1-\frac{Dn}{N}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{N(D-1)(n-1)+N(N-1)-(N-1)Dn}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{\cancel{NDn}-ND-Nn+\cancel{N}+N^2-\cancel{N}-\cancel{NDn}+Dn}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{-ND-Nn+N^2+Dn}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{-ND+N^2-Nn+Dn}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{N(N-D)-n(N-D)}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\left(\frac{(N-n)(N-D)}{N(N-1)}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{Dn}{N}\cdot\frac{(N-D)}{N}\cdot\frac{N-n}{N-1}\\
\end{aligned}
$$

Después de un largo sufrimiento de cuentas... Llegamos al resultado final.

Esto concluye el ejercicio