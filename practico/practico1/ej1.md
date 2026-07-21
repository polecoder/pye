# Ejercicio 01 - Conteo

**Fecha:** 25-02-2026
**Estado:** 🟢 Resuelto solo

## Consigna

En cierta ciudad las matrículas de los autos se forman con 2 vocales diferentes seguidas de 5 dígitos todos diferentes. Calcular la cantidad de matrículas que pueden hacerse y calcular cuántas de ellas comienzan con A y terminan con 89.

## Resolución

La resolución de este ejercicio es muy simple utilizando solamente la regla del producto.

Por un lado, la cantidad de matriculas que pueden hacerse en esta ciudad se calcula de la siguiente forma:

- $5\times4\times10\times9\times8\times7\times6=604800$

Por otra parte, la cantidad de matriculas que cumple con los requisitos indicados son:

- $4\times8\times7\times6=1344$

Donde el primer cuatro representa las cuatro vocales que quedan, y contamos solo 8 dígitos, pues el "8" y "9" ya están en la matrícula y debemos excluirlos.