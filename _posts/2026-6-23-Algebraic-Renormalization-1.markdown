---
layout:     post
title:      "Algebraic Renormalization-Chapter 2"
subtitle:   A trial translation of Piguet & Sorella's Book.
date:       2026-6-23 13:30:00
author:     "fromuly"
header-img: "img/post-bg-2026-2.jpg"
catalog: true
usemathjax: true
music-id: 2037885601
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
---

> 本系列文章是对 Piguet & Sorella 的 *Algebraic Renormalization* 一书部分章节的笔记。

## 重整化微扰理论

在本章中，我们应当首先回顾一些重整化理论的基本事实。

显然地，我们在量子场论中最关注的核心数据是 Green 函数。通过 LSZ 约化公式，实验所关注的散射矩阵元可以直接从 Green 函数中获得。微扰论中，我们将任何 Green 函数都展开为了*形式幂级数*。使用形式幂级数意味着我们并不期待这个级数展开的求和能给出有意义的收敛物理量；因此我们接下来要介绍的所有关系总是对幂级数的展开阶数逐阶成立的。形式幂级数有两个基本且重要的性质：

1. 一个形式幂级数为零当且仅当其所有项均为零。等价地，形式幂级数非零当且仅当其中至少有一项非零。
2. 一个形式幂级数存在一个同为形式幂级数的逆，当且仅当该形式幂级数的零阶项可逆。例如，如果我们有一个 $N\times N$ 的矩阵项形式幂级数，那么其可逆的条件是这个幂级数的零阶项要是一个可逆的 $N\times N$ 矩阵。

### 生成泛函

#### 定义

我们在大多数情况下选择在一个 $D$ 维的 Euclidean 时空处理问题；为了方便地展示逐阶展开的性质，我们有时会刻意保留 $\hbar$. Green 函数的生成泛函形式地写为：

$$
    Z[J]=\mathcal{N}\int\mathcal{D}\phi\,\exp\left\{-\frac{1}{\hbar}\left[S[\phi]+\int\mathrm{d}^Dx\,J^i(x)\phi_i(x)\right]\right\}
$$

其中 $\mathcal{N}$ 是一个（在大多数情况下非良定义的）的数值常系数。特别地，对于我们关注的微扰论，一般总是将作用量 $S[\phi]$ 拆解成严格可解的部分 `$S_{\text{free}}$`（称为自由理论）与需要做微扰展开的部分 `$S_{\text{int}}$`（称为相互作用）。在这样的拆分下，我们有：

$$
    Z[J]=\mathcal{N}\exp\left\{-\frac{1}{\hbar}S_{\text{int}}\left[-\hbar\frac{\delta}{\delta J}\right]\right\}Z_{\text{free}}[J]
$$

其中 $Z_{\text{free}}$ 是将 $S$ 替换为 `$S_{\text{free}}$` 后的生成泛函。

进一步地，连通生成泛函定义为：

$$
    W[J]=-\hbar\ln Z[J]
$$

单粒子不可约（1PI）图（或称顶点函数）被定义为一类连通的、截去外腿并且在切断任意一根内线后仍保持连通的图。顶点函数的生成泛函（又称量子有效作用量）定义为连通生成泛函的 Legendre 变换：

$$
    \Gamma[\phi]=\left.W[J]-\int\mathrm{d}^Dx\,J^i(x)\phi_i(x)\right|_{J^i(x)=\text{Sol of Eq.}\left\{\phi_i(x)=\frac{\delta W}{\delta J^i(x)}\right\}.}
$$

我们也可以用逆 Legendre 变换定义连通生成泛函：

$$
    W[J]=\left.\Gamma[\phi]+\int\mathrm{d}^Dx\,J^i(x)\phi_i(x)\right|_{\phi_i(x)=\text{Sol of Eq.}\left\{-J^i(x)=\frac{\delta \Gamma}{\delta \phi_i(x)}\right\}.}
$$

特别地，这个定义给出了关系：

$$
    \int\mathrm{d}^Dy\,\Gamma^{ij}(x,y)\langle \mathrm{T}\phi_j(y)\phi_k(z)\rangle_{c}=-\delta^i_k\delta^D(x-z).
