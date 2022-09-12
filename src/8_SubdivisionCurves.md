几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
细分曲线
GAMES 102在线课程：几何建模与处理基础
回顾：Bezier曲线的作图法
• de Casteljau作图算法
• 几何直观性：逐步割角、磨光
• 类似于雕塑雕刻过程
“其实，这座雕塑本
来就在那里，我只
是将它多余的边边
角角去掉而已。”
问题
• 输入：一个简单多边形（控制多边形）
• 输出：一条与之关联的光滑曲线
启发：通过不断“割角”构造曲线？
• 给定一个简单多边形
• 通过一定规则，割角磨光，产生更多边的多边形
• 不断迭代操作割角磨光，产生（极限）光滑曲线
细分方法的思想
两个步骤：
• 拓扑规则：加入新点，组成新多边形 (splitting)
• 几何规则：移动顶点，局部加权平均 (averaging)
• 对所有顶点都移动：逼近型
• 只对新顶点移动：插值型
1. 2. 3.
splitting averaging
subdivision
Chaikin细分方法
Chaikin割角法[1974]
• 每条边取中点，生成
新点
• 每个点与其相邻点平
均（顺时针）
• 迭代生成曲线
Chaikin割角法[1974]
• 拓扑规则：
• 点分裂成边（割角），老点被抛弃（逼近型）
• 新点老点重新编号
• 几何规则：新顶点是老顶点的线性组合
新边点
Chaikin细分曲线
• 可以证明：
• 极限曲线为二次均匀B样条曲线
• 节点处𝐶 ? ，其余点处𝐶 ?
初始多边形 细分一次 细分两次 细分三次
均匀三次B样条曲线细分方法
• 拓扑规则：边分裂成两条新边
• 几何规则：
边分裂成新边
新点点
新边点
细分曲线的性质证明
证明的思路
• 将细分过程表达成矩阵形式
• 新顶点是老顶点的线性组合
• 讨论细分矩阵的谱性质（特
征根）
举例：Chaikin细分
矩阵形式:
• Control points at level 𝑙: 𝒑 ? ?
• “Splitted” points at level 𝑙 ? 1:
𝒑 ? ?
???
• “Averaged” control points at
level 𝑙 ? 1: 𝒑 ? ???
Chaikin细分的矩阵形式
Splitting in matrix notation
2𝑛
⋮
𝑥? ??
???
𝑥? ??
???
⋮
? 2𝑛
⋱
1
1 2 ⁄ 1 2 ⁄
1
1 2 ⁄ 1 2 ⁄
⋱
⋮
𝑥 ?
?
𝑥 ???
?
⋮
𝑛
Averaging in matrix notation
2𝑛
⋮
𝑥 ??
???
𝑥 ??
???
⋮
? 2𝑛
⋱
1 2 ⁄ ⁄
1 2 ⁄ 1 2 ⁄
⋱
⋮
𝑥? ??
???
𝑥? ??
???
⋮
2𝑛
𝑛
2𝑛
Chaikin细分的矩阵形式
⋮
𝑃 ????
???
𝑃 ????
???
𝑃 ??
???
𝑃 ????
???
𝑃 ????
???
𝑃 ????
???
⋮
?
1
4
⋱ ⋰
0 3 1 0 0 0
0 1 3 0 0 0
0 0 3 1 0 0
0 0 1 3 0 0
0 0 0 3 1 0
0 0 0 1 3 0
⋰ ⋱
⋮
𝑃 ???
?
𝑃 ???
?
𝑃 ?
?
𝑃 ???
?
𝑃 ???
?
𝑃 ???
?
⋮
极限情况
极限曲线上的点可由细分矩阵的幂次的极限求得:
𝑥 ?
?
𝑥
?
𝑥 ?
?
? lim
?→?
𝑴 ??????
?
𝑥 ?
?
𝑥
?
𝑥 ?
?
极限情况
收敛的必要条件:
• 细分矩阵的最大特征根为1
• 否则会爆炸 (>1) 或收缩 (<1)
𝑥 ??
???
⋮
𝑥 ?
???
⋮
𝑥 ??
???
? 𝑴 ??????
?
𝑥 ??
?
⋮
𝑥 ?
?
⋮
𝑥 ??
?
? 𝑼𝑫 ? 𝑼 ??
𝑥 ??
?
⋮
𝑥 ?
?
⋮
𝑥 ??
?
插值型细分方法
插值型细分方法
• 细分方法：
• 保留原有顶点
• 对每条边，增加一个新顶点
• 不断迭代，生成一条曲线
• 可以看成是“补角法”
…
4点插值型细分规则
Nira Dyn, David Levin, John A. Gregory. A 4‐point interpolatory subdivision
scheme for curve design. Computer Aided Geometric Design, 4(4): 257‐268, 1987.
𝒑 ?
𝒑 ???
𝒑 ???
𝒑 ???
𝒑′ 𝟐??? ?
𝒑 ? ? 𝒑 ???
2
? 𝛼? 𝒑 ?
? 𝒑 ???
2
?
𝒑 ??? ? 𝒑 ???
2
?
𝒑′ 𝟐???
4点插值型细分曲线的例子
4点插值型细分曲线的例子
4点插值型细分规则
𝒑 ?
𝒑 ???
𝒑 ???
𝒑 ???
𝒑′ 𝟐??? ?
𝒑 ? ? 𝒑 ???
2
? 𝛼? 𝒑 ?
? 𝒑 ???
2
?
𝒑 ??? ? 𝒑 ???
2
?
𝒑′ 𝟐???
可以证明：当𝛼 ∈ ?0,
?
? ?时，生成的细分曲线是光滑的；
否则，细分曲线非光滑，生成了分形曲线。
4点细分曲线的例子
分形曲线（分数维）：分形几何
一般：2n点插值细分方法
• 连续阶随着n增大而增加
2点插值细分方法
4点插值细分方法
6点插值细分方法
非线性细分方法
• 基于双圆弧插值的曲线细分方法
• 给定一条边,新点为插值其两端点及两端切向的双圆弧的一个连
接点,也是其两端点两端切向的所确定三角形的内心.
• 每个细分步骤后调整切向.
基于双圆弧插值的曲线细分方法
• 性质（证明稍难）
• 极限曲线𝐺 ? ，光顺，保形
参考文献
• Denis Zorin et al. Subdivision for Modeling and Animation.
SIGGRAPH 2000 Course Notes
• Warren and Weimer. Subdivision Methods for Geometric Design:
A Constructive Approach. Morgan Kaufmann Publishers, 2002
• M.S. Sabin. Recent Progress in Subdivision: a Survey. Advances in
Multiresolution for Geometric Modelling, Mathematics and
Visualization 2005, 203‐230
• Cashman. Beyond Catmull–Clark? A survey of advances in
subdivision surface methods. Compute Graphics Forum,  31(1),
2012, 42–61
作业5
• 任务： 实现两种细分曲线的生成方法
• 逼近型细分：Chaikin方法（二次B样条）、三次B样条细分方法
• 插值型细分：4点细分方法
• 目的
• 学习使用细分方法生成曲线的原理和方法
• Deadline：2020 年11 月21日晚
谢 谢 ！
