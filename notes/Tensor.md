# 张量和矢量

> Ref:
>
> 1. [张量分析初步和矢量恒等式 - CSDN](https://blog.csdn.net/qq_23997101/article/details/78181074)
> 2. [电动力学 em02 - 杨焕雄](http://staff.ustc.edu.cn/~hyang/em/em02.pdf)

## 张量

$ m $ 维 $ n $ 阶张量：一个有 $ n $ 个自由下标，每个下标可以取从 1 到 m 的整数的多维数组

> 用张量是否隐含着标准正交基？
>
> 看 [这里](http://staff.ustc.edu.cn/~xtao/courses/ce/downloads/ddlx_1.pdf) 的时候里面的张量都是定义在 $ e_i, e_j, e_k $ 上面的 “高阶矢量”
>
> （高阶：$ e_i $ 一阶，$ e_i e_j $ 二阶，$ e_i e_j e_k $ 三阶..） 

#### 基本记号

- (Kronecker) $ \delta_{ij} $，仅当 $ i = j $ 时取值为 1，否则为 0
- (置换符号) $ \epsilon_{ijk} $ 的下标偶排列为 1，奇排列 -1，重复为 0



#### 常用关系


$$
\delta_{ij} \delta_{mj} = \delta_{im} \\

\epsilon_{i j k}= \sum_{i, j, k} \epsilon_{ijk} \delta_{i1} \delta_{j2} 
$$

$$
\epsilon_{ijk} \epsilon_{mnk} = \epsilon_{kij} \epsilon_{kmn} = \delta_{im} \delta_{jn} - \delta_{in} \delta_{jm}
$$

> 证明：
>
> 根据行列式的定义有
> $$
> \left|\begin{array}{lll}
> a_{11} & a_{12} & a_{13} \\
> a_{21} & a_{22} & a_{23} \\
> a_{31} & a_{32} & a_{33}
> \end{array}\right|=e_{i j k} a_{i 1} a_{j 2} a_{k 3}=e_{i j k} a_{1 i} a_{2 j} a_{3 k}
> $$
> 列换序有
> $$
> \left|\begin{array}{lll}
> a_{1 r} & a_{1 s} & a_{1 t} \\
> a_{2 r} & a_{2 s} & a_{2 t} \\
> a_{3 r} & a_{3 s} & a_{3 t}
> \end{array}\right|=e_{r s t} e_{i j k} a_{i 1} a_{j 2} a_{k 3}
> $$
> 行换序有
> $$
> \left|\begin{array}{lll}
> a_{o r} & a_{o s} & a_{o t} \\
> a_{p r} & a_{p s} & a_{p t} \\
> a_{q r} & a_{q s} & a_{q t}
> \end{array}\right|=e_{o p q} e_{r s t} e_{i j k} a_{i 1} a_{j 2} a_{k 3}
> $$
> 所以
> $$
> \left|\begin{array}{lll}
> \delta_{o r} & \delta_{o s} & \delta_{o t} \\
> \delta_{p r} & \delta_{p s} & \delta_{p t} \\
> \delta_{q r} & \delta_{q s} & \delta_{q t}
> \end{array}\right|=e_{o p q} e_{r s t} e_{i j k} \delta_{i 1} \delta_{j 2} \delta_{k 3}=e_{o p q} e_{r s t} e_{123}=e_{o p q} e_{r s t}
> $$
> 取 $ o = r $ 得到
> $$
> \begin{eqnarray}
> 
> e_{rpq}e_{rst} &=&
> \left|
> \begin{array}{lll}
> 3 & \delta_{rs} & \delta_{rt} \\
> \delta_{pr} & \delta_{ps} & \delta_{pt} \\
> \delta_{qr} & \delta_{qs} & \delta_{qt}
> \end{array}
> \right|
> \\ &=& 3(\delta_{ps} \delta_{qt} - \delta_{qs} \delta_{pt}) - (
> \delta_{rs}
> \left|
> \begin{array}{ll}
> \delta_{pr} & \delta_{pt} \\
> \delta_{qr} & \delta_{qt} \\
> \end{array}
> \right|
> 
> ) + (
> \delta_{rt}
> \left|
> \begin{array}{ll}
> \delta_{pr} & \delta_{ps} \\
> \delta_{qr} & \delta_{qs} \\
> \end{array}
> \right|
> ) \\
> 
> &=& 3(\delta_{ps} \delta_{qt} - \delta_{pt} \delta_{qs}) - (\delta_{pr} \delta_{rs} \delta_{qt} - \delta_{qr} \delta_{rs} \delta_{pt}) + (\delta_{pr} \delta_{rt} \delta_{qs} - \delta_{qr} \delta_{rt} \delta_{ps}) \\
> &=& 3(\delta_{ps} \delta_{qt} - \delta_{pt} \delta_{qs}) - (\delta_{ps} \delta_{qt} - \delta_{qs} \delta_{pt}) + (\delta_{pt} \delta_{qs} - \delta_{qt} \delta_{ps}) \\
> &=& \delta_{qt} \delta_{ps} - \delta_{pt} \delta_{qs} \\
> \end{eqnarray}
> $$

$$
\epsilon_{ijk} \epsilon_{ijk} = 6
$$

> 证明：上面证明取 $ o = r, p = s, q = t $ 得到
>
> 

## 矢量分析

