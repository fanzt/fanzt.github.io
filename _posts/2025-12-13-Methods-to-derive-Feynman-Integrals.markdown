---
layout:     post
title:      "Methods of Evaluating Feynman Integrals"
subtitle:   "IBP, MIs and Differential Equations."
date:       2025-12-13 13:00:00
author:     "fromuly"
header-img: "img/post-bg-2025-21.jpg"
catalog: true
usemathjax: true
music-id: 2749827543
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
---

> 文章内容主要参考了 [[arxiv:2502.14742](https://arxiv.org/abs/2502.14742)].

量子场论是现代粒子物理不可缺少的基本语言与计算工具。然而，众所周知地，大多数粒子唯象学所需要的场论计算（ $\beta$ 函数，反常磁矩，散射截面等），都使用基于 Feynman 图体系的微扰论技术，因此对更高计算精度的需求使得我们必须计算更高阶、更高圈的费曼图。譬如，对于如今的一个 state-of-art 的问题，人们往往需要计算数以千万计的高圈 Feynman 积分，这为高精度唯象学计算带来了极大的困难。解决这一问题的一条路径当然是抛弃掉基于 Feynman 积分的微扰论技术，这一方向延伸到了 S 矩阵计划、在壳纲领等现代振幅学成果；而另一条路则是想办法优化传统的 Feynman 积分计算技术。在这个方向上，如今的人们开发出了一套相对优秀的高圈积分计算技术，使这一问题在一定程度上得以解决或缓解[^1]。在本文中，我们便来简要介绍这一系列高圈 Feynman 积分计算技术，并展示一些基本的应用样例。

对于某一高阶微扰论问题所面对的大量高圈 Feynman 积分，现代的计算技术一般基于如下流程：在绝大多数情况下，这样的大量高圈积分不会是完全相互独立的，它们之间往往可以通过分部积分和线性组合相互转化。因此，我们可以通过分部积分将这大量的 Feynman 积分转化为几个线性独立的基本积分，称为**主积分**（Master Integrals, MIs），这一步骤被称为 **IBP 约化**；我们现在拥有成熟的计算机算法（Laporta algorithm）和程序[^2]来实现 IBP 约化的流程。在经过 IBP 约化后，我们便将问题转化为了如何计算出主积分的结果。由于主积分本身可以视为以运动学变量和相关质量为参量的多变量函数，我们往往可以将主积分表达为某个微分方程/方程组的解的形式，于是我们又将求解主积分转化为了求解系列微分方程/方程组的问题，进而可以使用特殊函数/级数展开等技术获得这些方程组的解，以得到我们最终需要的结果。

## Feynman Integral

为了详细地介绍这一套流程，我们首先需要给定 Feynman 积分的一般形式。

TBD.

----

[^1]: 当然，在现代振幅学中，这两套技术已经发生了深度的结合。
[^2]: 参考：AIR [[arXiv:hep-ph/0404258](https://arxiv.org/abs/hep-ph/0404258)], Blade [[arXiv:2405.14621](https://arxiv.org/abs/2405.14621)], FIRE [[arXiv:2311.02370](https://arxiv.org/abs/2311.02370)], Kira [[arXiv:2008.06494](https://arxiv.org/abs/2008.06494)], LiteRed [[arXiv:1310.1145](https://arxiv.org/abs/1310.1145)], NeatIBP [[arXiv:2305.08783](https://arxiv.org/abs/2305.08783)] and Reduze [[arXiv:1201.4330](https://arxiv.org/abs/1201.4330)]
