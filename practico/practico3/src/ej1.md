# Ejercicio 01 - Probabilidad condicional

**Fecha:** 20-04-2026
**Estado:** 🟢 Resuelto solo

## Consigna

Se consideran los sucesos $A$ y $B$ tales que $P(A)=\frac{1}{4}$ y $P(A\cup B)=\frac{1}{3}$. Calcular $P(B)$ en los siguientes casos:

1. Si $A$ y $B$ son independientes
2. Si $A$ y $B$ son disjuntos (o excluyentes)
3. Si $A$ es un subconjunto de $B$

## Resolución

### Parte 1

- Si $A$ y $B$ son independientes

Como $A$ y $B$ son independientes, podemos usar que:

- $P(A\cap B)=P(A)P(B)$

Además podemos usar el principio de inclusión-exclusión:

- $P(A\cup B)=P(A)+P(B)-P(A\cap B)$

Operemos con esto:

$$
\begin{aligned}
&P(A\cup B)=P(A)+P(B)-P(A\cap B)\\
&\iff\scriptstyle{(\text{sabiendo que }P(A\cap B)=P(A)P(B))}\\
&P(A\cup B)=P(A)+P(B)-P(A)P(B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(A\cup B)=P(A)+P(B)-P(A)P(B)\\
&\iff\scriptstyle{(\text{reemplazando valores conocidos})}\\
&\frac{1}{3}=\frac{1}{4}+P(B)-\frac{1}{4}P(B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&\frac{1}{12}=\frac{3}{4}P(B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(B)=\frac{4}{36}\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(B)=\frac{1}{9}\\
\end{aligned}
$$

Esto concluye esta parte.

### Parte 2

- Si $A$ y $B$ son disjuntos (o excluyentes)

Como $A$ y $B$ son disjuntos, podemos usar la regla de aditividad, y operando:

$$
\begin{aligned}
&P(A\cup B)=P(A)+P(B)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\frac{1}{3}-\frac{1}{4}=P(B)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(B)=\frac{1}{12}
\end{aligned}
$$

Esto concluye esta parte.

### Parte 3

- Si $A$ es un subconjunto de $B$

Como $A\subset B$, tenemos que $A\cap B=A$, con esto podemos plantear la regla de inclusión-exclusión y operar:

$$
\begin{aligned}
&P(A\cup B)=P(A)+P(B)-P(A\cap B)\\
&\iff\scriptstyle{(\text{sabiendo que }A\cap B=A)}\\
&P(A\cup B)=P(A)+P(B)-P(A)\\
&\iff\scriptstyle{(\text{operatoria})}\\
&P(A\cup B)=P(B)\\
&\iff\scriptstyle{(\text{reemplazando los valores conocidos})}\\
&\frac{1}{3}=P(B)\\
\end{aligned}
$$

Esto concluye el ejercicio.