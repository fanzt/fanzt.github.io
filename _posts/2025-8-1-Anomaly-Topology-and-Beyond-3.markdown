---
layout:     post
title:      "Anomaly, Topology and Beyond-3"
subtitle:   "Soliton and Instanton"
date:       2025-7-31 17:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-19.jpg"
catalog: true
usemathjax: true
music-id: 28556280
tags:
    - Physics
    - Quantum Field Theory
    - Standard Model
---

> 本系列文章致力于对近期笔者关于反常、瞬子、扩展场构型以及QCD的U(1)问题、强CP问题等相关内容做一个简单的复习回顾，以便梳理思路。
>
> 本文我们来讨论有关孤子、单极子、瞬子和一些拓扑性质的内容。
>
> 文章主要参考：*The Quantum Theory of Fields, Vol.II, Chapter 22*, Steven Weinberg; *Monopoles, Instantons and Confinement*, Gerard ’t Hooft


在前面几篇关于反常的推文中，我们提到了瞬子这一概念。瞬子实际上是一种拓扑非平庸的经典场构型。所谓“拓扑非平庸”指的是其不能经过一个连续的、保作用量有限的拓扑变换化为平庸场（常数场），而经典场构型则指的是其是经典场方程（ E-L 方程）的解。

除了瞬子（Instanton）之外，非线性场论中还有很多其他复杂但有用的拓扑非平庸场构型，包括孤子（Soliton）、漩涡（Vortex）、单极子（Monopole）、斯格明子（Skyrmion）等等。在本文（和后续文章中）中，我们来逐一讨论这些非平庸的拓扑场构型，以及它们对经典场、量子场的影响。

本文中的所有内容都在 Euclidean 空间中考虑。

## 非线性场论与拓扑

我们首先来讨论这些奇特的场构型是如何与拓扑学联系在一起的。量子场论研究的各种理论模型往往具有一定的对称性；常见的，这种对称性可以被一些李群描述。在这种情况下，场函数就变成了从 $d$ 维空间到李群的表示空间的一个映射。上文提到的“拓扑非平庸”场构型实际上定义了一种这类映射之间的等价关系：任何两个可以在连续的、保作用量有限的拓扑变换下相互转化的场构型都可以被认为是拓扑等价的。在这种意义下，我们自然首先希望能够为这些场构型（映射）依据拓扑等价关系进行分类。

注意到，拓扑等价的定义要求所有的映射不能使作用量的取值为无穷大（物理上无穷大的作用量（~能量）构型也是没有意义的），这为我们的场构型在无穷远处的取值做出了限制[^1]。从这个角度来说，我们可以将原本 $d$ 维空间的无穷远球面认同为一个点。经过这样的认同之后，$d$ 维空间就拓扑等价于 $d$ 维球面，即 $S^d$；所谓的场构型也就变成了从 $S^d$ 到对称群 $G$ 的表示空间的映射。在我们将要见到的各种情况下，这些条件会使得场构型都成为了满足如下描述的一类映射：其将 $d$ 维球面 $S^d$ 映射到某个流形 $\mathscr{M}$ 上，并保证 $S^d$ 上的无穷远点总是会被映射到流形 $\mathscr{M}$ 上的某个固定点。

幸运的是，我们早有系统研究上述映射的方法。在数学上，满足上述条件的拓扑不等价映射被称为**流形 $\mathscr{M}$ 的第 $d$ 同伦群**，记为 `$\pi_d(\mathscr{M})$`. 不幸的是，同伦群的计算是极为复杂的，除了一些简单的情形外我们暂时无法得到任一流形的第 $d$ 同伦群的表达式。但万幸的是，接下来的几个例子用到的同伦群都将恰好是那些简单的情形。

## 孤子与畴界

### 畴界解的基本性质

我们先从最简单的一维空间开始，这个情形过于简单以至于我们还暂时用不到同伦群的内容。一维空间中上述的拓扑不平庸场构型出现在离散对称性破缺的场景中：对称性有可能在不同的畴中破缺到了不同的基态上，而这些畴被“畴界”隔离开来，每个畴界中真空场都会从势的一个极小值跃到另一个极小值上。考虑场构型在 $yz$ 平面内平坦，问题便可在一维空间中考虑。一维空间中的畴界也叫做孤子，其典型的作用量为：

