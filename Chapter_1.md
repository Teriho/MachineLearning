

# 第一章 绪论

### 1.1 引言

> 机器学习致力于研究如何通过计算的手段，利用经验来改善系统自身的性能。

### 1.2 基本术语

>   D = {x~1~,x~2~,...,x~m~} 

- D 表示包含 m 个 instance 的 data set
- 每个 instance 是由 d 个 attribute 描述，则  
>   x~i~ = (x~i1~;x~i2~;...;x~id~)
- 那么 x~i~ 是 d 维 attibute space 的一个 feature vector
- x~ij~ 是x~i~ 在第 j 个维度上的 attribute value
- **dimensionality 维数**：d 称为样本 x~i~ 的维数 

- **data set 数据集**

- **instance 示例**： 是data set 的一条记录

- **attribute/ feature 属性/特征**：是每一条instance 的列

- **attribute value 属性值**：属性上的取值

- **attribute space 属性/样本/输入空间**：各个属性组成的坐标空间

- **feature vector 特征向量**：instance在attribute spcase的点的坐标位置

- **label space 标记空间/输出空间**

- **classification 分类**： 预测的输出空间为离散值的学习任务

- **regression 回归**：预测的输出空间为连续值得学习任务

- **clustering 聚类**

- **supervised learning 监督学习**

- **unsupervised learning 非监督学习**

- **generalization 泛化**：学习得出的模型适用于在新样本上的能力


### 1.3 假设空间

- **induction 归纳**： 从特殊到一般的“泛化”过程 (generalization)，即从具体的事实归结出一般性的规律
- **deduction 演绎**：从一般到特殊的“特化”过程 (specialization), 即从基础原理推演出具体状况
- **hypothesis space 假设空间**： 
- **version space 版本空间**： 存在一个与训练集一致的“假设集合”

### 1.4 归纳偏好

- **inductive bias 归纳偏好**：机器学习算法在学习过程中对某种类型假设的偏好
- **occam's razor 奥卡姆剃刀**：一个常用的、自然科学研究中最基本的原则，即“若有多个假设与观察一直，则选最简单的那个”。利用这个原则，我们用来引导算法确立的偏好。
- NFL定理(No Free Lunch Theorem)：在所有instance 出现的几率相同的情况下，任何学习算法的期望性能相同。即算法和胡乱猜几乎相同。此定理的前提条件是所有的instance出现的概率均相同，但是现实生活中，某一些情况出现的概率非常低。

### 1.5 发展历程

- 略

### 1.6 应用现状

- 略






