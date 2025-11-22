---
layout:     post
title:      "Yang-Mills Theory and the Fiber Bundle"
subtitle:   "“千古寸心事,欧高黎嘉陈。”"
date:       2025-11-19 23:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-20.jpg"
catalog: true
usemathjax: true
music-id: 2756892446
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
---

## The Basic Knowledge of Fiber Bundle

我们首先来介绍一些纤维丛的基本知识。*通俗的说，纤维丛就是一片地皮上长了一丛草*。一个一般的纤维丛 $E(M,F,\pi,G)$ 配备有四个结构，分别是底流形 $M$，纤维流形 $F$，投影映射 $\pi:E\rightarrow M$ 和结构群 $G$.

从直观上理解，纤维丛就像是在一个底流形 $M$ 上每个点粘贴了一个纤维流形 $F$，而投影函数负责把每个点上 $F$ 的元素全都打回底流形上对应的这个点。从这个理解层面，我们或许会希望使用 `$E=M\times F$` 来表示这个纤维丛（称为丛的平凡化），但这一般并不成立[^1]；事实上，对一个一般的纤维丛，我们只能在每一个局域（底流形上的小开集 $U$）上做**局域平凡化**。准确地说，将底流形用许多开集 `$\{U_\alpha\}$` 覆盖，对任一开集 `$U_\alpha$`，有微分同胚映射：

$$
    \psi_\alpha:\pi^{-1}(U_{\alpha})\rightarrow U_\alpha\times F
$$

可以将这种局域平凡化理解为纤维丛的**参数化**。我们知道流形上的覆盖往往会使得开集之间存在交，这就意味着对于某片区域 $D$，其有可能出现 `$D\subset U_{\alpha}\cap U_{\beta}$` 的情形；于是对于 `$E_D=\{u\in E|\pi (u)\in D\}$`，我们就有另一个微分同胚映射：

$$
    \psi_\beta:\pi^{-1}(U_{\beta})\rightarrow U_\beta\times F
$$

对于同一个 `$u\in E_D$`，两个同胚映射可能把它们映到了 $F$ 中不同的点（即给出了不同的参数化）；作为一个几何实体，其实际的结果当然不应当依赖于参数化，因此我们应当寻找一种纤维丛上的“坐标变换”来关联这两种参数化。显然地，我们可以选取：

$$
    g_{\alpha\beta}=\psi_\alpha\cdot\psi_\beta^{-1}:(U_{\alpha}\cap U_{\beta})\times F\rightarrow (U_{\alpha}\cap U_{\beta})\times F
$$

作为我们所需要的“坐标变换”。在纤维丛上，这称为转移函数；特别地，容易验证其构成一个群 $G$，称为纤维丛的**结构群**。

## Principle Bundle

对于物理学关心的 Yang-Mills 理论，我们所需要的是一类特殊的纤维丛，其纤维流形 $F$ 被取为一个 Lie 群 $G$，结构群也被取为 Lie 群 $G$。这样的纤维丛称为**主丛**（Principle Bundle），简记为 $P(M,G)$；在本文中我们主要关注这类纤维丛。

对任意 $u\in P$，由局域平凡化，我们总可以选择局域坐标 `$u=(x,g)$`。容易看出，在主丛上，“转移函数”被通过 Lie 群 $G$ 对自身的左平移实现；注意到我们没有在主丛的定义中写明投影函数 $\pi$，这是因为在主丛情形下，投影函数可以被自然地定义出来。由于 $G$ 对自身的左作用和右作用对易，我们定义 $G$ 对 $P$ 的右作用：

$$
    R:P\times G\rightarrow G
$$

容易看到，这个作用应当是自由的（$u\cdot g=u\iff g=e$），并且轨道 `$\{u(g)|u(g)=u_0 g\}$` 同胚于群 $G$，给出底流形 $M=P/G$，于是利用商空间（代表元）天然给出投影映射（称为正则投射） `$\pi:P\rightarrow M=P/G$`，满足：

