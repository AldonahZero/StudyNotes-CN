# 楔子

## 前言——破执

:::::::::::::: {.columns}
::: {.column width="35%"}
一切有为法，

如梦幻泡影，

如露亦如电，

应作如是观。

--《金刚经》
:::
::: {.column width="65%"}

* 独立于算法的机器学习[^Duda,2003] P365
* 没有免费午餐定理
  * 没有最好的学习算法
* 丑小鸭定理
  * 没有最好的特征描述算法
:::
::::::::::::::

::: notes
《金刚经》：谈空，破有。防止迷失在算法的细节中。
:::

## 前言——破空

:::::::::::::: {.columns}
::: {.column width="35%"}
身是菩提树，

心如明镜台，

时时勤拂拭，

勿使惹尘埃。

--《六祖坛经》
:::
::: {.column width="65%"}

* 1000小时定律
  * 每天4个小时，一年可以入门
* 10000小时定律
  * 每天8个小时，五年成为专家
* 理论与实践相结合
  * 理论告诉你原因，帮助你选择
  * 实践告诉你感受，帮助你记忆
  * 理论结合实践，才能把算法应用到合适的地方
:::
::::::::::::::

::: notes
《六祖坛经》：谈有，破空。防止学习只知其然不知其所以然。
:::

## 前言——三观

* 人生观 ：“机器学习”会带来什么？
  * 对于你的意义，你的原始驱动力
* 世界观 ：“机器学习”会改变什么？
  * 能够产生的作用，算法的适用性
* 价值观 ：“机器学习”的评价体系？
  * 你如何选择最有价值的算法去学习和使用

## 前言——方法论

* 学习方法：
  * 先泛读了解机器学习的轮廓
  * 再精读感兴趣的内容
  * 最后总结成自己的体系
* 实践方法
  * 先跟随经典的项目流程
  * 再尝试自己的兴趣方向
  * 最后总结出自己的代码库

# 基本概念

## 机器学习

* 有监督学习（输入数据 + 目标数据）
  * 回归问题（连续输入 + 连续目标）
  * 分类问题（连续输入 + 离散目标）
  * 分类问题（离散输入 + 离散目标）
  * 特征问题
* 无监督学习（输入数据）
  * 聚类问题（连续输入 + 离散输出）
  * 降维问题（高维输入 + 低维输出）

## 线性代数

* 线性方程组
  * 欠定问题：数据少于参数个数，无数解
  * 正定问题：数据等于参数个数，可能 惟一解
  * 超定问题：数据多于参数个数，可能 没有解
    * 需要增加限制条件，转化为最优化问题

## 概率统计——概率

* 似然函数[^Morris,2007] P235
  * 将观测数据的联合概率密度函数或者联合概率分布函数表示为参数的函数。
  * 例如：观测数据 $X,\mathbf{y}$ 已知，参数 $\mathbf{w}$ 未知，函数为 $p(\mathbf{y}|X,\mathbf{w})$
* 先验分布
  * 在得到观测数据之前参数的分布
  * 例如： $p(\mathbf{w}|\alpha,\beta)$
* 后验分布
  * 在给定观测数据之后参数的分布
  * 例如： $p(\mathbf{w}|X,\mathbf{y})\propto p(\mathbf{y}|X,\mathbf{w})p(\mathbf{w}|\alpha,\beta)$

## 概率统计——估计

* 最大似然估计器
  * 基于频率统计估计理论
  * 不基于先验分布和损失函数，而是基于数据集构造的似然函数最大来估计参数 θ
  * 参数 θ 是 未知的、定常的、没有任何先验信息的
* 最大后验估计器
  * 基于贝叶斯估计理论
  * 基于先验分布和损失函数，使后验概率最大来估计参数 θ。
  * 当先验假设为均匀分布时，最大后验估计 与 最大似然估计 等价
  * 参数 θ 是 未知的、随机的（基于某个概率分布的，与似然函数共轭分布，方便计算）

## 符号表

* 向量： $\mathbf{x}=(x_1,x_2,\cdots,x_D)^T$
  * $D$维特征 $\mathbf{x}_n$
  * 增广向量 $\dot{\mathbf{x}}_n = (1,\mathbf{x}_n^T)^T$
* 实数集： $\mathcal{R}$
* 高斯分布： $\mathcal{N}(\mu,\sigma^2)$
  * 均值为 *μ*，方差为 *σ*^2^
* 梯度算子： $\nabla_{\mathbf{w}} J(\mathbf{w}) = [\frac\partial{\partial w_0}J(\mathbf{w}),\frac\partial{\partial w_1}J(\mathbf{w}),\cdots,\frac\partial{\partial w_D}J(\mathbf{w})]^T$
