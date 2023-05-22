# Propiedad asintótica de los Estimadores de Máxima verosimilitud
Dada una muestra aleatoria $X_1,X_2, …, X_n$ de $X\sim f(x;\theta)$, con $\theta\in \Theta$, la propiedad asintótica de los Estimadores de Máxima Verosimilitud nos dice, que si $\hat\theta_{MV}$ es el estimador máximo verosímil de $\theta$, entonces, bajo condiciones de regularidad, se tiene que

$$
\hat\theta_{MV}\rightarrow N(\theta,\frac{1}{nI_X(\theta)})
$$

# Demostración

Antes de demostrar esta propiedad, es facil ver que si

$$
\hat\theta_{MV}\rightarrow N(\theta,\frac{1}{nI_X(\theta)})
$$

entonces por linealidad de la esperanza,

$$
(\hat\theta_{MV}-\theta)\rightarrow N(0,\frac{1}{nI_X(\theta)})
$$

y por propiedades de la varianza,

$$
\sqrt{n\cdot I_X(\theta)}\cdot(\hat\theta_{MV}-\theta)\rightarrow N(0,1)
$$

Entonces, si demostramos lo pasado, quedaría demostrada la propiedad.

Ahora sí, sea $\hat\theta_{EM}$ el EMV para $\theta$, sabemos que $\hat\theta$ maximiza la función de verosimilitud $L(\theta;x) \implies$ maximiza también la función de log-verosimilitud $\ell(\theta;x)$ porque es creciente y entonces se tendría por criterio de la primera derivada que

$$
\ell'(\hat\theta)=0\qquad(1)
$$

Entonces, utilizando expansiones de Taylor para expandir $\ell'$ al rededor de $\theta$ (truquito para obtener los términos que nos faltan para la demostración), se tiene que

$$
\ell'(\hat\theta)\approx \ell'(\theta)+\ell''(\theta)(\hat\theta-\theta)\qquad(2)
$$

entonces, juntando $(1)$ y $(2)$ tenemos,

$$
\ell'(\theta)+\ell''(\theta)(\hat\theta-\theta)=0
$$

$$
\implies(\hat\theta-\theta)=\frac{-\ell'(\theta)}{\ell''(\hat\theta)}
$$

$$
\implies \sqrt{n}(\hat\theta-\theta)=\sqrt{n}\frac{-\ell'(\theta)}{\ell''(\hat\theta)}
$$

$$
\implies \sqrt{n}(\hat\theta-\theta)=-\frac{n^{-\frac{1}{2}}\cdot\ell'(\theta)}{n^{-1}\ell''(\hat\theta)}
$$

Para sacar la esperanza y varianza del término, para determinar la distribución, primero analicemos la fracción por partes.

Primero veamos que, por lo visto en clase

$$
\mathbb{E}[n^{-\frac{1}{2}}l'(\theta)] =n^{-\frac{1}{2}} \mathbb{E}[l'(\theta)] = 0 \qquad (a)
$$

Analizando la varianza vemos que,

$$
Var[n^{-\frac{1}{2}}l'(\theta)] =n^{-1} Var[l'(\theta)] = I_{X}(\theta) \qquad (b)
$$

Ya que es la definición vista sobre la información esperada de Fischer para la muestra.

Ahora, analizando el denominador del término, veamos que, por definición de función de log-verosimilitud y por condiciones de regularidad (cambiar de lugar sumas o integrales por derivadas),

$$
n^{-1}l''(\theta) = n^{-1} \sum_{i=1}^{n} \frac{\partial^2}{\partial \theta^2} ln(f(X_i:\theta))
$$

Entonces, por Ley de los Grandes números sabemos que

$$
n^{-1}l''(\theta)\overset{P}{\rightarrow} \mathbb{E}[\frac{\delta^2}{\delta \theta^2} ln(f(X_i:\theta))] = - I_{X}(\theta)
$$

Por definición de Información esperada de Fisher por unidad muestral.

Entonces, podemos aproximar nuestro término principal como

$$
 n^{\frac{1}{2}} (\hat{\theta}- \theta) \approx  \frac{n^{-\frac{1}{2}}l'(\theta)}{I_{X}(\theta)} 
$$

Y ahora sacando la esperanza y varianza obtenemos,

$$
\mathbb{E}[n^{\frac{1}{2}} (\hat{\theta}- \theta)] \approx 0 \qquad(i)
$$

por $(a)$ y

$$
Var[n^{\frac{1}{2}} (\hat{\theta}- \theta)] = n Var[(\hat{\theta}- \theta)] \approx\frac{I_{X}(\theta)}{I_{X}^2(\theta)} = \frac{1}{I_{X}(\theta)}
$$

por $(b)$, dado que estamos aplicando nuevamente

$$
Var[n^{-\frac{1}{2}}l'(\theta)] = I_{X}(\theta)
$$

y como $I_{X}(\theta)$ es constante, sale al cuadrado por propiedades de la varianza

Entonces,

$$
\implies Var[(\hat{\theta}- \theta)] \approx\frac{1}{nI_{X}(\theta)}
$$

$$
\implies Var[\sqrt{n\cdot I_X(\theta)}(\hat{\theta}- \theta)] \approx1 \qquad (ii)
$$

Entonces, por $(1)$ y $(2)$

$$
\therefore\sqrt{n\cdot I_X(\theta)}\cdot(\hat\theta_{MV}-\theta)\rightarrow N(0,1)
$$

$$
\implies \hat\theta_{MV}\rightarrow N(\theta,\frac{1}{nI_X(\theta)})
$$

