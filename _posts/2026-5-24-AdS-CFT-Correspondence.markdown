---
layout:     post
title:      "AdS/CFT Correspondence"
subtitle:   "As above, so below; as within, so without; as the universe, so the soul."
date:       2026-5-24 22:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-5.jpg"
catalog: true
usemathjax: true
music-id: 3372975275
tags:
    - Physics
    - Quantum Field Theory
    - Mathematics
    - String Theory
---

## Introduction

毋庸置疑地，整个二十世纪的物理学被「对称性」所主导。从 Noether 证明连续对称性与守恒流的关系作为起始，对称性在过去的一百年中成为了所有指引理论物理学发展的思想中最为明亮的那一座灯塔。广义协变性与 Einstein 引力理论，规范对称性与 Yang-Mills 规范场论，时空对称性与 Lee-Yang 宇称不守恒，整体对称性破缺与 Nambu-Goldstone 定理，Landau-Ginzburg 相变与 Brout-Englert-Higgs 机制，一直到粒子物理标准模型的落成，对称性始终是其中每一个环节的核心。

然而，随着人们将目光投向超越标准模型的理论与量子化引力、建立终极理论的至高目标，另一个在二十世纪中多少有些被掩盖了光彩的性质——「对偶性」，逐渐在二十一世纪的物理学中展现出愈发重要的地位。不同于对称性表述了一个理论自身拥有的性质，对偶性将多个不同的理论联系在了一起。一方面，对于原本理论中的问题，这为我们带来了全新的工具——我们可以使用对偶理论中的技术来求解原本理论中的问题；另一方面，这启示我们开始思考，曾经被认为用来定义一个物理系统的方法（例如，Lagrangian），是否只是一种像坐标系一样的非本质的描述方式。

在本文中，我们便来简要介绍总结人们目前最为关注的对偶关系之一：AdS/CFT 对偶关系。

## Some knowledge about String Theory

为了介绍 AdS/CFT，我们需要首先简要回顾一下弦论的知识。

为了抵消 Weyl 反常，玻色弦理论需要生活在 26 维时空中，而超弦理论需要生活在 10 维时空中；这几乎已经是人尽皆知的特征。通过标准的光锥量子化/协变量子化，我们可以分别得到开弦的闭弦的最低激发态是快子，而第一激发态则分别是：

- 开弦：规范场 `$A_M$`；
- 闭弦：度规场 `$G_{MN}$`，Kalb-Ramond 二形式场 `$B_{MN}$` 以及胀子 `$\Phi$`. 

