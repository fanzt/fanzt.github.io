---
layout:     post
title:      "Spontaneous Symmetry Breaking and CCWZ Construction 1"
subtitle:   "A Useful Method to construct EFT."
date:       2025-3-22 13:30:00
author:     "fromuly"
header-img: "img/post-bg-2025-8.jpg"
catalog: true
usemathjax: true
music-id: 850775
tags:
    - Physics
    - Quantum Field Theory
---

## Review: Spontaneous Symmetry Breaking and Goldstone Theorem

> 文章主要参考了 https://arxiv.org/abs/2110.14504.

### Symmetry in Classical and Quantum

作为一个回顾，我们首先给出一般的自发对称性破缺的概念，以及 Goldstone 定理的证明。

一个物理系统的“对称性”被描述为该系统的运动方程在某种特定的变换下不发生改变的性质。如果一个物理系统可以被作用量体系描述，则我们所谈论的“对称性”可以被量化地表述为：

$$
    S\left[\phi\right]\rightarrow S\left[\phi^\prime\right]=S\left[\phi\right]
$$

相同的作用量显然会给出相同的运动方程，因此上式符合我们对“对称性”的定义。对于谈论对称性的绝大多数情况，我们所考虑的变换有显然的幺元，并且往往是可逆的，这表明它们一般构成了一个群。特别地，我们专注于这种变换是连续的情况。在这种情况下，我们总能将变换如下地参数化为：

