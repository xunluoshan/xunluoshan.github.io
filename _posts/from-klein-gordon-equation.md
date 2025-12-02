---
layout:     post
title:      "一些推导"
subtitle:   ""
author:     "Luoshan"
catalog: true
header-style: text
tags:
  - 数理方程
  - 物理
---

<head>
    <script>
    MathJax = {
      tex: {
        inlineMath: [['$', '$']],
        displayMath: [['$$', '$$']],
      }
    };
    </script>
    <script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
</head>


Klein-Gordon equation

$$ \left(-\frac{1}{c^2}\frac{\partial^2}{\partial t^2}+\nabla^2-\frac{M^2c^2}{\hbar^2}\right)\Psi(\vec{r},t)=0 $$

Natural unit, 

$$ \left( -\frac{\partial^2}{\partial t^2}+\nabla^2-M^2 \right)\Psi(\vec r,t)=0 $$

因为$\nabla^2-M^2$是厄米的，能展开为若干线性独立的本征态函数的叠加

令$\Psi(\vec r,t)=\sum_n C_n(t)\Psi_n(\vec r)$

代入原式，  
$$-\sum_n C''_n(t)\Psi_n(\vec r)+\sum_n C_n(t)(\nabla^2-M^2)\Psi_n(\vec r)=0$$

设$(\nabla^2-M^2)\Psi_n(\vec r)=-\lambda_n \Psi_n(\vec r)$，其中$\lambda_n$为一已知正常数（？），与$t$无关

$$-\sum_n C''_n(t)\Psi_n(\vec r)-\sum_n C_n(t)\lambda_n\Psi_n(\vec r)=0$$  
$$\sum_n [C''_n(t)+\lambda_n C_n(t)]\Psi_n(\vec r)=0$$  
因为$\Psi_n(\vec r)$是彼此正交独立的，所以对于任意的n，都有  
$$C''_n(t)+\lambda_n C_n(t)=0$$  
解得，  
$$C_n(t)=A e^{i \sqrt \lambda_n t}+B e^{-i\sqrt \lambda_n t}$$  
对于$\nabla^2\Psi_n(\vec r)=(M^2-\lambda_n) \Psi_n(\vec r)$，存在边界条件  
$$\Psi_n(r=0)有限，\Psi_n(r=r_0)=0$$  
$$\Psi_n(\theta=0)有限，\Psi_n(\theta=\pi)有限$$  
$$\Psi_n(\phi=0)=\Psi_n(\phi=2\pi),\Psi'_n(\phi=0)=\Psi'_n(\phi=2\pi)$$  

令$\Psi_n(\vec r)=\sum_m \psi_m(r,\theta) \Phi_m(\phi)$，代入$(\nabla^2-M^2)\Psi_n(\vec r)=-\lambda_n \Psi_n(\vec r)$展开

且使$\Phi_m(\phi)$满足，  
$$\frac{\partial^2}{\partial \phi^2}\Phi_m(\phi)=\bar{\lambda_m} \Phi_m(\phi)$$  
其中$\bar{\lambda_m}$为一常数。

解得，  
$$\Phi_m(\phi)=e^{im\phi},      \bar{\lambda_m}=-m^2$$  
将其代入$(\nabla^2-M^2)\Psi_n(\vec r)=-\lambda_n \Psi_n(\vec r)$，  

$$-(\frac{1}{r^2}\frac{\partial}{\partial r}r^2 \frac{\partial}{\partial r}+\frac{1}{r^2 sin\theta}\frac{\partial}{\partial \theta}sin\theta \frac{\partial}{\partial \theta}+\frac{1}{r^2sin^2\theta}\frac{\partial^2}{\partial \phi^2}+M^2-\lambda_n)\sum_m \psi_m(r,\theta) \Phi_m(\phi)=0$$  

$$-\sum_m(\frac{1}{r^2}\frac{\partial}{\partial r}r^2 \frac{\partial}{\partial r}+\frac{1}{r^2 sin\theta}\frac{\partial}{\partial \theta}sin\theta \frac{\partial}{\partial \theta}-\frac{m^2}{r^2sin^2\theta}+M^2-\lambda_n)\psi_m(r,\theta) \Phi_m(\phi)=0$$  

