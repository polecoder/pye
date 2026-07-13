# Clase 16 - Teorema central del límite

**Fecha:** 13-07-2026

## Teorema central del límite

Si $X$ es una variable aleatoria con esperanza $\mu$ y varianza $\sigma^2$, la estandarización de $X$ es la variable:

$$
Z=\frac{X-\mu}{\sigma}
$$

Observemos que $Z$ tiene esperanza $0$ (decimos que está centrada) y varianza 1 (se dice que está normalizada). Notemos que la estandarización de $X$ no tiene porque tener distribución normal estándar, esto solo pasa si $X$ originalmente es normal.

Sean $X_1,\ldots,X_n$ variables i.i.d. con esperanza $\mu=E(X_i)$ y varianza $\sigma^2=Var(X_i)$. Como antes lo hemos hecho, escribimos:

- $S_n=X_1+\ldots+X_n$
- $\overline{X}_n=\frac{X_1+\ldots+X_n}{n}$

Pero además introduciremos un nuevo miembro a esta lista. En la siguiente sección demostraremos que $S_n$ y $\overline{X}_n$ tienen la misma estandarización.

### Lema

Demostraremos que $S_n$ y $\overline{X}_n$ tienen la misma estandarización. Calculamos primero las estandarizaciones de $S_n$ y $\overline{X}_n$ y luego las igualamos. 

$$
\begin{aligned}
&Z_1\\
&=\scriptstyle{(\text{definción de estandarización para } S_n)}\\
&\frac{S_n-n\mu}{\sqrt{n}\sigma}
\end{aligned}
$$

Y por otra parte:

$$
\begin{aligned}
&Z_2\\
&=\scriptstyle{(\text{definición de estándarización para }\overline{X}_n)}\\
&\frac{\overline{X}_n-\mu}{\frac{\sigma}{\sqrt{n}}}
\end{aligned}
$$

Comparándolas, tenemos que:

$$
\begin{aligned}
&Z_1=Z_2\\
&\iff\scriptstyle{(\text{definición de }Z_1,Z_2)}\\
&\frac{S_n-n\mu}{\sqrt{n}\sigma}=\frac{\overline{X}_n-\mu}{\frac{\sigma}{\sqrt{n}}}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{S_n-n\mu}{\sqrt{n}\sigma}=\frac{\sqrt{n}\cdot\overline{X}_n-\sqrt{n}\mu}{\sigma}\\
&\iff\scriptstyle{(\text{multiplicando el lado derecho por }\frac{\sqrt{n}}{\sqrt{n}})}\\
&\frac{S_n-n\mu}{\sqrt{n}\sigma}=\frac{n\cdot\overline{X}_n-n\mu}{\sqrt{n}\sigma}\\
&=\scriptstyle{(\text{usando que }n\cdot\overline{X}_n=S_n)}\\
&\frac{S_n-n\mu}{\sqrt{n}\sigma}=\frac{S_n-n\mu}{\sqrt{n}\sigma}\\
\end{aligned}
$$

Esto demuestra que $S_n$ y $\overline{X}_n$ tienen la misma estandarización. $\blacksquare$

### Continuación

Con el lema demostrado, el nuevo miembro que introducimos es:

$$
Z_n=\frac{S_n-n\mu}{\sqrt{n}\sigma}=\frac{\overline{X}_n-\sqrt{n}\mu}{\sigma/\sqrt{n}}
$$

El teorema central del límite nos permite aproximar una suma o promedio de variables aleatorias i.i.d. por una variable aleatoria normal. Esto es extremadamente útil porque generalmente es fácil hacer cálculos con la distribución normal.

### Enunciado informal del TCL

Para $n$ grande, se tiene que:

$$
\overline{X}_n\overset{d}{\approx} N(\mu,\sigma^2/n),\quad S_n\overset{d}{\approx} N(n\mu,n\sigma^2),\quad Z_n\overset{d}{\approx} N(0,1)
$$

Donde la notación $X\overset{d}{\approx}Y$ quiere decir que la distribución de $X$ es aproximadamente igual a la de $Y$. Pero a no engañarse, esto no quiere decir que $X$ se parezca a $Y$, simplemente que la función de distribución $F_X$ se parece a $F_Y$.

### Enunciado preciso del TCL

Sea $X_1,\ldots,X_n$ una sucesión i.i.d. de variables aleatorias con esperanza $\mu$ y varianza $\sigma^2$. Sea $Z_n$ la estándarización de $S_n$ o de $\overline{X}_n$, entonces para todo $z\in\mathbb{R}$,

$$
\boxed{
\lim_{n\to\infty}F_{Z_n}(z)=\Phi(z)
}
$$

La prueba del TCL no es muy díficil, y las herramientas utilizadas están al alcance de este curso, pero si es un poco larga y técnica. Se deja como una lectura opcional en las notas del curso.

## Aplicaciones del TCL

Veamos algunas aplicaciones del teorema a continuación.

### Ejemplo 1

Se lanza una moneda justa $100$ veces. Estimar la probabilidad de que salga cara en más de $55$ de los lanzamientos.

Sea $X_i$ el resultado del $i$-ésimo lanzamiento, por lo que $X_i=1$ si sale cara y $X_i=0$ si sale cruz. La cantidad total de caras está representada por la nueva variable aleatoria:

