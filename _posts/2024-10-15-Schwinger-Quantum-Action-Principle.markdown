---
layout:     post
title:      "Schwinger Quantum Action Principle"
subtitle:   "From a footnote in Weinberg QFT."
date:       2024-10-15 22:40:00
author:     "fromuly"
header-img: "img/post-bg-2024-2.jpg"
catalog: true
usemathjax: true
music-id: 534064298
tags:
    - Physics
    - Quantum Mechanics
    - Weinberg QFT Notes
---

# Schwinger Quantum Action Principle

本篇blog的起源是笔者在学习 Weinberg QFT Chapter 6 时，于6.4节的脚注中注意到了一个全新的概念：“Schwinger 作用量原理”。在经过各方资料查阅后，笔者决定依据包括 Schwinger 原始论文在内的各方资料，将自己对该思想的理解与推导记录于此。鉴于本文内容多为笔者本人的理解，其内容可能存在错误，欢迎读者指正。（可以去Github上开issue（？））

## The Schwinger Action Principle in Quantum Mechanics

说到 “Quantum Action”，自然首先就想到 Path Integral，就想到 Propagator，就想到跃迁振幅。因此我们首先来考虑一个如下经典量子力学中的跃迁振幅：

$$
    \langle{a',t+\mathrm{d}t}\vert{b',t}\rangle
$$

其中 `$\vert{a',t+\mathrm{d}t}\rangle$` 和 `$\vert{b',t}\rangle$` 分别为 Heisenberg 绘景下定义在不同时间的两算符 `$A(t+\mathrm{d}t)$` 和 `$B(t)$` 的本征矢。考虑对该跃迁振幅进行变分：

$$
    \delta\langle{a',t+\mathrm{d}t}\vert{b',t}\rangle=(\delta\langle{a',t+\mathrm{d}t}\vert)\vert{b',t}\rangle+\langle{a',t+\mathrm{d}t}\vert(\delta\vert{b',t}\rangle)
$$

这里的变分同时对时间和空间进行，因而其可以利用时空平移的生成元得到：

$$
\begin{aligned}
    \delta\langle{a',t+\mathrm{d}t}\vert&=\langle{a',t+\mathrm{d}t}\vert\delta G(t+\mathrm{d}t)
    \\\delta\vert{b',t}\rangle&=\delta G^{-1}(t)\vert{b',t}\rangle
\end{aligned}
$$

其中 `$G(t)$` 是无穷小变分时空平移变换：

$$
    \delta G(t)=1+ip_{\mu}(t)\delta{x^{\mu}(t)}
$$

于是我们可以显然看到：

$$
    \delta\langle{a',t+\mathrm{d}t}\vert{b',t}\rangle=\langle{a',t+\mathrm{d}t}\vert{\mathrm{d}\delta G(t)}\vert{b',t}\rangle
$$

交换变分与微分符号，我们有：

$$
\begin{aligned}
    \delta\langle{a',t+\mathrm{d}t}\vert{b',t}\rangle&=\langle{a',t+\mathrm{d}t}\vert{\delta\mathrm{d}G(t)}\vert{b',t}\rangle
    \\&=\langle{a',t+\mathrm{d}t}\vert{\delta\left(\frac{\mathrm{d}G(t)}{\mathrm{d}t}\mathrm{d}t\right)}\vert{b',t}\rangle
    \\&=\langle{a',t+\mathrm{d}t}\vert{\delta\left[i\left(\sum p_i\dot{x}^i-H\right)\mathrm{d}t\right]}\vert{b',t}\rangle
\end{aligned}
$$

可以注意到，小括号中的内容，正是我们所熟知的经典力学中的 Lagrangian. 因此，我们就可以写出：

$$
    \delta\langle{a',t+\mathrm{d}t}\vert{b',t}\rangle=\langle{a',t+\mathrm{d}t}\vert{\delta\left[iL(t)\mathrm{d}t\right]}\vert{b',t}\rangle
$$

由此，我们可以自然地考虑有限时间间隔的跃迁振幅：

