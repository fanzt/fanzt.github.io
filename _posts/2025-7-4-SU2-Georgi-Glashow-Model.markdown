---
layout:     post
title:      "Georgi-Glashow SU(2) model"
subtitle:   "A toy model of our first grand unified theory."
date:       2025-7-4 22:10:00
author:     "fromuly"
header-img: "img/post-bg-2025-9.png"
catalog: true
usemathjax: true
music-id: 550137051
tags:
    - Physics
    - Quantum Field Theory
    - Standard Model
---

> An exercise of Michael Dine *《Supersymmetry and String Theory》*.
> 甜点题目。

在 1974 年，Howard Georgi 与 Sheldon Lee Glashow 共同提出了第一个尝试统一强弱电磁三种作用力的模型，被称为 $\mathrm{SU}(5)$ GUT 模型。该模型的一大特点在于其中用于引发自发对称性破缺的标量场被取为了规范群的伴随表示。虽然该模型由于预言了被实验证明未能观测到的质子衰变过程而基本被排除，但其作为一个理论仍旧有一些有趣的地方，例如单极子解等非微扰效应。在本文中，我们便来计算一下这个模型的最简版本：$\mathrm{SU}(2)$ Georgi-Glashow 模型。本篇内容我们将主要讨论该模型的自发对称性破缺过程，其非微扰效应或许会在后续推文中讨论。

## The Lagrangian of $\mathrm{SU}(2)$ Georgi-Glashow Model

我们首先来尝试写下该理论的 Lagrangian. 由于我们的 toy model 只讨论 $\mathrm{SU}(2)$ 这个最简单的情形，因此规范场项几乎与标准模型中的 $W$ 玻色子一致：

$$
    \mathscr{L}_{Gauge}=-\frac{1}{2}\mathrm{Tr}[\vec{W}_{\mu\nu}\vec{W}^{\mu\nu}]
$$

其中我们使用了通常的场归一化，这意味着耦合常数不会在规范场的运动学项出现，但会在协变导数中出现；并且我们有 Lie 代数 Killing 型的归一化条件：

$$
    \mathrm{Tr}[T_iT_j]=\frac{1}{2}\delta_{ij}
$$

其中我们用拉丁字母表示 $\mathfrak{su}(2)$ 的指标。

正如我们在前文中提到的，Georgi-Glashow 模型将用于 SSB 的标量场（"Higgs" 场）也会被取为规范群的伴随表示。因此其运动学项为：

$$
    \mathscr{L}_{Higgs}=\mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]
$$

这里 `$D_{\mu}=\partial_{\mu}-igW_{\mu}^iT^A_i$`，其中 `$T^A_i$` 是伴随表示下的生成元；而这里的 $\vec{\phi}$ 则为：

$$
    \vec{\phi}=\phi^iT_i
$$

其中 $T_i$ 与前文中一样是伴随表示空间中的基，也即是 Lie 代数的基。

容易看到，$\mathrm{SU}(2)$ 的伴随表示其实就是 $\mathrm{SO}(3)$ 的基本表示，其最多也就是破缺到 $\mathrm{SO}(2)$，也即是 $\mathrm{U}(1)$. 因此我们希望 $\vec{\phi}$ 的真空期望值为：

$$
    \langle\vec{\phi}\rangle=vT_3
$$

于是构造如下 Landau-Ginzburg 势：

$$
    V(\phi)=-\mu^2\mathrm{Tr}\phi^2+\lambda(\mathrm{Tr}\phi^2)^2
$$

容易看到其提供了真空期望值：

$$
    |\langle\vec{\phi}\rangle|=\frac{\mu}{\sqrt{\lambda}}\equiv v
$$

因此我们的 $\mathrm{SU}(2)$ Georgi-Glashow toy model 即为：

$$
    \mathscr{L}=-\frac{1}{2}\mathrm{Tr}[\vec{W}_{\mu\nu}\vec{W}^{\mu\nu}]+\mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]+\mu^2\mathrm{Tr}\phi^2-\lambda(\mathrm{Tr}\phi^2)^2
$$

## Spontaneous Symmetry Breaking

接下来我们来考虑 SSB 过程，并为该理论的规范玻色子赋予质量。为了获取玻色子的质量项，我们只需要计算 Higgs 的运动学项。考虑破缺后，Higgs 场可以被写为：

$$
    \vec{\phi}=\exp\left(\mathrm{i}\frac{\vec{\pi}(x)\cdot \vec{T}^A}{v}\right)(v+\sigma(x))T_3
$$

Goldstone 场 $\vec{\pi}(x)$ 总可以被一个规范变换分离掉，因此我们只考虑 `$v+\sigma(x)$`. 带入动力学项，我们有：

$$
\begin{aligned}
    \mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]=\mathrm{Tr}[(\partial_\mu\sigma T_3+\mathrm{i}gW^i_\mu\vec{\phi}^{\dagger}T^A_i)(\partial^\mu\sigma T_3-\mathrm{i}gW^{i\mu} T^A_i\vec{\phi})]
\end{aligned}
$$

注意到 $\mathrm{SU}(2)$ 的伴随表示为：

$$
    {(T^A_i)^j}_k=-i{\varepsilon^j}_{ki}
$$

将上式展开可以得到：

$$
    \mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]=\frac{1}{2}\partial_{\mu}\sigma\partial^\mu\sigma-\frac{1}{2}g^2W^i_\mu\phi_i W^{j\mu}\phi_j+\frac{1}{2}g^2W^i_\mu W_i^\mu \phi_j\phi^j
$$

只关注真空期望值 $v$ 的贡献，我们可以写出：

$$
    \mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]=\frac{1}{2}\partial_{\mu}\sigma\partial^\mu\sigma+\frac{1}{2}g^2v^2(W^1_\mu W^{1\mu}+W^2_\mu W^{2\mu})+(\sigma WW\text{ terms})
$$

容易看到 $W^3$ 没有质量，我们可以将其识别为该理论下的电磁场；这也告诉了我们在该理论中有 $Q=T_3$. 定义 `$W^{\pm}_\mu=W^1_{\mu}\pm\mathrm{i}W^2_{\mu}$`；进一步有：

$$
    \mathrm{Tr}[(D_{\mu}\vec{\phi})^{\dagger}(D^{\mu}\vec{\phi})]=\frac{1}{2}\partial_{\mu}\sigma\partial^\mu\sigma+\frac{1}{2}g^2v^2W^{+}_{\mu}W^{-\mu}+(\sigma WW\text{ terms})
$$

可以识别出 $m_W={1}/{\sqrt{2}}gv$. 
