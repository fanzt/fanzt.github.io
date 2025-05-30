---
layout:     post
title:      "Calculating The Vacuum Energy by Path Integral"
subtitle:   "Interesting method."
date:       2025-3-1 22:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-3.jpg"
catalog: true
usemathjax: true
music-id: 2020880853
tags:
    - Physics
    - Quantum Field Theory
    - Class Homework
---

## Review：Vacuum Energy by Canonical Quantization

我们首先来简单地回忆一下正则量子化是如何计算场的零点能的。作为例子，我们考虑标量场（抄点高中时的笔记.jpg）。

首先将正则场算符和正则动量算符做 Fourier 展开，我们有：

$$
\begin{aligned}
    \phi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^{3/2}}\:\frac{1}{\sqrt{2\omega_{\mathbf{p}}}}\left(a_{\mathbf{p}}e^{i\mathbf{p}·\mathbf{x}}+a_\mathbf{p}^\dagger e^{-i\mathbf{p}·\mathbf{x}}\right)
    \\\pi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^{3/2}}\:(-i)\sqrt{\frac{\omega_\mathbf{p}}{2}}\left(a_{\mathbf{p}}e^{i\mathbf{p}·\mathbf{x}}-a_\mathbf{p}^\dagger e^{-i\mathbf{p}·\mathbf{x}}\right)
\end{aligned}
$$

由于括号中的两项积分独立，我们可以将第二项中的 $\mathbf{p}$ 替换为 $-\mathbf{p}$ ，并将指数项提到后面：

$$
\begin{aligned}
    \phi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^{3/2}}\:\frac{1}{\sqrt{2\omega_{\mathbf{p}}}}\left(a_{\mathbf{p}}+a_\mathbf{-p}^\dagger\right)e^{i\mathbf{p}·\mathbf{x}}
    \\\pi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^{3/2}}\:(-i)\sqrt{\frac{\omega_\mathbf{p}}{2}}\left(a_{\mathbf{p}}-a_\mathbf{-p}^\dagger\right)e^{i\mathbf{p}·\mathbf{x}}
\end{aligned}
$$

产生湮灭算符的对易关系可以变为：