$$
    S[\phi]=\int\mathrm{d}^2x\:\left(\frac{1}{2}\dot{\phi}^2-\frac{1}{2}(\partial_x\phi)^2-V(\phi)\right)
$$

其中容易看到，单位面积上的能量值是：

$$
    E[\phi]=\int\mathrm{d}x\:\left[\frac{1}{2}(\partial_x\phi)^2+V(\phi)\right]
$$

作为例子，我们分别考虑两种不同的势能：Ginzberg-Landau 势 (a):

$$
    (a):\quad V(\phi)=\frac{\lambda}{4!}(\phi^2-F^2)^2
$$

与 Sine-Gordon 模型 (b)：

$$
    (b):\quad V(\phi)=A\left(1-\cos\frac{2\pi\phi}{F}\right)
$$

为了方便起见，我们在这里都对势能做了调整以保证其最低点恰好为零。（这个操作不会带来什么影响，一个全局的大能量是没有任何物理意义的。）

容易观察到，Ginzberg-Landau 势的最低点取在 $\phi=\pm F$ 的位置，而 Sine-Gordon 模型的势能最低点则取在了所有 `$\phi=nF, \: n\in\mathbb{Z}$` 的点上。我们研究的场构型是静态的，根据作用量可以给出 E-L 方程：

$$
    \frac{\partial^2\phi}{\partial x^2}-\frac{\partial V}{\partial\phi}=0
$$

两边乘 $\partial_x\phi$ 凑能量守恒，给出：

$$
    \partial_x\left(\frac{1}{2}(\partial_x\phi)^2-V(\phi)\right)=0
$$

这给出：

$$
    \frac{1}{2}(\partial_x\phi)^2-V(\phi)=Const
$$

为了获取这个常数，我们考虑到作用量有限的边界条件要求在 $x\rightarrow\infty$ 时 $\phi$ 要取在势能零点对应的那些常数场上，这意味着 `$x\rightarrow\infty, \: \partial_x\phi=0,V(\phi)=0$`，因此上式的常数就只能是零。于是我们可以解出：

$$
    x(\phi)=\int\frac{\mathrm{d}\phi}{\sqrt{2V(\phi)}}
$$

对于我们所考虑的这两种情况，$\phi$ 都可以被反解出来：

$$
\begin{aligned}
    &(a):\quad\phi(x)=F\tanh\frac{1}{2}m(x-x_0)
    \\&(b):\quad\phi(x)=\frac{2F}{\pi}\arctan\left(\mathrm{e}^{m(x-x_0)}\right)
\end{aligned}
$$

其中 $m$ 是由 $\lambda,F,A$ 等决定的参数。在 $m$ 足够大的情况下，这两个函数的形式都如同 `$F\text{sgn}(x-x_0)$` 一样，将整个 $x$ 轴区分为了两部分，其中一部分的场取为众多真空期望值中的一个，另一个场取为期望值中的另一个，而二者中间则被一段快速的跃变隔开。这正是所谓“畴界”的含义。

当 $m$ 足够大的时候，场方程就将会化为线性方程，此时我们就可以对这些解作线性叠加，而这就会带来所谓的“多孤子”（或者说，多畴界）场构型。这种构型会将 $x$ 轴分割为多个区域，每个区域都有自己的真空期望值；看起来就像很多墙壁各自围起来的地块一样。

### 与费米子耦合

考虑畴界和费米子场的耦合将是有用的，因为它可以为我们关于 Higgs 场的一些讨论做出演示。考察一个 $1+1d$ 的费米子场 Lagrangain：

$$
    \mathscr{L}_{\psi}=-\bar{\psi}(\gamma^{\mu}\partial_{\mu}+g\phi(x))\psi
$$

其中我们的 $\gamma$ 矩阵取为：

$$
    \gamma^1=\sigma_1,\gamma^4=\sigma_3,\gamma^5=\sigma_2
$$

而 $\phi(x)$ 则是上述 $(a)$ 情况的解。容易看到其实第二项充当了一个费米子的（空间依赖）的质量项。如果 $\phi(x)$ 的真空期望值在全空间都一样（我们熟知的 Higgs 机制），那么这就只会简单的给出一个 $m_{\psi}=gF$. 但如果 $\phi$ 取成孤子（畴界）解呢？同样考虑静态场，求解场方程，给出：

$$
    (\sigma_1\partial_x+g\phi)\psi_{\pm}=0
$$