又$\Phi_m(\phi)=e^{im\phi}$，当m不同时，$\Phi_m(\phi)$彼此是正交的。

因此，对任意的m，都有  

$$(\frac{1}{r^2}\frac{\partial}{\partial r}r^2 \frac{\partial}{\partial r}+\frac{1}{r^2 sin\theta}\frac{\partial}{\partial \theta}sin\theta \frac{\partial}{\partial \theta}-\frac{m^2}{r^2sin^2\theta}+M^2-\lambda_n)\psi_m(r,\theta)=0$$  

令$\psi_m(r,\theta)=\sum_{lm}R_{lm}(r)\Theta_{lm}(\theta)$

使$\Theta_{lm}(\theta)$满足，

$$(\frac{1}{sin\theta}\frac{\partial}{\partial \theta}sin\theta \frac{\partial}{\partial \theta}-\frac{m^2}{sin^2\theta})\Theta_{lm}(\theta)=\bar{\lambda_{lm}}\Theta_{lm}(\theta)$$

$$(\frac{\partial}{\partial cos\theta}sin^2\theta \frac{\partial}{\partial cos\theta}-\frac{m^2}{sin^2\theta}-\bar{\lambda_{lm}})\Theta_{lm}(\theta)=0$$

换元，令$x=cos\theta$，

$$[\frac{\partial}{\partial x}(1-x^2) \frac{\partial}{\partial x}-\frac{m^2}{1-x^2}-\bar{\lambda_{lm}}]\Theta_{lm}(\theta)=0$$

此为连带勒让德方程，可以解出

$$\Theta_{lm}(\theta)=P_m^l(cos\theta),       \bar{\lambda_{lm}}=-l(l+1)$$

代回原式，有

$$\sum_l(\frac{1}{r^2}\frac{\partial}{\partial r}r^2\frac{\partial}{\partial r}-\frac{l(l+1)}{r^2}+M^2-\lambda_n)R_{lm}(r)\Theta_{lm}(\theta)=0$$

因连带勒让德函数集合在$\theta \in [0,\pi]$上构成完备的正交函数系，

对任意的r都有

$$(\frac{1}{r^2}\frac{\partial}{\partial r}r^2\frac{\partial}{\partial r}-\frac{l(l+1)}{r^2}+M^2-\lambda_n)R_{lm}(r)=0$$




-----------------------

$$\frac{1}{r^2}(2r R'_{lm}(r)+r^2R''_{lm}(r))-l(l+1)\frac{R_{lm}(r)}{r^2}+(M^2-\lambda_n)R_{lm}(r)=0$$  
$$R''_{lm}(r)+\frac{2}{r}R'_{lm}(r)+[\frac{-l(l+1)}{r^2}+M^2-\lambda_n]R_{lm}(r)=0$$  
由于$M^2$小于$\lambda_n$，令$x=\frac{r}{2}\sqrt{\lambda_n-M^2}$，有  
$$R''(x)+\frac{1}{x}R'(x)-[1+\frac{l(l+1)}{4x^2}]R(x)=0$$  
为$\nu=\frac{\sqrt{l(l+1)}}{2}$阶虚宗量贝塞尔方程，其中$\sqrt{l(l+1)}$不是整数。  
...
$\nu$阶贝塞尔方程的两个独立的解为  

$$\begin{aligned}
R(z) & =\sum_{k=0}^{+\infty} a_{2 k} z^{s+2 k}, \quad(s= \pm \frac{\sqrt{l(l+1)}}{2}) \\
a_{2 k} & =\left(-\frac{1}{4}\right)^{k} \frac{\Gamma(s+1)}{k!\Gamma(k+s+1)} a_{0} . \quad(k \geq 0)
\end{aligned}$$

令$z=ix$,   
$$J_{\nu}(ix)=\sum_{k=0}^{+\infty}\frac{(-1)^k}{k!\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{ix}{2}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}$$  
为得到实函数的解，再乘以归一化因子$i^{-\nu}$  
$$I_{\nu}(x)=i^{-\nu}J_{\nu}(ix)$$  
因此，修正的$\nu$阶贝塞尔方程通解为  
$$R(x)=C_1\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x}{2}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}+C_2\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k-\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x}{2}\right)^{-\frac{\sqrt{l(l+1)}}{2}+2k}$$  
$$R(r)=C_1\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{r\sqrt{\lambda_n-M^2}}{4}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}+C_2\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k-\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{r\sqrt{\lambda_n-M^2}}{4}\right)^{-\frac{\sqrt{l(l+1)}}{2}+2k}$$  

