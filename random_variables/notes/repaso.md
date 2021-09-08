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
![center  h:300](./images/random-variable-1.svg)
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

> En el experimento de lanzar dos monedas, el espacio muestral viene dado por $\{CC,SS,CS,SC\}$. De esto modo podemos asociar a cada suceso del experimento el número de caras obtenidas. Con lo que el rango seria $\{0,1,2\}$ :coin:.




---
# Tipos de Variables Aleatorias.

Para variables con valores en $\mathbb{R}$ las variables aleatorias se clasifican usualmente en:

- **Discretas**. Es una variable aleatoria cuyos valores posibles constituyen un conjunto finito o pueden ser puestos en una secuencia infinita ordenada.
> Se sacan 2 bolas de una urna que contiene 4 rojas y 3 negras. Los posibles resultados de la variable aleatoria, el número de bolas rojas, son $\{0,1,2\}$ :red_circle::black_circle:.


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

- La **varianza** de una variable aleatoria $X$ , es el número $V[X]$ (en ocasiones $\sigma^2$) que representa la dispersión de la variable aleatoria. Esta se define como la esperanza del cuadrado de la desviación de dicha variable respecto a su media, $E[(X-\mu)^2]$.

    - $\displaystyle V[X] = \sum_{x} (x-\mu)^2 \cdot p(x)$,$\quad$ si $X$ es discreta.

    - $\displaystyle V[X] = \int_{-\infty}^{+\infty} (x-\mu)^2 \cdot f(x)\,dx$,$\quad$ si $X$ es continua.

    > Hay que tener en cuenta que la fórmula de la varianza para una población ($\sigma^2$) difiere de la fórmula de la varianza para una muestra ($s^2$). :eyes:


---
Distribuciones Discretas.
===
![center  h:400](./imagenes/unnamed.gif)

---
# Distribución de Bernoulli.
Sea $X$ es una v.a. que mide los dos posibles resultados de un único experimento (éxito o fracaso), se dice que $X$ tiene una distribución de Bernoulli de parámetro $p$. Esta toma valor 1 para la probabilidad de éxito ($p$) y valor 0 para la probabilidad de fracaso ($1-p$).

***

* **Función de Probabilidad.**
    $$p(x;p)=\begin{cases} p& x=1\\(1-p)& x=0\\0 & \text{cualquier caso}   \end{cases}$$

* $E[X] =p$
* $V[X]=p\cdot (1-p)$



---
# Distribución Binomial.
Sea $X$ es una v.a. que mide el número de éxitos en una secuencia de $n$ experimentos de Bernoulli independientes entre sí con una probabilidad fija $p$ de ocurrencia de éxito entre los experimentos, se dice que $X$ tiene una distribución Binomial de parámetro $n$ y $p$.

***

* **Función de Probabilidad.**
    $$b(x;n,p)=\begin{cases} \displaystyle\binom{n}{x}p^{x}(1-p)^{n-x}& x=0,1,2,\dots,n\\0 & \text{cualquier caso}   \end{cases}$$

* $E[X] = n\cdot p$ 
* $V[X] = n\cdot p\cdot (1 - p)$
        
```R
dbinom(x, size=n, prob=p) #Función de masa de probabilidad.
pbinom(q, size=n, prob=p) #Función de distribución acumulada hasta q.
```

---
# Distribución de Poisson.
Sea $X$ es una v.a. que mide el número de eventos durante cierto período de tiempo a partir de una frecuencia de ocurrencia media, se dice que $X$ tiene una distribución Poisson de parámetro $\lambda$.

***

* **Función de Probabilidad.**
    $$p(x;\lambda)=\begin{cases} \displaystyle\frac{e^{-\lambda}\lambda^{x}}{x!}& x=0,1,2,\dots \\0 & \text{cualquier caso}   \end{cases}$$

* $E[X] = V[X] = \lambda$
        
```R
dpois(x, lambda) #Función de masa de probabilidad.
ppois(q,lambda) #Función de distribución acumulada hasta q.
```
>Esta distribución se especializa en la probabilidad de ocurrencia de sucesos con probabilidades muy pequeñas. :open_mouth:

