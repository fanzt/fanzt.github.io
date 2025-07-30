---
layout:     post
title:      "Anomaly, Topology and Beyond-1"
subtitle:   "Anomaly"
date:       2025-7-30 20:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-16.jpg"
catalog: true
usemathjax: true
music-id: 2636530672
tags:
    - Physics
    - Quantum Field Theory
    - Standard Model
---

> 本系列文章致力于对近期笔者关于反常、瞬子、扩展场构型以及QCD的U(1)问题、强CP问题等相关内容做一个简单的复习回顾，以便梳理思路。
>
> 本文首先给出一个关于反常的快速回顾。
>
> 主要参考：*The Quantum Theory of Fields, Vol.II, Chapter 22*, Steven Weinberg

一句话来说，反常就是经典的对称性在量子化过程中被破坏了。从历史上来说，对反常最早期的探索来源于对 `$\pi_0\rightarrow\gamma\gamma$` 衰变速率的研究。从 QCD 的有效理论中，我们知道在上下夸克的零质量近似下，手征有效场论有一个**整体的** `$SU(2)_{L}\times{SU(2)_R}$` 的手征对称性，并且 $\pi$ 介子可以作为这个对称性自发破缺的 Goldstone 玻色子[^1]。当电磁相互作用介入其中时，这个 `$SU(2)\times SU(2)$` 对称性的绝大部分都被显著地破坏了，因为显然电磁场会与其中非电中性的生成元（部分对应于一些 Goldstone 粒子）产生相互作用。然而，一个合理的猜测是， $SU(2)\times SU(2)$ 对称性中那些电中性生成元对应的 `$U(1)_L\times U(1)_R$` 子群（更常用地，我们会写成等价的 `$U(1)_V\times U(1)_A$`，即矢量与轴矢量 $U(1)$ 对称性）至少应当被保留下来。

但是，这个想法却在实验上遇到了困难。考虑了这个对称性计算出的结果与实验严重不符；反而是忽略了这个对称性的简单估计给出了更接近实验的结果。这样的奇特情况暗示着应当存在一个理论上的机制，使得这个理应被保留的 $U(1)\times U(1)$ 对称性发生了一个破坏。进一步的理论研究展示了，这种破坏正是由于我们将一个**无限自由度的经典理论**进行了**量子化**导致的。

## 测度变换与手征反常

最直观地体现出反常与量子化关系的方法应当就是由 Fujikawa 给出的基于路径积分测度变换的计算。本小节我们来探讨在这种方法下对手征反常（也是 QCD 中最重要的反常）的计算。

首先写下一个与某种规范场有非手征耦合的无质量自旋 $1/2$ 费米子的路径积分：

$$
    Z=\int[\mathscr{D}\psi\mathscr{D}\bar{\psi}\mathscr{D}A]\mathrm{e}^{-\mathrm{i}S}
$$

虽然我们目前讨论的手征反常是整体的，但从一些（稍后可以看到的，出于给出 Noether 定理的需求导致的）技术上的原因，我们考虑对费米场们做一个任意的定域幺正变换，即 `$\psi(x)\rightarrow U(x)\psi(x)$`. 基本的 Grassmann 代数规则告诉我们，在这样的变换下，泛函测度的变换为[^2]：

$$
    [\mathscr{D}\psi\mathscr{D}\bar{\psi}]\rightarrow (\det\mathscr{U}\det\mathscr{\bar{U}})^{-1}[\mathscr{D}\psi\mathscr{D}\bar{\psi}]
$$

其中我们有：

$$
\begin{aligned}
    \mathscr{U}_{xn,ym}&=U(x)_{nm}\delta^4(x-y)
    \\\mathscr{\bar{U}}_{xn,ym}&=[\gamma^0 U(x)^{\dagger}\gamma^0]_{nm}\delta^4(x-y)
\end{aligned}
$$

如果 $U(x)$ 是非手征的，即 `$U(x)=\exp\{\mathrm{i}\alpha(x)t\}$`，那么显然有 $\mathscr{U}\bar{\mathscr{U}}=1$，这意味着变换给出的行列式没有产生额外的贡献。但是如果 $U(x)$ 是手征的，即有 `$U(x)=\exp\{\mathrm{i}\gamma_5\alpha(x)t\}$`，那么事情就会出现问题。由于手性矩阵 $\gamma_5$ 与其余所有 gamma 矩阵的反对易性质，我们实际上有 $\mathscr{U}=\mathscr{\bar{U}}$，即 $\mathscr{U}$ 是赝“幺正”的。这导致测度变换带来的行列式项没有成对消去，反而变为了：

$$
    [\mathscr{D}\psi\mathscr{D}\bar{\psi}]\rightarrow (\det\mathscr{U})^{-2}[\mathscr{D}\psi\mathscr{D}\bar{\psi}]
$$