所以，波函数的通解为  
$$\Psi(\vec r,t)=\sum_{n}C_n(t)\sum_{lm}R_{lm}(r)Y_l^m(\theta,\phi)$$  
$$\Psi_n(\vec r)=\sum_{lm}R_{lm}(r)Y_l^m(\theta,\phi)$$  

>    根据边界条件$\Psi_n(r=0)$有限，


考察$I_{-\nu}(x)$，该级数由幂指数不同的项组成，

当k=0时，第一项为$\frac{1}{\Gamma(1-\nu)}\left(\frac{x}{2}\right)^{-\nu}$  
当k=1时，第二项为$\frac{1}{\Gamma(2-\nu)}(\frac{x}{2})^{2-\nu}$  
当k=2时，第三项为$\frac{1}{2 \Gamma (3-\nu )}\left(\frac{x}{2}\right)^{4-\nu }$  
...  
其中$\nu=\sqrt{l(l+1)}$

当$x \to 0$时，$x^{-\nu} \to +\infty$，除了$k=0$的第一项，其余项均是高阶小量，可忽略不计。  
因此  
$$\lim_{x \to 0} I_{-\nu}(x) =\lim_{x \to 0} \frac{1}{\Gamma(1-\nu)}\left(\frac{x}{2}\right)^{-\nu}$$  
因为$\nu$不为整数，所以$\Gamma(1-\nu)$为一有限值，即$I_{-\nu}(x)$在$x\to 0$处发散  

所以当$r \to 0$时，$x \to 0$，$I_{-\nu}(x)$发散，不符合边界条件$\Psi_n(r=0)$有限的要求

因此$C_2=0$，$R_{lm}(r)=C_1I_{\nu}(x)$

>   根据$\Psi_n(r \to +\infty)=0$

考察$I_{\nu}(x)$，  
$$\lim_{x \to +\infty}I_{\nu}(x)=\lim_{x \to +\infty}\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x}{2}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}=+\infty$$  
当$r \to +\infty$时，$x \to + \infty$，$I_{\nu}(x)$发散，不符合束缚态波函数在无穷远处为0的条件。因此，考虑将$R_{lm}(r)$的通解用第二类修正的贝塞尔函数$K_{\nu}(x)$表示  
$$R(x)=AI_{\nu}(x)+BK_{\nu}(x)$$  
其中，  
$$K_{\nu}(x)=-\frac{\pi}{2}\frac{I_{\nu}(x)-I_{-\nu}(x)}{sin\pi\nu}$$  
当$x \to +\infty$时，$K_{\nu}(x) \to \sqrt{\frac{\pi}{2x}}e^{-x}$，$I_{\nu}(x) \to \frac{e^x}{\sqrt{2\pi x}}$，说明$K_{\nu}(x)$在无穷远处收敛，$I_{\nu}(x)$在无穷远处发散。

所以$R(x)=BK_{\nu}(x)$  
代入$\Psi_n(r=r_0)=0$，即$R_{lm}(r=r_0)=0$，  
$$-\frac{B\pi}{2sin\pi\nu}[I_{\nu}(x_0)-I_{-\nu}(x_0)]=0$$  
其中$x_0=\frac{r_0}{2}\sqrt{\lambda_n-M^2}$。又$\frac{B\pi}{2sin\pi\nu}$为一有限值，所以有  
$$I_{\nu}(x_0)-I_{-\nu}(x_0)=0$$  
$$\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x_0}{2}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}=\sum_{k=0}^{+\infty}\frac{1}{k!\Gamma(k-\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x_0}{2}\right)^{-\frac{\sqrt{l(l+1)}}{2}+2k}$$  
$$\sum_{k=0}^{+\infty}\frac{1}{k!}\left[\frac{1}{\Gamma(k+\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x_0}{2}\right)^{\frac{\sqrt{l(l+1)}}{2}+2k}-\frac{1}{\Gamma(k-\frac{\sqrt{l(l+1)}}{2}+1)}\left(\frac{x_0}{2}\right)^{-\frac{\sqrt{l(l+1)}}{2}+2k}\right]=0$$
  

