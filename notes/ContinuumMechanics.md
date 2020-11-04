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

 

