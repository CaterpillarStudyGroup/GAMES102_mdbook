几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
三次样条函数
GAMES 102在线课程：几何建模与处理基础
作业3情况
• 作业3情况
• 演示优秀demo
• 优秀代码和优秀报告
• 其他学员可以继续完成提交
• 可参照优秀作业尽快完成，赶上大部队
几何设计
工业产品的外形是如何设计的？
几何设计
• 传统的概念更多指的是“外形设计”
概念设计
设计图纸
从设计到数学（几何）表达
没有电脑之前，
设计师是如何画图设计的？
放样方法
样条与压铁
• 样条：具有一定弹性的软木条
• 压铁：较重的铁块，用来固定样条所经过的点
自由曲线
• 在产品初始设计阶段，描述其外形的曲线或曲面
常常只有大致形状或只知道它通过一些空间点列
（称为型值点），这类没有数学表达式的曲线或
曲面称为自由曲线或自由曲面(Free form
curve/surface)．
• 造型方法
• 拟合(fitting)
• 插值(interpolation)
• 逼近(approximation)
样条所形成的曲线的数学表达？
三次样条函数
样条曲线的数学表达推导
• 压铁：型值点
• 木样条：插值型曲线
力学解释
• 曲线：弹性梁，弹性模量为
• 压铁：载荷（力）
• 由材料力学中的贝努利‐欧拉方程
?
?
其中
𝑀 𝑥 ：曲线弯矩
𝐸：木样条的弹性模量（杨氏模量）
𝐼: 几何惯性矩
• 𝑘 𝑥 ：曲线的曲率
力学解释
• 曲线：软木弹性梁（弹性模量为 ）
• 压铁：载荷（力）
• 由材料力学中的贝努利‐欧拉方程
?
?
• 小扰度假设：
?
（弯角不大于
° ）
• 因两压铁之间无外力， 为一次式
• 因此可得，两压铁间 为三次函数，即样条曲线
为分段三次函数。
先限制在函数型讨论
数学性质
• 分段3次多项式的好处
• 2次多项式无法表达拐点，不够自由
• 高次（4次及以上）多项式拐点多，次数若较高计算
易出现较大误差
• 思考：
• 每段多项式函数之间满足什么条件？
• 如何求解？
求解思路
• 每段为3次多项式，有4个变量（待定系数）
? ? ? ?
?
?
?
• 假设有 个型值点（ 段），则总共有个 变量。
• 首先，曲线要插值型值点，有 个约束条件；
• 其次，假设曲线整体为
? 连续，则相邻两段在拼接
点要满足3个条件（
? 连续、 ? 连续、 ? 连续）；
则有 个约束条件；
• 则共有 个约束条件；
• 因此，再加2个额外条件，即可唯一确定整条曲线。
三次样条函数推导（方法1）
• 3次样条插值函数的定义
• 引入中间变量：节点处的2阶导数值
? （弯矩）
• 每段
?
表达为
? 和 ??? 的线性插值
• 则
?
为包含待定值
? 的3次多项式
• 再根据拼接条件（
? 、 ? 、 ? 连续），列出等式
• 最后加上2个边界条件，构成关于
?
的 阶的线性方程组
• 方程组为对称的、三对角的、对角占优的，称为
三弯矩方程组。方程组系数矩阵满秩，有唯一解。
• 可用追赶法求解三弯矩方程组。
边界条件
• I. 自由端： 指定曲线在两个端点处的二阶导数值
• 特别地，两个端点的二阶导数值指定为0时称为自然
三次样条
• II. 夹持端： 指定曲线在两个端点处的一阶导数值
• 其他：
• 抛物端：首末两段为抛物线
• 周期端
• 混合边界条件
三次样条函数推导（方法2）
• 3次样条插值函数的定义
• 引入中间变量：节点处的1阶导数值
? （转角）
• …（推导过程类似）
• 最后加上2个边界条件，构成关于
?
的 阶的线性方程组
• 方程组为对称的、三对角的、对角占优的，称
为三转角方程组。方程组系数矩阵满秩，有唯
一解。
• 同样可用追赶法求解三转角方程组。
三弯矩方程组/三转角方程组
• 三对角矩阵
• 主对角占优
• 有唯一解
• 追赶法求解
简化的计算技巧
• Hermite型插值多项式
• 两点及其一阶导数（切线）
• Lidstone型插值多项式
• 两点及其二阶导数（曲率）
• 好处：在给定两个端点及其导数情况下，可直接
写出函数的表达形式
• 这是数学上的一个通用技巧
Hermit型插值多项式
三次基样条
基样条特征
• 考虑定义在所有整数节点上的基样条
三次样条曲线
样条函数的局限性
• 须有小扰度假定
• 不能处理多值问题
• 不能很好表达空间曲线
• 不具有坐标不变性（几何不变性）
三次参数样条曲线
• 3个坐标分量 分别是参数 的三次样条函数
• 对型值点做参数化
• 对3个坐标分量分别处理
• （同课程3及作业3的处理）
曲线的几何连续性
参数连续性
• 在数学分析/高等数学中，我们所说的“连续性”
（光滑性）是指“参数连续性”：
• 给定 2 条曲线
𝒙 ? ? ?
𝒙 ? 𝑡 定义在 𝑡 ? ,𝑡 ?
• 曲线 𝒙 ? 和 𝒙 ? 在 𝑡 ? 称为𝐶 ? 连续的，如果它们的从 0 ??
（0阶） 至 𝑟 ?? （ 𝑟阶）的导数向量在 𝑡 ? 处完全相同。
参数连续性
•
? : position varies continuously
•
? : First derivative is continuous across junction
• In other words: the velocity vector remains the same
•
? : Second derivative is continuous across junction
• The acceleration vector remains the same
参数连续性
参数连续性的不足
• 参数连续性过于严格，在几何设计中不太直观
• 例子：一条直线
•
?
? ? ?? ?
?
?
? ? ?? ?
?
? ? ? ?? ?
?
• 但是，
? ? ?? ?
?
,
??? ? ?? ? ?
?
• 在 的左右导数不相等，因此， 在[0,2]
中不是
? 的，与直线的连续性应是 ? 的矛盾。
𝑣 ? 𝑣 ?
0 ? 𝑡 ? 1 1 ? 𝑡 ? 2
原因：连续性依赖于参数的选择，同一条曲线，参数不同，连续阶也不同。
参数连续性的不足
• 参数连续性过于严格，在几何设计中不太直观
• 例子：一条直线
• 𝜑?𝑡? ? ?
𝑣 ? ?
? ? ?? ?
?
𝑡,0 ? 𝑡 ?
?
?
,
𝑣 ? ?
? ? ?? ?
?
?
? ? ?? ?
?
?𝑡 ?
?
? ?,
?
?
? 𝑡 ? 2.
• 则𝜑′? ?
?
?? ? 𝜑′? ?
?
??, 𝜑 𝑡 在[0,2]就是𝐶 ? 了。
• 本质：是引入了参数的一个变换
𝑡 ?
2
3
𝑠,0 ? 𝑠 ?
2
3
,
3
4
𝑠 ?
2
3
? 1,
2
3
? 𝑠 ? 2.
• 使得原来不是𝐶 ? 的曲线变为𝐶 ? 的了。
𝑣 ? 𝑣 ?
0 ? 𝑡 ?
2
3
2
3
? 𝑡 ? 2
几何连续性
【定义】设 是给定的曲线。
若存在一个参数变换
? ?
，
使得
?
? ?
，且 ????????
??
，
则称曲线 是 阶几何连续的曲线，
记为
?
或
?
几何连续性：性质
【定义】设𝜑?𝑡??𝑎 ? 𝑡 ? 𝑏?是给定的曲线。
若存在一个参数变换𝑡 ? 𝜌?𝑠??𝑎 ? ? 𝑡 ? 𝑏 ? ?，
使得𝜑?𝜌?𝑠?? ∈ 𝐶 ? ?𝑎 ? ,𝑏 ? ?，且 ????????
??
? 0，
则称曲线𝜑?𝑡??𝑎 ? 𝑡 ? 𝑏?是𝑛阶几何连续的曲线，记为
𝜑 𝑡 ∈ 𝐺𝐶 ? 𝑎,𝑏 或𝜑?𝑡? ∈ 𝐺 ? ?𝑎,𝑏?
【性质】
1. 条件 ????????
??
? 0保证了曲线上无奇点；
2. 几何连续性与参数选取无关，是曲线本身固有的几何性质；
3. 𝐺 ? 的条件比𝐶 ? 的宽，曲线类型更多；
几何连续性的具体形式
? ：表示两曲线有公共的连接端点，与𝐶 ? 的条件一致
? ：两曲线在连接点处有公共的切线，即切线方向连续
• 𝐺 ? ：两曲线在连接点处有公共的曲率圆，即曲率连续
𝐺 ? 𝐺 ? 𝐺 ?
曲线设计及编辑工具
• 矢量曲线设计工具：PPT, Word, Adobe Illustrator,
Corel Draw, …
• 使用：PowerPoint的曲线编辑工具
两种连续性的比较
Parametric Continuity 𝑪 𝒓 :
• 𝐶 ? , 𝐶 ? , 𝐶 ? … continuity
• Does a particle moving on
this curve have a smooth
trajectory (position, velocity,
acceleration, …)?
• Depends on
parameterization
• Useful for animation
(object movement, camera
paths)
Geometric Continuity 𝑮 𝒓 :
• Is the curve itself
smooth?
• Independent of
parameterization
• More relevant for
modeling (curve design)
作业4
• 任务： 模仿PowerPoint写一个曲线设计与编辑工具
• 输入有序点列（型值点），实时生成分段的三次样条曲线
修改拖动型值点的位置（保持整条曲线𝐶 ? ）
• 可编辑型值点处的切线信息，成为𝐺 ? 或𝐺 ?
• 目的
• 学习三次样条函数的求解
• 了解曲线设计和编辑工具的原理
• Deadline：2020 年11 月14日晚
谢 谢 ！