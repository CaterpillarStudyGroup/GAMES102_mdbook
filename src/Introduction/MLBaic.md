> 如何求满足要求的函数？[51：113
1-确定某个函数集创空间
20度量哪个函故是"最好"的
3-求解与优化
大部分的实际问题可建模为
找一个映射/变换/函数

# 问题：如何求满足要求的函数？

• 大部分的实际应用问题
– 可建模为：找一个映射/变换/函数
– 输入不一样、变量不一样、维数不一样
• 如何找函数的三步曲：
– 到哪找？
• 确定某个函数集合/空间
– 找哪个？
• 度量哪个函数是好的/“最好”的
– 怎么找？
• 求解或优化：不同的优化方法与技巧，既要快、又要好…
• 【注】这里先暂时限定为单变量的函数形式

# 【例子】逆向工程：求船型曲线

• 已知：某条船的侧面投影曲线图
• 求：该投影轮廓线的表达函数？
• 方法：
– 从投影曲线上描（采样）一系列点
– 找一个函数拟合这些采样点

# 曲线/曲面拟合问题

• 输入：一些型值（采样）点集
• 输出：一条拟合这些点集的曲线/曲面
采样点云 光滑曲面

# 数据拟合

# 拟合(Fitting)问题

• 输入：一些观察的数据点
• 输出：反映这些数据规律的函数

# 1. 到哪找？

待定系数

# 2. 找哪个？

# 3. 怎么找？

# Lagrange插值函数

• 插值n+1个点、次数不超过n的多项式是存
在而且是唯一的
– （ n +1个变量， n +1个方程）
插值函数的自由度 = 未知量个数 - 已知量个数
# 2‐2. 找哪个？
# 3‐2. 怎么找？
最小二乘法
# Recap：拟合‐‐插值或逼近
插值
逼近
零误差
最小平方误差
(最小二乘拟合)
# Overfitting（过拟合）
• 误差为0，但是拟合的函数并无使用价值！
# 欠拟合或过拟合
• 如何选择合适的基函数？
High bias
(underfitting)
“Just right” High variance
(overfitting)
• 需要根据不同的应用与需求，不断尝试
（不断“调参”）
避免过拟合的常用方法
• 数据去噪
– 剔除训练样本中噪声
• 数据增广
– 增加样本数，或者增加样本的代表性和多样性
• 模型简化
– 预测模型过于复杂，拟合了训练样本中的噪声
– 选用更简单的模型，或者对模型进行裁剪
• 正则约束
– 适当的正则项，比如方差正则项、稀疏正则项
岭回归正则项
• 选择一个函数空间
– 基函数的线性表达
• 最小二乘拟合
• Ridge regression （岭回归）
稀疏学习：稀疏正则化
• 冗余基函数（过完备）
• 通过优化来选择合适的基函数
– 系数向量的 L 0 模（ 非0元素个数）尽量小
– 挑选（“学习”）出合适的基函数
从另一角度：压缩感知
M N 
• 已知y和Φ ，有无穷多解x
• 对于稀疏信号x，可通过优化能完全重建x
– 在一定条件下 (on Φ)  [Candes and Tao 2005]
s.t. x y  
0
min x
L 0 优化
思考：非函数型的曲线拟合？

1. 多项式插值
多项式插值定理
如果基函数选取
不一样，方程组
的系数矩阵不同
技巧1：构造插值问题的通用解
一般形式
技巧1：构造插值问题的通用解
技巧2：更方便的求解表达
• Newton插值：具有相同“导数”（差商）的多项式
构造（n阶Taylor展开）
多项式插值存在的问题
• 系统矩阵稠密
• 依赖于基函数选取，矩阵可能病态，导致难于求
解（求逆）
Thanks to Renjie Chen
病态矩阵示例
病态问题
• 输入数据的细微变化导致输出(解)的剧烈变化
• 将线性方程看成直线（超平面）
• 当系统病态时，直线变为近似平行
• 求解（即直线求交）变得困难、不精确
矩阵条件数
矩阵条件数
为什么？
幂(单项式) 函数
函数互相抵消
解决方法
• 使用正交多项式基
• 如何获得？
• Gram‐Schmidt正交化
多项式插值结果好吗？
结论
• 多项式插值不稳定
• 控制点的微小变化可导致完全不同的结果
• 振荡(Runge)现象
• 多项式随着插值点数(可以是细微)增加而摆动
• 需要更好的基函数来做插值
• Bernstein基函数？
• 分片多项式？
2. 多项式逼近
为什么逼近？
• 数据点含噪声、outliers等
• 更紧凑的表达
• 计算简单、更稳定
最小二乘逼近
最佳逼近的定义
求解
3. 函数空间及基函数
为什么用多项式？
用Bernstein多项式做逼近
Bernstein多项式
用Bernstein多项式做逼近
• Bernstein基函数的良好性质：非常好的几何意义！
• 正性、权性（和为1）凸包性
• 变差缩减性
• 递归线性求解方法
• 细分性
• …
• Bernstein多项式逼近示例
• 逼近结果优秀
• 需要高阶
丰富的理论：CAGD 课程
关于Bernstein函数…
丰富的理论：CAGD 课程
4. RBF函数插值/逼近
Gauss函数
RBF函数拟合
• RBF函数
• 方法
• 原因
讨论：现象
讨论：现象
思考：
5. 从另一个角度来看拟合函数
Gauss拟合函数
• 一般Gauss函数表达为标准Gauss函数的形式
基函数是由一个基本函数通
过平移和伸缩变换而来的
换个方式看函数：神经网络
• 将Gauss函数看成网络
𝑥
𝑔 ?,?
𝑦
1
𝑔 ?,?
𝑔 ?,?
1
输入层 隐层
输出层
激活函数
… …
𝑎 ?
𝑏 ?
抽象：神经元
𝑥
𝑔 ?,? 𝑦
1
𝑎 ?
𝑏 ?
Input
𝑓
? ?𝑥? ? 𝑎 ? 𝑥 ? 𝑏
Activation
𝑓 ? ?𝑥? ? 𝑔 ?,? ?𝑓
? ?𝑥??
Output
𝑓 ? ?𝑥? ? 𝑤 ? 𝑓 ? ?𝑥?
𝑤 ?
RBF 神经网络
• 高维情形：RBF (Radial Basis Function)，径向基函数
• 一种特殊的BP网络
• 优化：BP算法
• 核函数思想
• Gauss函数的特性：拟局部性
思考：激活函数的选择？
• 启发：由一个简单的函数通过（仿射）变换构造出一组
基函数，张成一个函数空间
• 表达能力是否足够强：是否完备/稠密的？
高维情形：多元函数
（后面的课程再展开解释）
• 变量的多个分量的线性组合
• 单隐层神经网络函数：
多层神经网络：多重复合的函数
• 线性函数和非线性函数的多重复合
56
Neuron
Neural network
f(net)
用神经网络函数来拟合数据
Regression problem:
Input: Given training set (x 1 , y 1 ), (x 2 , y 2 ), (x 3 , y 3  ), ….
Output: Adjust parameters  (for every node) to make:
Why it works?
• 万能逼近定理：自由度足够多！
与传统拟合一样存在
同样的问题：
函数个数如何选？!
与传统拟合一样存在
同样的问题：
函数个数如何选？!
调参！
Deep Learning Frameworks
使用深度学习的方法
• 问题建模
• 理解问题、问题分解（多个映射级联）…
• 找哪个？
• 损失函数、各种Penalty、正则项…
• 到哪找？
• 神经网络函数、网络简化…
• 怎么找？
• 优化方法（BP方法）
• 初始值、参数…
调参：有耐心、有直觉…
未来课程内容
• 全局函数局部函数
• 样条函数
• 多元函数一般曲线
• 参数曲线、参数域为本征维数
• 隐函数
• 曲线设计
• 计算机辅助几何设计
• 曲面设计
• 张量积的参数曲面

