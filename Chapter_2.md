# 第二章 模型评估与选择



## 1. 经验误差与过度拟合

- error rate 错误率: E = $\frac{a}{m}$ (a：样本分类错误数， m：总样本数量)
- accuracy 精度：1-$\frac{a}{m}$
- error 误差：预测输入和真实输入之间的差异
- training/empirical error 训练误差：在训练集上的误差
- generalization error 泛化误差：在新样本上的误差
- overfitting 过拟合：把训练集的一些特征误认为是整体样本都具有的特征，导致泛化能力下降
- underfitting 欠拟合：训练集样本的特征没有学习好

## 2. 评估方法

对数据集进行拆分的方法有

- hand-out 留出法：将数据集拆分成两个互斥的集合，可以用分层拆分、排拆分等，常见用2/3 ~4/5的样本用于训练，剩余的用作测试集
- cross validation 交叉验证法：将数据集划分为k个大小相似的互斥子集，每个子集尽可能的保持数据分布的一致性，然后每次用k-1 个子集的并集座位训练集，剩下的子集作为测试集。那么可以得到k组训练和测试，最后取k个结果的平均值作为结果返回。
- leave-one-out 留一法(LOO) ：是cross validation 的特例，即每个子集只有一个样本。
- booststrapping 自助法：不常用

## 3. 性能度量

####  3.1 预测任务：

预测任务评估学习器f的性能，是把预测结果f(x) 与x对应的真实结果进行比较。

- 回归任务最常用的性能度量是 “均方误差(mean squared error)”

  ***E(f;D) = $\frac{1}{m}\quad\sum_{i=1}^{m}{(f(x_i)-y_i)^2}$***

- 而一般情况下，对于数据分布D 和概率密度函数p(x),均方误差可以描述为：

  ***E(f;D) = $\int^D_x{(f(x)-y)^2p(x)dx}$***


#### 3.2 分类任务：

主要考核错误率和精度，对于样例集D：

- 错误率定义为：
  ***E(f;D) = $\frac{1}{m}\sum_{i=1}^{m}\prod{(f(x_i)\neq{y_i})}$***
- 精度定义为：
  ***ACC(f;D) = $\frac{1}{m}\sum_{i=1}^{m}\prod{(f(x_i)={y_i})}$ = 1 - E(f;D)***
- 一般情况下，对于数据分布D 和概率密度函数p(x)，错误率和精度可分别描述为:
  ***E(f;D) = $\int^D_x\prod{(f(x)\neq{y})p(x)dx}$***
  ***ACC(f;D) = $\int^D_x\prod{(f(x)={y})p(x)dx}$***

####3.3 其他任务：

- 查准率(precision)  = $\frac{TP}{TP+FP}$
- 查全率(recall)= $\frac{TP}{TP+FN}$
- P-R曲线：以查准率P为横轴，查全率R为纵轴的图。

| 真实情况 | 预测正例 | 预测反例 |
| ---- | ---- | ---- |
| 正例   | TP   | FN   |
| 反例   | FP   | FN   |

- ROC: 受试者工作特征(Receiver Operating Characteristic)
  - 横轴：假阳性TPR = $\frac{TP}{TP+FN}$
  - 纵轴：FPR = $\frac{FP}{TN+FP}$
  - 绘制方法：设前一个标记坐标为(x,y), 当前若为真正例，则对应坐标为(x,y+$\frac{1}{m+}$); 若为假正例，则对应坐标为(x+$\frac{1}{m}-$,y)，然后用线段链接相邻的点即可。
- AUC：Area Under Curve 
  - 量化ROC的曲线质量，面积越大，则效果越好。



## 4. 比较检验

- 统计假设检验为我们进行学习器性能比较提供了重要的依据，因为不能直接拿性能度量的值进行大小比较。
- 希望比较泛化性能
- 机器学习算法有一定的随机性，即使在同一个数据集上运行，也有可能结果不一样
- 统计假设检验（hypothesis test）
- 交叉验证t检验
- McNemar检验
- Friedman检验 与 Nemenyi后续检验

## 5. 偏差与方差

- 偏差-方差分解 (bias-variance decomposition) 是解释学习算法泛化性能的重要工具
- 泛化误差 = 偏差+方差+噪声