为了给出这个贡献的一个定量表达式，我们考虑该手征变换是无穷小定域变换的情况。利用 $\det=\exp\text{tr}\ln$ 的公式，我们可以得到：

$$
    (\det\mathscr{U})^{-2}=\exp\left\{\mathrm{i}\int\mathrm{d}^4x\:\alpha(x)\mathscr{A}(x)\right\}
$$

其中我们有：

$$
    \mathscr{A}(x)=-2\text{tr}\{\gamma_5 t\}\delta^4(x-x)
$$

显然这个 $\mathscr{A}(x)$ 包含一个类似 $0\cdot\infty$ 的情形，需要进行正规化计算。我们在这里不展示细节的正规化计算过程，大致的思路就是将 $\delta^4(0)$ 写成动量积分，再引入一个正规化因子分离发散，可以发现发散会被求迹抵消，剩下一个有限大的值。

最终的计算结果为：

$$
    \mathscr{A}(x)=-\frac{1}{16\pi^2}F_{\mu\nu}(x)\tilde{F}^{\mu\nu}(x)\text{tr}\{t_{\alpha}t_{\beta}t\}
$$

其中 `$t_{\alpha}$` 是最初我们假定的理论中与费米子耦合的规范场所取值的李代数生成元。

现在我们显然地看到了场的积分测度确实会出现在对称变换下发生额外变化的情况，这已经展示出了对经典对称性的破坏。但是，作为一个物理上的对应，我们可以进一步展示一下这个破坏对 Noether 流带来的影响。考察对费米场做上述无限小手征变换所导致的 $\mathcal{Z}$ 的变化，有：

$$
\begin{aligned}
    \delta\mathcal{Z}&=\int\delta\{[\mathscr{D}\psi\mathscr{D}\bar{\psi}]\}\mathrm{e}^{\mathrm{i}S}+[\mathscr{D}\psi\mathscr{D}\bar{\psi}]\delta\mathrm{e}^{\mathrm{i}S}
    \\&=\int[\mathscr{D}\psi\mathscr{D}\bar{\psi}]\left[\mathscr{A}(x)\alpha(x)+J_5^\mu(x)\partial_{\mu}\alpha(x)\right]\mathrm{e}^{\mathrm{i}S}
\end{aligned}
$$

由于上式的变换仅仅是对积分变量做出的替换，而这实际上不会改变路径积分的值，因此 $\delta\mathcal{Z}=0$. 以往的情况下，这个条件应当给出 Ward 恒等式（或者其类似物），但在现今的情形下，我们发现这给出：

$$
    \langle\partial_\mu J^{\mu}_5(x)\rangle=\mathscr{A}(x)
$$

即流守恒方程不再成立，这明显地意味着轴矢量 $U(1)$ 对称性被破坏了。因此，我们需要对量子情形下的流守恒做出修正。如果有不错的注意力，我们可以观察到 $\mathscr{A}(x)$ 实际上可以被写为一个全导数（其中我们使用了伴随表示的归一化条件，这给出了 $N$）：

$$
    \mathscr{A}(x)=-\frac{N}{8\pi^2}\partial_\mu\varepsilon^{\mu\nu\rho\sigma}\left[A_{\gamma\nu}F^{\gamma}_{\rho\sigma}-\frac{2}{3}C_{\alpha\beta\gamma}A^{\alpha}_{\nu}A^{\beta}_{\rho}A^{\gamma}_{\sigma}\right]
$$

（顺带，这个被求导的部分被称为 Chern-Pontryagin 密度。随着涉及到拓扑学的内容逐渐增多，Chern 的名字将会在后续内容中多次出现。）因此我们可以重新定义一个反常“守恒流”：

$$
    \partial_\mu(J_5^\mu+K^\mu)=0
$$

其中有：

$$
    K^\mu=\frac{N}{8\pi^2}\varepsilon^{\mu\nu\rho\sigma}\left[A_{\gamma\nu}F^{\gamma}_{\rho\sigma}-\frac{2}{3}C_{\alpha\beta\gamma}A^{\alpha}_{\nu}A^{\beta}_{\rho}A^{\gamma}_{\sigma}\right]
$$

这便是修正后的反常轴矢流方程。

## 三角圈图与一般情况的反常

TBD.

## 规范反常、引力反常与理论的自洽性

TBD.

----

[^1]: 严谨地说，是 Pseudo Nambu-Goldstone 玻色子，因为上下夸克实际拥有的极小但不为零的质量会给出一个显式破缺，其会带来势能改变导致的真空对齐。
[^2]: 一个显然的问题或许是：幺正变换应当是幺模的，怎么会通过行列式改变积分测度？这一点正是“无限自由度”所独有的性质。无穷维幺正矩阵的行列式并不一定为一，其可以相差至多一个相位项。接下来我们将会看到，正是这个相差的相位导致了反常的发生。