- $S_{100}=X_1+X_2+\ldots+X_{100}$

Veamos las siguientes tres observaciones:

1. $p=\frac{1}{2}$, pues la moneda es justa.
2. $E(X)=p$, entonces $E(X)=\frac{1}{2}$
3. $Var(X)=p(1-p)$, entonces $Var(X)=\frac{1}{4}$

Entonces con esto podemos concluir que:

1. $E(S_{100})=50$
2. $Var(S_{100})=25$
3. $\sigma=\sqrt{Var(S_{100})}=5$

Podemos entonces aplicar el TCL, que nos dice que la estándarización de $S_{100}$ es aproximadamente igual a la distribución $N(0,1)$. Esto es:

$$
\begin{aligned}
&P(S_{100}>55)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(\frac{S_{100}-50}{5}>\frac{55-50}{5}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P(Z_{100}>1)\\
&=\scriptstyle{(\text{propiedades de la probabilidad})}\\
&1-P(Z_{100}\leq1)\\
&=\scriptstyle{(\text{definición de }\Phi)}\\
&1-\Phi(1)\\
\end{aligned}
$$

Como $\Phi(1)\approx0.8413$, resulta que $P(S_{100}>55)\approx0.1587$.

### Ejemplo 2

El ejemplo anterior se puede calcular exactamente usando la distribución binomial, por lo que es posible preguntarse cual es el sentido de usar el TCL para obtener una respuesta aproximada. Veamos un caso donde no tenemos una distribución tan simple, donde cobrará más sentido usar el TCL.

Un dado desparejo tiene dos caras opuestas que son menos probables que las otras cuatro. Así el $1$ y el $6$ tienen probabilidad $1/10$ y los otro cuatro resultados tienen probabilidad $1/5$.
Estimar la probabilidad de que en $100$ lanzamientos, la suma esté entre $335$ y $365$.

Llamemos $X_i$ al resultado del $i$-ésimo lanzamiento. La f.p.p. de cada $X_i$ es:

$$
\begin{array}{c|cccccc}
\text{Valor de }X_i&1&2&3&4&5&6\\
\text{f.p.p.}&1/10&2/10&2/10&2/10&2/10&1/10\\
\end{array}
$$

De donde podemos obtener el valor de la esperanza de $X_i$:

$$
\begin{aligned}
E(X_i)&=1\cdot\frac{1}{10}+2\cdot\frac{2}{10}+3\cdot\frac{2}{10}+4\cdot\frac{2}{10}+5\cdot\frac{2}{10}+6\cdot\frac{1}{10}\\
&=\frac{1}{10}+\frac{4}{10}+\frac{6}{10}+\frac{8}{10}+\frac{10}{10}+\frac{6}{10}\\
&=\frac{35}{10}\\
&=3.5
\end{aligned}
$$

Ahora podemos usar la siguiente tabla para hallar la varianza:

$$
\begin{array}{c|cccccc}
\text{Valor de }X_i&1&2&3&4&5&6\\
\text{f.p.p.}&1/10&2/10&2/10&2/10&2/10&1/10\\
(X_i-E(X_i))^2&6.25&2.25&0.25&0.25&2.25&6.25
\end{array}
$$

De donde podemos desarrollar para obtener el valor de la varianza de $X_i$:

$$
\begin{aligned}
Var(X_i)&=6.25\cdot0.1+2.25\cdot0.2+0.25\cdot0.2+0.25\cdot0.2+2.25\cdot0.2+6.25\cdot0.1\\
&=2.25
\end{aligned}
$$

Entonces, para $S_{100}=X_1+\ldots+X_{100}$ tenemos que:

1. $E(S_{100})=350$
2. $\sigma^2=Var(S_{100})=225$
3. $\sigma=\sqrt{\sigma^2}=15$

Podemos entonces aplicar el TCL, que nos dice que la estándarización de $S_{100}$ es aproximadamente igual a la distribución $N(0,1)$. Esto es:

$$
\begin{aligned}
&P(335\leq S_{100}\leq 365)\\
&=\scriptstyle{(\text{estandarizando})}\\
&P\left(\frac{335-350}{15}\leq \frac{S_{100}-350}{15}\leq \frac{365-350}{15}\right)\\
&=\scriptstyle{(\text{operatoria})}\\
&P(-1\leq Z_{100}\leq 1)\\
&=\scriptstyle{(\text{propiedades de la probabilidad})}\\
&P(Z_{100}\leq 1)-P(Z_{100}\leq-1)\\
&=\scriptstyle{(\text{definición de }\Phi)}\\
&\Phi(1)-\Phi(-1)\\
&=\scriptstyle{(\text{propiedades de }\Phi)}\\
&\Phi(1)-(1-\Phi(1))\\
&=\scriptstyle{(\text{operatoria})}\\
&2\Phi(1)-1\\
&\approx\scriptstyle{(\Phi(1)\approx0.8413)}\\
&1.6826-1\\
&\approx\scriptstyle{(\text{operatoria})}\\
&0.6826\\
\end{aligned}
$$

Notar que para este caso dado no uniforme, es casi imposible calcular la distribución de $S_{100}$. Solamente con una computadora ese cálculo es razonable.