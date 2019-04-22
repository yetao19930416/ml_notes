# Logistic Regression

regression 回归，含义为：拟合成一条直线

logistic regression：

- 优点：开销、理解、实现
- 缺点：欠拟合、精度
- 数据：数值、标称

## Sigmoid 函数

两种 step function：

1. Heaviside step function：难以处理瞬间跳跃
2. Sigmoid function：更加平滑

Sigmoid 函数： <img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\bg_white&space;\sigma(z)=$$\frac&space;{1}{1&plus;e^{-z}}" title="\sigma(z)=$$\frac {1}{1+e^{-z}}" />


在小尺度看起来平滑，在大尺度看起来跳跃。


logistic regression 步骤：

1. feature * 系数
2. 求和
3. Sigmoid(和)
4. 分类：`x > 0.5 -> 1` 、`x < 0.5 -> 0`

## 确定回归系数

<img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\bg_white&space;z&space;=&space;w^t*x" title="z = w^t*x" />

z 是和，x 是输入数据，w 是待确定的参数。

### 梯度上升法

最优化理论：梯度上升法。

梯度：

<img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\bg_white&space;\nabla&space;f&space;(x,y)=&space;\begin{bmatrix}&space;$\cfrac&space;{\partial&space;f}&space;{\partial&space;x}$&space;\\&space;$\cfrac&space;{\partial&space;f}&space;{\partial&space;y}$&space;\end{bmatrix}" title="\nabla f (x,y)= \begin{bmatrix} $\cfrac {\partial f} {\partial x}$ \\ $\cfrac {\partial f} {\partial y}$ \end{bmatrix}" />

梯度上升法求最大值： <img src="https://latex.codecogs.com/gif.latex?\inline&space;\dpi{150}&space;\bg_white&space;w:=w&plus;\alpha\nabla_wf(w)" title="w:=w+\alpha\nabla_wf(w)" />

梯度下降法求最小值：把梯度上升公式的加号改为减号。


伪代码：

```
系数向量 = [1,1,1,...,1]
重复R次：
    计算梯度
    用梯度上升公式更新系数向量
返回系数向量
```

### 找最佳系数

```
logRegres.py

def loadDataSet() 获取数据
def sigmoid(inX) sigmoid 函数
def gradAscent(dataMatIn,classLabels) 计算梯度下降
```

python 代码技巧：

```
fr = open('xx.txt')
for line in fr.readlines():
    lineArr = line.strip().split()
```

源数据预处理结果：

```
X0=1.0, X1, X2 -> dataMat
Label -> labelMat
```

剩下两个函数还没开始看。

4.22 周一 下午5点29 p78 机器学习实战

---

### 决策边界图

### 随机梯度上升算法

## 示例

### 准备数据：缺失值处理

### 测试

## 总结

知识点：

- [ ] sigmoid 函数
- [ ] logistic regression
- [ ] 最优化理论
- [ ] 梯度下降算法
- [ ] 缺失值处理