$$

这个关系是一般的作用量中“二次项的逆等于传播子”的推广。

#### 按 $\hbar$ 展开

我们可以将有效作用量按圈展开：

$$
    \Gamma[\phi]=\sum_{n=0}^{\infty}\hbar^n\Gamma^{(n)}[\phi].
$$

其中 $n$ 是圈计数而 $\Gamma^{(n)}$ 是所有 $n$ 圈图的贡献。这个关系可以简单地使用 Euler 恒等式论证：考虑一个有 $I$ 条内线 $V$ 个顶点 $L$ 圈的 1PI 图，每条内线贡献一个 $\hbar$ 而每个顶点贡献一个 $\hbar^{-1}$，再加上 $W=-\hbar\ln Z$ 提供的额外 $\hbar$，我们有每个这样的 1PI 图都贡献 $I-V+1$ 个 $\hbar$；而 Euler 恒等式告诉我们：

$$
    I-V+1=L
$$

因此我们可以识别出每个 $L$ 圈图总会带 $L$ 个 $\hbar$. 特别地，这意味着有效作用量的第零阶必须给出经典作用量：

$$
    \Gamma^{(0)}[\phi]=S[\phi].
$$

#### 复合场算符

除了基本场的关联函数作为 Green 函数外，我们经常关注的另一类物理量是各种携带复合场算符插入的关联函数，这样的情况经常出现在 QCD 和包含非线性变换的理论中。为此，考虑一复合场算符 $Q^p(x)$，其经典解对应于一复合场多项式 `$Q^p_{\text{classical}}(x)$`. 利用同样的构造，我们会在作用量中引入源项：

$$
    S_{\text{int}}(\phi,K)=S_{\text{int}}+\int\mathrm{d}^D x\,K_p(x)Q^p_{\text{classical}}(x)
$$

以这样的作用量，我们定义出生成泛函：

$$
    Z[J,K]=\mathcal{N}\int\mathcal{D}\phi\,\exp\left\{-\frac{1}{\hbar}\left[S[\phi]+\int\mathrm{d}^Dx\,J^i(x)\phi_i(x)+\int\mathrm{d}^D x\,K_p(x)Q^p_{\text{classical}}(x)\right]\right\}
$$

这样定义的生成泛函可以一并生成任意复合算符插入数量的场关联函数。进一步地，我们可以定义连通生成泛函：

$$
    W[J,K]=-\hbar\ln Z[J,K]
$$

与有效作用量：

$$
    \Gamma[\phi,K]=\left.W[J,K]-\int\mathrm{d}^Dx\,J^i(x)\phi_i(x)\right|_{J^i(x)=\text{Sol of Eq.}\left\{\phi_i(x)=\frac{\delta W}{\delta J^i(x)}\right\}.}
$$

特别地：

$$
    -\left.\hbar\frac{\delta Z}{\delta K_p(y)}\right|_{K=0}:=Q^p(y)\cdot Z[J]
$$

可以生成所有带单个复合算符插入的 Green 函数：

$$
    \langle\mathrm{T}Q^p(y)\phi_{i_1}(x_1)\cdots\phi_{i_N}(x_N)\rangle
$$

这样的关联函数对应的 Feynman 图会包含一个新的“外顶点”，其对应于作为算符插入的 `$Q^p_{\text{classical}}(y)$` 复合场。进一步有：

$$
\begin{aligned}
    \left.\frac{\delta W}{\delta K_p(y)}\right|_{K=0}&=Q^p(y)\cdot W[J]
    \\\left.\frac{\delta \Gamma}{\delta K_p(y)}\right|_{K=0}&=Q^p(y)\cdot \Gamma[\phi]
\end{aligned}
$$

在 $\hbar$ 展开意义下，我们有：

$$
    Q^p(y)\cdot\Gamma[\phi]=Q^p_{\text{classical}}(y)+O(\hbar)
$$

这正对应于量子算符 $Q^p(y)$ 的经典构造。

### 重整化

接下来我们将着手考虑如何系统地对上述构造执行完善的重整化程序。