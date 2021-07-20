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
![center  h:300](./imagenes/likelihood.png)
### Distribuciones muestrales
###### Braulio Fuentes - Diego Quezada

---
# Temario
- Introducción
- Estimacion puntual
    - Propiedades estimadores
    - Metodo de los momentos
    - Metodo de maxima verosimilitud (MLE)
- Intervalos de confianza

---

# Introduccion

- El objetivo es sacar conclusiones sobre uno o más parámetros que definen la distribución.

- Seguimos trabajando bajo el supuesto IID.

- En particular estudiaremos inferencia parametrica. Es decir vamos a inferir sobre modelos parametricos de la forma $f(x; \theta): \theta \in \Theta$.

- Por ejemplo, para data proveniente de una distribución normal el modelo se define como $f(x; \mu, \sigma)$.

---

# Estimacion puntual

La idea es obtener una única "mejor estimación" $\hat{\theta}$ de un estadístico de interés $\theta$.

Importante destacar que $\hat{\theta}$ es una función de la muestra $X_i$, es una **variable aleatoria**.

Dado un parámetro de interés $\theta$, existe más de un estimador razonable $\hat{\theta}$ generalmente. Se elegirá aquel que **mejor se desempeña** para cualquier muestra $X_i$.

La pregunta es como medir el desempeno :thinking:

---

## Caracteristicas

### Estimador insesgado

Un estimador puntual $\hat{\theta}$ es un estimador **insesgado** de $\theta$ si $E[\hat{\theta}] = \theta$.
> Para estimadores sesgados es el sesgo es  $E[\hat{\theta}] - \theta$.

---

### Estimador consistente

Recordemos el minimo error cuadratico:

$$
MSE = E(\hat{\theta} - \theta)^2 = V[\theta] + (E[\theta] - \theta)^2
$$

> $V[\theta]$ se conoce como error estándar y $E[\theta] - \theta$ como sesgo.

Un estimador es **consistente** cuando el sesgo y el error estándar tienden a cero a medida que $n \rightarrow \infty$.


---

### Estimador eficiente

Recordemos la cota de Cramer-Rao:

$$
V[\theta] \geq \frac{1}{- E[\frac{\partial^2 \log(f(\underline{x}, \theta))}{\partial \theta^2}]} = \frac{1}{- nE[\frac{\partial^2 \log(f(x, \theta))}{\partial\theta^2}]}
$$

Un estimador es **eficiente** cuando su variaza es minima, es decir cuando su varianza cumple la igualdad.


---

### Estimador suficiente

Un estimador es suficiente cuando es posible expresar la funcion de verosimilitud como:

$$
L( \underline{x}, \theta) = h(\hat{\theta}, \theta) \cdot g(\underline{x}) 
$$

En tal caso sabemos que el estimador esta utilizando toda la informacion de la muestra.

---

## Metodo de los momentos

Supongamos una muestra extraída desde una distribución con $m$ parámetros. Para obtener $\hat{\theta}$ se deben igualar los primeros $m$ momentos muestrales con los poblacionales y resolver las ecuaciones.


---

## Metodo de maxima verosimilitud

Buscamos los parámetros $\theta_i$ que "más concuerdan" con los datos observados.

> Asegurese de comprender la imagen de la presentacion.

Se maximiza la función de verosimilitud (likelihood):

$$
f(x_1, \dots, x_n ; \theta) = \prod_{i = 1}^n f(x_i ; \theta)
$$

> A la hora de realizar calculos se suele maximizar el logaritmo natural de la funcion de verosimililud.



---

# Intervalos de confianza

Las estimaciones puntuales no indican un grado de correctitud, no se sabe con qué probabilidad $\hat{\theta} = \theta$.

La alternativa es generar un intervalo en donde se sepa que el valor $\theta$ pertenece a este con un nivel de confianza (probailidad) dado.

> Las ganancia de confiabilidad acarrea una pérdida de precisión.

---

## Formulario

### Intervalos para la media

Notacion $P(z_{\frac{\alpha}{2}} \leq Z \leq z_{1 - \frac{\alpha}{2}}) = \gamma = 1 - \alpha$

1.  Varianza conocida:
$$\left(\overline{x} + z_{\frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}, \quad \overline{x}  + z_{1 - \frac{\alpha}{2}} \cdot \frac{\sigma}{\sqrt{n}}  \right)$$

2. Varianza desconocida y $n$ "grande":

$$\left(\overline{x} + z_{\frac{\alpha}{2}} \cdot \frac{s}{\sqrt{n}}, \quad \overline{x} + z_{1 - \frac{\alpha}{2}} \cdot \frac{s}{\sqrt{n}}  \right)$$

---

Si la muestra no es "grande", se utiliza la distribucion $t$ student con $n - 1$ grados de libertad donde $n$ es el tamano de la muestra.

Notacion $P(t_{\frac{\alpha}{2}, n - 1} \leq T \leq t_{1 - \frac{\alpha}{2}}, n - 1) = \gamma = 1 - \alpha$

3. Varianza desconocida:

$$\left(\overline{x} + t_{\frac{\alpha}{2}, n - 1} \cdot \frac{\sigma}{\sqrt{n}}, \quad \overline{x}  + t_{1 - \frac{\alpha}{2}, n - 1} \cdot \frac{\sigma}{\sqrt{n}}  \right)$$

---

### Intervalo para la varianza

Notacion $P(\chi_{\frac{\alpha}{2}, n -1} \leq \chi \leq \chi_{1 - \frac{\alpha}{2}, n - 1}) = \gamma = 1 - \alpha$

- Utilizando la distribucion chi cuadrado obtenemos: 
$$\left(\frac{(n - 1) s^2}{\chi_{\frac{\alpha}{2}, n -1}}, \frac{(n - 1) s^2}{\chi_{1 - \frac{\alpha}{2}, n -1}}  \right)$$


---

# Recomendaciones

1. https://towardsdatascience.com/understanding-maximum-likelihood-estimation-fa495a03017a
2. https://www.statology.org/confidence-intervals-python/ 