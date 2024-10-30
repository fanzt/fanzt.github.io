---
layout:     post
title:      "Sequence Limit and Real Number Completeness Theorem"
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

数分前两章复习。
根据 SJTU 数学分析教材的思路，我们使用实数的无限小数定义。

## 实数的无限小数表示

首先，$\forall{x}\in{\mathbb{R}}, \exists!\:n_0\in{\mathbb{Z}},x\in(n_0,n_0+1]$. 利用半开半闭区间将 $(n_0,n_0+1]$ 十等分，又有 $\forall{x}\in{\mathbb{R}}, \exists!\:a_1\in{\mathbb{Z}},x\in(n_0+a_1/10,n_0+(a_1+1)/10]$. 如此下去，我们即有实数的无限小数表示：

$$
    x=n_0.a_1a_2a_3\cdots
$$

## 数列极限

1. 存在极限：
   $$
        \forall{\varepsilon}>0,\:\exists{N\in{\mathbb{N}}},\:s.t.\forall{n>N}, |x_n-a|<\varepsilon\Leftrightarrow\lim_{n\rightarrow\infty}x_n=a.
    $$
2. 不存在极限：
    $$
        \forall{a\in{\mathbb{R}}},\:\exists\varepsilon_0>0,\:\forall{N\in\mathbb{N}},\:\exists{n>N},\:|x_n-a|>\varepsilon_0
    $$
3. 极限无穷大：
    $$
        \forall{M>0},\:\exists{N\in{\mathbb{N}}},\:s.t.\forall{n>N},x_n>M\Leftrightarrow{\lim_{n\rightarrow\infty}}x_n=+\infty
    $$

- 数列极限的性质：唯一性，有界性，保序性
- 利用定义求极限的思想/技巧
  - 迫敛性：构造两数列使待求数列夹于两数列之中，且两数列均收敛于同一极限；
  - 四则运算：仅可用于有限次，需要先保证被运算极限存在；
  - 大N截断：用于由极限条件推导极限结论，常见于分式加和的极限（令前N项为有限值截断，后N项依赖于n但收敛）

$子列定理:{x_n}收敛\Leftrightarrow其任意子列均收敛到同一个数。$
可用于利用两个或多个子列拼凑出原数列；更常用于反证极限不存在。

$Stolz定理:$
若有：
$$
    \{y_n\}单调增且\lim_{n\rightarrow\infty}y_n=+\infty,\:\lim_{n\rightarrow\infty}\frac{x_{n+1}-x_{n}}{y_{n+1}-y_n}=a
$$
则有：
$$
    \lim_{n\rightarrow\infty}\frac{x_n}{y_n}=a
$$
*注：Stolz定理的逆定理并不成立。*
常见于分式数列的求解。

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

- 常见用法：对递推数列极限，先判断差分的正负号以期给出单调性，再根据可能的单调性分类讨论，寻找对应的上下界。

## 闭区间套定理

`$\mathrm{Theorem}:对一闭区间集合 \{[a_n,b_n]\}_{n\geq{1}}$`
若有：

1. $[a_{n+1},b_{n+1}]\subset[a_n,b_n]$
2. $\lim_{n\rightarrow\infty}(b_n-a_n)=0$

则有：

$$
    \exists!\:\xi\:s.t.\bigcap_{n=1}^{\infty}[a_n,b_n]={\xi}
$$

亦即：

$$
    \lim_{n\rightarrow\infty}a_n=\lim_{n\rightarrow\infty}b_n=\xi
$$

$\mathrm{Proof}:$
由单调收敛定理有：$a_n$ 单调递增有上界，$b_n$ 单调递减有下界，因而其均收敛，设极限分别为 $\xi$、$\eta$。又由条件2有 $\xi-\eta=0$.

- 常见用法：多用于证明其余定理。

## Bolzano-Weierstrass 定理

$\mathrm{Theorem}:若数列{x_n}有界，则其必有收敛子列。$

$\mathrm{Proof}:$

设 $x_n$ 有界，则

$$\exists{a_1<b_1},\:s.t.x_n\in[a_1,b_1]\:\forall{n>1}
$$

将 `$[a_1,b_1]$` 二等分，其中必有一个有 `${x_n}$` 中无穷多个点。记该闭区间为 $[a_2,b_2]$. 
数学归纳法，有 

$$
\begin{aligned}
&[a_{n+1},b_{n+1}]\subset[a_n,b_n]
\\ [a_{n+1},b_{n+1}]&=1/2[a_n,b_n]=1/2^n[a_1,b_1]\rightarrow{0}
\end{aligned}
$$

在每一个这样的区间中都可以取到一个 $x_{n_k}\in[a_k,b_k]$，而由闭区间套定理有：

$$
    \bigcap_{n=1}^{\infty}[a_n,b_n]={\xi}
$$

因此 $x_{n_k}$ 收敛。

- 常见用法：多用于证明其余定理（例如联合 Heine 定理证明闭区间上连续函数性质。）

## Cauchy 收敛准则

Cauchy 列：

$$
    \forall{\varepsilon>0},\:\exists{N},\:\forall{n,m>N},|x_n-x_m|<\varepsilon
$$

$\mathrm{Theorem}:实数列{x_n}收敛当且仅当其为 Cauchy 列。$

$\mathrm{Proof}:$
一方面，当 `${x_n}$` 是 Cauchy 列时，我们总可以取 Cauchy 列定义中的 $\varepsilon$ 为一有限值（例如，取为1），则 $N$ 之后的所有项均被限制在 `$x_N\pm{1}$` 中。这意味着数列的大小被限制在前有限项中，自然有界；而由 B-W 定理知其必存在一收敛子列。将截断标准 $N$ 取得比 Cauchy 列与 B-W 收敛子列的两个截断标准 $N_1$ 与 $N_2$ 都要大，就可以保证剩余项同时满足 Cauchy 与 B-W 的检验，而由此就有：

$$
    |x_n-\xi|=|x_n-x_{n_k}+x_{n_k}-\xi|\leq|x_n-x_{n_k}|+|x_{n_k}-\xi|=2\varepsilon
$$

由此即有极限存在。
另一方面，有：

$$
\begin{aligned}
    \lim_{n\rightarrow\infty}x_n=\xi&\Leftrightarrow\forall{\varepsilon>0},\exists{N\in\mathbb{N}},\:\forall{n>N},\:|x_n-\xi|<\frac{\varepsilon}{2}
    \\&\Rightarrow|x_n-x_m|=|x_n-\xi+\xi-x_m|\leq|x_n-\xi|+|x_m-\xi|<\varepsilon
\end{aligned}
$$

即有其为 Cauchy 列。

- 常见用法：证明级数列是否收敛；证明其余定理。

## 确界原理

TBD.