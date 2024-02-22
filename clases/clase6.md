<head>
    <link rel="stylesheet" href="../styles.css">
</head>

# Clase 6

## Analisis de error para metodos iteraticos 

**Definicion** 

Supongamos que $\{p_n\}_{n=0}^\infty$  es una sucesion que converge a $p$., $p_n \neq p$ para todo $n$,. Si existen constantes $\lambda$ y $\alpha$ talque 
$$
\lim_{n\to \infty} \frac{|p_{n+1}-p|}{|p_n-p|^\alpha} = \lambda
$$


entonces $\{p_n\}_{n=1}^{\infty}$ converge a $p$ con orden $\alpha$ y constante constante de rror asintotica $\lambda$


**Nota:**: El metodo $p_n =g(p_{n-1})$ esde orden $\alpha$ si $\{p_n\}_{n=1}^{\infty}$ converge a p con orden $\alpha$ y

**Nota:** 
1. Si $\alpha = 1$ entonces la sucesion es linealmente convergente 
2. Si $\alpha = 2$ entonces la sucesion es cuadraticamente convergente
3. Si $\alpha>2$ entonces la sucesion es de orden superior
**Ejemplo**

Sean $\{p_n\}_{n=1}^\infty$, $\{\hat p_n\}_{n=1}^\infty$ ambas con convergencia en $0$, Ademas 

$$
\lim_{n\to \infty} \frac{|p_{n+1}-p|}{|p_n-p|} = \frac 12

\quad \textrm{ y } \quad  \lim_{n\to \infty} \frac{|\hat p_{n+1}-p|}{|\hat p_n-p|^2} = \frac 12$$

por simplicidad, podemos reescribir asi 

$$
\frac {p_{n+1}}{p_n} \approx 0.5$$

$$
\frac {\hat p_{n+1}}{\hat p_n^2} \approx 0.5$$



De esta forma $|p_n| \approx 0.5*|p_{n-1}| \approx 0.5(0.5|p_{n-2})= (0.5)^2 |p_{n-2}| \approx 0.5^3 p_{n-3} = 0.5^n |p_0|$

De manera semejante 
$|\hat p_n| \approx 0.5|\hat p_{n-1}|^2 \approx 0.5^3\hat p_{n-2}|^4 \approx 0.5^5|\hat p_{n-3}|^8 = 0.5^{2^n -1}|\hat p_0|^{2^n}$

Rapidez relatiVa de convergencia a $0$,
 $|p_0| = |\hat p_0|= 1$

|$0.5^n$| $0.5^{2^n-1}$|
|---|---|
|$5.0000\times10^{-1}$| $5.0000\times10^{-1}$|
|$2.5000\times10^{-1}$| $1.2500\times10^{-1}$|
|$1.2500\times10^{-1}$ | $7.8125\times10^{-3}$|
|$6.2500\times10^{-2}$ | $3.0518\times10^{-5}$|
|$3.1250\times10^{-2}$ | $4.6566\times10^{-10}$|
|$1.5625\times10^{-2}$ | $1.0842\times10^{-17}$|
|$7.8125\times10^{-3}$ | $5.8775\times10^{-39}$|


**Teorema**

Sea $g\in C[a,b]$ta; qie $g(x) \in [a,b]$ para todo $x\in [a,b]$. Suponga que $g'$ es continua en $(a,b)$ y que existe $k$ tal que $0< k < 1$  tal que

$$
|g'(x)| \leq k \quad \textrm{ para todo } x\in (a,b)
$$

si $g'(p) = \neq 0$ entonces para cualquier numero $p_0 \in [a,b]$, la sucesion dada por $p_n =g(p_{n-1})$  converge solamente linealmente ene unico punto fijo $p\in[a,b]$

**Demostracion**

Por el teorema de punto fijo, la sucesion converge a $p$. Como $g'$ existe en el $(a,b)$ entonces el teorema del valor medio.

$$p_{n+1} - p = g(p_n) - g(p) = g'(\zeta_n)(p_n-p)$$

donde $\zeta_n$ es un numero que esta entre $p_n$ y $p$.

Como $\{p_n\}_{n=1}^\infty$ cpmverge a p, entonces $\{\zeta_n\}_{n=1}^\infty$ converge a $p$. 

Por continuidad de $g;$ :

$$
\lim_{n\to \infty} g'(\zeta_n) = g'(p)
$$

