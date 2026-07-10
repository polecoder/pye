# Ejercicio 07 - Sesgo de un estimador

**Fecha:** 09-07-2026
**Estado:** 🟡 Con ayuda

## Consigna

Se considera una muestra $X_1,X_2,\ldots,X_n$ iid con media $E(X)=\mu$ y varianza $\text{Var}(X)=\sigma^2$. Se considera el estimador $\hat{\mu}=\sum_{i=1}^{n}a_iX_i$ (una combinación lineal de las observaciones).

1. Hallar la relación que tienen que cumplir los coeficientes $a_i$ para que $\hat{\mu}$ sea un estimador insesgado de la media $\mu$.
2. Entre todos los estimadores lineales e insesgados de la media $\mu$ hallar el de varianza mínima. Sugerencia: usar la desigualdad de Cauchy-Schwarz para vectores en $\mathbb{R}^n$.

## Resolución

### Parte 1

- Hallar la relación que tienen que cumplir los coeficientes $a_i$ para que $\hat{\mu}$ sea un estimador insesgado de la media $\mu$.

Para que el estimador dado $\hat{\mu}$ sea un estimador insesgado de la media $\mu$, la esperanza de este tiene que ser igual a $\mu$. Basándonos en esto, desarrollamos:

$$
\begin{aligned}
&E(\hat{\mu})\\
&=\scriptstyle{(\text{definición de }\hat{\mu})}\\
&E\left(\sum_{i=1}^na_iX_i\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\sum_{i=1}^n a_i\cdot E(X_i)\\
&=\scriptstyle{(\text{para todo }i:\ X_i=\mu)}\\
&\sum_{i=1}^n a_i\cdot\mu\\
&=\scriptstyle{(\text{sacando factor común }\mu)}\\
&\mu\cdot\sum_{i=1}^n a_i\\
\end{aligned}
$$

De este último punto, hallamos la condición que tienen que cumplir los coeficientes $a_i$, pues para que $E(\hat{\mu})=\mu$, se tiene que cumplir que:

$$
\boxed{
\sum_{i=1}^n a_i=1
}
$$

Esto concluye la parte 1.

### Parte 2

- Entre todos los estimadores lineales e insesgados de la media $\mu$ hallar el de varianza mínima. Sugerencia: usar la desigualdad de Cauchy-Schwarz para vectores en $\mathbb{R}^n$.

Veamos que podemos decir sobre la varianza del estimador $\hat\mu$

$$
\begin{aligned}
&Var(\hat\mu)\\
&=\scriptstyle{(\text{definición de }\hat\mu)}\\
&Var\left(\sum_{i=1}^na_iX_i\right)\\
&=\scriptstyle{(\text{por independencia de las }X_i)}\\
&\sum_{i=1}^nVar(a_iX_i)\\
&=\scriptstyle{(\text{propiedades de la varianza})}\\
&\sum_{i=1}^na_i^2\cdot Var(X_i)\\
&=\scriptstyle{(Var(X_i)=\sigma^2)}\\
&\sum_{i=1}^na_i^2\sigma^2\\
&=\scriptstyle{(\text{operatoria})}\\
&\sigma^2\cdot\sum_{i=1}^na_i^2\\
\end{aligned}
$$

Queremos minimizar dicha expresión, que es lo mismo que minimizar la sumatoria del cuadrado de los coeficientes $a_i$.
Consideramos los vectores:

- $a=(a_1,a_2,\ldots,a_n)$
- $v=(1,1,\ldots,1)$

Ahora planteamos la desigualdad de Cauchy-Schwarz para dichos vectores y desarrollamos:

$$
\begin{aligned}
&\left<a, v\right>^2\leq\|a\|^2\|v\|^2\\
&=\scriptstyle{(\text{producto interno estándar})}\\
&\left(\sum_{i=1}^na_i\right)^2\leq\sum_{i=1}^na_i^2\cdot\sum_{i=1}^n1^2\\
&=\scriptstyle{(\text{operatoria y resultado de la parte 1})}\\
&1^2\leq\sum_{i=1}^na_i^2\cdot n\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{n}\leq\sum_{i=1}^na_i^2
\end{aligned}
$$

Entonces lo mínimo que puede valer dicha sumatoria es $1/n$, que sucede cuando existe igualdad.
Recordemos que la desigualdad de Cauchy-Schwarz se convierte en igualdad sii los vectores son proporcionales es decir si $a=k\cdot v$ para algún $k\in\mathbb{K}$, esto nos permite desarrollar:

$$
\begin{aligned}
&a=k\cdot v\\
&\iff\scriptstyle{(\text{expandiendo los vectores})}\\
&a_i=k\cdot v_i\quad\forall i\in\{1,\ldots,n\}\\
&\iff\scriptstyle{(\text{valor de }v_i)}\\
&a_i=k\quad(*_1)\\
\end{aligned}
$$

Además hallamos en la parte 1 que la suma de todos los coeficientes $a_i$ es igual a uno, entonces reemplazando esto en el resultado mencionado, obtenemos:

$$
\begin{aligned}
&\sum_{i=1}^na_i=1\\
&\iff\scriptstyle{(\text{por }*_1)}\\
&nk=1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&k=\frac{1}{n}\\
\end{aligned}
$$

Entonces, concluimos que:

$$
\boxed{
a_i=\frac{1}{n}\quad\forall i\in\{1,\ldots, n\}
}
$$

Por lo tanto, el estimador $\hat\mu$ que minimiza la varianza es el promedio muestral:

$$
\boxed{
\hat\mu=\frac{1}{n}\sum_{i=1}^nX_i
}
$$

Esto concluye el ejercicio.
