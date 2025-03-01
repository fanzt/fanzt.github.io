---
layout:     post
title:      "Calculating The Vacuum Energy by Path Integral"
subtitle:   "Interesting method."
date:       2025-3-1 22:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-3.png"
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
    \phi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^3}\:\frac{1}{\sqrt{2\omega_{\mathbf{p}}}}\left(a_{\mathbf{p}}e^{i\mathbf{p}·\mathbf{x}}+a_\mathbf{p}^\dagger e^{-i\mathbf{p}·\mathbf{x}}\right)
    \\\pi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^3}\:(-i)\sqrt{\frac{\omega_\mathbf{p}}{2}}\left(a_{\mathbf{p}}e^{i\mathbf{p}·\mathbf{x}}-a_\mathbf{p}^\dagger e^{-i\mathbf{p}·\mathbf{x}}\right)
\end{aligned}
$$

由于括号中的两项积分独立，我们可以将第二项中的 $\mathbf{p}$ 替换为 $-\mathbf{p}$ ，并将指数项提到后面：

$$
\begin{aligned}
    \phi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^3}\:\frac{1}{\sqrt{2\omega_{\mathbf{p}}}}\left(a_{\mathbf{p}}+a_\mathbf{-p}^\dagger\right)e^{i\mathbf{p}·\mathbf{x}}
    \\\pi(\mathbf{x})&=\int\:\frac{d^3p}{(2\pi)^3}\:(-i)\sqrt{\frac{\omega_\mathbf{p}}{2}}\left(a_{\mathbf{p}}-a_\mathbf{-p}^\dagger\right)e^{i\mathbf{p}·\mathbf{x}}
\end{aligned}
$$

产生湮灭算符的对易关系可以变为：

$$
    [a_{\mathbf{p}},a_\mathbf{p'}^\dagger]=(2\pi)^3\delta^{(3)}(\mathbf{p}-\mathbf{p}')
$$

（这里 $(2\pi)^3$ 项的引入是为了后续计算能与分母上的 $(2\pi)^3$ 项消掉。）

我们通过计算 $\phi$ 与 $\pi$ 的对易子来验证一下这个对易关系的正确性：

$$
\begin{aligned}
    \left[\phi(\boldsymbol{\rm x}),\pi(\boldsymbol{\rm x}')\right]&=\int\frac{d^3pd^3p'}{(2\pi)^6}\frac{-i}{2}\sqrt{\frac{\omega_\mathbf{p'}}{\omega_\mathbf{p}}}([a^\dagger_\mathbf{-p},a_\mathbf{p}]-[a_\mathbf{p},a^\dagger_\mathbf{-p}])e^{i(\mathbf{p}·\mathbf{x}+\mathbf{p'}·\mathbf{x'})}\\&=\int\frac{d^3pd^3p'}{(2\pi)^3}i\delta^3(\mathbf{p}-(-\mathbf{p'}))e^{(i(\mathbf{p}·\mathbf{x}+\mathbf{p'}·\mathbf{x'}))}\\&=\int\frac{d^3p}{(2\pi)^3}ie^{i\mathbf{p}·(\mathbf{x}-\mathbf{x'})}\\&=i\delta^3(\mathbf{x}-\mathbf{x'})
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
    \frac{d^3pd^3p'}{(2\pi)^6}
    \frac{1}{2\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\pi^2&=\int
    \frac{d^3pd^3p'}{(2\pi)^6}
    \frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{2}
    (a_\mathbf{p}-a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}-a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\nabla\phi&=\int
    \frac{d^3p}{(2\pi)^3}
    \frac{i\mathbf{p}}{\sqrt{2\omega_\mathbf{p}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    e^{i\mathbf{p}·\mathbf{x}}
    \\(\nabla\phi)^2&=\int
    \frac{d^3pd^3p'}{(2\pi)^6}
    \frac{-\mathbf{p}·\mathbf{p'}}{2\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}
    (a_\mathbf{p}+a^\dagger_\mathbf{-p})
    (a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
\end{aligned}
$$

于是：

$$
\begin{aligned}
    H&=\int d^3x\int\frac{d^3pd^3p'}{(2\pi)^6}e^{i(\mathbf{p}+\mathbf{p'})·\mathbf{x}}
    \\\times&\left\{\frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{4}(a_\mathbf{p}-a^\dagger_\mathbf{-p})(a_\mathbf{p'}-a^\dagger_\mathbf{-p'})+\frac{-\mathbf{p}·\mathbf{p'}+m^2}{4\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}(a_\mathbf{p}+a^\dagger_\mathbf{-p})(a_\mathbf{p'}+a^\dagger_\mathbf{-p'})\right\}
    \\&=\int\frac{d^3pd^3p'}{(2\pi)^3}\delta^3(\mathbf{p}-(-\mathbf{p'}))
    \\&\times\frac{-\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}{4}(a_\mathbf{p}-a^\dagger_\mathbf{-p})(a_\mathbf{p'}-a^\dagger_\mathbf{-p'})+\frac{-\mathbf{p}·\mathbf{p'}+m^2}{4\sqrt{\omega_\mathbf{p}\omega_\mathbf{p'}}}(a_\mathbf{p}+a^\dagger_\mathbf{-p})(a_\mathbf{p'}+a^\dagger_\mathbf{-p'})
    \\&=\int\frac{d^3p}{(2\pi)^3}\left(-\frac{\omega_\mathbf{p}}{4}\right)(a_\mathbf{p}-a^\dagger_{-\mathbf{p}})(a_{-\mathbf{p}}-a^\dagger_{\mathbf{p}})+\frac{\omega_\mathbf{p}}{4}(a_\mathbf{p}+a^\dagger_{-\mathbf{p}})(a_{-\mathbf{p}}+a^\dagger_{\mathbf{p}})
\end{aligned}
$$

注意到：

$$
    \int^\infty_{-\infty} f(-x)\:dx=\int^{-\infty}_\infty -f(u)\:du=\int^\infty_{-\infty}f(u)\:du
$$

于是有：

$$
\begin{aligned}
    H&=\int\frac{d^3p}{(2\pi)^3}\frac{\omega_\mathbf{p}}{4}(2[a_\mathbf{p},a^\dagger_\mathbf{p}]+4a^\dagger_\mathbf{p}a_\mathbf{p})
    \\&=\int\frac{d^3p}{(2\pi)^2}\omega_\mathbf{p}\left(\frac{1}{2}[a_\mathbf{p},a^\dagger_\mathbf{p}]+a^\dagger_\mathbf{p}a_\mathbf{p}\right)
\end{aligned}
$$

可以看到，标量场的 Hamiltonian 中多了一项正比于 `$[a_\mathbf{p},a^\dagger_\mathbf{p}]=\delta^3(0)$` 的项。这一项是无穷大的发散，也便是所谓的零点能。

## Path Integral Method

我们都知道路径积分量子化方法从原理上是和正则量子化方法等价的。但一般的教科书上都不会介绍利用路径积分方法计算场的真空零点能的方法。不过，作为只使用路径积分方法构建量子场论的典范，A.Zee 的教科书确实展示了如何利用路径积分方法获得标量场的零点能。本小节我们便来介绍这一方法，并尝试将其拓展到旋量场。此外，在下一小节，我们将会利用该方法求出规范矢量场（电磁场）的零点能，并探讨其规范不变性。

首先，路径积分的起始自然是写下我们熟悉的生成泛函：

$$
    \mathcal{Z}[J]=\int\mathcal{D}\phi\:\exp\left\{i\int\mathrm{d}^4x\:\mathscr{L}[\phi]+J\phi\right\}
$$

TBD.