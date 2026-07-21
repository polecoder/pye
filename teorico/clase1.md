# Clase 01 - Casos favorables sobre posibles

**Fecha:** 18-02-2026
**Estado:** 🟢 Completado

## Resumen en 3 líneas

En esta clase tuvimos los primeros acercamientos a la probabilidad: como medirla, como interpretarla y algunas propiedades básicas.
Además repasamos algunas reglas de conteo que necesitaremos para calcular las probabilidades.

## Preguntas Clave

- Cómo podemos medir la probabilidad?
- Una vez que calculamos la probabilidad de un determinado evento, qué significa el número que obtuvimos?
- Qué es el espacio muestral en el contexto de un problema de probabilidad?

## Contenido

### Se puede medir la probabilidad?

Si se nos pidiera definir que es una probabilidad, lo primero en lo que pensaríamos es en algo así como:

$$
\text{probabilidad}=\frac{\text{número de casos favorables}}{\text{número de casos posibles}}
$$

Por ejemplo, si lanzamos una moneda la probabilidad de que salga cruz es $1/2$, pues se trata de un caso favorable en dos posibles.
Esto que hicimos es más una forma de medir la probabilidad más que una definición de la misma.

Entonces, para medir una probabilidad primero buscamos casos de igual "peso" y luego contamos.
La definición está basada en el principio de indiferencia: si no hay razones para pensar que un resultado particular tiene más chances de ocurrir que los demás, entonces todos los resultados tienen que tener la misma probabilidad. En el ejemplo de la moneda, la probabilidad es $1/2$, que en este sentido significa que nuestras razones para pensar que saldrá cara, son idénticas a las que nos hace pensar que saldrá cruz.

#### Ejemplo 1

Una moneda es *justa* si sale cara o cruz con igual probabilidad. Consideremos el siguiente juego simple: se tira una moneda justa tres veces, y ganas si exactamente uno de los lanzamientos resulta cara. Cuál es la probabilidad de ganar?

Con tres lanzamientos, podemos enumerar fácilmente los 8 casos posibles.

$$
XXX,XXC,XCX,XCC,CXX,CXC,CCX,CCC
$$

Tres de éstos tienen exactamente una cara $XXC, XCX, CXX$. Como todas las probabilidades son igualmente probables, tenemos que:

$$
P(\text{1 cara en 3 lanzamientos})=\frac{\text{número de casos favorables}}{\text{número de casos posibles}}=\frac{3}{8}
$$

Vamos a mantener un estilo informal, al menos en esta clase, pero es importante subrayar que cuando decimos probabilidad nos referimos a la probabilidad de un cierto *evento*. En general denotaremos los eventos con una letra mayúscula como $A,B,$ etc. y la probabilidad de un evento por $P(A),P(B),$ etc. En el ejemplo de la moneda (el primero), el evento $A=\text{"el resultado es cara"}$ tiene probabilidad $P(A)=1/2$.
El conjunto de todos los resultados posibles lo denotaremos $\Omega$ y le daremos el nombre de *espacio muestral*. Si lo pensamos como un evento, es simplemente el evento $\text{"algo ocurre"}$, y claramente $P(\Omega)=1$

#### Cálculo básico (casos equiprobables)

Si en un procedimiento hay $n$ resultados posibles, éstos son igualmente probables (equiprobables), y un evento puede ocurrir de $k$ formas posibles, la probilidad del evento es entonces $k/n$.

#### Reglas básicas de la probabilidad

1. $P(A)\geq0$ para cualquier evento $A$
2. $P(\Omega)=1$
3. $P(A\lor B)=P(A)+P(B)$ si $A$ y $B$ son incompatibles.

Donde las reglas uno y dos son triviales, y se entienden por si solas. Mientras tanto, la tercera tiene el pequeño detalle que $A$ y $B$ tienen que ser incompatibles, esto significa que no pueden tener casos favorables en común. Por esta razón al sumar las probabilidades estamos tranquilos de no estar contando "doble" estos casos favorables en común.

A partir de estas reglas, podemos deducir varias más, como por ejemplo:

4. $0\leq P(A)\leq 1$ para cualquier evento $A$.
5. $P(\neg A)=1-P(A)$

Sin embargo, estas reglas no son "básicas" en el sentido de que pueden deducirse de las reglas 1,2 y 3. Además de éstas, podemos deducir muchas más reglas sobre la probabilidad a partir de las básicas, pero las que tenemos son suficientes por ahora.

### Cómo interpretamos la probabilidad?

