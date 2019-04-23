# 决策树入门

决策树的作用：

1. 分类问题a
2. 数据挖掘

流程图式的决策树：

1. 方框：判断模块 decision block
2. 椭圆框：终止模块 terminating block
3. 箭头：分支 branch

kNN -> 决策树：kNN 无法给出数据的内在含义，决策树可以。

## 构造决策树

香农熵：信息的期望值


信息 <img src="https://latex.codecogs.com/png.latex?\inline&space;\dpi{150}&space;\bg_white&space;\small&space;l(x_i)&space;=&space;-log_2p(x_i)" title="\small l(x_i) = -log_2p(x_i)" />

熵 <img src="https://latex.codecogs.com/png.latex?\inline&space;\dpi{150}&space;\bg_white&space;\small&space;H&space;=&space;-\sum_{i=1}^{n}p(x_i)log_2p(x_i)" title="\small H = -\sum_{i=1}^{n}p(x_i)log_2p(x_i)" />

香农熵只和 label 的值有关，与 feature 的值无关。

另一个度量集合无序程度的方法：Gini impurity 基尼不纯度。

## 划分数据集

python 语言中，a.append(b) 表示把 b 作为一个元素硬加到 a 中，a.extend(b) 表示把 b 拆开，里面的元素加到 a 中。

在按照给定特征划分数据集这里，我开始看不懂了。《机器学习实战》$p_{37}$

周六 4.20 晚 11:26

---