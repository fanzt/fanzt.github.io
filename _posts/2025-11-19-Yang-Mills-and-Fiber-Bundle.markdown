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

可以将这种局域平凡化理解为纤维丛的**参数化**。我们知道流形上的覆盖往往会使得开集之间存在交，这就意味着对于某篇区域 $D$，其有可能出现 `$D\subset U_{\alpha}\cap U_{\beta}$` 的情形；于是对于 `$E_D=\{u\in E|\pi (u)\in D\}$`，我们就有另一个微分同胚映射：

$$
    \psi_\beta:\pi^{-1}(U_{\beta})\rightarrow U_\beta\times F
$$

对于同一个 `$u\in E_D$`，两个同胚映射可能把它们映到了 $F$ 中不同的点（即给出了不同的参数化）；作为一个几何实体，其实际的结果当然不应当依赖于参数化，因此我们应当寻找一种纤维丛上的“坐标变换”来关联这两种参数化。显然地，我们可以选取：

$$
    g_{\alpha\beta}=\psi_\alpha\cdot\psi_\beta^{-1}:(U_{\alpha}\cap U_{\beta})\times F\rightarrow (U_{\alpha}\cap U_{\beta})\times F
$$

作为我们所需要的“坐标变换”。在纤维丛上，这称为转移函数；特别地，容易验证其构成一个群 $G$，称为纤维丛的**结构群**。

## Principle Bundle

对于物理学关心的 Yang-Mills 理论，我们所需要的是一类特殊的纤维丛，其纤维流形 $F$ 被取为一个李群 $G$，结构群也被取为李群 $G$。这样的纤维丛称为**主丛**（Principle Bundle），简记为 $P(M,G)$；在本文中我们主要关注这类纤维丛。

容易看出，在主丛上，“转移函数”被通过李群 $G$ 对自身的左平移实现；注意到我们没有在主丛的定义中写明投影函数 $\pi$，这是因为在主丛情形下，投影函数可以被自然地定义出来。由于 $G$ 对自身的左作用和右作用对易，我们定义 $G$ 对 $P$ 的右作用：

$$
    R:P\times G\rightarrow G
$$

容易看到，这个作用应当是自由的（$u\cdot g=u\iff g=e$），并且轨道 `$\{u(g)|u(g)=u_0 g\}$` 同构于群 $G$，给出底流形 $M=P/G$，于是利用商空间（代表元）天然给出投影映射（称为正则投射） `$\pi:P\rightarrow M=P/G$`，满足：

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
- 例2：陪集构造 `$P(G/H,H)$`[^2]
  - TBD

### Connection and Curvature on Principle Bundle

----

[^1]: 从名字也能看出来，怎么可能大家都是平凡的……
[^2]: 我们会在 CCWZ (Callan-Coleman-Wess-Zumino) 构造的内容中再次遇到这个情形。