$$
\begin{aligned}
    \delta\langle{a',t_2}\vert{b',t_1}\rangle&=\delta\left(\sum_{all\:states}\langle{a',t_2}\vert{\alpha_1,t_2-\mathrm{d}t}\rangle\langle{\alpha_1,t_2-\mathrm{d}t}\vert{\alpha_2,t_2-2\mathrm{d}t}\rangle\langle{\alpha_2,t_2-2\mathrm{d}t}\vert\cdots\vert{\alpha_{n-1},t_1+2\mathrm{d}t}\rangle\langle{\alpha_n,t_1+\mathrm{d}t}\vert{b',t_1}\rangle\right)
    \\&=\sum_{all\:states}\delta\left(\langle{a',t_2}\vert{\alpha_1,t_2-\mathrm{d}t}\rangle\right)\langle{\alpha_1,t_2-\mathrm{d}t}\vert{\alpha_2,t_2-2\mathrm{d}t}\rangle\langle{\alpha_2,t_2-2\mathrm{d}t}\vert\cdots\vert{\alpha_{n-1},t_1+2\mathrm{d}t}\rangle\langle{\alpha_n,t_1+\mathrm{d}t}\vert{b',t_1}\rangle
    \\&+\sum_{all\:states}\langle{a',t_2}\vert{\alpha_1,t_2-\mathrm{d}t}\rangle\delta\left(\langle{\alpha_1,t_2-\mathrm{d}t}\vert{\alpha_2,t_2-2\mathrm{d}t}\rangle\right)\langle{\alpha_2,t_2-2\mathrm{d}t}\vert\cdots\vert{\alpha_{n-1},t_1+2\mathrm{d}t}\rangle\langle{\alpha_n,t_1+\mathrm{d}t}\vert{b',t_1}\rangle
    \\&+\cdots
    \\&+\sum_{all\:states}\langle{a',t_2}\vert{\alpha_1,t_2-\mathrm{d}t}\rangle\langle{\alpha_1,t_2-\mathrm{d}t}\vert{\alpha_2,t_2-2\mathrm{d}t}\rangle\langle{\alpha_2,t_2-2\mathrm{d}t}\vert\cdots\vert{\alpha_{n-1},t_1+2\mathrm{d}t}\rangle\delta\left(\langle{\alpha_n,t_1+\mathrm{d}t}\vert{b',t_1}\rangle\right)
    \\&=i\langle{a',t_2}\vert{\delta\int^{t_2}_{t_1}L(t)\:\mathrm{d}t}\vert{b',t_1}\rangle
\end{aligned}
$$

定义作用量 `$\displaystyle S=\int^{t_2}_{t_1}L(t)\:\mathrm{d}t$`，于是我们就有：

$$
    \delta\langle{a',t_2}\vert{b',t_1}\rangle=i\langle{a',t_2}\vert{\delta{S}}\vert{b',t_1}\rangle
$$

值得注意的是，在此我们将 Lagrangian 视为一个算符而不是一个标量，其包含了态的变分的所有信息，因此上式中的作用量也是一个算符。

## The Schwinger Action Principle in Quantum Field Theory

我们的目的是将上述内容推广到量子场论当中。仍旧采取 Heisenberg 绘景，考虑两个类空超曲面 `$\Sigma_1$` 和 `$\Sigma_2$`，使得所有 `$\Sigma_2$` 上的点都处于 `$\Sigma_1$` 的绝对未来上。分别在其上定义的两个算符 `$\tau_1$` 和 `$\tau_2$`，使得其具有完全相同的本征值谱。这样的要求使得我们有：

$$
    {\tau_2}=\mathcal{U}_{12}{\tau_1}\mathcal{U}_{12}^{-1}
$$

其中 `$\mathcal{U}_{12}$` 为一幺正算符。分别考虑其本征态 `$\left\vert{{\tau'}_1,\Sigma_1}\right\rangle$` 和 `$\left\vert{{\tau'}_2,\Sigma_2}\right\rangle$`，我们自然有：

$$
    \left\vert{{\tau'}_2,\Sigma_2}\right\rangle=\mathcal{U}_{12}\left\vert{{\tau'}_1,\Sigma_1}\right\rangle
$$

考虑跃迁振幅，有：

$$
    \left\langle{{\tau'}_2,\Sigma_2}\right\vert\left.{{\tau'}_1,\Sigma_1}\right\rangle=\left\langle{{\tau'}_1,\Sigma_1}\right\vert{\mathcal{U}^{-1}_{12}}\left\vert{{\tau'}_1,\Sigma_1}\right\rangle
$$

计算其变分，有：

$$
    \delta\left\langle{{\tau'}_2,\Sigma_2}\right\vert\left.{{\tau'}_1,\Sigma_1}\right\rangle=\left\langle{{\tau'}_1,\Sigma_1}\right\vert{\delta\mathcal{U}^{-1}_{12}}\left\vert{{\tau'}_1,\Sigma_1}\right\rangle
$$

由于算符 $\mathcal{U}_{12}$ 的幺正性，我们必须有：

$$
    \mathcal{U}_{12}\delta\mathcal{U}^{-1}_{12}=-\delta\mathcal{U}_{12}\mathcal{U}^{-1}_{12}
$$

这意味着 `$i\mathcal{U}_{12}\delta\mathcal{U}^{-1}_{12}$` 一定是一个厄米算符。设其为 `$\delta{S_{12}}$`，有：

$$
    \delta\mathcal{U}^{-1}_{12}=i\mathcal{U}^{-1}_{12}\delta{S_{12}}
