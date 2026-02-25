# Ejercicio 02 - Conteo

**Fecha:** 25-02-2026
**Estado:** 🟢 Resuelto solo

## Consigna

De un grupo formado por 3 ingenieros, 5 economistas y 4 arquitectos deben seleccionarse 4 para formar una comisión.

1. Calcular cuántas comisiones diferentes podrían formarse.
2. Calcular cuántas de esas comisiones estarían integradas por un ingeniero, dos economistas y un arquitecto.
3. Calcular en cuántas configuraciones hay por lo menos dos arquitectos.

## Resolución

### Parte 1

- Calcular cuántas comisiones diferentes podrían formarse.

Primero tendríamos que sumar todos los profesionales para obtener la cantidad total que podemos elegir, en este caso: $3+5+4=12$.
Como queremos elegir cuatro para formar la comisión, la respuesta es:

- $\binom{12}{4}=\frac{12!}{4!8!}=\frac{12\cdot11\cdot10\cdot9}{4\cdot3\cdot2\cdot1}=11\cdot5\cdot9=495$

Usamos combinaciones porque no nos importa el orden en el que elegimos, por ejemplo el siguiente caso es uno de los que NO queremos distinguir:

- $I_1,I_2,A_1,E_1$
- $E_1,A_1,I_2,I_1$

### Parte 2

- Calcular cuántas de esas comisiones estarían integradas por un ingeniero, dos economistas y un arquitecto.

Para esta parte si usamos las cantidades de profesionales por separado. Elegiremos por cada grupo de profesionales y multiplicaremos todo para obtener el resultado:

- **Elegir al ingeniero**: $C^3_1=3$
- **Elegir a los economistas**: $C^5_2=10$
- **Elegir al arquitecto**: $C^4_1=4$

Entonces la respuesta es:

- $3\cdot10\cdot4=120$

### Parte 3

- Calcular en cuántas configuraciones hay por lo menos dos arquitectos.

Este caso se puede encarar de distintas maneras, voy a seguir con la que creo más simple.
La idea es contar las configuraciones con uno o ningún arquitecto, y restarlas a las totales para obtener las configuraciones que buscamos.

- **Configuraciones con ningún arquitecto:** Es bastante directo, queremos elegir 4 personas de un conjunto de 8 (pues restamos a los arquitectos), el número que buscamos es $\binom{8}{4}=\frac{8!}{4!4!}=\frac{8\cdot7\cdot6\cdot5}{4\cdot3\cdot2\cdot1}=7\cdot2\cdot5=70$
- **Configuraciones con un arquitecto:** También es bastante directo, pero tenemos que multiplicar por las formas de elegir al arquitecto que tenemos. El número que buscamos es $\binom{4}{1}\cdot\binom{8}{3}=4\cdot\frac{8!}{3!5!}=4\cdot\frac{8\cdot7\cdot6}{3\cdot2\cdot1}=4\cdot8\cdot7=224$

Entonces, estas son las configuraciones que queremos eliminar de las totales, por lo tanto las configuraciones con por lo menos dos arquitectos son:

- $495-70-224=201$