# Distribución asintótica de la razón de verosimilitudes generalizadas - H0 simple
<strong>Teorema</strong>: Considere una muestra aleatoria $X_1,X_2,…,X_n$ de tamaño $n$ de una población con función de densidad $f(x;\theta)$, que satisface las condiciones de regularidad y se desean probar las hipótesis

$$
\mathscr{H}_0:\theta=\theta_0
$$

                                v.s.

$$
\mathscr{H}_1:\theta\neq\theta_0
$$

Entonces, bajo $\mathscr{H}_0$, cuando $n\rightarrow\infty$ se cumple que

$$
-2ln(\lambda)\xrightarrow{d}\chi^2_{(1)}
$$

con $\lambda=\frac{L(\theta_0)}{L(\hat\theta_{MV})}$ 

# Demostración:

Dada la función de log-verosimilitud $\ell(\theta;x)=log(L(\theta;x))$, tenemos que la expanción de Taylor al rededor de $\hat\theta$ es de la forma

$$
\ell(\theta)=\ell(\hat\theta)+\ell'(\hat\theta)(\theta-\hat\theta)+\ell''(\theta)\frac{(\theta-\hat\theta)^2}{2!}+...\quad (1)
$$

Sea también por hipótesis, bajo $\mathscr{H}_0$

$$
\lambda=\frac{L(\theta_0)}{L(\hat\theta_{MV})}\implies -2ln(\lambda)=-2ln(\frac{L(\theta_0)}{L(\hat\theta_{MV})})=-2[ln(L(\theta_0))-ln(L(\hat\theta_{MV}))]
$$

tenemos por definición de función log-verosimilitud que,

$$
-2ln(\lambda)=-2\ell(\theta_0)+2\ell(\hat\theta)\quad (2)
$$

Primero es importante notar que, sea $\hat\theta_{EM}$ el EMV para $\theta$, sabemos que $\hat\theta$ maximiza la función de verosimilitud $L(\theta;x) \implies$ maximiza también la función de log-verosimilitud $\ell(\theta;x)$ porque es creciente y entonces se tendría por criterio de la primera derivada que

$$
\ell'(\hat\theta)=0\qquad(3)
$$

Segundo, notemos que si

$$
L(\theta;\textbf{X})=\Pi_{i=1}^nL(\theta;X_i)
$$

entonces,

$$
\ell(\theta;\textbf{X})=\sum_{i=1}^{n}\ell(\theta;X_i)\quad(4)
$$

Ahora sí, sustituyendo únicamente los 2 primeros términos de la expansión de Taylor $(3)$ para $\ell(\theta_0)$ al rededor de $\hat\theta$ (por conveniencia) en $(2)$ tenemos

$$
-2\ln(\lambda(\textbf{X}))=-2[\ell(\hat\theta;\textbf{X})+\ell'(\hat\theta;\textbf{X})(\theta_0-\hat\theta)+\ell''(\hat\theta;\textbf{X})\frac{(\theta_0-\hat\theta)^2}{2!}]+2\ell(\hat\theta;\textbf{X})
$$

Entonces, sabemos por $(3)$ que

$$
=-2\ell(\hat\theta)-0-2\cdot\frac{\ell''(\hat\theta)(\theta_0-\hat\theta)^2}{2}+2\ell(\hat\theta)
$$

$$
=-\ell''(\hat\theta;\textbf{X})(\theta_0-\hat\theta)^2
$$

 Por $(4)$, tenemos

$$
=-(\theta_0-\hat\theta)^2\sum_{i=1}^{n}\ell''(\hat\theta;X_i)\cdot\frac{n}{n}
$$

$$
=-n(\theta_0-\hat\theta)^2\cdot[\frac{1}{n}\sum_{i=1}^{n}\ell''(\hat\theta;X_i)]
$$

Por Ley de los Grandes Números tenemos que si $n\rightarrow\infty$, bajo $\mathscr{H}_0$

$$
\approx -n(\theta_0-\hat\theta)^2\cdot\mathbb{E[\ell''(\hat\theta;\textbf{X})]}
$$

$$
=n\cdot(\theta_0-\hat\theta)^2\cdot[-\mathbb{E}[\ell''(\hat\theta;\textbf{X})]]
$$

Recordemos que la Información Esperada de Fischer de la muestra aleatoria se define como $I_{\underline{x}}(\theta)=-\mathbb{E}[(\frac{\partial^2}{\partial\theta^2}\ell(\theta;\textbf{X})]$, entonces tenemos que si $n\rightarrow\infty$ 

$$
-2ln(\lambda(\textbf{X}))\approx n (\theta_0-\hat\theta)^2\cdot I_{\underline x}(\hat\theta)
$$

$$
=(\sqrt{n I_{\underline{x}}(\hat\theta)}\cdot(\theta_0-\hat\theta))^2
$$

Como se demostró en la investigación pasada, por Teorema de Slutsky sabemos que 

$$
\sqrt{n\cdot I_X(\theta)}\cdot(\hat\theta_{MV}-\theta)\xrightarrow{d} N(0,1)
$$

entonces,

$$
(\sqrt{n\cdot I_X(\theta)}\cdot(\hat\theta_{MV}-\theta))^2=n (\theta_0-\hat\theta)^2\cdot I_{\underline x}(\hat\theta)\xrightarrow{d} \chi^2_{(1)} \quad \square
$$