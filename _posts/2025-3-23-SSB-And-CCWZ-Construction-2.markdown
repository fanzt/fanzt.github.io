---
layout:     post
title:      "Spontaneous Symmetry Breaking and CCWZ Construction 2"
subtitle:   "Anderson-Higgs Mechanism"
date:       2025-3-23 20:20:00
author:     "fromuly"
header-img: "img/post-bg-2025-7.jpg"
catalog: true
usemathjax: true
music-id: 496869422
tags:
    - Physics
    - Quantum Field Theory
---

## Anderson-Higgs Mechanism

在上一篇文章中，我们讨论了自发破缺的整体对称性与描述产生相应 NG 粒子的 Goldstone 定理。其中，我们提到了“局域对称性”不得自发破缺的结论。然而，广为人知地，标准模型的电弱统一理论经常被描述为通过所谓的“自发规范对称性破缺”（即 Anderson-Higgs 机制）为玻色子和费米子赋予质量。事实上，这一说法多少有一些误导。Anderson-Higgs 机制实际上并没有（依 Elitzur 定理，也不能）破缺定域的规范对称性，其本质是取定规范后破缺了相应的整体对称性。在本篇文章中，我们便来简短地讨论一下这个问题。

作为例子，考虑我们最熟悉的 $U(1)$ 规范对称性（QED）作用量：

$$
    S=\int\mathrm{d}^4x\left\{-|D_\mu\phi|^2-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-V(\phi)\right\}
$$

其中标量场相互作用为：

$$
    V(\phi)=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2
$$

协变导数为：

$$
    D_\mu=\partial_\mu+\mathrm{i}eA_\mu\ .
$$

我们说该理论具有 $U(1)$ 规范对称性，是指作用量在如下变换下不发生改变：

$$
    \phi(x)\rightarrow\phi(x)\mathrm{e}^{\mathrm{i}\alpha(x)},\quad A_\mu(x)\rightarrow A_\mu(x)-\frac{1}{e}\partial_\mu\alpha(x)\ .
$$

接下来考虑自发破缺的**整体** $U(1)$ 对称性，一如我们在处理 Goldstone 粒子时的操作一样，将标量场重写为极坐标形式（分离破缺方向与未破缺方向）：

$$
    \phi(x)=\frac{1}{\sqrt{2}}\mathrm{e}^{\mathrm{i}\xi(x)}(v+\sigma(x))
$$

其中 $v=\sqrt{\mu^2/\lambda}$ 是标量场的 VEV.

将其带入 Lagrangian 并化简，有：

$$
\begin{aligned}
    \mathscr{L}&=-\frac{1}{2}\partial_\mu\sigma\partial^\mu\sigma-\frac{1}{2}\left(2\lambda v^2\right)\sigma^2-\frac{1}{2}e^2(v+\sigma(x))^2\left(A_\mu+\frac{1}{e}\partial_\mu\xi\right)^2
    \\&-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\lambda v\sigma^3-\frac{1}{4}\lambda\sigma^4+\frac{1}{4}\lambda v^4\ .
\end{aligned}
$$

注意到，此时的 Lagrangian **仍旧是规范不变的**，因为此时规范变换变为了：

$$
    \xi(x)\rightarrow\xi(x)+\alpha(x),\quad A_\mu(x)\rightarrow A_\mu(x)-\frac{1}{e}\partial_\mu\alpha(x)\ .
$$

于是 Lagrangian 显然规范不变。然而，我们知道所谓 Anderson-Higgs 机制描述的实际上是 NG 粒子被规范场吸收提供了纵向极化态的过程。因此接下来我们要**取定规范**：

$$
    A'_\mu=A_\mu+\frac{1}{e}\partial_\mu\xi
$$

直到这一步，我们才相当于移除了系统的规范对称性。从此处可以看到，规范对称性的消失**并不是一个自发对称性破缺的过程**。没有任何序参量描述规范对称性的消失。

在取定规范后，我们有：

$$
\begin{aligned}
    \mathscr{L}&=-\frac{1}{2}\partial_\mu\sigma\partial^\mu\sigma-\frac{1}{2}\left(2\lambda v^2\right)\sigma^2-\frac{1}{2}e^2(v+\sigma(x))^2A'_\mu A'^\mu
    \\&-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-\lambda v\sigma^3-\frac{1}{4}\lambda\sigma^4+\frac{1}{4}\lambda v^4
\end{aligned}
$$

此时，我们会发现，矢量场 `$A'_\mu$` 获得了三个自由度，并获得了一个大小为 $ev$ 的质量。而获得质量 $2\lambda v^2$ 的标量场 $\sigma$，便是我们所知的 Higgs 粒子。

## Electroweak Theory

我们当然要展示一下 Anderson-Higgs 机制最为著名的应用，电弱理论标准模型的 `$\mathrm{SU(2)\times U(1)}\rightarrow\mathrm{U(1)}$` 过程。作为例子，我们暂时不考察含费米子项的手征理论，只关注规范场和 Higgs 部分。

TBD.