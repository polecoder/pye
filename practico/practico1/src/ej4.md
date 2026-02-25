# Ejercicio 04 - Conteo

**Fecha:** 25-02-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Una caja fuerte se abre mediante una cierta clave de 5 dígitos (pueden ser repetidos). Usted es lo suficientemente audaz como para intentar abrirla, y lo hace probando números al azar.

1. ¿Cuántas claves posibles hay?
2. ¿Cuántas claves posibles hay si se usan sólo los dígitos de 1 a 6 en vez de usar los 10?

## Resolución

### Parte 1

- ¿Cuántas claves posibles hay?

Este ejercicio es exageradamente sencillo. Tenemos 5 dígitos que pueden ser repetidos, por lo tanto, usando la regla del producto tenemos que la cantidad de claves posibles es:

- $10^5=100000$

### Parte 2

- ¿Cuántas claves posibles hay si se usan sólo los dígitos de 1 a 6 en vez de usar los 10?

Nuevamente tenemos 6 dígitos, pero el conjunto del que elegimos ahora es $\{1,2,3,4,5,6\}$, que tiene 6 elementos. Por lo tanto la respuesta es:

- $6^5=7776$