Pensemos en el lanzamiento de un dado. Si el dado es perfectamente simétrico, entonces todas las caras del dado tienen la misma probabilidad de ocurrir, esto es $1/6$ que en porcentajes es apróximadamente $16.67%$.
Pero cómo interpretamos esa probabilidad? La interpretación es: si lanzamos un dado una y otra vez, repitiendo el proceso aleatorio básico en las mismas condiciones, a la larga saldrá un seis aproximadamente un $16.67%$ del tiempo.

Entonces resumiendo, la probabilidad de un evento da el porcentaje de tiempo que se espera que ocurra, cuando el proceso básico se realiza una y otra vez, de forma independiente y bajo las mismas condiciones.

### Glosario probabilístico

Vamos a definir la terminología estándar para trabajar con eventos en la teoría de probabilidades.

- **Experimento**: cualquier acto en el cual el resultado exacto no se puede predecir con certeza. Todos los ejemplos que vimos son experimientos en este sentido.
- **Espacio muestral**: es el conjunto $\Omega$ de todos los resultados posibles de un experimento. Los elementos del espacio muestral se denotan usualmente por la letra griega $\omega$ y se llaman eventos simples o elementales.
- **Evento**: es una subcolección de resultados posibles de un experimento (un evento $A$ es un subconjunto del espacio muestral $\Omega$).
Si el resultado observado es un cierto $\omega$ perteneciente a un evento $A$ (esto lo escribimos $\omega\in A$), decimos entonces que $A$ ha ocurrido.
- **Cardinal**: es la cantidad de elementos de un evento, lo escribimos $|A|$. Con esta notación, la probabilidad de un evento $A$ es:
    - $P(A)=\frac{|A|}{|\Omega|}$

- **Complemento, Intersección, Unión, Inclusión, Diferencia**: las operaciones de conjuntos que ya conocemos.

#### Leyes de De Morgan

Las leyes de De Morgan son dos reglas útiles que permiten pasar de uniones a intersecciones tomando complementos.

- **Complemento de la unión**: El complemento de la unión de $A$ y $B$ es la intersección de sus complementos.
    - $(A\cup B)^C=A^C\cap B^C$

- **Complemento de la intersección**: El complemento de la intersección de $A$ y $B$ es la unión de sus complementos.
    - $(A\cap B)^C=A^C\cup B^C$

### Reglas de conteo

Para calcular probabilidades, ya hemos visto que necesitamos contar, por lo menos para encontrar el cardinal del espacio muestral y el de los casos favorables. En los casos que vimos, el conteo es sumamente simple, pero esto no será así siempre.
Por esta razón, tendremos que tener presentes algunas de las reglas de conteo que vimos en matemática discreta.

#### Principio de inclusión-exclusión

Esta regla es bastante simple, nos dice que: *para contar el número de elementos en una unión finita de conjuntos finitos, primero se suman las cardinalidades de los conjuntos individuales, luego se resta el número de elementos que aparecen en al menos dos conjuntos, luego se vuelve a sumar el número de elementos que aparecen en al menos tres conjuntos, luego se resta el número de elementos que aparecen en al menos cuatro conjuntos, y así sucesivamente*.

Esto para dos conjuntos se ve así:

- $|A\cup B|=|A|+|B|-|A\cap B|$

Mientras que para tres conjuntos:

- $|A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|A\cap C|-|B\cap C|+|A\cap B\cap C|$

#### Regla del producto

Supongamos que queremos realizar una tarea, y que esta tarea se componga por $k$ etapas secuenciales independientes entre si. Suponiendo además que la tarea $i$-ésima tiene $n_i$ formas de hacerse para todo $i$, tenemos que la tarea que queremos realizar tiene las siguientes formas de hacerse:

- $n_1\times n_2\times\cdots\times n_k$

#### Arreglos y permutaciones

- **Permutaciones**: las permutaciones de $n$ son simplemente las formas de reordenar una lista de $n$ elementos distintos.
    - $P_n=n!$
- **Arreglos**: los arreglos de $n$ en $k$ son las formas de ordenar $k$ elementos distintos tomando de una lista de $n$ elementos distintos.
    - $A^n_k=\frac{n!}{n-k!}$

#### Combinaciones

Las combinaciones tienen la idea de ignorar el orden en comparación con los arreglos, pero la idea es básicamente la misma: *cuántos conjuntos de tamaño $k$ puedo formar utilizando elementos distintos de una lista de $n$ elementos distintos?*

La palabra "conjuntos" es importante, ya que es quién nos indica que el órden NO importa en este caso.

- $C^n_k=\binom{n}{k}=\frac{n!}{k!\ n-k!}$