$$
    [a_{\mathbf{p}},a_\mathbf{p'}^\dagger]=\delta^{(3)}(\mathbf{p}-\mathbf{p}')
$$

我们通过计算 $\phi$ 与 $\pi$ 的对易子来验证一下这个对易关系的正确性：

$$
\begin{aligned}
    \left[\phi(\boldsymbol{\rm x}),\pi(\boldsymbol{\rm x}')\right]&=\int\frac{d^3pd^3p'}{(2\pi)^3}\frac{-i}{2}\sqrt{\frac{\omega_\mathbf{p'}}{\omega_\mathbf{p}}}([a^\dagger_\mathbf{-p},a_\mathbf{p}]-[a_\mathbf{p},a^\dagger_\mathbf{-p}])e^{i(\mathbf{p}·\mathbf{x}+\mathbf{p'}·\mathbf{x'})}\\&=\int\frac{d^3pd^3p'}{(2\pi)^3}i\delta^3(\mathbf{p}-(-\mathbf{p'}))e^{(i(\mathbf{p}·\mathbf{x}+\mathbf{p'}·\mathbf{x'}))}\\&=\int\frac{d^3p}{(2\pi)^3}ie^{i\mathbf{p}·(\mathbf{x}-\mathbf{x'})}\\&=i\delta^3(\mathbf{x}-\mathbf{x'})
\end{aligned}
$$

然后我们可以构建Hamiltonian：

$$
\begin{aligned}
    H&=\int d^3x\:\mathcal H\\&=\int d^3x[\frac{1}{2}\pi^2+\frac{1}{2}(\nabla\phi)^2+\frac{1}{2}m^2\phi^2]
\end{aligned}
$$

其中：

$$
\begin{aligned}
    \phi^2&=\int
    \frac{d^3pd^3p'}{(2\pi)^3}
    \frac{1}{2\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\pi^2&=\int
    \frac{d^3pd^3p'}{(2\pi)^3}
    \frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{2}
    (a_\mathbf{p}-a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}-a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\nabla\phi&=\int
    \frac{d^3p}{(2\pi)^{3/2}}
    \frac{i\mathbf{p}}{\sqrt{2\omega_\mathbf{p}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    e^{i\mathbf{p}·\mathbf{x}}
    \\(\nabla\phi)^2&=\int
    \frac{d^3pd^3p'}{(2\pi)^3}
    \frac{-\mathbf{p}·\mathbf{p'}}{2\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
\end{aligned}
$$

于是：

$$
\begin{aligned}
    H&=\int d^3x\int\frac{d^3pd^3p'}{(2\pi)^3}e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\times&\left\{\frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{4}(a_\mathbf{p}-a^\dagger_\mathbf{-p})(a_\mathbf{p'}-a^\dagger_\mathbf{-p'})+\frac{-\mathbf{p}·\mathbf{p'}+m^2}{4\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}(a_\mathbf{p}+a^\dagger_\mathbf{-p})(a_\mathbf{p'}+a^\dagger_\mathbf{-p'})\right\}
    \\&=\int{d^3pd^3p'}\delta^3(\mathbf{p}-(-\mathbf{p'}))
    \\&\times\frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{4}(a_\mathbf{p}-a^\dagger_\mathbf{-p})(a_\mathbf{p'}-a^\dagger_\mathbf{-p'})+\frac{-\mathbf{p}·\mathbf{p'}+m^2}{4\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}(a_\mathbf{p}+a^\dagger_\mathbf{-p})(a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    \\&=\int{d^3p}\left(-\frac{\omega_\mathbf{p}}{4}\right)(a_\mathbf{p}-a^\dagger_{-\mathbf{p}})(a_{-\mathbf{p}}-a^\dagger_{\mathbf{p}})+\frac{\omega_\mathbf{p}}{4}(a_\mathbf{p}+a^\dagger_{-\mathbf{p}})(a_{-\mathbf{p}}+a^\dagger_{\mathbf{p}})
\end{aligned}
$$

注意到：

$$
    \int^\infty_{-\infty} f(-x)\:dx=\int^{-\infty}_\infty -f(u)\:du=\int^\infty_{-\infty}f(u)\:du
$$

于是有：

$$
\begin{aligned}
    H&=\int{d^3p}\frac{\omega_\mathbf{p}}{4}(2[a_\mathbf{p},a^\dagger_\mathbf{p}]+4a^\dagger_\mathbf{p}a_\mathbf{p})
    \\&=\int{d^3p}\omega_\mathbf{p}\left(\frac{1}{2}[a_\mathbf{p},a^\dagger_\mathbf{p}]+a^\dagger_\mathbf{p}a_\mathbf{p}\right)
\end{aligned}
$$

可以看到，标量场的 Hamiltonian 中多了一项正比于 `$[a_\mathbf{p},a^\dagger_\mathbf{p}]=\delta^3(0)$` 的项。这一项是无穷大的发散，也便是所谓的零点能。

## Path Integral Method: Scalar and Spinor

我们都知道路径积分量子化方法从原理上是和正则量子化方法等价的。但一般的教科书上都不会介绍利用路径积分方法计算场的真空零点能的途径。不过，作为只使用路径积分方法构建量子场论的典范，A.Zee 的教科书确实展示了如何利用路径积分方法获得标量场的零点能。本小节我们便来介绍这一方法，并尝试将其拓展到旋量场。此外，在下一小节，我们将会利用该方法求出规范矢量场（电磁场）的零点能，并探讨其规范不变性。

首先，路径积分的起始自然是写下我们熟悉的生成泛函：

$$
    \mathcal{Z}[J]=C_0\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\mathscr{L}[\phi]+J\phi\right\}
$$

其中 $C_0$ 是一个常数（来源于边界波函数）。

我们知道对流 $J$ 求泛函导数可以获得关联函数。如果把流 $J$ 取成 $0$，我们可以给出其物理意义为：

$$
    \mathcal{Z}[0]=\langle\mathrm{vac};(+\infty)|\mathrm{vac};(-\infty)\rangle=\lim_{t_1,t_2\rightarrow-\infty,+\infty}\langle\Omega|\mathrm{e}^{-\mathrm{i}H(t_2-t_1)}|\Omega\rangle
$$

在一般的利用路径积分方法微扰计算关联函数的时候，我们往往直接将这样的真空-真空图贡献作为分母除掉了。然而，实际上，将该贡献如上写开，并利用通常的归一化规则后，我们恰好能看到其物理意义是：

$$
    \langle\mathrm{vac};(+\infty)|\mathrm{vac};(-\infty)\rangle=\mathrm{e}^{-\mathrm{i}E_{0}T}
$$

其中 `$T=\lim_{t_1,t_2\rightarrow-\infty,+\infty}(t_2-t_1)$`，而 `$E_0$` 恰好正是 Hamiltonian 的真空期望值，也就是零点能。而另一方面，依生成泛函的表达式，我们又有：

$$
    \mathcal{Z}[0]=C_0\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\mathscr{L}[\phi]\right\}
$$

于是，我们便有了一个很直接的想法：直接把这个积分积出来，再取对数，就可以求得我们需要的零点能了。接下来我们就会看到，这套思想确实是可行的。

作为一个例子，我们先来算标量场（玻色子）的情形：

$$
\begin{aligned}
    \mathcal{Z}[0]&=C_0\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\left[-\frac{1}{2}\partial_{\mu}\phi\partial^{\mu}\phi-\frac{1}{2}m^2\phi^2-\mathrm{i}\varepsilon项\right]\right\}
    \\&=C_0\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\mathrm{d}^4y\:\left[-\frac{1}{2}\left(\frac{\partial}{\partial x^\mu}\frac{\partial}{\partial y_\mu}+m^2-\mathrm{i}\varepsilon项\right)\delta^4(x-y)\phi(x)\phi(y)\right]\right\}
\end{aligned}
$$

依据多变量高斯积分公式的一个直接的连续推广，我们可以将其积分出来：

$$
    \mathcal{Z}[0]=C_0\left[\det\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\delta^4(x-y)\right)\right]^{-1/2}
$$

再利用行列式的一个著名的公式，我们便可以将其化为指数形式：

$$
    \mathcal{Z}[0]=C_0\exp\left[-\frac{1}{2}\mathrm{Tr}\ln\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\delta^4(x-y)\right)\right]
$$

$\delta^4(x-y)$ 仅有筛选作用，将其提到对数外面（严格来说我们应当将这里的 $\delta$ 函数定义在离散时空格点上。）

将上式中的迹写成积分：

$$
\begin{aligned}
    &\mathrm{Tr}\ln\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\right)\delta^4(x-y)&\\=&\int\mathrm{d}^4x\:\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)\mathrm{e}^{\mathrm{i}p\cdot(x-x)}
    \\=&\:VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)
\end{aligned}
$$

与零点能的公式对比，我们就有：

$$
    iE_0T=\frac{1}{2}VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)+C'_0
$$

然而，容易注意到，表达式中的对数竟然含有量纲，并且这个积分是发散的。此时常数 `$C'_0$` 便有了用处。我们将其作为一个正规化因子引入。将积分改写为：

$$
    iE_0T=\frac{1}{2}VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\left[\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)-\ln\left(\frac{p^2+m'^2-\mathrm{i}\varepsilon}{2\pi}\right)\right]
$$

由于正规化因子不应当对能量有任何实质的贡献，我们需要在计算的最后令 `$E'_{\mathbf{p}}=\sqrt{|\mathbf{p}|^2+m'^2}=0$`.

做掉这个正规化后的积分，我们有：

$$
\begin{aligned}
    &\int\frac{\mathrm{d}^4p}{(2\pi)^4}\left[\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)-(m\rightarrow m')\right]
    \\=&-\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{2\pi}{|\mathbf{p}|^2-(p^0)^2+m^2-\mathrm{i}\varepsilon}\cdot(\frac{-2p^0}{2\pi})-(m\rightarrow m')
    \\=&\:i\int\frac{\mathrm{d}^3p}{(2\pi)^3}2E_{\mathbf{p}}^2\frac{1}{2E_{\mathbf{p}}}-(E_{\mathbf{p}}\rightarrow E'_{\mathbf{p}})
    \\=&\:i\int\frac{\mathrm{d}^3p}{(2\pi)^3}E_{\mathbf{p}}
\end{aligned}
$$

最后一步我们通过令 $E'_{\mathbf{p}}\rightarrow0$ 移除了正规化。

于是我们最终有：

$$
    E_0=\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{1}{2}E_{\mathbf{p}}V
$$

其中 `$E_{\mathbf{p}}=\sqrt{|\mathbf{p}|^2+m^2}$`，体元 $V$ 可以被理解为：

$$
    V=\int\mathrm{d}^3x\:\mathrm{e}^{\mathrm{i}p\cdot0}=(2\pi)^3\delta^3(0)
$$

这和正则方法的答案一致。

同样，我们可以将这套方案应用在旋量场上。写出 Dirac 旋量场的生成泛函，我们有：

$$
\begin{aligned}
    \mathcal{Z}[0]&=C_0\int\mathcal{D}\psi\mathcal{D}(i\psi^\dagger)\:\exp\left\{i\int\mathrm{d}^4x\:\left[-\bar{\psi}(\gamma^\mu\partial_\mu+m)\psi-\mathrm{i}\varepsilon项\right]\right\}
    \\&=C_0\int\mathcal{D}\psi\mathcal{D}(i\psi^\dagger)\:\exp\left\{i\int\mathrm{d}^4x\mathrm{d}^4y\:\left[-\gamma^0\left(\gamma^\mu\frac{\partial}{\partial x^\mu}+m-\mathrm{i}\varepsilon项\right)\delta^4(x-y)i\psi^\dagger(x)\psi(y)\right]\right\}
\end{aligned}
$$

注意，我们不使用 $\bar{\psi}$ 的原因是它不是正则共轭变量。利用 Grassmann 代数的换元和积分规则，我们可以得到：

$$
    \mathcal{Z}[0]=C_0\det\left[\gamma^0\left(\gamma^\mu\frac{\partial}{\partial x^\mu}+m-\mathrm{i}\varepsilon\right)\delta^4(x-y)\right]
$$

利用行列式的恒等式，我们将其写为：

$$
    \mathcal{Z}[0]=C_0\exp\left[\mathrm{Tr}\ln\gamma^0\left(\gamma^\mu\frac{\partial}{\partial x^\mu}+m-\mathrm{i}\varepsilon\right)\delta^4(x-y)\right]
$$

（其实我们在这里已经可以窥见费米子和玻色子零点能系数区别的端倪，二者刚好相差负二倍。负号来源于 Grassmann 代数的反对易性，二倍则来自于 Grassmann 代数中正则场和共轭正则动量是独立变量。）

将迹写为：

$$
\begin{aligned}
    &\mathrm{Tr}\ln\gamma^0\left(\gamma^\mu\frac{\partial}{\partial x^\mu}+m-\mathrm{i}\varepsilon\right)\delta^4(x-y)
    \\=&\sum_{\ell}\int\mathrm{d}^4x\:\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\gamma^0\left(\mathrm{i}p\!\!\!/+m-\mathrm{i}\varepsilon\right)\mathrm{e}^{\mathrm{i}p\cdot(x-x)}
    \\=&\:VT\sum_{\ell}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\gamma^0\left(\mathrm{i}p\!\!\!/+m-\mathrm{i}\varepsilon\right)
\end{aligned}
$$

其中 $\ell$ 是旋量指标。

对比后我们便得到了 Dirac 旋量零点能的表达式：

$$
    iE_0T=-VT\sum_{\ell}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\gamma^0\left(\mathrm{i}p\!\!\!/+m-\mathrm{i}\varepsilon\right)+C'_0
$$

其中 $C_0'$ 同样将作为正规化因子引入，以便令我们将对数无量纲化并使得积分收敛。

做掉这个积分，我们有：

$$
\begin{aligned}
    &\sum_{\ell}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\gamma^0\left(\mathrm{i}p\!\!\!/+m-\mathrm{i}\varepsilon\right)+C'_0
    \\=&\sum_{\ell}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}\ln\gamma^0\left(\mathrm{i}p\!\!\!/+m-\mathrm{i}\varepsilon\right)+C'_0
    \\=&-\sum_{\ell}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\left(-\gamma^0\frac{-ip\!\!\!/+m}{p^2+m^2-\mathrm{i}\varepsilon}\right)\cdot\left(-i\gamma^0\gamma^0\right)+C'_0
    \\=&-\sum_{\ell}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\left(-\gamma^0\frac{-ip\!\!\!/+m}{p^2+m^2-\mathrm{i}\varepsilon}\right)\cdot\left(-i\gamma^0\gamma^0\right)+C'_0
    \\=&\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\left(\frac{4p^0}{p^2+m^2-\mathrm{i}\varepsilon}\right)+C'_0
\end{aligned}
$$

于是经过与标量场类似的计算，我们可以最终得到：

$$
    E_0=-\int\frac{\mathrm{d}^3p}{(2\pi)^3}2E_{\mathbf{p}}V
$$

或许我们会疑惑这个结果为什么是标量场的四倍而非我们预期的二倍。事实上这是因为 Dirac 场同时描述了自旋为 $+1/2$ 和 $-1/2$ 的费米子，而我们这里的结果实际上是对自旋求和了，因此又额外增加了二倍。这也与一般见到的正则方法获得的结果一致（正则方法一般会保留对自旋的求和号）。

## Gauge Field Example: Electromagnet Field

通过上面的讨论，我们看到路径积分方法的确给出了和正则方法一致的结果。然而，众所周知，相比于正则形式，路径积分方法一个显著的优势是其可以保证显式的 Lorentz 不变性和更加方便的规范对称性处理。因此，我们接下来便考虑利用路径积分方法处理最简单的规范场零点能，也就是电磁场的零点能。

首先写出经过了 Faddeev-Popov 规范固定后的有效生成泛函：

$$
\begin{aligned}
    \mathcal{Z}[0]&=\int\mathcal{D}A_{\mu}\exp\left\{\mathrm{i}\int\mathrm{d}^4x\left[-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\frac{1}{2}\alpha\left(\partial_{\mu}A^{\mu}\right)^2-\mathrm{i}\varepsilon 项\right]\right\}
    \\&=\int\mathcal{D}A_{\mu}\exp\left\{\mathrm{i}\int\mathrm{d}^4x\mathrm{d}^4y\left[-\frac{1}{2}\left(\eta_{\mu\nu}\frac{\partial}{\partial x^\rho}\frac{\partial}{\partial y_\rho}-(1-\alpha)\frac{\partial}{\partial x^\mu}\frac{\partial}{\partial y^\nu}-\mathrm{i}\varepsilon\right)\delta^4(x-y)A^{\mu}(x)A^{\nu}(y)\right]\right\}
\end{aligned}
$$

经过一串几乎与标量场完全一致的讨论，我们最终需要的便是做掉这个积分：

$$
    I=\sum_{\mu=\nu}\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\eta_{\mu\nu}p^2-(1-\alpha)p_{\mu}p_{\nu}-\mathrm{i}\varepsilon\right)+C'
$$

利用类似的操作进行化简，我们有：

$$
\begin{aligned}
    I&=-\sum_{\mu=\nu}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{1}{p^2-\mathrm{i}\varepsilon}\left[\eta^{\mu\rho}-\left(1-\frac{1}{\alpha}\right)\frac{p^{\mu}p^{\rho}}{p^2}\right]\cdot\left[-2p^0\eta_{\rho\nu}-(1-\alpha)\left(\eta_{0\rho}p_{\nu}+p_{\rho}\eta_{0\nu}\right)\right]+C'
    \\&=-\sum_{\mu=\nu}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{1}{p^2-\mathrm{i}\varepsilon}\left[-8p^0+2p^0\left(1-\frac{1}{\alpha}\right)-(1-\alpha)(-p^0-p^0)+\left(1-\frac{1}{\alpha}\right)(1-\alpha)(-p^0-p^0)\right]+C'
    \\&=-\sum_{\mu=\nu}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{-2p^0}{p^2-\mathrm{i}\varepsilon}\left[4-\left(1-\frac{1}{\alpha}\right)-(1-\alpha)+(1-\alpha)\left(1-\frac{1}{\alpha}\right)\right]+C'
    \\&=-\sum_{\mu=\nu}\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{-2p^0}{p^2-\mathrm{i}\varepsilon}\times 4+C'
\end{aligned}
$$

可以看到，规范项恰好消掉了，因此我们验证了真空能量的规范不变性。上式给出了与标量场一致的形式，但是差了四倍的系数。然而我们都知道，光子场只有两个物理自由度，其应当是标量场的两倍。事实上，这是因为我们未考虑 Faddeev-Popov 鬼场的贡献。

## Ghost Field

$$
    \begin{aligned}
        \mathcal{Z}[0]_G=C_1\int\mathcal{D}\omega^*\mathcal{D}\omega\exp\left\{\mathrm{i}\int\mathrm{d}^4x\mathrm{d}^4y{\omega}^*(x)\omega(y)\mathcal{M}(x,y)\right\}=C_1\det\mathcal{M}(x,y)
    \end{aligned}
$$

基于类似的讨论，有：

$$
    \begin{aligned}
        -\mathrm{i}E_{0G}T&=\mathrm{tr}\ln\left[\left(\frac{\partial}{\partial x_\mu}\frac{\partial}{\partial y^\mu}-\mathrm{i}\varepsilon\right)\delta^4(x-y)\right]+\ln{C_1}
        \\&=VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(p^2-\mathrm{i}\varepsilon\right)+\ln{C'_1}
    \end{aligned}
$$

类似地进行积分，可以算出：

$$
    \begin{aligned}
        \mathrm{i}E_{0G}&=V\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{-2p^0}{|\mathbf{p}|^2-(p^0)^2-\mathrm{i}\varepsilon}+C'
        \\&=-\mathrm{i}V\int\frac{\mathrm{d}^3p}{(2\pi)^3}\left(E_{\mathbf{p}}-E'_{\mathbf{p}}\right)
    \end{aligned}
$$

因而有：

$$
    E_{0G}=-2\times\frac{1}{2}V\int\frac{\mathrm{d}^3p}{(2\pi)^3}\left(E_{\mathbf{p}}-E'_{\mathbf{p}}\right).
$$

将两项的贡献加和，即有：

$$
    E_0=(4-2)\times\frac{1}{2}V\int\frac{\mathrm{d}^3p}{(2\pi)^3}\left(E_{\mathbf{p}}-E'_{\mathbf{p}}\right)=2\times\frac{1}{2}V\int\frac{\mathrm{d}^3p}{(2\pi)^3}\left(E_{\mathbf{p}}-E'_{\mathbf{p}}\right).
$$
