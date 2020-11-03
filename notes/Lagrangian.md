# 拉格朗日视角

本笔记包含第二讲和第三讲的笔记内容。

> Ref:
>
> 1. GAMES-201 讲义
> 2. [Smoothed Particle Hydrodynamics](https://arxiv.org/pdf/1007.1245.pdf) (arXiv 1007.1245)

## SPH 方法

SPH (Smoothed Particle Hydrodynamics) 法的大致想法是用粒子来保存物理量在某点的采样，同时用一个核函数 $ W $ 来近似连续场。

### 连续场的离散近似

对于 $ f: R^3 \to R $ 来说，显然有如下关系成立：
$$
f(r) = \int_V f({\bf r′}) δ({\bf r − r′}) dr′
$$

> Note: 这里 Dirac 函数定义在 $ R^3 $

现在我们需要一个带参数 $ h $ 的核函数 $ W $，满足
$$
\lim_{h \to 0} W({\bf r}, h) = \delta ({\bf r})
$$
同时满足归一化条件
$$
\int_V W({\bf r}, h) d{\bf r'} = 1
$$
考虑 $ W $ 的泰勒展开
$$
\begin{eqnarray}
W({\bf r}, h) &=& W({\bf r}, 0) + W'({\bf r}, 0)h + O(h^2) \\
&=& \delta({\bf r}) + W'({\bf r}, 0)h + O(h^2)
\end{eqnarray}
$$
如果 $ W $ 关于 $ \bf r $ 对称的话，$ W' $ 项为 0，则有下式成立
$$
f(r) = \int_V f(r′) W(r − r′, h) dr′ + O(h^2)
$$

> 其实可以把 W 展开到更高阶，这样精度会更高，但是根据 Ref 2 中的提法，某些时候会有病态条件

对任何有限的密度 $ \rho(r) $ 有下式成立
$$
f(r) = \int_V \frac{f(r′)}{\rho(r')} W(r − r′, h) \rho(r') dr′ + O(h^2)
$$
将上述连续场离散到一系列质量 $ m = \rho(r') dr' $ 的粒子中（$ i$ 是粒子的下标）
$$
f(r) \approx \sum_i \frac{m_i}{\rho_i} f(r_i) W(r-r_i, h)
$$

> 这里可以注意到，$ f(r) $ 中 $ r $ 的取值可以是任意的，而并不一定非得在粒子的位置

### 空间导数近似

为了让 SPH 可以应用于流体问题，下面推导一下物理量关于空间的导数。

#### 标量导数

$$
\nabla f({\bf r}) \approx \sum_i \frac{m_i}{\rho_i} f({\bf r_i}) \nabla W({\bf r}-{\bf r_i}, h)
$$

#### 散度

对于矢量场 $ \mathbf{F(r)} $ 来说，仍然有此等式成立
$$
{\bf F}({\bf r}) = \int_V F({\bf r′}) δ({\bf r − r′}) dr′
$$
类似上文推导，左右取散度
$$
\nabla \cdot {\bf F}({\bf r}) \approx \sum_i \frac{m_i}{\rho_i} {\bf F}({\bf r_i})  \cdot \nabla W({\bf r}-{\bf r_i}, h)
$$

#### 旋度

$$
\nabla \times {\bf F}({\bf r}) \approx \sum_i \frac{m_i}{\rho_i} {\bf F}({\bf r_i})  \times \nabla W({\bf r}-{\bf r_i}, h)
$$

### 误差分析

误差主要有两个来源：

1. $ W(r, h) $ 与 Dirac 函数的区别（$ O(h^2) $）
2. 体积分变成离散点求和的离散误差（a.k.a. 采样误差）

事实上，考虑 $ f({\bf r}) \equiv 1 $ 的常值场，SPH 近似也不能给出精确解

（TODO 抄上去）



### 改进的空间导数近似

用恒等式 $ \nabla (f \rho^n) \equiv nf \rho ^{n-1} \nabla \rho + \rho^n \nabla f $，得到



### 改进的散度近似



### 核函数 W

综上，核函数应该满足如下条件：

1. 空间对称（偶函数）
2. $ h \to 0 $ 时趋近于 Dirac 函数
3. 有一阶导数

常见的核函数有如下几种：
$$
W(r, h) = \frac{1}{h^3\pi^{3/2}}e^{-x^2} \text{(高斯核)}
$$
缺点是全空间都有值，这样求一次 $ f(r) $ 需要 $ O(N^2) $ 的复杂度.
$$
W(r, h) = asdf
$$


### 流体模拟

首先，根据连续性方程
$$
\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho {\bf v}) = 0
$$
对于无黏性流体，根据动量守恒可以得到
$$

$$