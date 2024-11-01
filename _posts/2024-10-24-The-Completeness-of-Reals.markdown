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
        \forall{\varepsilon}>0,\:\exists{N\in{\mathbb{N}}},\:s.t.\forall{n>N}, |x_n-a|<\varepsilon\iff\lim_{n\rightarrow\infty}x_n=a.
    $$

2. 不存在极限：

    $$
        \forall{a\in{\mathbb{R}}},\:\exists\varepsilon_0>0,\:\forall{N\in\mathbb{N}},\:\exists{n>N},\:|x_n-a|>\varepsilon_0
    $$

3. 极限无穷大：

    $$
        \forall{M>0},\:\exists{N\in{\mathbb{N}}},\:s.t.\forall{n>N},x_n>M\iff{\lim_{n\rightarrow\infty}}x_n=+\infty
    $$

- 数列极限的性质：唯一性，有界性，保序性
- 利用定义求极限的思想/技巧
  - 迫敛性：构造两数列使待求数列夹于两数列之中，且两数列均收敛于同一极限；
  - 四则运算：仅可用于有限次，需要先保证被运算极限存在；
  - 大N截断：用于由极限条件推导极限结论，常见于分式加和的极限（令前N项为有限值截断，后N项依赖于n但收敛）

$子列定理:{x_n}收敛\iff其任意子列均收敛到同一个数。$

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

### 几个需要注意的结论

*常见的坏东西不是振荡就是调和级数。*

1. 发散数列的绝对值数列可能收敛。
   - e.g. `$x_n=(-1)^{n-1}$`
2. 收敛数列与发散数列的积既可以是收敛的，也可以是发散的。
   - e.g.1 `$a_n=\frac{1}{n},b_n=n\Rightarrow{a_nb_n}$` 收敛。
   - e.g.2 `$a_n=\frac{1}{n+1},b_n=n\sin{\frac{n\pi}{2}}\Rightarrow{a_nb_n}$` 发散。
3. 非负发散数列的积可以收敛。
   - e.g. $x_n=\frac{1+(-1)^n}{2},y_n=\frac{1-(-1)^n}{2}\Rightarrow{x_ny_n=0}$.
4. 非负发散数列的和可以收敛。
   - e.g. 取一个收敛于 $a$ 的数列，间隔插入 $0$ 构成不收敛的交错数列，再取一个在上述数列为 $0$ 的项为 $a$，非零项为 $0$ 的数列，二者加和显然收敛于 $a$.
5. 算术平均值收敛的数列可以发散（亦即Stolz定理的逆不成立）。
6. 对任意的 `$p\in\mathbb{N}$`，总可以有数列 `$a_n$` 使得 `$\lim_{n\rightarrow\infty}(a_{n+p}-a_n)=0$` 而 `${a_n}$` 发散。
   - e.g. 调和级数前 $n$ 项和。
   - 与 Cauchy 列等价定义的区别：Cauchy 列定义要求固定 $n$ 后对每个 $p$ 都有 `$|x_{n+p}-x_{n}|<\varepsilon$`，而这里则是固定了 $p$ 之后对任意大的 $n$ 有 `$|x_{n+p}-x_{n}|<\varepsilon$`.

## 单调收敛定理

$\mathrm{Theorem}:单调有界实数列必收敛。$

$\mathrm{Proof}:$

$$
\{x_n\} 有上界 \iff \exists{M}s.t.\forall{n\geq1},x_n\leq{M}
$$

又由单调增有：

$$
x_1\leq x_2\leq x_3\cdots\leq M
$$

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
    \lim_{n\rightarrow\infty}x_n=\xi&\iff\forall{\varepsilon>0},\exists{N\in\mathbb{N}},\:\forall{n>N},\:|x_n-\xi|<\frac{\varepsilon}{2}
    \\&\Rightarrow|x_n-x_m|=|x_n-\xi+\xi-x_m|\leq|x_n-\xi|+|x_m-\xi|<\varepsilon
\end{aligned}
$$

即有其为 Cauchy 列。

- 常见用法：证明级数列是否收敛；证明其余定理。

### Cauchy 收敛的几个等价表述

1. 数列 ${x_n}$ 收敛 `$\iff\forall\varepsilon>0,\exists N=N(\varepsilon), \forall n,m>N, |x_n-x_m|<\varepsilon$`.
2. 数列 ${x_n}$ 收敛 `$\iff\forall\varepsilon>0,\exists N=N(\varepsilon),\forall n>N,\forall p\in\mathbb{N}, |x_{n+p}-x_n|<\varepsilon$`
3. 数列 ${x_n}$ 收敛 `$\iff\forall\varepsilon>0,\exists N=N(\varepsilon), \forall m\in\mathbb{N}, |x_{N+m}-x_N|<\varepsilon$`