$$
    \pi(R_g u)=\pi(ug)=\pi(u)\in M
$$

- 例1：第一 Hopf 丛 `$P(\text{C}P^n,\text{U}(1))$`
  - 考虑 `$\text{U}(1)\hookrightarrow S^{2n+1}\rightarrow \text{C}P^n$`，其中有：
    $$
        S^{2n+1}=\{Z\in\mathbb{C}^{n+1}:|Z|^2=1\}
    $$

    以及：
    $$
    \begin{aligned}
        \text{C}P^{n}&=\{[Z]=[cZ],Z\in\mathbb{C}^{n+1},c\in\mathbb{C}\}
        \\&=\{[Z]=[\mathrm{e}^{\mathrm{i}\varphi}Z],Z\in S^{2n+1},\mathrm{e}^{\mathrm{i}\varphi}\in\text{U}(1)\}
    \end{aligned}
    $$

    注意到在 $\text{C}P^n$ 的定义中我们认同了 $Z$ 与 $\mathrm{e}^{\mathrm{i}\varphi}Z$，这正是商空间构造，因此在这种情况下我们可以将 $S^{2n+1}$ 识别为一个主丛，而将 $\text{C}P^{n}$ 识别为它的底流形，$\text{U}(1)$ 为它的结构群/纤维流形。特别地，当 $n=1$ 时，我们称该纤维丛为复 Hopf 丛或**第一 Hopf 丛**：
    $$
        \text{U}(1)\hookrightarrow S^{3}\rightarrow S^2
    $$
- 例2：陪集构造 `$P(G/H,H)$`
  - 当 Lie 群 $G$ 存在闭 Lie 子群 $H$ 时，容易看到 $H$ 作用在 $G$ 上的每一个轨道同胚于 $H$，于是我们可以识别：$H$ 作为纤维，$G/H$ 作为底流形，$G$ 本身作为丛流形：
  
  $$
    H\hookrightarrow G\rightarrow G/H
  $$

  这种想法与自发对称性破缺不谋而合。[^2]

### Connection and Curvature on Fiber Bundle

Yang-Mills 规范场论在几何学上的最终形式由所谓的 Wu–Yang 字典提供，它给出了物理上规范理论中一系列概念与纤维丛理论中一系列概念的对应关系。为了详细介绍这个关系，我们首先要讲明如何在主丛上定义一系列相关的几何结构；其中最重要的便是如何给出主丛上联络与曲率的定义。

#### Connection on Riemannian Manifolds

回忆一下一般 Riemannian 流形上的联络与协变导数，协变导数定义了我们如何将一个标架随流形上某条曲线 $\gamma(t)$ 做平行输运，而联络则给出了为实现这个平行输运，我们需要为标架在只移动底点的基础上额外补充多少（旋转）补正；这意味着我们需要在曲线上的每点指定一个标架。将这套想法转换为标架丛的语言，我们就可以得到纤维丛上联络的思想。

视 Riemannian 流形为底流形，在其上的每点粘贴一个所有可能的标架组成的集合为纤维流形，并取标架的刚性变换（即 $\text{O}(n)$ 群）为结构群，我们就获得了一个标架丛；于是流形上一系列标架的选取就变成了从标架丛取截面的过程；而旋转补正的大小就变为了在纤维流形方向上的移动量。特别地，平行输运被定义为对底流形上的曲线 $\gamma(t)$，给出一个在纤维丛上的**水平提升** $\tilde{\gamma}(t)$，即满足下关系的标架丛截面：

$$
    \nabla_\dot{\tilde{\gamma}} e_i(t)=0
$$

由此可见，协变导数（亦即联络）决定了何为平行输运，也即是决定了何为底流形上曲线在纤维丛中的水平提升；更直接地说，联络决定了一个纤维丛上的**水平方向**。

