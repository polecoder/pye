# Ejercicio 02 - Probabilidad condicional

**Fecha:** 20-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Si $A$ y $B$ son sucesos independientes y $B$ y $C$ también son sucesos independientes. ¿Puede afirmarse que $A$ y $C$ son independientes? En caso afirmativo demostrarlo, en caso contrario dar un contraejemplo.

## Resolución

La respuesta a esta pregunta es **no, no podemos afirmar que $A$ y $C$ son independientes**, para mostrar esto vamos a pensar en un contraejemplo.
Supongamos que tenemos dos barajas de cartas, y nombramos de la siguiente forma a los siguientes eventos:

- $A:$ Sacar una carta par de la baraja #1
- $B:$ Sacar una carta par de la baraja #2
- $C:$ Sacar una carta impar de la baraja #1

Entonces a nivel teórico, tenemos que las siguientes afirmaciones son verdaderas:

1. $A$ y $B$ son independientes. Esto está claro pues las barajas de cartas son diferentes.
2. $B$ y $C$ son independientes. De la misma forma que en el caso anterior, esto está claro pues las barajas son diferentes.

Aún así, no se cumple que $A$ y $C$ son independientes, pues obviamente si saco una carta par de la primer baraja, las probabilidades de sacar una carta impar de esa misma baraja cambian.
Con esto **concluimos que la afirmación es falsa**.
