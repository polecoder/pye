# Clase 12 - Covarianza

**Fecha:** 30-06-2026

## Covarianza y correlación

¿Cómo hacemos para medir la dependencia entre dos v.a.? En esta clase veremos una primera aproximación a este problema.
Sean $X$ e $Y$ dos variables aleatorias con varianza finita. Comencemos por notar lo siguiente: si la varianza $Var(X-Y)$ es pequeña, entonces intuitivamente $Y$ es muy parecida a $X$.
En general, $Y$ puede depender fuertemente de $X$, sin ser igual a ella. Por ejemplo, la forma más fuerte de dependencia es cuando $Y$ es una función de $X$, es decir cuando existe una función $g:\mathbb{R}\to\mathbb{R}$ tal que $Y=g(X)$.

Una forma de medir cuán cerca está $Y$ de ser una función de $X$ es entonces minimizar la varianza $Var(Y-g(X))$ entre todas las funciones posibles $g$.
Naturalmente, si $Y=g(X)$ para alguna $g$, entonces el mínimo es cero. Por otro lado, si $Y$ es independiente de $X$, entonces:

$$
Var(Y-g(X))=Var(Y)+Var(g(X))\geq Var(Y)
$$

Esto pues la varianza es siempre positiva. Con esto entonces vemos que el mínimo es $Var(Y)$.
Consideremos ahora el problema de encontrar:

$$
v=\frac{\min\limits_{g}\{Var(Y-g(X))\}}{Var(Y)}
$$

Donde dividimos por $Var(Y)$ para que $v=[0,1]$.
Veremos el problema de calcular $v$ en toda su generalidad más adelante. Por ahora, empecemos por calcular el mínimo entre aquellas funciones que son lineales.
Nos restringiremos entonces a funciones $g(x)=ax$, y buscamos:

$$
v_L=\frac{\min\limits_{a\in\mathbb{R}}\{Var(Y-aX)\}}{Var(Y)}
$$

De la definición de varianza, tenemos que:

$$
\begin{aligned}
&Var(Y-aX)\\
&=\scriptstyle{(\text{definición de varianza})}\\
&E((Y-aX-E(Y-aX))^2)\\
&=\scriptstyle{(\text{operatoria})}\\
&E((Y-aX-E(Y)+E(aX))^2)\\
&=\scriptstyle{(\text{operatoria})}\\
&E((Y-aX-E(Y)+aE(X))^2)\\
&=\scriptstyle{(\text{operatoria})}\\
&E((Y-E(Y)-a(X-E(X)))^2)\\
\end{aligned}
$$

Desde este punto, desarrollando el cuadrado terminamos llegando a:

$$
\begin{aligned}
&Var(Y-aX)\\
&=\scriptstyle{(\text{desarrollando el cuadrado})}\\
&a^2Var(X)-2aE((Y-E(Y))(X-E(X)))+Var(Y)
\end{aligned}
$$

Que es un polinomio cuadrático de $a$, por lo que derivando e igualando a cero, obtenemos que el mínimo se da en:

$$
\begin{aligned}
&a_0\\
&=\scriptstyle{(\text{derivando e igualando a cero})}\\
&\frac{E((Y-E(Y)(X-E(X))))}{Var(X)}\\
\end{aligned}
$$

El numerador de esta expresión es tan importante que tiene un nombre propio, se llama la covarianza de $X$ e $Y$ y se escribe $Cov(X,Y)$. Un cálculo sencillo, similar a los que ya hemos hecho, muestra que podemos escribir la covarianza como:

$$
\boxed{
Cov(X,Y)=E(XY)-E(X)E(Y)
}
$$

Para aliviar un poco la notación, denotamos:

$$
\sigma^2_X=Var(X);\ \sigma^2_Y=Var(Y);\ \sigma_{XY}=Cov(X,Y)
$$

Reemplazando el valor de $a_0$ en la ecuación para $v_L$, vemos entonces que:

$$
v_L=1-\left(\frac{\sigma_{XY}}{\sigma_{X}\sigma_{Y}}\right)^2
$$

