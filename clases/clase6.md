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

Rapidez relatica de convergencia a $0$,
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

