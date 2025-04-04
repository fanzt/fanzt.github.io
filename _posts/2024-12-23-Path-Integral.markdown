---
layout:     post
title:      "Basic Conception of Path Integral"
subtitle:   "The review of Quantum Mechanics and the prepare for Quantum Field Theory."
date:       2024-12-23 19:10:00
author:     "fromuly"
header-img: "img/post-bg-2024-10.png"
catalog: true
usemathjax: true
music-id: 2629077702
tags:
    - Quantum Mechanics
---

> 存稿.

## 1 Propagator

首先我们来介绍传播子（Propagator）的概念。考虑一个态矢量的时间演化，我们显然有：

$$
    \begin{aligned}
        |\psi,t_0;t\rangle&=\hat{\mathscr{U}}|\psi,t_0\rangle
        \\&=\exp\left[\frac{-i\hat{H}(t-t_0)}{\hbar}\right]|\psi,t_0\rangle
        \\&=\sum_{a'}|a'\rangle\langle{a'}|\psi,t_0\rangle\exp\left[\frac{-iE_{a'}(t-t_0)}{\hbar}\right]
    \end{aligned}
$$

对态矢量左乘一个位置本征矢来获得该态在位置表象下的波函数，有：

$$
    \begin{aligned}
        \langle\mathbf{x}|\psi,t;t_0\rangle=\sum_{a'}\langle\mathbf{x}|a'\rangle\langle{a'}|\psi,t_0\rangle\exp\left[\frac{-iE_{a'}(t-t_0)}{\hbar}\right]
    \end{aligned}
$$

再在态矢量与能量本征态之间插入一个位置矢量的完备性关系，即可有：

