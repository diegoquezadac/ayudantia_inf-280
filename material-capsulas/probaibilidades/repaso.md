---
marp: true
size: 4:3
number: true
paginate: true
theme: default
style: |
    img[alt~="center"]{display:block;margin: 0 auto;}

---
Estadistica Computacional
===
![center  h:400](./imagenes/probabilidades.jpg)
### Introducción a Teoría de Probabilidades :game_die: :black_joker: 
###### Braulio Fuentes - Diego Quezada

---
# Temario
- Conceptos Básicos.
- Axiomas y Propiedades.
- Probabilidad de un Evento
- Probabilidad Condicional
- Teorema de Bayes.
- Independencia Probabilística

---
# Conceptos Básicos.

- Un **experimento** es cualquier acción o proceso cuyo resultado está sujeto a la incertidumbre, no se puede predecir el resultado exacto de cada experiencia particular.
> Sacar dos cartas de un mazo de naipe ingles :spades::clubs::hearts::diamonds:

- El **espacio muestral**, $\Omega$, de un experimento es el conjunto de todos los posibles resultadosde dicho experimento.
> Todas las combinaciones posibles al sacar dos cartas de un mazo de naipe ingles (:spades::hearts:,:clubs::diamonds:, etc)

***

- Un **evento** es cualquier subconjunto de resultados contenidos en el espacio muestral.
> Sacar dos cartas de pinta color rojo :hearts::diamonds: 

-  Se dice que dos eventos son **mutuamente excluyentes** (disjuntos) si ninguno de los dos eventos pueden suceder simultaneamente.

- Se dice que dos eventos son **equiprobables** cuando ambos tienen las mismas oportunidades de ocurrir.

- Se dice que un grupo de eventos es **exhaustivos** si la union de todos estos es igual al espacio muestral.

---
# Axiomas y Propiedades

Diremos que la probabilidad de un evento $A$, $P(A)$, perteneciente al espacio muestral $\Omega$, es una medida precisa de la oportunidad de que $A$ ocurra. Esta debe satisfacer los siguientes axiomas:

- **Axioma 1.** Para cualquier evento $A$, $P(A)\ge0$.
- **Axioma 2.** $P(\Omega)=1$
- **Axioma 3.** Si $A_1, A_2, A_3, \dots$ es un conjunto de eventos mutuamente excluyentes, entonces:
$$ P(A_1\cup A_2\cup A_3\cup \dots)=\sum_i P(A_i) $$

***
Sean dos eventos $A$ y $B$, pertenecientes al espacio muestral $\Omega$. Podemos enumerar las siguientes propiedades:

1. $P(A) \le 1$ 
2. $P(\Omega\setminus A)=P(A^c)=1-P(A)$
3. $A\subseteq B \rightarrow P(A)\le P(B)$
4. $P(\Omega^c)=P(\varnothing)=0$
5. $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

---
# Probabilidad de un Evento

Sea $|\Omega|$ el tamaño del espacio muestral, *resultados posibles*, y $|A|$ el número de elementos pertenecientes al evento $A$, *resultados favorables*. La probabilidad de ocurrencia del evento $A$ viene dada por:

$$P(A)=\frac{|A|}{|\Omega|} $$

> En un mazo de 52 cartas de naipe ingles la cantidad de cartas de pinta roja, :hearts::diamonds:, es 26.
>Con lo que la probabilidad de escojer una carta de pinta roja es igual $\frac{26}{52}=0.5$ 


---
# Probabilidad Condicional
Sean dos eventos $A$ y $B$, la probabilidad de que ocurra el evento $A$ dado que ya ha ocurrido el evento $B$ se define como:

$$P(A|B)=\frac{P(A\cap B)}{P(B)} $$

> Si sabemos que hemos escogido una carta de corazón de un naipe ingles (evento $B$). ¿Cual es la probabilidad de que esa carta sea un número par? (evento $A$) :hearts:
> Entonces $P(A|B)=\frac{\frac{5}{52}}{\frac{13}{52}}=\frac{5}{13}\approx 0.38$

---
# Teorema de Bayes

Sean $A_1, \dots,  A_k$ eventos mutuamente excluyentes y exhaustivos y otro evento $B$.


- **Ley de probabilidad total**



$$P(B)= \sum_{i=1}^{k} P(A_i \cap B) = \sum_{i=1}^{k} P(A_i|B)\cdot P(A_i)$$
***
- **Regla de Bayes**

$$P(A_i|B)=\frac{P(A_i\cap B)}{P(B)}=\frac{P(B|A_i)\cdot P(A_i)}{P(B)}$$

> Si existen pocos eventos en la particion se puede un diagrama de arbol para calcular las probabilidades :smile:.  

---
# Independencia Probabilística

Sean dos eventos $A$ y $B$, se dice que ambos son independientes cuando la probabilidad de ocurrencia de $A$ no se ve afecta por la ocurrencia de $B$. 
Cuando ambos eventos son independientes tenemos que:

- $P(A | B) = P(A)$
- $P(A \cap B) = P(A) \cdot P(B)$

En caso contrario, ambos eventos son dependientes.