$$
    \begin{cases}
        \phantom{\phi^i(}x^{\mu} &\rightarrow \; x'^{\mu}=x^{\mu}+ \alpha^a \, \xi_a^\mu(x) \ , \\
        \phi^i(x) & \rightarrow \; \phi'^{i}(x)=\phi^i(x) + \alpha^a \, \delta_a\phi^i(x) \ .
    \end{cases}
$$

容易见到，我们考虑的变换一般被分为两部分，一部分是对时空坐标的变换，另一部分是对场的变换。

基于此，我们可以定义出变换的生成元 $T_a$：

$$
    T_a\phi^i(x)=\delta_a\phi^i(x)
$$

由 Noether 定理，我们可以给出守恒流的表达式：

$$
    j^\nu_a=\frac{\partial \mathscr{L}}{\partial(\partial_\nu \phi^i)}\delta_a\phi^i-{K^\nu_a}
$$

其中 $K^\nu_a$ 如下定义：

$$
    \delta_a\mathscr{L}=\partial_\mu K^\mu_a\:.
$$

并且我们可以进一步地给出守恒荷的表达式：

$$
    Q_a\equiv\int\:\mathrm{d}^{d-1}j_a^0(x)\ .
$$

以上的讨论仍旧属于经典场论范围。量子力学告诉我们系统的状态是 Hilbert 空间中的射线。因此我们需要考虑上述变换作用在态矢量上的效果，Wigner 定理告诉我们其必然是一个线性幺正算符或者反线性反幺正算符。基于常见于教科书的证明[^1]，我们知道上述讨论中定义出的守恒荷恰好就是这样算符的生成元，即态矢量的变换总可以表示为：

$$
    |\psi\rangle\rightarrow|\psi^\prime\rangle=\mathrm{e}^{\mathrm{i}\alpha^a Q_a}|\psi\rangle
$$

其中 $Q_a$ 总是厄米算符。从量子力学的角度，对称性被表述为：

$$
    \langle\psi|A|\psi\rangle=\langle\psi^\prime|A^\prime|\psi^\prime\rangle
$$

于是容易见到算符的变换是一个伴随操作：

$$
    A\rightarrow A^\prime = \mathrm{e}^{\mathrm{i}\alpha^a Q_a}A\mathrm{e}^{-\mathrm{i}\alpha^a Q_a}
$$

同样基于常见的教科书证明[^1]，我们知道守恒荷和场算符的对易子给出场的变换：

$$
    [\mathrm{i}Q_a,\phi^i]=T_a\phi^i\ .
$$

### Spontaneous Symmetry Breaking and Goldstone Theorem

接下来我们将考虑所谓的对称性破缺。对称性的破缺一般被分为明显对称性破缺（Explicit Symmetry Breaking, ESB）和自发对称性破缺（Spontaneous Symmetry Breaking, SSB）两种。ESB 指的是通过手动在 Lagrangian 中添入显然破坏原本对称性的项，使得 Lagrangian 本身就已经发生了对称性破坏。而 SSB 则指的是 Lagrangian 本身仍旧保持原有的对称性，而实际的物理基态却失去了对称性的情况。我们主要将关注点放在 SSB 上，利用态矢量的变换，我们将其描述为[^2]：

$$
    \mathrm{e}^{\mathrm{i}\alpha^a Q_a}|0\rangle\neq|0\rangle\Rightarrow Q_a|0\rangle\neq 0
$$

或者等价地：

$$
    -T_a\langle\phi^i\rangle=\langle0|[Q_a,\phi^i]|0\rangle\neq 0
$$

基于此，我们定义 $\langle\phi^i\rangle$ ，即场的真空期望值（Vacuum Expectation Value, VEV）为 **序参量（Order Parameter）** ，用于描述系统是否发生 SSB. 如果物理系统存在 SSB，则 $\langle\phi^i\rangle\neq0$.

基于以上讨论，我们便可以开始证明所谓的 Goldstone 定理。

**Goldstone Theorem:**

考虑一个具有全局连续对称群 $G$ 所描述的对称性的量子理论，其自发破缺到了 $G$ 的一个子群 $H$，那么该理论中至少会包含一个没有能隙的激发态，也就是一个无质量的粒子。

**Proof:**

我们给出一个基于 Kallen-Lehmann 谱表示的证明。

考虑序参量的表达式，在其中插入完备态，我们有：

$$
\begin{aligned}
    \langle{0}|[Q,\Phi(x)]|{0}\rangle&=\int d^{d-1}x' \langle{0}|[j^0(x'),\Phi(x)]|{0}\rangle \ , \\
    &=\int d^{d-1}x' \sum\limits_{n}\int \frac{d^{d-1}k}{(2\pi)^{d-1}}\left(\langle{0}|j^0(x')|{n_{\vec{k}}}\rangle\langle{n_{\vec{k}}}|\Phi(x)|{0}\rangle\right. \\
    & \phantom{=\int d^{d-1}x' \sum\limits_{n}\int \frac{d^{d-1}k}{(2\pi)^{3}}}\left. -\langle{0}|\Phi(x)|{n_{-\vec{k}}}\rangle\langle{n_{-\vec{k}}}|j^0(x')|{0}\rangle \right) \ . \\
\end{aligned}
$$

将守恒流对坐标的依赖用平移变换分离出来，我们有：