.
.
.








先暂时忽略这一部分
-----------------------------


令$u(r)=rR_{lm}(r)$，可进一步简化方程形式
$$\frac{d^2u(r)}{dr^2}+[-\frac{l(l+1)}{r^2}+M^2-\lambda_n]u(r)=0$$
为l阶球贝塞尔方程。


此方程一阶导系数为0，$p(r)=0$
$$u''(r)+q(r)u(r)=0$$
在$r=0$的邻域$0<|r|<R$内解方程，
$$q(r)=-\frac{l(l+1)}{r^2}+M^2-\lambda_n,  p(r)=0$$
所以，
$$p_{-1}=0,  q_{-2}=-l(l+1)$$
代入判定方程，
$$s(s-1)+p_{-1}s+q_{-2}=0$$
$$s(s-1)-l(l+1)=0$$
$$s=-l或l+1$$
因为$s_1-s_2=2l+1$为整数。

所以，方程的两个线性无关的解为
$$u_1(r)=\sum_{k=0}^{+\infty}a_kr^{s_1+k}=\sum_{k=0}^{+\infty}a_kr^{k+l+1}$$
$$u_2(r)=Au_1(r)lnr+\sum_{k=0}^{+\infty}b_kr^{k-l}$$
所以
$$u_1'(r)=\sum_{k=0}^{+\infty}(k+l+1)a_kr^{k+l}$$
$$u_1''(r)=\sum_{k=0}^{+\infty}(k+l)(k+l+1)a_kr^{k+l-1}$$
$$-\frac{l(l+1)}{r^2}u_1(r)=\sum_{k=0}^{+\infty}-l(l+1)a_kr^{k+l-1}$$
$$(M^2-\lambda_n)u_1(r)=\sum_{k=0}^{+\infty}(M^2-\lambda_n)a_kr^{k+l+1}=\sum_{k=2}^{+\infty}(M^2-\lambda_n)a_{k-2}r^{k+l-1}$$
代回原方程，
$$\sum_{k=0}^{1}[(k+l)(k+l+1)-l(l+1)]a_kr^{k+l-1}+\sum_{k=2}^{+\infty}\left[[(k+l)(k+l+1)-l(l+1)]a_k+(M^2-\lambda_n)a_{k-2}\right]r^{k+l-1}=0$$
$$\sum_{k=0}^{1}k(k+2l+1)a_kr^{k+l-1}+\sum_{k=2}^{+\infty}[k(k+2l+1)a_k+(M^2-\lambda_n)a_{k-2}]r^{k+l-1}=0$$
因此有，
$$0a_0=0$$
$$2(l+1)a_1=0$$
$$a_k=\frac{\lambda_n-M^2}{k(k+2l+1)}a_{k-2}     \quad      (k \geq 2)$$
因为$a_1=0$，由递推公式知奇数项$a_{2k+1}$都为0，因此只需求偶数项$a_{2k}$
所以
$$a_{2k}=\frac{\lambda_n-M^2}{2k(2k+2l+1)}a_{2k-2}$$
对方程两边都进行连乘，
$$\prod_{k=1}^na_{2k}=\prod_{k=1}^n\frac{\lambda_n-M^2}{2k(2k+2l+1)}\prod_{k=1}^na_{2k-2}$$
$$a_{2n}=[\frac{\lambda_n-M^2}{2}]^n \frac{(2l+2)!}{n!(2l+2n+1)!} a_0 \quad (n\geq0)$$
>     此处$a_{2n}$的n与$\lambda_n$中的n无关。

用指标k替换n，
$$a_{2k}=[\frac{\lambda_n-M^2}{2}]^k \frac{\Gamma(2l+3)}{k!\ \Gamma(2l+2k+2)} a_0 \quad (k\geq0)$$
收敛半径
$$R=\sqrt{\lim_{k \to +\infty}\left|\frac{a_{2k-2}}{a_{2k}}\right|}=\sqrt{\lim_{k \to +\infty}\left|\frac{2k(2l+2k+1)}{\lambda_n-M^2}\right|}=+\infty$$

