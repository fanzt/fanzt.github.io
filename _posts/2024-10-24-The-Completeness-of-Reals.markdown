---
layout:     post
title:      "Real Number Completeness Theorem"
subtitle:   "The Review of Mathematical Analysis."
date:       2024-10-24 12:10:00
author:     "fromuly"
header-img: "img/post-bg-2024-3.jpg"
catalog: true
usemathjax: true
music-id: 730806
tags:
    - Mathematical Analysis
---

# 实数完备性定理

数分前两章复习。
根据 SJTU 数学分析教材的思路，我们使用实数的无限小数定义。

## 实数的无限小数表示

首先，$\forall{x}\in{\mathbb{R}}, \exists!\:n_0\in{\mathbb{Z}},x\in(n_0,n_0+1]$. 利用半开半闭区间将 $(n_0,n_0+1]$ 十等分，又有 $\forall{x}\in{\mathbb{R}}, \exists!\:a_1\in{\mathbb{Z}},x\in(n_0+a_1/10,n_0+(a_1+1)/10]$. 如此下去，我们即有实数的无限小数表示：

$$
    x=n_0.a_1a_2a_3\cdots
$$

## 单调收敛定理

$\mathrm{Theorem}:单调有界实数列必收敛。$

$\mathrm{Proof}:$
$$\{x_n\} 有上界 \Leftrightarrow \exists{M}s.t.\forall{n\geq1},x_n\leq{M}$$

又由单调增有：

$$x_1\leq x_2\leq x_3\cdots\leq M$$

利用实数的无限小数定义思想
$$
\begin{aligned}
    &\exists n_0\:s.t.\:x_{n_1}\in(n_0,n_0+1]
    \\&\exists a_1\:s.t.\:x_{n_2}\in(n_0+a_1/10,n_0+(a_1+1)/10]
    \\&\exists a_2\:s.t.\:x_{n_3}\in(n_0+a_1/10+a_2/100,n_0+a_1/10+(a_2+1)/100]
    \\&\cdots
\end{aligned}
$$

于是有：
$$
\begin{aligned}
    &\forall{\varepsilon>0},\exists{k}\:s.t.\:10^{-k}<\varepsilon,
    \\&\forall{n\geq{n_k}},n_0.a_1a_2\cdots{a_k}\leq{x_{n_k}}\leq{n_0.a_1a_2\cdots{(a_k+1)}}
    \\&\Rightarrow\forall{n\geq{n_k}},|x_n-a|<10^{-k}<\varepsilon
\end{aligned}
$$

因而收敛。

## 待施工