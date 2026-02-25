# Ejercicio 05 - Conteo

**Fecha:** 25-02-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se juega a un juego del tipo 5 de Oro: hay que acertar 5 números, elegidos dentro de 36 posibilidades.

1. ¿Cuántas jugadas posibles hay?
2. Si se eligen 5 números a priori, ¿cuántas jugadas posibles hay que contengan exactamente uno de los números elegidos?
3. Si se eligen 5 números a priori, ¿cuántas jugadas posibles hay que contengan por lo menos 2 de los números elegidos?

## Resolución

### Parte 1

- ¿Cuántas jugadas posibles hay?

Considerando que el orden en el que aparecen los números no importa, las jugadas posibles del juego son $\binom{36}{5}=376992$.

### Parte 2

- Si se eligen 5 números a priori, ¿cuántas jugadas posibles hay que contengan exactamente uno de los números elegidos?

Es bastante similar a la parte anterior, solo que tenemos que tener algo de cuidado a la hora de elegir los números.
Las diferencias importantes son que:

1. Vamos a elegir sobre 31 números en vez de 36, pues no queremos contar las jugadas que contengan ninguno de los números elegidos a priori.
2. En vez de elegir 5 números, elegiremos 4 de esos 31, y luego para completar elegiremos 1 entre los 5 que habían sido seleccionados inicialmente.

Con estas observaciones tenemos que el número buscado es:

- $\binom{5}{1}\cdot\binom{31}{4}=5\cdot31465=157325$

### Parte 3

- Si se eligen 5 números a priori, ¿cuántas jugadas posibles hay que contengan por lo menos 2 de los números elegidos?

La estrategia para esta parte puede variar, la que me parece más intuitiva consiste en:

1. Calcular el total de jugadas posibles (ya lo tenemos).
2. Calcular la cantidad de jugadas posibles con ningún número de los elegidos.
3. Calcular la cantidad de jugadas posibles con un número de los elegidos (ya lo tenemos)
4. Sumar lo obtenido en los puntos dos y tres y restarlo al total de jugadas.

Entonces, calculamos la cantidad de jugadas con cero números de los elegidos simplemente reduciendo el total de números de los que podemos elegir a 31, por lo tanto el número es:

- $\binom{31}{5}=169911$

Entonces el resultado final es:

- $376992-157325-169911=49756$