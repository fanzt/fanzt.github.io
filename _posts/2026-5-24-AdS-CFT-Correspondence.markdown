---
layout:     post
title:      "AdS/CFT Correspondence"
subtitle:   "As above, so below; as within, so without; as the universe, so the soul."
date:       2026-5-24 22:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-5.png"
catalog: true
usemathjax: true
music-id: 3372975275
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
    - String Theory
---

## Introduction

毋庸置疑地，整个二十世纪的物理学被「对称性」所主导。从 Noether 证明连续对称性与守恒流的关系作为起始，对称性在过去的一百年中成为了所有指引理论物理学发展的思想中最为明亮的那一座灯塔。广义协变性与 Einstein 引力理论，规范对称性与 Yang-Mills 规范场论，时空对称性与 Lee-Yang 宇称不守恒，整体对称性破缺与 Nambu-Goldstone 定理，Landau-Ginzburg 相变与 Brout-Englert-Higgs 机制，一直到粒子物理标准模型的落成，对称性始终是其中每一个环节的核心。

然而，随着人们将目光投向超越标准模型的理论与量子化引力、建立终极理论的至高目标，另一个在二十世纪中多少有些被掩盖了光彩的性质——「对偶性」，逐渐在二十一世纪的物理学中展现出愈发重要的地位。不同于对称性表述了一个理论自身拥有的性质，对偶性将多个不同的理论联系在了一起。一方面，对于原本理论中的问题，这为我们带来了全新的工具——我们可以使用对偶理论中的技术来求解原本理论中的问题；另一方面，这启示我们开始思考，曾经被认为用来定义一个物理系统的方法（例如，Lagrangian），是否只是一种像坐标系一样的非本质的描述方式。

在本文中，我们便来简要介绍总结人们目前最为关注的对偶关系之一：AdS/CFT 对偶关系。

## Some knowledge about String Theory

为了介绍 AdS/CFT，我们需要首先简要回顾一下弦论的知识。

### Strings in curved spacetime background

为了抵消 Weyl 反常，玻色弦理论需要生活在 26 维时空中，而超弦理论需要生活在 10 维时空中；这几乎已经是人尽皆知的特征。通过标准的光锥量子化/协变量子化，我们可以分别得到开弦和闭弦的最低激发态是快子场 $T(X)$，而第一激发态则分别是：

- 开弦：规范场 `$A_M(X)$`；
- 闭弦：度规场 `$G_{MN}(X)$`，Kalb-Ramond 二形式场 `$B_{MN}(X)$` 以及胀子场 `$\Phi(X)$`.

在低能截断的情况下，以上第一激发态对应的顶点算符对应于时空中这些相应背景场与弦世界面的耦合[^1]。因此，一般地，弦（只考虑第一激发态）的作用量可以写为：

$$
\begin{aligned}
    S_{eff}=\frac{1}{4\pi \alpha'}&\int_{\Sigma}\mathrm{d}^2\sigma\,\sqrt{\gamma}\left\{\left[\gamma^{ab} G_{MN}(X)+\mathrm{i}\epsilon^{ab}B_{MN}(X)\right]\partial_{a}X^{M}(\sigma)\partial_{b}X^{N}(\sigma)+\alpha' R(\gamma)\Phi(X)+T(X)\right\}
    \\+\mathrm{i}&\int_{\partial\Sigma}\mathrm{d}\Sigma^{a}\,\partial_a X^{M}(\sigma) A_M(X),
\end{aligned}
$$

其中最后一项是开弦的边界耦合。定义 $\beta^{\mathscr{F}}=\mathrm{d}\mathscr{F}/\mathrm{d}\ln\mu$，并令所有的耦合 $G, B, \Phi, A$ 的 $\beta$ 函数为零，可以给出背景场符合的运动方程（特别地，对于时空度规 $G$，这给出 Einstein 场方程）。反向构造可以实现这些运动方程的作用量，我们会得到：