问题：若将 $\mathbb{N}$ 替换为 $\mathbb{N}$ 的任意子集 $P$ 如何？
答案是这样的替换无法保证数列仍旧收敛。上述叙述与数列收敛等价要求 $P=\mathbb{N}$ 必须成立。

### 压缩映像

- $\mathrm{Theorem:Banach不动点定理}$

    考虑 $f:\mathbb{R}\rightarrow\mathbb{R}$，满足：$\exists\:0<q<1$，且有：

    $$
        \forall a,b\in\mathbb{R},\:|f(a)-f(b)|\leq q|a-b|,
    $$

    则有：

    $$
        \exists!\xi\in\mathbb{R},\:s.t.\xi=f(\xi)
    $$

    称 $\xi$ 为 $f(x)$ 的不动点。
- $\mathrm{Proof:}$

    任取 `$x_1\in\mathbb{R}$`, 令 `$x_{n+1}=f(x_n)$`，则有：

    $$
    \begin{aligned}
        |x_{n+1}-x_n|&=|f(x_n)-f(x_{n-1})|\\&<q|x_n-x_{n-1}|<\cdots<q^{n-1}|x_2-x_1|
    \end{aligned}
    $$

    因而有：

    $$
    \begin{aligned}
        &|x_{n+m}-x_n|
        \\&\leq|x_{n+m}-x_{n+m-1}|+|x_{n+m-1}-x_{n+m-2}|+\cdots+|x_{n+1}-x_{n}|
        \\&<q^{n-1}\left(\sum_{k=0}^{m-1}{q^k}\right)|x_2-x_1|
        \\&\leq q^n\frac{1}{1-q}|x_2-x_1|
    \end{aligned}
    $$

    当 $n$ 任意大的时候，上式可以任意小，因而 $x_n$ 为一 Cauchy 列，其有极限 $\xi$.
    进一步考虑 `$\lim_{n\rightarrow\infty}f(x_n)$`，有：

    $$
        |f(x_n)-f(\xi)|\leq q|x_n-\xi|<c\varepsilon
    $$

    因而极限成立。于是我们可以对递推公式两边取极限：

    $$
        \lim_{n\rightarrow\infty}x_{n+1}=\lim_{n\rightarrow\infty}f(x_n)\Rightarrow\xi=f(\xi)
    $$

    由此命题得证。

## 确界原理

- 确界的定义：
  - 给定非空数集 $S$，若存在实数 $\alpha$ 和 $\beta$ 分别满足：

    $$
    \begin{aligned}
        \forall x\in S&,\alpha\leq x\leq\beta
        \\\:\forall\varepsilon>0,\:\exists x_0,x_1\in S,&\:s.t. x_0<\alpha+\varepsilon,\:x_0>\beta-\varepsilon
    \end{aligned}
    $$

    则称 $\alpha$ 和 $\beta$ 分别为 $S$ 的下确界和上确界，记为 $\alpha=\inf{S}$，$\beta=\sup{S}$.
- $\mathrm{Theorem}:确界存在定理$

  - 非空有上界的数集必有上确界，非空有下界的集合必有下确界。
  - $\mathrm{Proof:}$

    以上确界为例，利用二分法构造闭区间套压低上界。取初始上界为 $b$,取 $a\in{S}$，二等分 $[a,b]$ 为 $[a,(a+b)/2]$ 和 $[(a+b)/2,b]$，若后者与 $S$ 交集非空则取后者为 `$[a_1,b_1]$`，否则取前者为 `$[a_1,b_1]$`，继续对 `$[a_1,b_1]$` 如此重复，可得系列闭区间套 `$[a_n,b_n]$`，其满足闭区间套定理的要求且保证 `$b_n$` 永远是 $S$ 的上界，`$a_n$` 永远属于 $S$。于是由闭区间套定理有：

    $$
        \exists\xi\:s.t.\lim_{n\rightarrow\infty}a_n=\lim_{n\rightarrow\infty}b_n=\xi
    $$

    这意味着对于 $\xi$，有 $\forall x\in S, x\leq\xi$；且有：

    $$
        \forall\varepsilon>0,\exists N\in\mathbb{N},\forall{n>N},\:\xi-a_n<\varepsilon,\:b_n-\xi<\varepsilon
    $$

    亦即：

    $$
        \forall\varepsilon>0,\exists N\in\mathbb{N},\forall{n>N},\:\xi-\varepsilon<a_n\in{S}
    $$

    这就满足了上确界的条件，因此 $\sup{S}=\xi$.
    下确界的证明类似；特别地，若一个数集 $A$ 没有上界，则 $\sup{A}=+\infty$；若其没有下界，则 $\inf{A}=-\infty$. 规定 $\sup{\varnothing}=-\infty$，$\inf{\varnothing}=+\infty$.

