# Ejercicio 09 - Sesgo de un estimador

**Fecha:** 12-07-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Sean $X_1,\ldots,X_n\sim U[0,\theta]$ i.i.d. Interesa estimar el valor de $\theta$.

1. Hallar el estimador de $\theta$ por el método de los momentos.
2. Estudiar su sesgo, varianza y error cuadrático medio.
3. Demostrar que el estimador de máxima verosimilitud de $\theta$ es $X_n^*$, el máximo de los valores muestrales.

## Resolución

### Parte 1

- Hallar el estimador de $\theta$ por el método de los momentos.

Como queremos hallar un solo parámetro, recordemos que el método de los momentos nos da la siguiente ecuación:

$$
E(X)=\overline{X}_n
$$

Y como sabemos que la esperanza de $X\sim U[0,\theta]$ es $\theta/2$, podemos obtener el estimador sustituyendo en la ecuación anterior

$$
\begin{aligned}
&E(X)=\overline{X}_n\\
&\iff\scriptstyle{(E(X)=\theta/2)}\\
&\frac{\theta}{2}=\overline{X}_n\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\boxed{
\hat\theta=2\overline{X}_n
}\\
\end{aligned}
$$

### Parte 2

- Estudiar su sesgo, varianza y error cuadrático medio.

Yendo en orden, con respecto al sesgo del estimador, operemos para ver que devuelve su esperanza.

$$
\begin{aligned}
&E(\hat\theta)\\
&=\scriptstyle{(\text{definición de }\hat\theta)}\\
&E(2\overline{X}_n)\\
&=\scriptstyle{(\text{definición de promedio muestral y propiedades de esperanza})}\\
&2\cdot E\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de esperanza})}\\
&\frac{2}{n}\cdot\left(\sum_{i=1}^nE(X_i)\right)\\
&=\scriptstyle{(\text{recordando que }E(X_i)=\theta/2)}\\
&\frac{2}{n}\cdot\frac{n\theta}{2}\\
&=\scriptstyle{(\text{operatoria})}\\
&\theta
\end{aligned}
$$

Con esto concluimos que $\hat\theta$ es un estimador insesgado.
Pasemos ahora a calcular su varianza.

$$
\begin{aligned}
&Var(\hat\theta)\\
&=\scriptstyle{(\text{definición de }\hat\theta)}\\
&Var(2\overline{X}_n)\\
&=\scriptstyle{(\text{propiedades de la varianza})}\\
&4\cdot Var\left(\frac{1}{n}\sum_{i=1}^nX_i\right)\\
&=\scriptstyle{(\text{propiedades de la varianza por independencia})}\\
&4\cdot\frac{1}{n^2}\cdot\left(\sum_{i=1}^nVar(X_i)\right)\\
&=\scriptstyle{(Var(X_i)=\theta^2/12)}\\
&\frac{4}{n^2}\cdot\frac{n\theta^2}{12}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{\theta^2}{3n}
\end{aligned}
$$

Nos faltaría tener la definición formal de error cuadrático medio, que es la siguiente:

El **Error Cuadrático Medio (ECM)** mide que tan "cerca" está un estimador del parámetro real, considerando tanto su varianza como su alejamiento sistemático. Se define por:

$$
\boxed{
ECM(\hat\theta)=Var(\hat\theta)+[Sesgo(\hat\theta)]^2
}
$$

En este caso, el sesgo es cero pues el estimador es insesgado, entonces el error cuadrático es:

$$
ECM(\hat\theta)=\frac{\theta^2}{3n}
$$

Esto concluye la parte dos.

### Parte 3

- Demostrar que el estimador de máxima verosimilitud de $\theta$ es $X_n^*$, el máximo de los valores muestrales.

Recordemos que la densidad de la variable $X\sim U[0,\theta]$ está dada por:

$$
f_x(x)=
\begin{cases}
\frac{1}{\theta}&\text{si }0\leq x\leq\theta\\
0&\text{en otro caso}
\end{cases}
$$

Entonces, para que la función de verosimilitud tenga sentido, es decir que sea distinta de cero, precisamos que todos los valores muestrales estén entre $0$ y $\theta$. Esto nos lleva a definir $L(\theta)$ de la siguiente forma:

$$
\begin{aligned}
&L(\theta)\\
&=\scriptstyle{(\text{definición de }L)}\\
&\prod_{i=1}^n\frac{1}{\theta}\\
&=\scriptstyle{(\text{operatoria})}\\
&\frac{1}{\theta^n}\\
\end{aligned}
$$

Recordemos y marquemos que este razonamiento solo tiene sentido si:

$$
\boxed{
x_i\leq\theta\quad\forall i\in\{1,\ldots,n\}
}
$$

Por lo tanto, definiendo $X_n^*=\max\{x_1,\ldots,x_n\}$, también podemos concluir que:

$$
\boxed{
X_n^*\leq\theta
}\quad(*_1)
$$

Para rematar el problema, observemos que $L(\theta)$ es una función estrictamente decreciente, y nosotros queremos maximizar la función. Observemos que a medida que $\theta$ aumenta, la función se vuelve más y más pequeña. Además por $*_1$ sabemos que:

$$
X_n^*\leq\theta
$$

Entonces el valor que maximiza la función es el más chico que puede ser, es decir:

$$
\boxed{
\hat\theta=X_n^*
}
$$

$$
\boxed{
x_i\leq\theta\quad\forall i\in\{1,\ldots,n\}
}
$$

Esto concluye el ejercicio.