Por lo tanto:


$$  
\lim_{n\to \infty } \frac{p_{n+1}-p}{p_n-p} = \lim_{n\to \infty} g'(\zeta_n) = g'(p)
$$

por lo que 

$$
\lim_{n\to \infty} \frac{|p_{n+1}-p|}{|p_n-p|} = |g'(p)|
$$

y por lo tanto los esquema s de punto fijo muestran una convergencia de carcter lineal.

**Teorema**

Sea $p$ una solucion $x=g(x)$. Supongamos que $g'(p) = 0$ y ademas supongamos que $g''$ es continua y acotada por un $M$ en un intervalo abierto $I\subseteq [a,b]$ ($p\in[a,b]$). Existe un $\delta >0$ tal que para $p_0 \in [p-\delta, p+\delta]$ la sucesion definida por $p_n= g(p_{n-1})$, $n\geq 1$ converge al menos cuadraticamente para $p$. Ademas para $n$ lo suficientemente grande 

$$
|p_n-p| \leq \frac{M}{2} |p_{n-1}-p|^2
$$

**Demostracion**

Elija un $k \in (0,1)$, $\delta >0$ talque $[p-\delta, p+\delta] \subseteq I$; se tenga $|g'(x)| \leq k$ y $g''$ sea continua, entonces:(por le arg del eje .27b)

si $f(p)$, y $k>0$  $\exist \delta$ tal que $|f(x)| \leq k$. $[p-\delta, p+\delta] \subseteq [a,b]$ entonces $\{p_n\}_{n=1}^\infty$ estaran contenidos en $[p-\delta, p+\delta]$.

Ahora desarrollamos taylor (alrededor de p):

$$
g(x) = g(p) + g'(p)(x-p) + \frac{g''(\zeta)}{2}(x-p)^2
$$

con $\zeta$ entre $x$ y $p$. Como $g(p) = p$ y $g'(p) = 0$ entonces 

$$
\begin{align*}
g(x) &= p + 0(x-p) + \frac{g''(\zeta)}{2}(x-p)^2\\
&= p + \frac{g''(\zeta)}{2}(x-p)^2
\end{align*}
$$ 

Si $x = p_n$: 

$$
\begin{align*}
p_{n+1} &= g(p_n) = p + \frac{g''(\zeta_n)}{2}(p_n-p)^2\\
p_{n+1} - p &= \frac{g''(\zeta_n)}{2}(p_n-p)^2\\
\frac {p_{n+1}-p}{(p_n-p)^2} &= \frac{g''(\zeta_n)}{2}
\end{align*} \quad \zeta_n \in [p_n, p]
$$



Como $|g'(x)|<k$ y g se mapea en si mismol entonces $\{p_n\}$ convege a $p$. Por lo tanto 

$$
\lim_{n\to \infty} = \frac{|p_{n+1}-p|}{|p_n-p|^2} = \lim_{n\to \infty} \frac{g''(\zeta_n)}{2} = \frac{|g''(p)|}{2}
$$

Como $g''$ esta acotado por $M$ en $[p-\delta, p+\delta]$ entonces:

$$
|p_{n+1}-p| \leq \frac{M}{2} |p_n-p|^2
$$

**Nota:** Los metodos punto fijo que son cuadraticamente convergentes deberan ser aquellos donde las derivadas de la funcion se anulan en el punto fijo.

Considere $p_n =g(p_{n-1})$ con $n\geq 1$, un esquema de punto fijo es:

$$g(x) = x - \not o(x) f(x)$$

donde $\not o(x)$ es uan funcion diferenciable para el proceso:

- Necesitamos que $g'(p) = 0$ cuando $f(p) <0$

$$g'(x) = 1- \not o(x)f'(x) - \not o'(x)f(x) \quad \rightarrow$$
si $x=p$

$$
\begin{align*}
g'(p) &= 1 - \not o(p)f'(p) - \not o'(p)f(p) \\
&= 1 - \not o(p)f'(p) \quad  \text{o mejor} \quad g'(p) = 0\\
0&= 1- \not o(p)f'(p)\\
\not o(p) &= \frac 1{f'(p)} \quad \Rightarrow 
 \end{align*} 
$$

$$
\not o(x) = \frac 1{f'(x)} \quad p_n = g(p_{n-1}) = p_{n-1} - \frac{f(p_{n-1})}{f'(p_{n-1})}