$$
\begin{aligned}
    S_{eff,open}&=-T_{D-1}\int\mathrm{d}^Dx\,\mathrm{e}^{-\Phi}\sqrt{-\det(G_{MN}+B_{MN}+2\pi\alpha' F_{MN})},
    \\S_{eff,close}&=\frac{1}{2\kappa_0^2}\int\mathrm{d}^Dx\,\sqrt{-G}\mathrm{e}^{-2\Phi}\left\{R+4(\partial_M\Phi)^2-\frac{1}{12}H_{MNL}H^{MNL}-\frac{2(D-D_c)}{3\alpha'}\right.
    \\&\quad\:\:\left.-\partial_M T^2+\frac{4}{\alpha'}T^2+O(\alpha')\right\}.
\end{aligned}
$$

我们将它们分别识别为开弦和闭弦的低能有效作用量。

### Superstring and Supergravity

由于我们关注的 AdS/CFT 主要来自于 Type II 超弦，我们在这里只关注 Type II 超弦的作用量和低能极限。Type II 超弦在时空中只有闭弦部分，但是其可以有 D-p 膜解，这使得其可以允许引入连接在 D-p 膜上的开超弦。我们使用所谓的 RNS 超弦形式，即显式地引入世界面超对称（Type IIA 是 $(1,1)$ 型超对称而 Type IIB 是 $(2,0)$ 型）[^2]。对于 Type II 超弦，除了闭玻色弦所含的低能激发外，还会多出一系列 $p$ 形式规范场 $C_p(x)$，$p=1,3$ 对于 Type IIA，$p=0,2,4$ 对于 Type IIB. 世界面超场可以简便地表达出是界面超对称。定义：

$$
    \mathscr{D}_m={E_{m}}^{n}(\partial_{n}+\Omega_{n} \mathcal{J})
$$

其中 $m$ 指标取为 $(a,\alpha)=(++,--,+,-)$ 是超世界面参数化（$+\rightarrow\theta,-\rightarrow\bar{\theta}$）；${E_m}^n$ 是超世界面联络，$\Omega_n$ 是自旋联络，$\mathcal{J}$ 是超世界面上的 Lorentz 群生成元。

构造坐标超场 $\mathbf{X}^{\mu}(\mathbf{z},\mathbf{\bar{z}})$ 为：

$$
    \mathbf{X}^{\mu}(\mathbf{z},\mathbf{\bar{z}})=X^{\mu}+\mathrm{i}\sqrt{\alpha'}\theta\psi^{\mu}+\mathrm{i}\sqrt{\alpha'}\bar{\theta}\tilde{\psi}^{\mu}+\mathrm{i}\alpha'\theta\bar{\theta}F^{\mu}.
$$

其中 $\psi^{\mu}(z)$ 与 $\tilde{\psi}^{\mu}(\bar{z})$ 是世界面上的 Weyl-Majorana 旋量，但同时是时空中的 Lorentz 矢量；$F^{\mu}$ 是世界面上的标量，时空上的 Lorentz 矢量。于是我们可以给出 RNS 超弦耦合到 NS-NS 背景场后的 Polyakov 作用量：

$$
    S=\frac{1}{4\pi\alpha'}\int\mathrm{d}^2z\,\mathrm{d}^2\theta\,\mathrm{\,sdet}\,E\left\{\left[G_{\mu\nu}(\mathbf{X})+B_{\mu\nu}(\mathbf{X})\right]\mathscr{D}_{\bar{\theta}}\mathbf{X}^{\mu}\mathscr{D}_{\theta}\mathbf{X}^{\nu}+\alpha'\Phi(\mathbf{X})\mathcal{R}\right\}
$$

其中 $\mathcal{R}$ 定义为：

$$
    \{\nabla_+,\nabla_-\}=\mathcal{R}\mathcal{J}.
$$

我们原则上可以通过要求上述作用量的各个 $\beta$ 函数为零来得到 NS-NS 部分的低能有效作用量。

然而 Type II 超弦还包含 R-R 部分，它们对应的顶点算子不能简单地写成类非线性 sigma  模型，因此无法直接通过令 $\beta$ 函数为零来获得场方程。一般来说，处理 R-R 部分更好的方法是 GS 超弦形式，但如果我们坚持使用 RNS 形式，一个更基本的方法是通过顶点算子计算弦散射振幅，然后寻找能复现这个振幅的低能有效作用量。

不管怎么说，我们可以得到 Type II 超弦的低能有效作用量，其会是一个超引力。我们关注其中的玻色部分，因此有：

$$
    S_{eff,NSNS-RR,p}=\frac{1}{2\kappa_0^2g_s^2}\int\mathrm{d}^{10}x\,\sqrt{-G}\left\{\mathrm{e}^{-2\tilde{\Phi}}\left(R+4(\partial_M\tilde{\Phi})^2-\frac{1}{12}H_{MNL}H^{MNL}\right)-\frac{g_s^2}{2}|F_{p+2}|^2\right\}.
$$

其中 $F_{p+2}=\mathrm{d}C_{p+1}$ 是 $p+1$ 形式规范场的场强。注意该作用量依赖于 $p$，这将对应于 D-p 膜的维度 $p$.

### D-p brane

----

[^1]: 更一般地，在近平直背景附近，弦的任何一个激发态都会对应于一个顶点算符 $V_i(\sigma)$；打开这个激发态对应的背景场就是向 Polyakov 作用量中加入一项 $$\displaystyle\delta S_i= \lambda_i\int\mathrm{d}^2\sigma\,V_i(\sigma)$$，这将会给出任一激发态对应的背景场耦合。
[^2]: 相对应的，我们还有 GS 超弦和 pure spinor 形式；前者显式引入时空超对称，后者通过引入额外的 pure spinor 将前者进行 BRST 量子化。