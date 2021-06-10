---
marp: true
size: 4:3
number: true
paginate: true
theme: default
style: |
    img[alt~="center"]{display:block;margin: 0 auto;}

---
Estadística Computacional
===
![center  h:350](./imagenes/lognormal-distribution.jpg)
### Funciones de Variables Aleatorias y Generadora de Momentos :chart_with_upwards_trend: :monocle_face:	
###### Braulio Fuentes - Diego Quezada

---
# Temario
- Funciones de Variables Aleatorias.
    - Transformaciones de Variables Aleatorias.
    - $X$ no es uno a uno con $Y$.
    - Esperanza y Varianza.
- Función Generadora de Momentos.
    - Teoremas Importantes.  

---
# Funciones de Variables Aleatorias.

Por lo general podemos modelar un fenómeno en términos de una variable aleatoria $X$ cuya función de distribución acumulada es $F(x)$. La pregunta es si estaremos también en condiciones de estudiar el comportamiento de aquellas variables aleatorias que son trasformaciones de $X$; una transformación uno a uno entre los valores de $X$ y otra v.a. $Y$.

---
## Transformaciones de Variables Aleatorias.
Cualquier función de $X$ es también una variable aleatoria. Si se define $Y = h(X)$, es posible describir el comportamiento probabilístico de $Y$ en términos de $X$. 
La transformación *uno a uno* implica que cada valor $x$ está relacionado con un único valor $y$, y que $y$ está relacionado con un único valor $x$.

>En un proceso para refinar azúcar la cantidad real producida es una variable aleatoria debido a descomposturas de máquinas y otros problemas. Una transformación de V.A. serviría para calcular la utilidad diaria. :moneybag:


***
* **Caso Discreto.**
Suponga que $X$ es una v.a. discreta con función masa de probabilidad $f_{x}$. Definimos una transformación uno a uno $Y = h(X)$, de manera que la ecuación $y = h(x)$ se resuelva exclusivamente para $x$ en términos de $y$, digamos $x = h^{-1}(y)$. Entonces, función masa de probabilidad de $Y$ es:

    $$f_{y}=f_{x}\left(h^{-1}(y)\right)$$

***

* **Caso Continuo.**
Suponga que $X$ es una variable aleatoria continua con función densidad de probabilidad $f_{x}$. Definimos una transformación uno a uno $Y = h(X)$, de manera que la ecuación $y = h(x)$ se resuelva exclusivamente para $x$ en términos de $y$, digamos $x = h^{-1}(y)$. Entonces, la función densidad de probabilidad de $Y$ es:

    $$f_{y}=f_{x}\left(h^{-1}(y)\right)\cdot \left|\frac{d\left(h^{-1}(y)\right)}{dy}\right|$$

---
## $X$ no es uno a uno con $Y$.
Vamos a suponer que la transformación entre los valores de $X$ y $Y$ no es uno a uno. Si el intervalo sobre el que se define $X$ se puede dividir en $k$ conjuntos mutuamente disjuntos, de manera que cada una de las funciones tenga inversas de $y=h(x)$:

$$x_{1}=h_{1}^{-1}(y), \, x_{2}=h_{2}^{-1}(y), \,   \dots \,, x_{k}=h_{k}^{-1}(y)$$

Entonces la distribución de probabilidad de $Y$ es:

$$    f_{y}= \sum_{i=1}^{k} f_{x}\left(h_{i}^{-1}(y)\right)\cdot \left|\frac{d\left(h_{i}^{-1}(y)\right)}{dy}\right| $$


---
## Esperanza y Varianza.
* **Caso Discreto.**
Si $X$ es una variable discreta con una función masa de probabilidad $f_{x}$ y $h(X)$ es cualquier función de $X$, entonces:
$$
\begin{align*}
E[h(X)]&= \sum_i h(x_i) \cdot f_{x}(x_i)\\&=\sum_i y_i\cdot f_{y}(y_i)\\
V[h(X)]&=E\left[\left(h(X)\right)^{2}\right]-\left(E[h(X)]\right)^{2}\\
&= E[Y^{2}]-(E[Y])^{2}
\end{align*}
$$

***

* **Caso Continuo.**
Si $X$ es una variable aleatoria continua con función de densidad de probabilidad $f_{x}$ y $h(X)$ es cualquier función de $X$, entonces:
$$
\begin{align*}
    E[h(X)] &= \int h(x) \cdot f_{x}(x) \cdot dx\\
    &=\int y \cdot f_{y}(y) \cdot dy\\
    V[h(X)]&=E\left[\left(h(X)\right)^{2}\right]-\left(E[h(X)]\right)^{2}\\
    &= E[Y^{2}]-(E[Y])^{2}
\end{align*}
$$

---
# Función Generadora de Momentos.

Para una distribución $X$ en ocasiones tanto $\mu$ como $\sigma$ no dan una única caracterización, existen distribuciones con los mismos valores. Los momentos son los valores esperados de ciertas funciones de $X$.
El $r-$ésimo momento alrededor del origen de la variable aleatoria $X$ es dado por:

$$
m_{r}=E(X^{r})=\begin{cases}
    \displaystyle\sum x^{r}\cdot f(x) & \text{si $X$ es discreta}\\
    \displaystyle\int x^{r}\cdot f(x)\cdot dx & \text{si $X$ es continua}
    \end{cases}
$$

>Los momentos son un conjunto de medidas descriptivas que se usan para caracterizar una distribución.

***
Existe un procedimiento alternativo para determinar los momentos de una variable aleatoria, la ***función generadora de momentos***. Esta tiene la ventaja de permitir compactar todos los momentos para una variable aleatoria en una sola expresión, la cual para la variable aleatoria $X$ es dada por:

$$
\phi_{X}(t)=E\left[e^{tX}\right]=\begin{cases}\displaystyle
    \sum e^{tx}\cdot f(x) & \text{si $X$ es discreta}\\
    \displaystyle\int e^{tx}\cdot f(x)\cdot dx & \text{si $X$ es continua}
    \end{cases}
$$

> Las `fgm`  existirán sólo si la sumatoria o integral converge.

***


Sea $X$ una variable aleatoria con función generadora de momentos $\phi_{X}(t)$, el $r-$ésimo momento viene dado por:

$$
m_{r}=\left.\frac{d^{r}\phi_{X}(t)}{dt^{r}}\right|_{t=0}
$$

> Si las `fgm` de dos variables aleatorias $X$ y $Y$ son iguales para cualquier $t$, entonces $X$ y $Y$ tienen la misma distribución de probabilidad. :money_mouth_face:
---
## Teoremas importantes

1. $\phi_{aX+b}(t) = e^{b\cdot t}\cdot\phi_{X}(a\cdot t)$

2. Si $X_{1}, X_{2}, \dots, X_{n}$ son v.a. independientes con funciones generadoras de momentos $\phi_{X_{n}}(t)$, y $Y=X_{1}+ X_{2}+ \dots+ X_{n}$, entonces:
$$
\phi_{Y}(t)=\phi_{X_{1}}(t)\times \phi_{X_{2}}(t)\times \dots \times \phi_{X_{n}}(t)
$$