---
Distribuciones Continuas.
===
![center  h:400](./imagenes/SQDVZ.png)


---
# Distribución Uniforme.
Cuando $X$ sigue una *distribución uniforme*, todos los rangos de valores que toma $X$ tienen igual probabilidad.

* **Función de Probabilidad.**
    $$f(x; A, B) =  \begin{cases} \displaystyle\frac{1}{B-A}  & A\le x\le B\\ 0 & \text{de lo contrario} \end{cases} $$


* $E[X] = \frac{A+B}{2}$
* $V[X] = \frac{(B-A)^2}{12}$
        
```R
punif(q, min = A, max = B) #Función de distribución acumulada hasta q.
```

---
# Distribución Normal.
Se dice que una v.a. continua $X$ tiene una *distribución normal* con parámetros $\mu$ y $\sigma$, donde $x \in \mathbb{R}$ y $\sigma >0$, si su función de probabilidad:

$$f(x;\mu,\sigma)=\frac{1}{\sqrt{2\pi}\sigma}e^{-{\frac{(x-\mu)^2}{2\sigma^{2}}}}$$


* $E[X] = \mu$ y $V[X] = \sigma^2$

  ​      
```R
pnorm(q, mean , sd) #Función de distribución acumulada hasta q.
```
> La estatura, el efecto de un fármaco, el cociente intelectual tienen una distribución normal. :nerd_face:

---
## Distribución Normal Estándar.
Cuando la distribución normal toma valores de parámetro $\mu=0$ y $\sigma= 1$ se conoce *distribución normal estándar*. Cunado una v.a. sigue una distribución normal estándar se denotará por $Z$ y tiene función de probabilidad:

$$f(z;\mu,\sigma)=\frac{1}{\sqrt{2\pi}}e^{\frac{z^{2}}{2}}$$

> La función de distribución acumulativa de $Z$ se denota $\Phi(z)$.
***
### Estandarización o Normalización.
Si $X$ tiene una distribución normal con media $\mu$ y desviación estándar $\sigma$, entonces $Z=\frac{X-\mu}{\sigma}$ tiene una distribución normal estándar.
$$
\begin{align*}
    P(a\le X\le b)&=P\left(\frac{a-\mu}{\sigma}\le Z \le \frac{b-\mu}{\sigma}\right)\\
    &= \Phi\left(\frac{b-\mu}{\sigma}\right)-\Phi\left(\frac{a-\mu}{\sigma}\right)
\end{align*}
$$

> De este modo podemos usar los valores tabulados de la distribución normal estándar para encontrar valores de la función de distribución de cualquier otra distribución normal. :scream:

---
# Distribución Exponencial.
Se dice que $X$ tiene una *distribución exponencial* con parámetro $\lambda (\lambda > 0)$ si la función de probabilidad es:

$$f(x;\lambda)=\begin{cases} \displaystyle \lambda e^{-\lambda x}  & x\ge0 \\0 & \text{cualquier caso}   \end{cases}$$


* $E[X] = \frac{1}{\lambda}$
* $V[X] = \frac{1}{\lambda^{2}}$

```R
pexp(q, lambda) #Función de distribución acumulada hasta q.
```
>La distribución exponencial se utiliza para modelar tiempos de espera para la ocurrencia de un cierto evento. :hourglass_flowing_sand:


---
# Distribución de Rayleigh.
Se dice que $X$ tiene una *distribución rayleigh* con parámetro $\alpha$ si la función de probabilidad de $X$ es:

$$f(x;\alpha)=\begin{cases}\frac{x}{\alpha^{2}}e^{\left(-\frac{x^{2}}{2\alpha^{2}}\right)} & x\ge 0\\  0 & \text{de lo contrario} \end{cases}$$


* $E[X] = \alpha\frac{\sqrt{2\pi}}{2}$
* $V[X] = \alpha^{2}\frac{4-\pi}{2}$

```R
prayleigh(q, alpha) #Función de distribución acumulada hasta q.
```
