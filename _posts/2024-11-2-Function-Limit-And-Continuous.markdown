---
layout:     post
title:      "Function Limit and Continuous"
subtitle:   "The Review of Mathematical Analysis, Second Part."
date:       2024-10-24 12:10:00
author:     "fromuly"
header-img: "img/post-bg-2024-8.png"
catalog: true
usemathjax: true
music-id: 1972641406
tags:
    - Mathematical Analysis
---

## 函数的极限

六种趋近，四类结果。

- `$\lim_{x\rightarrow+\infty}f(x)=A\in\mathbb{R}\quad(D_f=[a,+\infty))$`

    $$
        \forall{\varepsilon>0},\exists N,\forall x>N, |f(x)-A|<\varepsilon
    $$

- `$\lim_{x\rightarrow-\infty}f(x)=A\in\mathbb{R}\quad(D_f=(-\infty,a])$`

    $$
        \forall{\varepsilon>0},\exists N,\forall x<-N, |f(x)-A|<\varepsilon
    $$

- `$\lim_{x\rightarrow\infty}f(x)=A\in\mathbb{R}\quad(D_f=(-\infty,b]\cup[a,+\infty))$`

    $$
        \forall{\varepsilon>0},\exists N,\forall |x|>N, |f(x)-A|<\varepsilon
    $$

- `$\lim_{x\rightarrow x_0}f(x)=A\in\mathbb{R}\quad(D_f=(x_0-\delta,x_0)\cup(x_0,x_0+\delta))$`

    $$
        \forall{\varepsilon>0},\exists\delta>0,\forall 0<|x-x_0|<\delta, |f(x)-A|<\varepsilon
    $$

- 特殊发散： $\varepsilon\rightarrow M$，`$|f(x)-A|<\varepsilon\rightarrow f(x)>M/f(x)<-M$`

*注意：函数极限的复合要求被复合函数必须从去心邻域映射到去心邻域，又或者复合函数在中心点连续。*

## Heine 定理

$\mathrm{Theorem}:\lim_{x\rightarrow x_0}f(x)=A\iff\forall x_n\rightarrow x_0,\lim_{n\rightarrow\infty}f(x_n)=A.$
$\mathrm{Proof}:$
懒得写了。
充分性主要思想在于取数列的 $\varepsilon$ 为函数的 $\delta.$
必要性使用反证法，选取一系列 `$\delta_k$` 不断压缩区间，使得一系列被压缩区间中的 `$x_k$` 构成 `$f(x_k)$` 不趋近于 $f(x)$ 的数列，与题设矛盾。

常见应用：从数列极限求函数极限；证明其余定理。

## Cauchy 收敛准则

`$\mathrm{Theorem}:\lim_{x\rightarrow x_0}收敛\iff\forall\varepsilon>0,\exists\delta>0,\forall{x_1,x_2}\in\mathring{O}(x_0,\delta),|f(x_1)-f(x_2)|<\varepsilon$`.
$\mathrm{Proof}:$
利用 Heine 定理。核心思想仍旧在于将数列极限的 $\varepsilon$ 作为函数极限的 $\delta$ 使用。

## 单调收敛定理

$\mathrm{Theorem}:若f(x)在(x_0,x_0+\delta)中单调有界，则\lim_{x\rightarrow x_0^+}f(x)收敛.$
$类似地，若f(x)在(x_0-\delta,x_0)中单调有界，则\lim_{x\rightarrow x_0^-}f(x)收敛.$
$\mathrm{Proof:}$
此处数列的单调收敛定理联合 Heine 定理仅能给出单调趋近 `$x_0$` 的数列 `$x_n$` 保证 `$f(x_n)$` 收敛。因此我们选定一个单调数列，利用该数列将所有去心邻域中的点夹在数列两项之间，再利用迫敛性给出极限。

## 函数的连续性

`$\mathrm{Definition:}\lim_{x\rightarrow x_0}f(x)=f(x_0)\iff f(x) 连续$`

连续函数的四则运算均连续。连续函数的点点复合运算均连续。
基本初等函数：常指幂对反三

### 间断点

第一类：可去/跳跃
第二类：无穷/振荡