$$
\begin{aligned}
    \langle{0}|[Q,\Phi(x)]|{0}\rangle&=\int d^{d-1}x' \sum\limits_{n}\int \frac{d^{d-1}k}{(2\pi)^{d-1}} \, e^{-i k_{\mu} x'^{\mu}}\left(\langle{0}|j^0(0)|{n_{\vec{k}}}\rangle\langle{n_{\vec{k}}}|\Phi(x)|{0}\rangle\right. \\
    & \phantom{=\int d^{d-1}x' \sum\limits_{n}\int \frac{d^{d-1}k}{(2\pi)^{d-1}}}\left. -\langle{0}|\Phi(x)|{n_{-\vec{k}}}\rangle\langle{n_{-\vec{k}}}|j^0(0)|{0}\rangle \right)  \ ,\\
    &= \sum\limits_{n}\int d^{d-1}k \, e^{-i E_n(\vec{k}) t^\prime}\,\delta^3(\vec{k})\left(\langle{0}|j^0(0)|{n_{\vec{k}}}\rangle\langle{n_{\vec{k}}}|\Phi(x)|{0}\rangle\right. \\
    & \phantom{=\int d^{d-1}x' \sum\limits_{n}\int \frac{d^{d-1}k}{(2\pi)^{3}}}\left. -\langle{0}|\Phi(x)|{n_{-\vec{k}}}\rangle\langle{n_{-\vec{k}}}|j^0(0)|{0}\rangle \right)  \ ,\\
\end{aligned}
$$

注意到荷本身不依赖于时间参量 $t^\prime$，这意味着上式想要成立，积掉动量后的 $E(0)=0$ 必须为零。而我们知道 $E(0)$ 实际上正代表了中间态 `$|{n_{\vec{k}}}\rangle$` 的质量，这表明激发态 `$|{n_{\vec{k}}}\rangle$` 必然描述了一个无能隙（即无质量）的粒子，称为 Nambu-Goldstone（NG） 粒子。

该证明无法给出这样的 NG 粒子的种类数。一些其他的证明[^3]可以给出明确的种类数（例如使用有效作用量的证明），但这一般要求对称群 $G$ 描述的是体系的内部对称性。我们不会使用这些证明，但我们会在接下来给出一个包括时空对称性的讨论，更加全面地给出对 NG 粒子的计数方法。

接下来我们要对 NG 粒子的物理意义作一些讨论。回想我们对自发对称性破缺存在的基本要求是真空态在对称变换下不会回到原本的真空态。但我们可以看到，变化后的真空态理论上还会是系统的基态，因为我们的 Lagrangian 是具有对称性的，因而相互作用项以及有效势都是具有相应的对称性的，因此原本的对称变换不会改变体系的能量。这意味着我们有着可以用对称变换标记的，至少多于一个的真空态，即**简并真空**。由于我们的对称变换是连续的，这些简并真空便都可以被一个连续的变换联系在一起，也就是说它们之间不会有能隙或势阱。于是，一个沿着简并真空方向的微小涨落变化到二阶项为止都不会提供势能的变化，因而这些涨落态都是无质量的，而它们正是我们所需要的 NG 粒子。一方面，这可以从谱分解的讨论中看出，我们在 K-L 谱表示的证明中所计算的那个量不等于零正说明了中间态 `$|{n_{\vec{k}}}\rangle$` 在由守恒荷（守恒流）激发出的态 `$\langle{0}|j^0(x)$` 上有非零的投影，这表示其正是由破缺的对称变化生成的真空扰动产生的态；另一方面这一点也可以从一些具体模型中看出：我们最常见的标量场引发 $\mathrm{U}(1)$ 对称性破缺总会在最终将标量场写为：

$$
    \phi(x)=\frac{v+h(x)}{\sqrt{2}}\mathrm{e}^{\mathrm{i}\pi(x)/v}
$$

其中 $\pi(x)$ 恰好会在 Lagrangian 中充当无质量的 Goldstone 粒子。实际上，如果我们考虑 $\phi(x)$ 处于基态，那么就可以更加显然地看到，$\pi(x)$ 也正好参数化了标量场真空期望值的扰动变化。

### Spontaneous Spacetime Symmetry Breaking and the Counting of Nambu-Goldstone Particle[^4]

接下来，我们考虑如何计数独立的 NG 粒子态。特别地，本节的方法会一并展示内部对称性和时空对称性破缺的 NG 粒子计数方法，并展示出它们的区别。

我们在接下来的所有内容中用 `$T_A$` 表示原始对称群 $G$ 的生成元，用 `$T_\alpha$` 表示未破缺的子群 $H$ 的生成元，用 `$T_a$` 表示破缺的陪集 $G/H$ 的生成元。

考察序参量的小振幅长波扰动：

$$
    \delta\phi(\vec{r})=c_A(\vec{r})T^A\langle\phi(\vec{r})\rangle=c_a(\vec{r})T^a\langle\phi(\vec{r})\rangle
$$

基于上一节的论述，我们知道每一个独立的 `$c_a(\vec{r})$` 代表了一个独立的 NG 粒子模式。直观来看，`$T_a$` 作为李代数 $\mathfrak{g}$ 一组独立基矢的一个子集，显然应该是互相独立的，因此我们应当自然地有每一个独立的破缺对称性 $T^a$ 都对应于一个独立的 `$c_a$`，于是我们有对每一个独立破缺的对称性，都会生成一个 NG 模式。这正是一般的教科书推导会给出的 Goldstone 定理的结论。

然而，这一结论并不严谨，至少其不适用于时空对称性的自发破缺。这是因为，`$c_a(\vec{r})$` 是一个与未破缺平移对称性的剩余维度中的位矢 $r$ 相关的参数[^5]，这使得如果某些生成元之间产生了相互抵消，即下述方程如果有 $n$ 个非平凡解：

$$
    c_a(\vec{r})T^a\langle\phi(\vec{r})\rangle=0
$$

那么独立的 NG 模式的个数就不会是 $|a|=\mathrm{dim}(G/H)$ 个，而是 $\mathrm{dim}(G/H)-n$ 个。

为了看到这一点，考虑在该方程的左右两边作用未破缺平移生成元 $P_\mu$：

$$
\begin{aligned}
    0&=P_\mu c_a(\vec{r})T^a\langle\phi(\vec{r})\rangle
    \\&=c_a(\vec{r}) \left[P_\mu,T^a\right] \langle\phi(\vec{r})\rangle
    \\&=-i\left(\partial_\mu c_a(\vec{r})T^a-{f^{\mu a}}_bc_a(\vec{r})T^b\right)\langle\phi(\vec{r})\rangle
\end{aligned}
$$

其中我们假设了破缺生成元与 $P_\mu$ 的对易关系：

$$
    [P_\mu,T^a]=i{f^{\mu a}}_b T^b+i{f^{\mu a}}_\beta T^\beta
$$

并利用了未破缺群 $H$ 的生成元对序参量作用为零的性质。

对于内部对称性，基于定义其生成元必须与时空对称性的生成元对易，因而方程中的第二项直接消失，我们仅能从上述方程中获知 `$c_a(\vec{r})$` 是一个不依赖于坐标的常数，而这意味着一开始的方程仅能有所有系数均为零的平凡解，这也印证了其余常见证明中内部对称性破缺生成的独立 NG 模式数量恰好等于破缺对称性生成元数量（即 $\mathrm{dim}(G/H)$）的结论。

而对于时空对称性，其生成元完全可以与 `$P_\mu$` 不对易。而这就意味着，我们可以给出：

$$
    \left(\partial_\mu c_a(\vec{r})-{f^{\mu b}}_ac_b(\vec{r})\right)T^a\langle\phi(\vec{r})\rangle=0
$$

也就是说，$T^a$ 生成的 NG 模式 $c_a$ 的导数与 $T^b$ 生成的 NG 模式 $c_b$ 线性相关，二者并不独立。而每一个这样的不独立都为一开始的方程贡献了一个非平凡的解，因而就要扣除掉一个 NG 模式数量。于是我们自然得到独立的 NG 模式只能有 $\mathrm{dim}(G/H)-n$ 个。

----

[^1]: *The Quantum Theory of Fields, Vol.I, Chapter 7*, Steven Weinberg
[^2]: 注意，下式的 `$Q_a|0\rangle$` 在无限大的空间中其实不是良定义的量，但我们可以通过先在有限体积中处理问题将其绕过去。
[^3]: *The Quantum Theory of Fields, Vol.II, Chapter 19*, Steven Weinberg
[^4]: Ian Low and Aneesh V. Manohar. Spontaneously broken spacetime symmetries and goldstone’s theorem. *Physical Review Letters*, 88(10), February 2002.
[^5]: 这是因为 NG 模式必须依赖于其动量 $\vec{k}$（因为其没有能隙，所有耦合都必须直接与 $k$ 相关，或者说在 Lagrangian 中以导数耦合呈现），而动量只能在没有破缺平移对称性的空间中定义。
