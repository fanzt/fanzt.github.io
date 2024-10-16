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

本篇blog的起源是笔者在学习 Weinberg QFT Chapter 6 时，于6.4节的脚注中注意到了一个全新的概念：“Schwinger 作用量原理”。出于笔者水平不足，Weinberg 给出的 Schwinger 论文原文并没能让笔者看懂这一原理的具体内容，而在查阅了中文互联网和其余常见的 QM 或 QFT 教材后，笔者也并未找到对这一概念足够详实的解释。但最终笔者在arxiv上找到了一篇综述性书籍，详细地介绍了所谓 Schwinger 作用量原理的来源与应用方法。因此，笔者决定在仔细进行学习与推导的同时将其转述为中文，记录在blog上。

## The derivation of Schwinger Action Principle

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

其中 `$G(t)$` 是无穷小变分时空平移生成元：

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

## 施工中···