Donde el número que aparece elevado al cuadrado se conoce como el **coeficiente de correlación lineal** entre $X$ e $Y$, y se denota por $\rho_{XY}$, o simplemente $\rho$ si se está claro con que variables se está trabajando.
Así que:

$$
\boxed{
v_L=1-\rho^2\quad\text{con }\rho=\frac{\sigma_{XY}}{\sigma_X\sigma_Y}
}
$$

## Covarianza e independencia

Si $X$ e $Y$ son independientes, entonces $\boxed{Cov(X,Y)=0}$. Esto es debido a que en este caso tenemos que:

- $E(XY)=E(X)E(Y)$

Tengamos presente que el recíproco no es cierto en general.

## Propiedades de la covarianza

### Desigualdad de Cauchy-Schwarz

Observemos primero una desigualdad notable que se deduce de lo que vimos hasta ahora. Claramente, el coeficiente $v_L$ es mayor a cero por definición. Esto implica que $|\rho_{XY}|\leq1$. Operemos con esto en mente para llegar a una desigualdad interesante.

$$
\begin{aligned}
&|\rho_{XY}|\leq1\\
&\iff\scriptstyle{(\text{definición de }\rho)}\\
&\left|\frac{\sigma_{XY}}{\sigma_X\sigma_Y}\right|\leq1\\
&\iff\scriptstyle{(\sigma_X,\sigma_Y\text{ son siempre positivos por definición})}\\
&\frac{|\sigma_{XY}|}{\sigma_X\sigma_Y}\leq1\\
&\iff\scriptstyle{(\text{operatoria})}\\
&|\sigma_{XY}|\leq\sigma_X\sigma_Y\\
&\iff\scriptstyle{(\text{notación extendida})}\\
&\boxed{
|Cov(X,Y)|\leq \sqrt{Var(X)}\sqrt{Var(Y)}
}\\
\end{aligned}
$$

Que es la famosa desigualdad de Cauchy-Schwarz. Esto nos sugiere que la covarianza tiene las propiedades de un producto interno.

### Propiedades derivadas de ser un producto interno

Claramente la covarianza es simétrica, esto es:

$$
\boxed{
Cov(X,Y)=Cov(Y,X)
}
$$

Por otra parte, si $Cov(X,X)=0$ entonces $Var(X)=0$, y esto implica que $X$ es una constante. Como las v.a. que son constantes no son muy interesantes, las trataremos como variables triviales, es así que obtenemos otra propiedad:

$$
\boxed{
Cov(X,X)=0\iff X\text{ es trivial}
}
$$

Y por último, la covarianza es bi-lineal. Es decir, si $X,Y,Z$ son tres v.a. y $a$ es una constante, entonces:

$$
\boxed{
Cov(aX+Y,Z)=a\cdot Cov(X,Z)+Cov(Y,Z)
}
$$

Demostremos esta última que es menos directa que las anteriores.

#### Demostración de bi-linealidad

Primero observemos que:

$$
E(aX+Y)=aE(X)+E(Y)
$$

Ahora operamos con la definición de covarianza:

$$
\begin{aligned}
&Cov(aX+Y,Z)\\
&=\scriptstyle{(\text{definición de covarianza})}\\
&E((aX+Y)Z)-E(aX+Y)E(Z)\\
&=\scriptstyle{(\text{operatoria y reemplazando valores conocidos})}\\
&E(aXZ+YZ)-(aE(X)+E(Y))E(Z)\\
&=\scriptstyle{(\text{operatoria y propiedades de esperanza})}\\
&E(aXZ)+E(YZ)-aE(X)E(Z)-E(Y)E(Z)\\
&=\scriptstyle{(\text{operatoria y propiedades de esperanza})}\\
&aE(XZ)-aE(X)E(Z)+E(YZ)-E(Y)E(Z)\\
&=\scriptstyle{(\text{operatoria})}\\
&a(E(XZ)-E(X)E(Z))+E(YZ)-E(Y)E(Z)\\
&=\scriptstyle{(\text{definición de covarianza})}\\
&a\cdot Cov(X,Z)+Cov(Y,Z)\\
\end{aligned}
$$

Que es lo que queríamos demostrar. $\blacksquare$