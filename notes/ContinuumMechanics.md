# 连续介质力学

## 质量守恒

既然物质是在空间中连续的，那么给定区域 $ V $，从边界进入的物质 = 空间内增加的物质，也就是
$$
\begin{eqnarray}
\int_{\partial V} \rho \vec v \cdot d \vec S 
&=& - \frac{d}{dt}\int_V \rho dV
\end{eqnarray}
$$

> Convention: $ d \vec S $ 是外法向

根据 Gauss 散度定理
$$
\int_{\partial V} \vec F \cdot d \vec S = \int_V (\nabla \cdot \vec F) dV
$$
所以
$$
\begin{eqnarray}
\int_V(\nabla \cdot (\rho \vec v)) dV
&=& - \frac{d}{dt}\int_V \rho dV \\
\nabla \cdot (\rho \vec v) &=&- \frac{d \rho}{dt}
\end{eqnarray}
$$
即
$$
\nabla \cdot (\rho \vec v) + \frac{d \rho}{dt} = 0
$$

## 连续介质的模型

一些假设：

- 牛顿运动定律
- 热力学第二定律
- 材料的连续性在力的作用下仍然保持连续
- 应力和应变在物体的每一部分均可确定
- 每一点的应力只与同一点的应变和该瞬时的应变率有关

> P15 冯元桢 在此定义下，外力及因外力而产生的反作用力一般会视为只作用在端点上，而且只会让元件产生[张力](https://zh.wikipedia.org/wiki/張力)及[压缩力](https://zh.wikipedia.org/w/index.php?title=壓縮力&action=edit&redlink=1)，若都是直杆元件，不考虑各元件所受到的[转矩](https://zh.wikipedia.org/wiki/轉矩)，因为桁架中所有元件的结构节点都是[旋转接点](https://zh.wikipedia.org/wiki/旋轉接點)。一元件受到的转矩无法传递到其他元件。

### Material Space 和 World Space

众所周知，物理变形（通常）会产生力，那为了描述“变形”，就需要“原来的形状”。

所以，一般用 $ X $ 表示在材料空间中的坐标，用 $ x $ 表示在世界空间中的坐标，并且有
$$
x = \Phi(X, t)
$$
成立。

#### Push forward 和 Pull back

Push forward 表示 $ G \to g $，pull back 表示 $ g \to G $。

**大写字母（如 $ V, A $）表示在材料空间的值，而小写字母代表在世界空间的值**，如下所示：
$$
V(X,t) =\frac{\partial \phi }{\partial t}(X,t) \\
A(X,t) =\frac{\partial V }{\partial t}(X,t)
$$
如果，在 $ (X, t) $ 的邻域有逆映射
$$
X = \Phi^{-1}(x, t)
$$
成立，那么就可以定义
$$
V(X, t) = V(\Phi^{-1}(x,t), t) \\
A(X, t) = A(\Phi^{-1}(x,t), t)
$$
这样的记法有什么好处呢？如果只使用 $ x= \Phi(X, t) $ 的话，我们有
$$
v_i(t) = \frac{\partial x_i}{\partial t} = \frac{\partial \Phi_i}{\partial X_j} \frac{\partial X_j}{\partial t} + \frac{\partial \Phi_i}{\partial t} \\
a_i(t) = \frac{\partial v_i}{\partial t} = \frac{\partial ^2\Phi_i}{\partial X_j \partial t} \frac{\partial X_j}{\partial t} + \frac{\partial \Phi_i}{\partial X_j} \frac{\partial^2 X_j}{\partial t^2} + \frac{\partial ^2 \Phi_i}{\partial t^2} \\
$$
$ a_i(t) $ 的式子会显得比较复杂。但是如果使用 $ A(X, t) $ 进行 Push forward 的话，就可以得到
$$
\begin{eqnarray}
a(x, t) &=& A(\Phi^{-1}(x, t), t) = \frac{\partial V_i(\Phi^{-1}(x, t) ,t)}{\partial t} \\
&=& a(\Phi(\Phi^{-1}(x, t),t),t) = TODO
\end{eqnarray}
$$

> 事实上，TODO