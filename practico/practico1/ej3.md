# Ejercicio 03 - Conteo

**Fecha:** 25-02-2026
**Estado:** 🟡 Con ayuda

## Consigna

En una fábrica los productos se codifican con 3 letras distintas que indican 3 operaciones que sufren cada uno de los productos y 3 cifras distintas y en ese orden: primero las letras y después los números. Las letras utilizadas son A, B, C y D.

1. ¿Cuántos productos pueden codificarse?
2. ¿Cuántos códigos empiezan con A y terminan con 9?
3. ¿En cuántos los números 0 y 2 aparecen juntos y en ese orden?
4. ¿En cuántos los números 0 y 2 aparecen juntos?
5. ¿En cuántos productos aparecen dos números pares juntos y el otro es impar?

## Resolución

### Parte 1

- ¿Cuántos productos pueden codificarse?

Primero queremos obtener la cantidad de formas de elegir las letras, luego multiplicar lo obtenido por las formas de elegir los dígitos. Entonces el número que buscamos es:

- $A^4_3\cdot A^{10}_3=\frac{4!}{1!}\cdot\frac{10!}{7!}=24\cdot10\cdot9\cdot8=17280$

### Parte 2

- ¿Cuántos códigos empiezan con A y terminan con 9?

Es el mismo razonamiento, pero tenemos en cuenta que la primera letra y último número están fijos. Entonces el número que buscamos es:

- $A^3_2\cdot A^9_2=\frac{3!}{1!}\cdot\frac{9!}{7!}=6\cdot9\cdot8=432$

### Parte 3

- ¿En cuántos los números 0 y 2 aparecen juntos y en ese orden?

Este caso se puede resolver de varias maneras, la más intuitiva para mi es:

1. Numerar las posiciones de dígitos por 1,2,3 respectivamente.
2. Contar las configuraciones que tienen lo que buscamos, con el 0 y 2 en las posiciones 1 y 2 respectivamente. Llamemos $q_1$ a este número.
3. Repetir el paso 2, pero considerando las configuraciones con el 0 y 2 en las posiciones 2 y 3 respectivamente. Llamemos $q_2$ a este número.

Entonces el resultado será $q_1+q_2$.

- **Cálculo de $q_1$:** Primero elegimos las letras, y luego tenemos 2 números fijos y tenemos que elegir el tercero. Entonces el número que buscamos es:
    - $q_1=A^4_3\cdot A^8_1=\frac{4!}{1!}\cdot8=192$
- **Cálculo de $q_2$:** Para $q_2$ el razonamiento es análogo, por lo que $q_2=q_1$.

Entonces la respuesta es $q_1+q_2=384$.

### Parte 4

- ¿En cuántos los números 0 y 2 aparecen juntos?

Este caso es fácil si lo combinamos con la parte anterior. Lo más importante es que donde antes iban el 0 y el 2 en ese orden, ahora tenemos dos posibilidades. O bien van en el orden $0,2$ o bien $2,0$.
Entonces en nuestras cuentas anteriores, tenemos que multiplicar por dos, contemplando esta diferencia.
Notemos que en realidad la multiplicación por dos es una casualidad de que $A^2_1=2$

El resultado entonces es $768$.

### Parte 5

- ¿En cuántos productos aparecen dos números pares juntos y el otro es impar?

El razonamiento es análogo, lo que cambiará es la elección de los números.
Vayamos detallando los pasos que todavía no hicimos en las partes anteriores:

- **Elegir dos números pares juntos:** Esto se calcula con arreglos: $A^5_2=20$
- **Elegir el número impar restante**: $A^5_1=5$
- **Elegir la distribución de los números**: Los números pueden estar distribuidos de las siguientes formas: IPP o PPI (P por par e I por impar), por lo que corresponde multiplicar todo por 2 para contemplar esto.

Múltiplicamos todo esto para agregar la elección de las letras y obtenemos el resultado:

- $A^4_3\cdot20\cdot5\cdot2=24\cdot200=4800$