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
![center  h:300](./imagenes/random-variable-1.svg)
### Variables Aleatorias :chart_with_upwards_trend::bar_chart:
###### Braulio Fuentes - Diego Quezada

---
# Temario
- ¿Que es una Variable Aleatoria?
- Tipos de Variables Aleatorias.
- Distribución de probabilidad.
- Función de Distribución Acumulativa.
- Valores Esperados y Varianza.
- Distribuciones Discretas.
- Distribuciones Continuas.

---
# ¿Que es una Variable Aleatoria?
Una variable aleatoria es una función que tiene como dominio el espacio muestral de un experimento y como rango tiene un conjunto de numero reales.

La notación $X(\omega) = x$ significa que $x$ es el valor asociado con el resultado $\omega$ por la v.a. $X$. 

> En el experimento de lanzar dos monedas, el espacio muestral viene dado por $\{CC,SS,CS,SC\}$. De esto modo podemos asociar a cada suceso del experimento el número de caras obtenidas, la v.a. Ahora el rango seria $\{0,1,2\}$ :coin:.




---
# Tipos de Variables Aleatorias.

Para variables con valores en $\mathbb{R}$ las variables aleatorias se clasifican usualmente en:

- **Discretas**. Es una variable aleatoria cuyos valores posibles constituyen un conjunto finito o pueden ser puestos en una secuencia infinita ordenada.
> Se sacan 2 bolas de una urna que contiene 4 rojas y 3 negras. Los posibles resultados la variable aleatoria, el número de bolas rojas, son $\{0,1,2\}$ :red_circle::black_circle:.


***
- **Continuas**. Es una variable aleatoria donde su conjunto de valores posibles se compone de todos los números que hay en un solo intervalo, extensión infinita. Además, ningún valor posible de la variable aleatoria tiene probabilidad positiva ($P(X = c) = 0$).

> Si consideramos como variable aleatoria el tiempo de espera, en horas, entre conductores sucesivos que exceden los límites de velocidad detectados, esta toma  todos los valores de  $x$  tales que  $x\ge 0$ :car::blue_car:. 




---
# Distribución de probabilidad.
La distribución de probabilidad de una v.a. es una función que asigna a cada suceso definido sobre la variable la probabilidad de que dicho suceso ocurra. Estas se dividen según el tipo de variable a estudiar.

- La *Función Masa de Probabilidad* para una v.a. discreta se define para cada número $x$ como  $p(x)=P(X=x)$. Para cualquier `fmp` se debe cumplir que:
    * $p(x) \ge 0$

    * $\displaystyle \sum_{x} p(x) = 1$

***
- La *Función de Densidad de Probabilidad* para una v.a. continua es la probabilidad de que $X$ asuma un valor en el intervalo $[a,  b]$: 

    $$P(a\le X\le b)= \int_{a}^{b} f(x)dx$$

    Para cualquier `fdp` se debe cumplir que:
    * $f(x) \ge 0$

    * $\displaystyle \int_{-\infty}^{+\infty} f(x)\,dx = 1$

> La gráfica de $f(x)$ a menudo se conoce como  curva de densidad. :chart_with_downwards_trend:

---
# Función de Distribución Acumulativa.
La función de distribución acumulada asociada a una variable aleatoria $X$, es una función de la variable $x$ que describe la probabilidad de que $X$ tenga un valor menor o igual que $x$.

- **Caso Discreto.** 
    La `fda`, $F(x)$, de una v.a. discreta $X$ con función masa de probabilidad $p(x)$ se define para cada $x$ como:

    $$ F(x) = P(X\le x) = \sum_{y: y\le x} p(y)$$

    > Para cualquier número $x$, $F(x)$ es la probabilidad de que el valor observado de $X$ será cuando mucho $x$. :exploding_head: 
***
- **Caso Continuo.**
    La `fda`, $F(x)$, de una v.a. continua $X$ con función densidad de probabilidad $f(x)$ se define para cada $x$ como:

     $$ F(x) = P(X\le x) = \int_{-\infty}^{x} f(y)\,dy$$

     > Con cada $x$, $F(x)$ es el área bajo la curva de densidad a la izquierda de $x$. :exploding_head: 

---
# Valores Esperados y Varianza.
- La **esperanza** de una variable aleatoria $X$ , es el número $E[X]$ (en ocasiones $\mu$) que formaliza la idea de valor medio de un fenómeno aleatorio. 

    - $\displaystyle E[X] = \sum_{x} x\cdot p(x)$,$\quad$ si $X$ es discreta.

    - $\displaystyle E[X] = \int_{-\infty}^{+\infty} x\cdot f(x)\,dx$,$\quad$ si $X$ es continua.

    > Es un concepto análogo a la media aritmética de un conjunto de datos. :open_mouth:
 
***

- La **varianza** de una variable aleatoria $X$ , es el número $V[X]$ (en ocasiones $\sigma^2$) que representa la dispersión de la variable aleatoria. Esta definida como la esperanza del cuadrado de la desviación de dicha variable respecto a su media, $E[(X-\mu)^2]$.

    - $\displaystyle V[X] = \sum_{x} (x-\mu)^2 \cdot p(x)$,$\quad$ si $X$ es discreta.

    - $\displaystyle V[X] = \int_{-\infty}^{+\infty} (x-\mu)^2 \cdot f(x)\,dx$,$\quad$ si $X$ es continua.

    > Hay que tener en cuenta que la fórmula de la varianza para una población ($\sigma^2$) difiere de la fórmula de la varianza para una muestra ($s^2$). :eyes:


---
Distribuciones Discretas.
===
![center  h:400](./imagenes/unnamed.gif)




---
Distribuciones Continuas.
===
![center  h:400](./imagenes/SQDVZ.png)