将以上的想法用更加严谨的语言套用在主丛上，我们可以获得主丛上联络的定义：**主丛上的联络被定义为一种分解方式，其给出了主丛 $P$ 在点 $u\in P$ 上的切空间 `$T_u(P)$` 的一个分解：**

$$
    T_u=H_u \oplus V_u
$$

**其中 `$H_u$` 称为水平子空间，`$V_u$` 称为垂直子空间。**

特别地，水平子空间需满足：

1. `$H_u=\pi^*[T_x(M)]$`，即水平子空间确是底流形切空间的丛对应；
2. `$R_{g*}[H_u]=H_{ug}$`，即水平子空间的定义是对纤维认同的；
3. `$H_u$` 关于 $u$ 光滑可微。

为了实际地给出这个分解，我们必须显式地写出这两个空间的基矢。垂直子空间描述了纤维流形自身的切空间，因此对于主丛情形，我们可以简单地取同构于 Lie 代数 $\mathfrak{g}$ 的右不变矢量场 $X_a$ 作为垂直子空间的基矢；这一定义不依赖于联络的选取，因此我们构造分解时的要求也没有哪个是施加在垂直子空间上的。

而对于水平子空间基矢的构造，迫使我们不得不显式引入联络，进而给出物理学最熟悉的内容。定义底流形上的协变微分算子（注意与之后将要定义的主丛上的协变微分算子区分） $\nabla$ 为：

$$
    \nabla=\mathrm{d}+A
$$

其中 $\mathrm{d}$ 是底流形上的外微分算子，$A=A_\mu\mathrm{d}x^\mu$ 是**底流形上的联络 1-形式**，以逐个开集的方式在底流形上定义。 记 `$\tau=\mathrm{d}/\mathrm{d}t$` 为 $\gamma(t)$ 的水平提升曲线 $u(t)$ 的切矢，则平行输运条件给出：

$$
    \nabla_\tau g(t)=0
$$

即：

$$
    \left(\frac{\mathrm{d}}{\mathrm{d}t}+A_\mu\frac{\mathrm{d}x^\mu}{\mathrm{d}t}\right)g=0
$$

这给出 `$A=-\mathrm{d}g\cdot g^{-1}=A_\mu^a \tau_a \mathrm{d}x^\mu$` 为一 $\mathfrak{g}$ 值 1-形式。不妨假设我们考虑的 Lie 群都有矩阵表示，对切矢 $\tau$ 按主丛的参数化做分解，有：

$$
    \frac{\mathrm{d}}{\mathrm{d}t}=\frac{\mathrm{d}x^\mu}{\mathrm{dt}}\frac{\partial}{\partial x^\mu}+\frac{\mathrm{d}{g^{i}}_{j}}{\mathrm{d}t}\frac{\partial}{\partial {g^{i}}_{j}}
$$

于是给出：

$$
\begin{aligned}
    \frac{\mathrm{d}}{\mathrm{d}t}&=\frac{\mathrm{d}x^\mu}{\mathrm{d}t}\left(\frac{\partial}{\partial x^\mu}-A^a_\mu{(\tau_a)^i}_k {g^k}_j\frac{\partial}{\partial {g^{i}}_{j}}\right)
    \\&=\frac{\mathrm{d}x^\mu}{\mathrm{d}t}\left(\frac{\partial}{\partial x^\mu}-A_\mu^a X_a\right)
\end{aligned}
$$

其中 `$X_a$` 是纤维流形上的右不变矢量场，其同构于 Lie 代数 $\mathfrak{g}$. 我们记：

$$
    \mathscr{D}_\mu=\frac{\partial}{\partial x^\mu}-A_\mu^a X_a
$$

作为水平子空间 $H_u$ 的基矢。

进一步地，我们可以定义**主丛上的联络 1-形式** $\omega$ 为：