$$
    \begin{aligned}
        \langle\mathbf{x}|\psi,t;t_0\rangle=\int{}d^3{x'}\sum_{a'}\langle\mathbf{x}|a'\rangle\langle{a'}|\mathbf{x'}\rangle\langle\mathbf{x'}|\psi,t_0\rangle\exp\left[\frac{-iE_{a'}(t-t_0)}{\hbar}\right]
    \end{aligned}
$$

于是我们可以显然的看到，上式形成了一个如下的形式：

$$
    \begin{aligned}
        \langle\mathbf{x}|\psi,t;t_0\rangle=\int{}d^3{x'}K(\mathbf{x},t;\mathbf{x'},t_0)\langle\mathbf{x'}|\psi,t_0\rangle
    \end{aligned}
$$

亦即：

$$
    \begin{aligned}
        \psi(\mathbf{x},t)=\int{}d^3{x'}K(\mathbf{x},t;\mathbf{x'},t_0)\psi(\mathbf{x'},t_0)
    \end{aligned}
$$

其中有：

$$
    \begin{aligned}
        K(\mathbf{x},t;\mathbf{x'},t_0)&=\sum_{a'}\langle\mathbf{x}|a'\rangle\langle{a'}|\mathbf{x'}\rangle\exp\left[\frac{-iE_{a'}(t-t_0)}{\hbar}\right]
        \\&=\langle{\mathbf{x}}|\exp\left[\frac{-iH(t-t_0)}{\hbar}\right]|\mathbf{x'}\rangle
    \end{aligned}
$$

称为传播子（Propagator）。
由上述推导，我们可以看到，传播子本质上是一个积分核，其通过对初态的波函数进行一个积分变换而得到了末态的波函数。如果对电动力学有一定的了解，我们可以看出传播子的功能类似于Schrodinger Equation的格林函数。事实上，我们的确有：

$$
        \left[-\frac{\hbar^2}{2m}\nabla^2+V(\mathbf{x})-i\hbar\frac{\partial}{\partial{t}}\right]K(\mathbf{x},t;\mathbf{x'},t_0)=-i\hbar\delta^3(\mathbf{x}-\mathbf{x'})\delta(t-t_0)
$$

考虑最简单的Hamiltonian为一维自由粒子的情况，有：

$$
    \begin{aligned}
        K(x,t;x',t_0)&=
        \int{}d{p'}\langle{x}|\exp\left[\frac{-iH(t-t_0)}{\hbar}\right]|p'\rangle\langle{p'}|x'\rangle
        \\&=\int{}d^3{p'}\exp\left[-\frac{ip'^{2}(t-t_0)}{2m\hbar}+\frac{ip'(x-x')}{\hbar}\right]
    \end{aligned}
$$

利用配方法转化为高斯积分，我们可以得到：

$$
        K(x,t;x',t_0)=\sqrt{\frac{m}{2\pi{i}\hbar(t-t_0)}}\exp\left[\frac{im(x-x')^2}{2\hbar(t-t_0)}\right]
$$

对于谐振子的传播子，在此不再展开，计划下一篇给出。

## 2 Transition Amplitude and the Sum over Paths

进一步考虑传播子的物理意义，我们显然有：

$$
    \begin{aligned}
        K(\mathbf{x},t;\mathbf{x'},t_0)&=\langle{\mathbf{x}}|\exp\left[\frac{-iH(t-t_0)}{\hbar}\right]|\mathbf{x'}\rangle
        \\&=\langle{\mathbf{x}}|\exp\left(\frac{-iHt}{\hbar}\right)\exp\left(\frac{iHt_0}{\hbar}\right)|\mathbf{x'}\rangle
        \\&=\langle\mathbf{x},t|\mathbf{x'},t_0\rangle
    \end{aligned}
$$

即传播子是从 `$t_0$` 时刻某一位置本征态变为 $t$ 时刻另一位置本征态的振幅，称作跃迁振幅（Transition Amplitude）。
考虑到任意时刻的所有位置本征态构成一组完备基矢，我们总有：

$$
        \langle\mathbf{x'''},t'''|\mathbf{x'},t'\rangle=\int{}d^3x''\langle\mathbf{x'''},t'''|\mathbf{x''},t''\rangle\langle\mathbf{x''},t''|\mathbf{x'},t'\rangle\qquad\qquad(t'''>t''>t')
$$

因此，我们显然可以像上式一样，无限地在两个态之间插入完备性关系，而这为量子力学的路径积分形式打下了基础。
不失一般性的，仍旧考虑一维问题。我们考虑一个粒子从初始的 `$(x_1,t_1)$` 状态演化到 `$(x_N,t_N)$` 状态的跃迁振幅。我们首先将 `$t_1$` 到 `$t_N$` 之间的事件分割为 `$N$` 等份，即有：

$$
        t_j-t_{j-1}=\Delta{t}=\frac{t_N-t_1}{N-1}
$$

通过往跃迁振幅中无穷无尽地插入完备性关系，我们有：

$$
    \begin{aligned}
        \langle{x_N,t_N}|{x_1,t_1}\rangle=&\int{}d{x_{N-1}}\int{}d{x_{N-2}}\cdots\int{}d{x_{2}}\langle{x_{N},t_{N}}|{x_{N-1},t_{N-1}}\rangle
        \\&\times\langle{x_{N-1},t_{N-1}}|{x_{N-2},t_{N-2}}\rangle\cdots\langle{x_{2},t_{2}}|{x_{1},t_{1}}\rangle
    \end{aligned}
$$

对每一个时刻的所有可能位置进行积分，即可以理解为对时间演化上每一条可能的路径的影响进行求和，因而上式的形式某种意义上解释了“路径积分”一词的来源。这样的理解将路径积分引导向了它的经典对应——Lagrange力学。

## 3 Feynman's Formulation and Path Integral

既然路径积分的经典对应是Lagrange力学，我们便先考虑一个作用量：

$$
        S(n,n-1)\equiv\int^{t_n}_{t_{n-1}}d{t}L_{classical}(x,\dot{x})
$$

考虑到经典的Lagrangian始终是 `$x$` 和 `$\dot{x}$` 的函数，上式定义的作用量仍旧需要依赖于某一特定路径才有意义。因此，我们将该作用量视为对于某一条路径进行积分得到的结果，即某一个 `$x(t)$` 的泛函。沿着该路径前进，我们遵循Dirac的提示（历史上Feynman也确实如此），考虑尝试建立 `$\exp[iS(n,n-1)/\hbar]$` 与跃迁振幅之间的对应关系：

$$
        \prod^{N}_{n=2}\exp\left[\frac{iS(n,n-1)}{\hbar}\right]=\exp\left[\frac{i}{\hbar}\sum^{N}_{n=2}S(n,n-1)\right]=\exp\left[\frac{iS(N,1)}{\hbar}\right]
$$

由于作用量是在选取路径后定义的，该式应当表征的是跃迁振幅中沿某一特定路径演化的贡献。而从“对每一条可能路径求和”的角度，我们或许可以写出：

$$
        \langle{x_N,t_N}|{x_1,t_1}\rangle\sim\sum_{all\:path}\exp\left[\frac{iS(N,1)}{\hbar}\right]
$$

进一步考虑更加精确的关系，我们应当有：

$$
        \langle{x_n,t_n}|{x_{n-1},t_{n-1}}\rangle=\frac{1}{w}\exp\left[\frac{iS(n,n-1)}{\hbar}\right]
$$

其中的系数 `$\displaystyle\frac{1}{w}$` 应当是一个具有 `$[\mathrm{L}^{-1}]$` 量纲（一维情况下）的系数，这一点可以通过位置本征态的正交关系即 `$\langle{x_n,t_n}|{x_{n-1},t_{n-1}}\rangle|_{t_n=t_{n-1}}=\delta(x_n-x_{n-1})$` 看出来。将作用量展开为Lagrangian的积分，我们有：

$$
    \begin{aligned}
        S(n,n-1)&=\int^{t_n}_{t_{n-1}}d{t}\left[\frac{m\dot{x}^2}{2}-V(x)\right]
        \\&=\Delta{t}\left\{\frac{m}{2}\left[\frac{(x_n-x_{n-1})}{\Delta{t}}\right]^2-V\left(\frac{x_n+x_{n-1}}{2}\right)\right\}
    \end{aligned}
$$

于是我们有：

$$
    \begin{aligned}
        \langle{x_n,t_n}|{x_{n-1},t_{n-1}}\rangle&=\frac{1}{w}\exp\left[\frac{iS(n,n-1)}{\hbar}\right]
        \\&=\frac{1}{w}\exp\left[\frac{im(x_n-x_{n-1})^2}{2\hbar\Delta{t}}-
        \frac{i\Delta{t}}{\hbar}\cdot{V}\left(\frac{x_n+x_{n-1}}{2}\right)\right]
    \end{aligned}
$$

考虑到：

$$
        \lim_{\Delta{t}\rightarrow{0}}\exp\left[\frac{im(x_n-x_{n-1})^2}{2\hbar\Delta{t}}-
        \frac{i\Delta{t}}{\hbar}\cdot{V}\left(\frac{x_n+x_{n-1}}{2}\right)\right]=\sqrt{\frac{2\pi{i}\hbar\Delta{t}}{m}}\delta(x_n-x_{n-1})
$$

以及：

$$
        \lim_{\Delta{t}\rightarrow{0}}\langle{x_n,t_n}|{x_{n-1},t_{n-1}}\rangle=\delta(x_n-x_{n-1})
$$

即可有：

$$
        \frac{1}{w}=\sqrt{\frac{m}{2\pi{i}\hbar\Delta{t}}}
$$

因而我们就有：

$$
        \langle{x_n,t_n}|{x_{n-1},t_{n-1}}\rangle=\sqrt{\frac{m}{2\pi{i}\hbar\Delta{t}}}\exp\left[\frac{iS(n,n-1)}{\hbar}\right]
$$

将其代回 `$\langle{x_N,t_N}|{x_1,t_1}\rangle$` 的表达式，即有：

$$
    \begin{aligned}
        \langle{x_N,t_N}|{x_1,t_1}\rangle=\lim_{N\rightarrow\infty}\left(\frac{m}{2\pi{i}\hbar\Delta{t}}\right)^{(N-1)/2}\int{}d{x_{N-1}}\int{}d{x_{N-2}}\cdots\int{}d{x_{2}}\prod_{n=2}^N\exp\left[\frac{iS(n,n-1)}{\hbar}\right]
    \end{aligned}
$$

定义泛函积分算子：

$$
        \int^{x_N}_{x_1}\mathscr{D}[x(t)]\equiv\lim_{N\rightarrow\infty}\left(\frac{m}{2\pi{i}\hbar\Delta{t}}\right)^{(N-1)/2}\int{}d{x_{N-1}}\int{}d{x_{N-2}}\cdots\int{}d{x_{2}}
$$

我们就有：

$$
        \langle{x_N,t_N}|{x_1,t_1}\rangle=
        \int^{x_N}_{x_1}\mathscr{D}[x(t)]\exp\left[i\int^{t_N}_{t_1}d{t}\frac{L_{classical}(x,\dot{x})}{\hbar}\right]
$$

该式即Feynman的 **路径积分（Path Integral）**。
通过将上式作泰勒展开，可以验证其满足Schrodinger方程。
