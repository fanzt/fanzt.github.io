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
    \mathcal{Z}[J]=\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\mathscr{L}[\phi]+J\phi\right\}
$$

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
    \mathcal{Z}[0]=\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\mathscr{L}[\phi]\right\}
$$

于是，我们便有了一个很直接的想法：直接把这个积分积出来，再取对数，就可以求得我们需要的零点能了。接下来我们就会看到，这套思想确实是可行的。

作为一个例子，我们先来算标量场（玻色子）的情形：

$$
\begin{aligned}
    \mathcal{Z}[0]&=\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\left[-\frac{1}{2}\partial_{\mu}\phi\partial^{\mu}\phi-\frac{1}{2}m^2\phi^2-\mathrm{i}\varepsilon项\right]\right\}
    \\&=\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\mathrm{d}^4y\:\left[-\frac{1}{2}\left(\frac{\partial}{\partial x^\mu}\frac{\partial}{\partial y_\mu}+m^2-\mathrm{i}\varepsilon项\right)\delta^4(x-y)\phi(x)\phi(y)\right]\right\}
\end{aligned}
$$

依据多变量高斯积分公式的一个直接的连续推广，我们可以将其积分出来：

$$
    \mathcal{Z}[0]=\left[\det\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\delta^4(x-y)\right)\right]^{-1/2}
$$

再利用行列式的一个著名的公式，我们便可以将其化为指数形式：

$$
    \mathcal{Z}[0]=\exp\left[-\frac{1}{2}\mathrm{Tr}\ln\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\delta^4(x-y)\right)\right]
$$

$\delta^4(x-y)$ 仅有筛选作用，将其提到对数外面（严格来说我们应当将这里的 $\delta$ 函数定义在离散时空格点上。）

将上式中的迹写成积分：

$$
\begin{aligned}
    \mathrm{Tr}\ln\left(\frac{\partial_\mu\partial^\mu+m^2-\mathrm{i}\varepsilon}{2\pi}\right)\delta^4(x-y)&=\int\mathrm{d}^4x\:\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)\mathrm{e}^{\mathrm{i}p\cdot(x-x)}
    \\&=VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)
\end{aligned}
$$

与零点能的公式对比，我们就有：

$$
    iE_0T=\frac{1}{2}VT\int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)
$$

做掉这个积分，我们有：

$$
\begin{aligned}
    \int\frac{\mathrm{d}^4p}{(2\pi)^4}\ln\left(\frac{p^2+m^2-\mathrm{i}\varepsilon}{2\pi}\right)&=-\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{\mathrm{d}p^0}{2\pi}p^0\frac{2\pi}{|\mathbf{p}|^2-(p^0)^2+m^2-\mathrm{i}\varepsilon}\cdot(\frac{-2p^0}{2\pi})
    \\&=i\int\frac{\mathrm{d}^3p}{(2\pi)^3}2E_{\mathbf{p}}^2\frac{1}{2E_{\mathbf{p}}}
    \\&=i\int\frac{\mathrm{d}^3p}{(2\pi)^3}E_{\mathbf{p}}
\end{aligned}
$$

于是我们最终有：

$$
    E_0=\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{1}{2}E_{\mathbf{p}}V
$$

其中 `$E_{\mathbf{p}}=\sqrt{|\mathbf{p}|^2+m^2}$`，体元 $V$ 可以被理解为：

$$
    V=\int\mathrm{d}^3x\:\mathrm{e}^{\mathrm{i}p\cdot0}=(2\pi)^3\delta^3(0)
$$

于是这和正则方法的答案一致。