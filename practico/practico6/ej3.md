# Ejercicio 03 - Distribución conjunta y variables independientes

**Fecha:** 18-05-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se consideran dos variables aleatorias $X$ e $Y$, que toman los valores $1$, $2$ y $3$ cada una con las probabilidades conjuntas dadas en la siguiente tabla:

![Figura 1](../img/ej3fig1.png)

1. Hallar $a$, $b$ y $c$ sabiendo que $X$ e $Y$ son independientes.
2. Calcular las funciones de probabilidad marginales.

## Resolución

### Consecuencia de la independencia entre dos variables aleatorias en tablas de contingencia

En una tabla de contingencia, la independencia implica que las filas son proporcionales entre sí, y lo mismo ocurre con las columnas.
Esto sucede porque la razón entre dos probabilidades de una misma columna $j$ depende únicamente de las marginales de $X$: 

$$
\frac{P(X=x_1,Y=y_j)}{P(X=x_2,Y=y_j)}=\frac{P(X=x_1)\cdot \cancel{P(Y=y_j)}}{P(X=x_2)\cdot \cancel{P(Y=y_j)}}=\frac{P(X=x_1)}{P(X=x_2)}
$$

Esto será fundamental para la resolución del ejercicio.

### Parte 1

- Hallar $a$, $b$ y $c$ sabiendo que $X$ e $Y$ son independientes.

Podemos usar el dato de que $X$ e $Y$ son independientes, junto a la consecuencia que vimos antes de empezar con la resolución del ejercicio.

Si hallamos la proporción $p$ entre (por ejemplo) las celdas $(3,1)$ y $(1,1)$, sabemos que para cualquier columna, se mantiene la proporción $p$ entre su fila $3$ y su fila $1$. Entonces hallemos $p$:

- $p=\frac{0.06}{0.02}=3$

Trasladando esto a la columna 2:

$$
\begin{aligned}
&p\cdot0.08=b\\
&\iff\scriptstyle{(\text{sabiendo que }p=3)}\\
&0.24=b\\
\end{aligned}
$$

Ahora viendo la columna 3:

$$
\begin{aligned}
&p\cdot c=0.3\\
&\iff\scriptstyle{(\text{sabiendo que }p=3)}\\
&c=\frac{0.3}{3}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&c=0.1\\
\end{aligned}
$$

Entonces solo nos falta hallar $a$. Mirando la columna 2, podemos usar la misma cuestión de la proporción, como en dicha columna la fila 1 y 2 son iguales, lo mismo será cierto para la columna 1. Entonces $a=0.02$.

### Parte 2

- Calcular las funciones de probabilidad marginales.

Construyamos la tabla completa para poder calcular las funciones de probabilidad marginales.

![Figura 2](../img/ej3fig2.png)

Esto concluye el ejercicio.