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

量子场论是现代粒子物理不可缺少的基本语言与计算工具。然而，众所周知地，大多数粒子唯象学所需要的场论计算（ $\beta$ 函数，反常磁矩，散射截面等），都使用基于 Feynman 图体系的微扰论技术，因此对更高计算精度的需求使得我们必须计算更高阶、更高圈的费曼图。譬如，对于如今的一个 state-of-art 的问题，人们往往需要计算数以千计万计的高圈 Feynman 积分，这为高精度唯象学计算带来了极大的困难。解决这一问题的一条路径当然是抛弃掉基于 Feynman 积分的微扰论技术，这一方向延伸到了 S 矩阵计划、在壳纲领等现代振幅学成果；而另一条路则是想办法优化传统的 Feynman 积分计算技术。在这个方向上，如今的人们开发出了一套相对优秀的高圈积分计算技术，使这一问题在一定程度上得以解决或缓解[^1]。在本文中，我们便来简要介绍这一系列高圈 Feynman 积分计算技术，并展示一些基本的应用样例。

对于某一高阶微扰论问题所面对的大量高圈 Feynman 积分，现代的计算技术一般基于如下流程：在绝大多数情况下，这样的大量高圈积分不会是完全相互独立的，它们之间往往可以通过分部积分和线性组合相互转化。因此，我们可以通过分部积分将这大量的 Feynman 积分转化为几个线性独立的基本积分，称为**主积分**（Master Integrals, MIs），这一步骤被称为 **IBP 约化**；我们现在拥有成熟的计算机算法（Laporta algorithm）和程序[^2]来实现 IBP 约化的流程。在经过 IBP 约化后，我们便将问题转化为了如何计算出主积分的结果。由于主积分本身可以视为以运动学变量和相关质量为参量的多变量函数，我们往往可以将主积分表达为某个微分方程/方程组的解的形式，于是我们又将求解主积分转化为了求解系列微分方程/方程组的问题，进而可以使用特殊函数/级数展开等技术获得这些方程组的解，以得到我们最终需要的结果。

## Feynman Integral

为了详细地介绍这一套流程，我们首先需要给定 Feynman 积分的一般形式。在最常用的维度正规化下，一个一般的 Feynman 积分具有如下形式：

$$
    I_{\boldsymbol{\alpha}}(s_j;d)=\int\prod_{k=1}^l\frac{\mathrm{d}^dq_k}{(2\pi)^d}\frac{1}{\mathcal{D}_{1}^{\alpha_1}\dots\mathcal{D}_n^{\alpha_n}}
$$

其中 $l$ 是圈动量的数量，亦即 Feynman 图的圈数，$d=4-2\epsilon$ 是维度正规化后的维数，$s_j$ 是所有的运动学不变量，$q_k$ 是圈动量而 $\mathcal{D}_i=p_i^2-m_i^2$ 是传播子分母，$\alpha_i$ 则是每个传播子的幂次数（也可以是负的）。

然而，容易想到地，一般的圈图计算中常常会有上述形式未提到的分子出现在计算过程中。如果分子中不包含圈动量，这当然无关紧要；但如果分子中包含了圈动量，我们就需要想办法把这样的积分转化为上述标准形式。一个通用的方法是，将这样的分子表达为运动学不变量 $s_j$ 与分母 $\mathcal{D}_i^{\boldsymbol{\alpha}}$ 的线性组合。考虑到我们可以构造出最多 $l(l+1)/2+l(n-1)\sim l^2+l(n-1)$ 个独立的含圈动量内积（$l$ 个圈动量自相内积，加上 $l$ 个圈动量与 $n-1$ 个独立外线动量内积），我们至少也需要相同数量的分母，才能够实现一一的抵消化简；为此，我们可能需要在 Feynman 积分中加入额外的辅助分母。

### Example: two-loop massless triangle

![two-loop triangle diagram](/img/poster_img/Feynman_Integral/g85.svg)

考虑一个如图所示的二圈图，其中的粒子都是无质量的。根据我们上述的计数，容易看到我们会有 $7$ 个独立的动量内积；但图中只有六个传播子，所以我们需要额外引入一个辅助分母来实现这 $7$ 个可能的内积分子。上图中已经包含的传播子是：

$$
\begin{aligned}
    &\mathcal{D}_1=q_1^2,\qquad&\mathcal{D}_2=q_2^2
    \\&\mathcal{D}_3=(q_1-p_1)^2\qquad &\mathcal{D}_4=(q_1-q_2)^2
    \\&\mathcal{D}_5=(q_1-p_1-p_2)^2,\qquad&\mathcal{D}_6=(q_2-p_1-p_2)^2
\end{aligned}
$$

再额外引入一个辅助分母 $\mathcal{D}_7=(q_2-p_1)^2$，我们就可以构造出所有需要的标量内积：

| Scalar Product | Relation |
|      ---       |    ---   |
|     $q_1^2$    |$\mathcal{D}_1$|
|     $q_2^2$    |$\mathcal{D}_2$|
|     $q_1\cdot q_2$    |$\frac{1}{2}(\mathcal{D}_1+\mathcal{D}_2-\mathcal{D}_4)$|
| $q_1\cdot p_1$| $\frac{1}{2}(\mathcal{D}_1-\mathcal{D}_3)$|
| $q_1\cdot p_2$| $\frac{1}{2}(\mathcal{D}_3-\mathcal{D}_5)$|
| $q_2\cdot p_1$| $\frac{1}{2}(\mathcal{D}_2-\mathcal{D}_7)$|
| $q_2\cdot p_2$| $\frac{1}{2}(\mathcal{D}_7-\mathcal{D}_6)$|

于是我们就可以将图中可能出现的积分转化为标准 Feynman 积分形式。例如，含导数顶点可能给出的如下形式圈积分即可化为标准积分：

$$
\begin{aligned}
    \int\frac{\mathrm{d}^dq_1}{(2\pi)^d}\frac{\mathrm{d}^dq_2}{(2\pi)^d}\frac{q_1\cdot q_2}{\mathcal{D}_1\mathcal{D}_3\mathcal{D}_4\mathcal{D}_5}&=\frac{1}{2}\int\frac{\mathrm{d}^dq_1}{(2\pi)^d}\frac{\mathrm{d}^dq_2}{(2\pi)^d}\frac{\mathcal{D}_1+\mathcal{D}_2-\mathcal{D}_4}{\mathcal{D}_1\mathcal{D}_3\mathcal{D}_4\mathcal{D}_5}\\&=\frac{1}{2}(I_{0,0,1,1,1,0,0}+I_{1,-1,1,1,1,0,0}-I_{1,0,1,0,1,0,0})
\end{aligned}
$$

## Integration-by-parts identities

TBD.

----

[^1]: 当然，在现代振幅学中，这两套技术已经发生了深度的结合。
[^2]: 参考：AIR [[arXiv:hep-ph/0404258](https://arxiv.org/abs/hep-ph/0404258)], Blade [[arXiv:2405.14621](https://arxiv.org/abs/2405.14621)], FIRE [[arXiv:2311.02370](https://arxiv.org/abs/2311.02370)], Kira [[arXiv:2008.06494](https://arxiv.org/abs/2008.06494)], LiteRed [[arXiv:1310.1145](https://arxiv.org/abs/1310.1145)], NeatIBP [[arXiv:2305.08783](https://arxiv.org/abs/2305.08783)] and Reduze [[arXiv:1201.4330](https://arxiv.org/abs/1201.4330)]