其中 `$\psi_{\pm}$` 是零能的 $\sigma_1$ 本征值为 `$\pm 1$` 的解。最终我们可以解出：

$$
\begin{aligned}
    &\psi_{+}=C_1\left(\cosh\frac{m}{2}(x-x_0)\right)^{-2m/m_{\psi}}
    \begin{pmatrix}
        1
        \\1
    \end{pmatrix}
    \\&\psi_{-}=C_2\left(\cosh\frac{m}{2}(x-x_0)\right)^{-2m/m_{\psi}}
    \begin{pmatrix}
        1
        \\-1
    \end{pmatrix}
\end{aligned}
$$

这被称为 Jackiw-Rebbi 模式，我们将其是做孤子-费米子束缚态；我们可以看到，当这个模式处在畴界上的时候，它将不会拥有质量。

## 斯格明子与 Derrick 定理

接下来我们考虑一个更加普遍的情形。在自发对称性破缺的过程中，我们经常见到如下的非线性 $\sigma$ 模型：

$$
    S[\pi]=\int\mathrm{d}^dx\left[\frac{1}{2}g_{ab}(\pi)\partial_i\pi^a\partial^i\pi^b+\cdots\right]
$$

作用量有限的条件要求 `$\partial_i\pi_a(\boldsymbol{x})$` 在 `$|\boldsymbol{x}|\rightarrow\infty$` 时至少以快于 `$|\boldsymbol{x}|^{-d/2}$` 的速度向零衰减，这意味着场 `$\pi_a(\boldsymbol{x})$` 要在 `$|\boldsymbol{x}|\rightarrow\infty$` 时趋于一个全域常值，且余项衰减速度要快于 `$|\boldsymbol{x}|^{1-d/2}$`.

## 涡旋线

我们已经看到，畴界是一维空间中的拓扑不平庸场构型的例子。我们可以尝试在更高维度寻找一些更加有趣的拓扑场构型。一个这样的例子发生在 $2+1d$ 时空中，被称为**涡旋线**。

## 单极子

## 瞬子

另一个更加有趣（如前所述，也更加有用）的拓扑场构型被称为**瞬子**。不同于孤子描述的是类标量场的构型，瞬子描述的是更加物理的规范场理论。

考虑一个 $d$ 维欧几里得空间的规范场，其作用量为：

$$
    S[A]=\frac{1}{4}\int\mathrm{d}^dxF_{\alpha ij}F^{\alpha ij}
$$

我们使用拉丁指标是因为这是欧几里得空间。作用量有限的条件告诉我们 Lagrangian 需要在无穷远处足够快的趋于零。简单的幂次分析告诉我们，只要场 `$A_{\alpha i}$` 快于 `$x^{1-d/2}$` 的趋于零，那么作用量就一定是有限的。然而，即使对于 $d\geq 4$ 的空间，规范带来的额外自由性告诉我们，以 $1/x$ 趋近于零的场构型仍旧有机会满足零作用量有限，只要我们能保证在 $x\rightarrow\infty$ 时场趋于纯规范，即：

$$
    \mathrm{i}t^{\alpha}A_{\alpha i}(\boldsymbol{x})\rightarrow g^{-1}(\hat{\boldsymbol{x}})\partial_i g(\hat{\boldsymbol{x}})
$$

其中 $\hat{\boldsymbol{x}}$ 表征方向；其构成了 `$S^{d-1}$`. 在这样的纯规范上进行一个常规范变换对场 `$A_{\alpha i}$` 是没有影响的，因此我们总可以对任意的这类构型选定一个统一的方向 $\hat{\boldsymbol{x}}_1$，并作整体规范变换，令这个方向的规范 `$g(\hat{\boldsymbol{x}}_1)=e$`. 这意味着，场构型构成了一类从 $S^{d-1}$ 到 $G$ 的映射，并且其把 $S^{d-1}$ 上某固定点 `$\hat{\boldsymbol{x}}_1$` 映到 $G$ 上的恒等元 $e$. 正如我们讨论过的，这定义了同伦群 `$\pi_{d-1}(G)$`. 特别地，数学上已经证明了，对于任意的半单李群 $G$，`$\pi_3(G)$` 都是非平庸的；因此我们将 $d=4$ 时这样非平庸的场构型称为**瞬子**。

----

[^1]: 不同情况的限制不尽相同，但它们都是对任意方向的无穷远点做出的统一限制要求。