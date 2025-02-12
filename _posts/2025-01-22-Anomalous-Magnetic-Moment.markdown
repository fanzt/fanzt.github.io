---
layout:     post
title:      "Anomalous Magnetic Moment"
subtitle:   "The application of Quantum Electrodynamics."
date:       2025-01-22 09:00:00
author:     "fromuly"
header-img: "img/post-bg-2024-12.png"
catalog: true
usemathjax: true
music-id: 29460709
tags:
    - Physics
    - Weinberg QFT Notes
    - Quantum Field Theory
---

> *“人类历史上最精确的理论预言之一。”*

## 1 相互作用顶点的形式

为了计算磁矩，我们首先需要给出全电磁相互作用顶点的形式表达式。考虑如下矩阵元：

$$
    \langle{\mathbf{p}',\sigma'}|J^\mu(x)|\mathbf{p},\sigma\rangle
$$

其显然描述了电磁相互作用耦合中去除电磁场的部分。依据基本的对称性，我们可以对该矩阵元给出如下约束信息：

1. 平移对称性：

    $$
        \langle{\mathbf{p}',\sigma'}|J^\mu(x)|\mathbf{p},\sigma\rangle=\exp[i(p-p')\cdot x]\langle{\mathbf{p}',\sigma'}|J^\mu(0)|\mathbf{p},\sigma\rangle
    $$

2. 规范对称性：

    $$
        \partial_\mu\langle{\mathbf{p}',\sigma'}|J^\mu(x)|\mathbf{p},\sigma\rangle=0
    $$

3. Lorentz 协变性：

    $$
        \langle{\mathbf{p}',\sigma'}|J^\mu(0)|\mathbf{p},\sigma\rangle=iq(2\pi)^{-3}\bar{u}(\mathbf{p}',\sigma')\Gamma^{\mu}(p',p)u(\mathbf{p},\sigma)
    $$

*说真的，我算完了。但我不想把那长达两页纸的反对易关系化简抄上来。太恶心了。*
