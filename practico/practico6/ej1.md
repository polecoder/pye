# Ejercicio 01 - Distribución conjunta y variables independientes

**Fecha:** 18-05-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se considera un grupo de 9 personas de las cuales hay 2 que son contadores y 3 que son abogados. Se eligen al azar 5 personas de ese grupo de 9. Se definen: $X=$ Cantidad de contadores en las 5 personas elegidas e $Y=$ Cantidad de abogados en las 5 personas elegidas.

1. ¿Qué valores pueden tomar las variables aleatorias $X$ e $Y$?
2. Construir la función de probabilidad (puntual) conjunta de $X$ e $Y$.
3. A partir de lo hallado en la parte 2, halle las funciones de probabilidad (puntual) marginales de $X$ e $Y$.
4. Calcular $P\{X=Y\}$.
5. ¿Son $X$ e $Y$ variables aleatorias independientes?

## Resolución

### Parte 1

- ¿Qué valores pueden tomar las variables aleatorias $X$ e $Y$?

Las variables aleatorias mencionadas pueden tomar los siguientes valores:

- $X\to\{0,1,2\}$
- $Y\to\{0,1,2,3\}$

### Parte 2

- Construir la función de probabilidad (puntual) conjunta de $X$ e $Y$.

Para esta parte vamos caso por caso y calculamos la probabilidad usando conteo. Para lo que veremos que:

- $|\Omega|=C^9_5=\frac{9!}{5!4!}=\frac{9\cdot8\cdot7\cdot6}{4\cdot3\cdot2}=9\cdot2\cdot7=126$

Y ahora iremos uno por uno calculando las probabilidades con combinatoria.

- $P(X=0,Y=0)=0$, pues tenemos que elegir 5 personas de 9, y hay 5 que son abogados o contadores.
- $P(X=0,Y=1)=\frac{C^3_1\cdot C^4_4}{126}=\frac{3}{126}$
- $P(X=1,Y=0)=\frac{C^2_1\cdot C^4_4}{126}=\frac{2}{126}$
- $P(X=2,Y=0)=\frac{C^2_2\cdot C^4_3}{126}=\frac{4}{126}$
- $P(X=0,Y=2)=\frac{C^3_2\cdot C^4_3}{126}=\frac{4\cdot3}{126}=\frac{12}{126}$
- $P(X=1,Y=1)=\frac{C^3_1\cdot C^2_1\cdot C^4_3}{126}=\frac{3\cdot2\cdot4}{126}=\frac{24}{126}$
- $P(X=0,Y=3)=\frac{C^3_3\cdot C^4_2}{126}=\frac{6}{126}$
- $P(X=1,Y=2)=\frac{C^3_2\cdot C^2_1\cdot C^4_2}{126}=\frac{3\cdot2\cdot6}{126}=\frac{36}{126}$
- $P(X=2,Y=1)=\frac{C^3_1\cdot C^2_2\cdot C^4_2}{126}=\frac{3\cdot6}{126}=\frac{18}{126}$
- $P(X=1,Y=3)=\frac{C^3_3\cdot C^2_1\cdot C^4_1}{126}=\frac{2\cdot4}{126}=\frac{8}{126}$
- $P(X=2,Y=2)=\frac{C^3_2\cdot C^2_2\cdot C^4_1}{126}=\frac{3\cdot4}{126}=\frac{12}{126}$
- $P(X=2,Y=3)=\frac{1}{126}$

Con esto tenemos todas las probabilidades que necesitamos, esto nos permite construir la tabla para la probabilidad conjunta. Recordemos que es fundamental verificar haciendo las sumas correspondientes para obtener que la probabilidad total es 1.

![Figura 1](../img/ej1fig1.png)

### Parte 3

- A partir de lo hallado en la parte 2, halle las funciones de probabilidad (puntual) marginales de $X$ e $Y$.

Esto ya lo encontramos cuando hallamos la tabla en la parte anterior, descrito por la sección $P(X)$ y $P(Y)$ respectivamente.

#### Parte 4

- Calcular $P\{X=Y\}$.

Basandonos en la tabla, tenemos que sumar las probabilidades en las cuales $X=Y$, estos son:

1. $X=Y=1$
2. $X=Y=2$

Por lo tanto, $P(X=Y)=\frac{24}{126}+\frac{12}{126}=\frac{36}{126}\approx0.28571$.

#### Parte 5

- ¿Son $X$ e $Y$ variables aleatorias independientes?

Es bastante simple, para responder a esta pregunta tenemos que verificar si para cualquier $x,y$ se cumple que:

- $P_{X,Y}(x,y)=P_X(x)\cdot P_Y(y)$

Veamos que $x=y=0$ es un contraejemplo claro:

- $0=^?21/126\cdot6/126$

Donde esto es claramente falso. Concluimos que $X$ e $Y$ no son independientes.