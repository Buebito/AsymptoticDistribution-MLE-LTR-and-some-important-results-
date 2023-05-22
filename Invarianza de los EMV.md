# Propiedad de invarianza de los Estimadores Máximo verosímiles
La propiedad de invarianza de los estimadores de máxima verosimilitud dice que, si tenemos un estimador de máxima verosimilitud $\hat{\theta}_{EMV}$ de algún parámetro $\underline\theta\in\Theta$ entonces, para cualquier función $\mathbb{g}$, el EMV de $g(\underline\theta)$ es $g(\hat{\theta}_{EMV})$.

# Demostración:

Definamos a la función $g:\Theta\rightarrow \Lambda\subset \mathbb{R}$ y al parámetro $\eta =g(\theta)$, buscamos el valor $\hat{\eta}_{EMV}$ que maximice la función de verosimilitud $L(\eta)=L(g(\theta))$. Para ello analicemos los siguiente 2 casos.

Caso 1: $g$ es función inyectiva

Como $g$ es inyectiva entonces sabemos que existe su función inversa, tal que

$$
max\{L(\eta)\}=max_\eta\{L(g^{-1}(n))\}
$$

Esto es, alcanzan el máximo en el mismo punto. Además, $g^{-1}(n)=g^{-1}(g(\theta))=\theta$, es decir,

$$
max\{L(\eta)\}=max\{L(g^{-1}(n))\}=max\{L(g^{-1}(g(\theta)))\}=max\{L(\theta)\}
$$

Por hipótesis,

$$
max\{L(\theta)\}=\hat\theta_{EMV}
$$

Es decir, $g^{-1}(\eta)$ alcanza su máximo en $\hat\theta_{EMV}$ $\implies \eta$ alcanza su máximo en $g(\hat\theta_{EMV})$

$$
\therefore \hat\eta_{EMV}=g(\hat\theta_{EMV})
$$

Es el estimador máximo verosimil de $g(\theta)$

Caso 2: $g$ no es inyectiva:

Por hipótesis, sea $g$ una función con rango $\Lambda$ y dominio $\Theta$ , y dado el EMV $\hat\theta\in \Theta$ de $\theta$, tenemos que $g(\hat\theta)$ está bien definido y es único. Definamos entonces

$$
\hat\eta=g(\hat\theta)
$$

con $\hat\eta\in\Lambda$.

Definamos entonces también a la preimágen de $g$ como $A\subset \Theta$ tal que, $\forall \eta\in\Lambda$

$$
A=\{\theta:g(\theta)=\eta\}
$$

Para probar que $\hat\eta$ es el estimador máximo verosímil para $g(\theta)$, debemos probar que maximiza a $M(\eta)$, función de verosimilitud que mapea valores del rango $\Lambda$ de $g$ a $\mathbb{R}$ (función de máxima verosimilitud inducida por $g$), pero sea

$$
M(\eta)=sup_{\theta\in A}L(\theta) \qquad (1) 
$$

Esto lo tomamos de esta forma por conveniencia (un pequeño truquito), ya que como $g$ no es necesariamente inyectiva, puede que el mismo $\eta$ haya sido mapeado por dos $\theta$'s distintas, entonces nos tomamos el más grande para asegurar máximo. Por esto mismo, tendríamos que

$$
M(\hat\eta)=sup_{\theta\in \Theta}L(\theta)\qquad (2)
$$

como $A\subset \Theta$, entonces tenemos que

$$
sup_{\theta\in A}L(\theta)\leq sup_{\theta\in \Theta}L(\theta)
$$

Sabemos por hipótesis que $L(\hat\theta)=sup_{\theta\in \Theta}L(\theta)$, es decir, $\hat\theta$ es el punto que maximiza $L(\theta)$ por ser el extimador máximo verosimil. Entonces, por lo anterior y por $(1)$ y $(2)$, tenemos

$$
L(\eta)=sup_{\theta\in A}L(\theta)=sup_{\theta\in A}L(\theta)\leq sup_{\theta\in \Theta}L(\theta)=L(\hat\theta)=L(\hat\eta)
$$

$$
\therefore L(\eta)\leq L(\hat\eta)
$$

Entonces $\hat\eta=g(\hat\theta)$ es el estimador máximo verosimil de $\eta=g(\theta)$