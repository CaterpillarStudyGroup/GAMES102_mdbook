几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
NURBS曲线
GAMES 102在线课程：几何建模与处理基础
作业4情况
• 作业4情况
• 演示优秀demo
• 优秀代码和优秀报告
• 其他学员可以继续完成提交
• 可参照优秀作业尽快完成，赶上大部队
回顾：Bézier曲线
• 类似RBF函数：对每个控制点叠加权函数
• 几何设计观点：给定控制顶点
?
，使
用一组（随 变化的）权系数函数
?
?
对它们进行线性组合，得到的点的集合
𝑥 𝑡 ? ?𝐵 ?
?
𝑡 ⋅ 𝑏 ?
?
???
Bezier曲线的性质来源于Bernstein基函数的性质
回顾：B样条曲线
• Bézier曲线、RBF函数：每个控制点上的权系数
函数都是全局（定义在整个定义域）的
• B样条曲线：每个控制点上的权系数函数是局部
定义的（定义在其参数节点附近的支集）
全局基函数 局部基函数
有理曲线
问题：Bézier曲线无法表示圆弧！
思考：如何证明？
Approximation of Circle using Cubic Bezier Evaluation of 𝒙 𝟐 ? 𝒚 𝟐 for points on the Bezier curve
投影几何
• 齐次坐标：
欧氏坐标
（欧氏空间）
齐次坐标
（投影空间）
𝒙 →
𝜔𝒙
𝜔
1
𝜔
𝒙 ←
𝒙
𝜔
 2D case:
𝑥
𝑦
→
𝜔𝑥
𝜔𝑦
𝜔
 3D case:
𝑥
𝑦
𝑧
→
𝜔𝑥
𝜔𝑦
𝜔𝑧
𝜔
𝑥 ? ? 𝑑
?
? ,     𝑦
?
? 𝑑
?
?
𝑥 ?
𝑦 ?
𝑧 ?
𝜔 ?
?
𝑑 0 0 0
0 𝑑 0 0
0 0 𝑑 0
0 0 1 0
𝑥
𝑦
𝑧
1
有理Bezier曲线
• Rational Bezier curves in
?
of degree :
• Form a Bezier curve of degree 𝑑 in 𝑛 ? 1 dimensional
space
• Interpret last coordinates as homogenous component
• Euclidean coordinates are obtained by projection
𝒇
???
𝑡 ? ∑ 𝐵
?
?
𝑡 𝒑 ?
?
???
, 𝒑 ? ∈ ℝ ???
𝒇
????
𝑡 ?
∑ 𝐵 ?
?
𝑡
𝑝 ?
?
…
𝑝 ?
?
?
???
∑ 𝐵
?
?
𝑡 𝑝 ?
???
?
???
有理Bezier曲线
• 每个控制顶点上设置一个权系数
𝒇
????
𝑡 ?
∑ 𝐵
?
?
𝑡 𝜔 ? 𝒑 ?
?
???
∑ 𝐵
?
?
𝑡 𝜔 𝒊
?
???
• 另一种形式
????
?
?
???
?
?
?
?
?
?
?
???
? ?
?
???
• 如权系数都相等，则退化为Bezier曲线
𝒑 ? =
𝑝 ?
?
…
𝑝 ?
?
with ∑ 𝑞 ? 𝑡
?
???
? 1
有理Bezier曲线的几何解释
• 高维的Bezier曲线的中心投影
权系数对曲线形状的影响
• 控制顶点的权系数越大，曲线就越靠近该点
移动控制顶点
增加权系数
1:1:1:1 10:1:1:10
1:10:1:10
1:10:10:1
有理Bezier曲线的性质
• 具有Bezier曲线的大部分性质（设
?
）:
• 端点插值
• 端点切线
• 凸包性
• 导数递推性
• de Casteljau作图算法
• …
2次有理Bezier曲线表示圆
NURBS曲线
NURBS: Non‐Uniform Rational B‐
Spline （非均匀有理B样条）
NURBS: Rational B‐Splines
• Formally:(𝑁 ?
?
:B‐spline basis function 𝑖 of degree d)
𝒇 𝑡 ?
∑ 𝑁
?
?
𝑡 𝜔 ? 𝒑 ?
?
???
∑ 𝑁
?
?
𝑡 𝜔 𝒊
?
???
• Knot sequences etc. all remain the same
• De Boor algorithm – similar to rational de Casteljau alg.
• option 1. – apply separately to numerator, denominator
• option 2. – normalize weights in each intermediate result
‐ the second option is numerically more stable
NURBS曲线
• 影响NURBS曲线建模的因素
• 控制顶点：用户交互的手段
• 节点向量：决定了B样条基函数
• 权系数：也影响曲线的形状，生成圆锥曲线等
• NURBS曲线的性质
• 大部分与Bezier/B样条曲线类同：具有良好的几何直观性
NURBS曲线的例子
NURBS曲线的例子
NURBS曲线
• NURBS曲线/曲面表达是当前的工业标准
• 工业CAD软件的基本表达形式
• 各种CAD系统的数据交换标准
• 3D建模软件：
• 工业设计：AutoCAD, CATIA, SolidWorks, Rhino, …
• 动画设计：3DS Max, Maya, SoftImage, Cinema 4D, …
产品设计的工业标准
谢 谢 ！