$$

于是有：

$$
    \delta\left\langle{{\tau'}_2,\Sigma_2}\right\vert\left.{{\tau'}_1,\Sigma_1}\right\rangle=i\left\langle{{\tau'}_2,\Sigma_2}\right\vert{\delta{S_{12}}}\left\vert{{\tau'}_1,\Sigma_1}\right\rangle
$$

容易看到，$\delta{S_{12}}$ 总具有可加性（适当插入完备性关系即可）：

$$
    \delta{S_{13}}=\delta{S_{12}}+\delta{S_{23}}
$$

我们假设 $\delta{S_{12}}$ 确由某个厄米算符 $S_{12}$ 的变分给出，这样算符描述了从 $\tau_1$ 到 $\tau_2$ 的演化，因而包含了两个超曲面之间可能的所有信息。由可加性可知，其一般形式为：

$$
    S_{12}=\int^{\Sigma_2}_{\Sigma_1}\mathscr{L}[x]\:d^4x
$$

其中 $\mathscr{L}[x]$ 是场及其时空坐标导数的函数。出于经典力学与场论中的讨论，我们应该将其称为 Lagrange 算符，并称 $S_{12}$ 为作用量算符。
而将我们在 Quantum Mechanics 部分的讨论进行推广，我们又知道跃迁振幅的变分可以被描述为一无穷小幺正变换 $F$ 的差：

$$
    \delta\left\langle{{\tau'}_2,\Sigma_2}\right\vert\left.{{\tau'}_1,\Sigma_1}\right\rangle=i\left\langle{{\tau'}_2,\Sigma_2}\right\vert{F(\Sigma_2)-F(\Sigma_1)}\left\vert{{\tau'}_1,\Sigma_1}\right\rangle
$$

于是我们有：

$$
    \delta{S_{12}}=F(\Sigma_2)-F(\Sigma_1)
$$

这便是所谓 Schwinger Action Principle. 该等式要求了对作用量 `$S_{12}$` 的变分中，所有的非边界项都必须不提供贡献，仅有边界项给出一个幺正变换的差。
考虑对 `$S_{12}$` 的变分 `$\delta{S_{12}}$`，其包含了两部分，分别为两超曲面之间场自身的变分，对应于 `$\delta_0{\mathscr{L}}$`；以及两超曲面自身的变分，对应于两边界的相减：

$$
    \delta{S_{12}}=\int^{\Sigma_2}_{\Sigma_1}d^4x\:\delta_0{\mathscr{L}}+\left(\int_{\Sigma_2}-\int_{\Sigma_1}\right)d\Sigma_{\mu}\delta{x^{\mu}}\mathscr{L}
$$

计算 $\delta_0{\mathscr{L}}$ 作为 $\phi^a(x)$ 与 $\partial_{\mu}\phi^a(x)$ 的展开：

$$
    \delta_0{\mathscr{L}}=\left(\frac{\partial{\mathscr{L}}}{\partial{\phi^a}}-\partial_{\mu}\frac{\partial{\mathscr{L}}}{\partial(\partial_{\mu}\phi^a)}\right)\delta_0{\phi^a}+\partial_{\mu}\left[\frac{\partial\mathscr{L}}{\partial(\partial_{\mu}\phi^a)}\delta_0\phi^a\right]
$$

由于我们要求非边界项不提供贡献，这直接给出了场的运动方程，也就是我们熟知的 Euler-Lagrange 方程：

$$
    \frac{\partial{\mathscr{L}}}{\partial{\phi^a}}-\partial_{\mu}\frac{\partial{\mathscr{L}}}{\partial(\partial_{\mu}\phi^a)}=0
$$

而剩下的全导数项则与额外的边界变分项一起给出了边界幺正变换的形式：

$$
    F(\Sigma)=\int_{\Sigma}d\Sigma_{\mu}\left(\frac{\partial{\mathscr{L}}}{\partial(\partial_{\mu}\phi^a)}\delta_0\phi^a+\mathscr{L}\delta{x^\mu}\right)
$$

这便是 Schwinger Quantum Action Principle 的基本内容。
可以证明，Schwinger Quantum Action Principle 与 Feynman Path Integral 具有完全等价性。也可以使用该 Action Principle 进行一些具体计算。笔者在此不多赘述（其实是看不懂也看不动了呜呜呜……）

----

参考文献：

***The Theory of Quantized Fields. I***, Julian Schwinger (<https://journals.aps.org/pr/pdf/10.1103/PhysRev.82.914>)

***The Schwinger Action Principle and Its Applications to Quantum Mechanics***, Paul Bracken (<http://dx.doi.org/10.5772/53472>)

***Schwinger’s Quantum Action Principle***, Kimball A. Milton (<https://arxiv.org/pdf/1503.08091>)