$$
    \omega=g^{-1}\nabla g=g^{-1}Ag+g^{-1}\mathrm{d}g
$$

容易识别出 $\omega$ 在右作用下按伴随表示变换，并且有性质：

$$
    \langle\omega,\mathscr{D}_\mu\rangle=0,\langle \omega,V_a\rangle=g^{-1}\tau_ag
$$

即 $\omega$ 作为一形式，负责将 $P$ 上任意切矢的垂直部分提取出来；这正展现了其负责给定垂直方向补正的联络性质；于是我们自然地可以定义：

$$
    H_u=\ker\omega_u
$$

我们可以进一步定义**主丛上的协变微分算子**为：

$$
    \mathcal{D}=\mathrm{d}+\omega
$$

并给出主丛上的曲率二形式：

$$
    \Omega=\mathcal{D}^2=\mathrm{d}\omega+\omega\wedge\omega
$$

### Gauge Transformation and Gauge Fields

接下来，我们将展示如何将规范变换的概念用主丛的语言表达出来。

正如 Riemannian 流形上存在主动（微分同胚）变换和被动（坐标）变换那样，我们也有两种观点来定义规范变化。两种规范变换的定义方法都基于将主丛上的联络 1-形式 $\omega$ 拉回到底流形上；只不过如何实现这个拉回，二者存在一些差异。

#### Transition Function Gauge Transformation

反过来将主丛上的联络 1-形式 $\omega$（及其满足的系列性质）作为联络的初定义，在给定截面 $s(x)$ 的一个局域平凡化 `$g_\alpha:U_\alpha\rightarrow P$` 之后，我们可以通过拉回映射将主丛上的联络 1-形式 $\omega$ 与底流形上的联络 1-形式 $A$ 联系在一起：

$$
    g_\alpha^*(\omega)=A^\alpha
$$

对于两个开集的交叠区，我们要求：

$$
    \omega=g_\alpha^{-1}A^{\alpha}g_\alpha+g_\alpha^{-1}\mathrm{d}g_\alpha=g_\beta^{-1}A^{\beta}g_\beta+g_\beta^{-1}\mathrm{d}g_\beta
$$

开集的交叠区域以左作用提供了转移函数：

$$
    g_\alpha(x)=g_{\alpha\beta}(x)g_{\beta}(x)
$$

这给出了当主丛发生“坐标变换”时，底流形上的联络 1-形式的变换规则：

$$
    A^{\beta}=g_{\alpha\beta}^{-1}A^\alpha g_{\alpha\beta}+g_{\alpha\beta}^{-1}\mathrm{d}g_{\alpha\beta}
$$

而这正是规范场 $A$ 的规范变换规则。类似地，将之扩展到曲率 $\Omega$，定义：

$$
    g_\alpha^*(\Omega)=F
$$

容易得到：

$$
    F=\mathrm{d}A+A\wedge A
$$

并给出 $F$ 的变换规则：

$$
    F^{\beta}=g_{\alpha\beta}^{-1}F^{\alpha}g_{\alpha\beta}
$$

#### Automorphism Gauge Transformation

替代地，我们可以选择改变截面的选取，即对整个主丛用右作用做自同构变换。考虑主丛上的两个不同截面 $s(x)$ 与 $s'(x)=s(x)g(x)$，在同一局域平凡化下做拉回，有：

$$
    A'=s'^*(\omega)=(s\cdot g)^*(\omega)=s^*[R_g^*(\omega)]=s^*[g^{-1}\omega g]=g^{-1}Ag
$$

即给出了规范变换。

在这种定义下我们甚至不需要知道 $\omega$ 的具体表达式，就可以获得规范变换的形式；曲率变换的结果同上。

----

[^1]: 从名字也能看出来，怎么可能大家都是平凡的……
[^2]: 事实上，我们会在 CCWZ (Callan-Coleman-Wess-Zumino) 构造的内容中再次遇到这个情形。
