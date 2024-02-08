$$
\DeclareMathOperator{\Trans}{\mathrm{Trans}}
\DeclareMathOperator{\cut}{\text{cut}}
\DeclareMathOperator{\maxcut}{\text{Max-Cut}}
\DeclareMathOperator{\E}{\mathbb{E}}
\DeclareMathOperator{\poly}{\mathrm{poly}}
\DeclareMathOperator{\diam}{\mathrm{diam}}
\DeclareMathOperator{\polylog}{\poly \log}
\DeclareMathOperator{\Unif}{\mathrm{Unif}}
\DeclareMathOperator{\TVD}{\text{TVD}}
$$



Let $G$ be a finite abelian group and $\varphi : \mathbb R^n \to G$. 

We equip $G$ with normalized Haar measure. Define an inner product over $L^2(G)$ $\langle f, g \rangle = \E_{x} f(x)\overline{g(x)}$. Define $\hat G$ the dual space of $G$. We have a orthonormal Fourier basis for $L^2(G)$: $\{\chi(x)\}_{\chi\in \hat G}$. $\chi(x)$ is conjugate symmetric. Fourier expansion of $f$ is $\hat f(\chi) = \E_x f(x) \overline{\chi(x)}$. Define a convolution operator $f*g=\E_{y } f(y)g(x-y) $. A useful formula is $\widehat{f*g} = \hat f \cdot \hat g$ where $\cdot$ is the pointwise-multiplication operator.

Now get into the point. Consider two $d$-dimensional Gaussians $X \sim_\rho Y$, which means $X$ and $Y$ are $\rho$-correlated for $|\rho| < 1$. In other words, $X_i,Y_j$ are marginally distributed as $N(0,1)$. For each $i$, $(X_i,Y_i) \sim N\left(0,\begin{bmatrix}1 & \rho \\ \rho & 1\end{bmatrix}\right)$. Other not-mentioned covariances are all 0.

Consider a probability density $P$ (i.e. $\E_x P(x)=1$) generated by $\varphi(x)+\varphi(y)$ over $G$ (we assume some measurability).  We want to prove that $\lVert P^{*n} - P_0^{*n} \rVert_{\TVD}$ for some $0 < \varepsilon < 0.1$.  By Cauchy-Schwarz,
$$
& \lVert P^{*n}-P_0^{*n} \rVert_{\TVD}\\
= & \frac 1 2 \lVert P^{*n}-P_0^{*n} \rVert_{1}\\
= & \frac 1 2 \frac{1}{|G|} \sum_{x \in G} |P^{*n}(x)-P_0^{*n}(x)|\\
\le & \frac 1 2 \sqrt{\frac{1}{|G|} \sum_{x \in G} | P^{*n}(x) - P_0^{*n}(x)|^2}\\
= & \frac 1 2 \lVert P^{*n}-P_0^{*n}\rVert_2\\
=&\frac 1 2 \left\lVert \widehat{P}^n - \widehat{P_0}^{n} \right\rVert_2\\
=&\frac 1 2 \sqrt{\frac{1}{|G|}\sum_{\chi}|\widehat P(\chi)^n - \hat{P_0}(\chi)^n|^{2}} < 0.01
$$
To make this $< \varepsilon$, we want $\frac{1}{|G|}\sum_{\chi\ne 0}|\widehat P(\chi)|^{2n} < 4\varepsilon^2$.

Consider
$$
& \hat P(\chi)\\
=& \E_x P(x) \chi(-x)\\
=& \sum_{x \in G} \Pr[\varphi(X)+\varphi(Y)=x]\chi(-x)\\
=& \E  \chi(-\varphi(X)) \chi(-\varphi(Y))
$$
$\hat P(-\chi) = \E \chi(\varphi(X)) \chi(\varphi(Y))$

$\left\{e^{2 \pi i \sum \chi_i m_i/q_i} : 1 \le i \le s,0\le m_i \le q_i-1\right\}$

Note that $\{\chi_i m_i / q_i\}$ effectively takes value in multiples of $(q_i,\chi_i)$.

Consider a most simple form, where we can take arbitrary value in

$\left\{e^{2 \pi i \sum m_i/q_i} : 1 \le i \le s,0\le m_i \le q_i-1\right\}$

The important problem is: how does ${\sum m_i/q_i}$ approximate $[0,1]$ good?

$[\E  \chi(-\varphi(X)) \chi(-\varphi(Y))]^n - [\E \chi(-\varphi(X))]^{2n}$

It's just

$\left\{e^{2 \pi i x/N} : 0\le x <N\right\}$