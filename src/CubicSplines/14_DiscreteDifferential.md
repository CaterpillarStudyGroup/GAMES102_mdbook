几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
离散微分几何
GAMES 102在线课程：几何建模与处理基础
回顾：三角网格曲面
陶瓷兔子实物
回顾：三角网格曲面
• 观点
1：曲面的离散逼近
• 采样：顶点为从曲面上的采样点
• 构网：每个三角面为线性平面
• 本质：分片线性逼近
• 观点
2：平面图的嵌入
• 平面图
• 图的顶点提升 (lifting) 至三维空间
• 本质：二维流形
回顾：数据结构
—
图 (graph)
• G={V, E, F}
• V: 顶点集合；E: 边集合；F: 三角形集合
• 有其中两个集合可推出另一个集合
• 多边形网格均可转化为三角网格
• 不考虑非流形结构
v 1.0 0.0 0.0
v 0.0 1.0 0.0
v 0.0 -1.0 0.0
v 0.0 0.0 1.0
f 1 2 3
f 1 4 2
f 3 2 4
f 1 3 4
三角网格编程初步
半边 (half‐edge) 数据结构
• 半边结构：以“边”为中心的数据结构
• 网格连接关系存储在边上，每条边表达为两条“半边”
• 目的：提高点线面的查询或增删改操作的效率
https://www.flipcode.com/archives/The_Half‐Edge_Data_Structure.shtml
半边 (half‐edge) 数据结构
https://www.flipcode.com/archives/The_Half‐Edge_Data_Structure.shtml
基本边、点、面数据结构
邻域关系查询方法
由边找两顶点及两邻面 由面找其所有半边 由顶点找其所有半边
几何（网格）处理库
• CGAL: http://www.cgal.org
• Libigl: https://github.com/libigl/libigl
• MeshLab: http://www.meshlab.net
• OpenMesh: https://www.openmesh.org
• PCL (Point Cloud Library): http://www.pointclouds.org
• TriMesh: http://graphics.stanford.edu/software/trimesh
• DGtal: https://dgtal.org
• 本课程作业框架：Utopia (USTC自研）
http://staff.ustc.edu.cn/~lgliu/Resources/CG/3D_modeling.htm
曲线曲面的微分几何
Curves
Differential Geometry of a Curve
C(u)
Differential Geometry of a Curve
p
C(u)
p=C(u
0
)
Point p on the curve at u
0
Differential Geometry of a Curve
C(u)
C
u
p
Tangent T to the curve at u
0
u
u
C
C
T
  
u
C
u
Cu



Differential Geometry of a Curve
C(u)
C
u
Cuu
N
p
Normal N and Binormal B to the curve at u
0
 
 
 
u uu
u
u uu
u
uu uu
uu uu
C
C
C
C
C
C
B
T
C
T
C
T
C
T
C
T
N






 
    
2
2
u
C
u
Cuu



u uu
u uu
C
C
C
C
B



B Frenet frame: {T,N,B}
Differential Geometry of a Curve
C(u)
C
u
Cuu
N


1

p
Curvature κ at u0 and the radius ρ osculating circle 
B
Curves
Curve Curvature
Surfaces
Differential Geometry of a Surface
S(u,v)
Differential Geometry of a Surface
S(u,v)
p
Point p on the surface at (u
0,v
0) 
Differential Geometry of a Surface
S(u,v)
p
S
u
Tangent Su in the u direction 
 
u
S
u
v
S
u


 ,
Differential Geometry of a Surface
S(u,v)
p
S
u
 
S
v
v
S
u
v
S
v


 ,
Tangent Sv in the v direction 
Differential Geometry of a Surface
S(u,v)
p
Plane of tangents T
S
u
S
v
T
u
v
T
 uS
 vS
Differential Geometry of a Surface
S(u,v)
N
p
S
u
S
v
T
u
v
u
v
S
S
S
S
N



Normal N
Differential Geometry of a Surface
S(u,v)
N
p
S
u
S
v
T
Normal section
Differential Geometry of a Surface
S(u,v)
N
T
T


1

p
Curvature
S
u
S
v
T
方向曲率：曲率是随着方向变化的
S(u,v)
N
T
T


1

p
Curvature
S
u
S
v
T
曲面的曲率
• 主曲率
• 两个方向（正交）曲率：最大曲率𝜅ଵ和最小曲率𝜅ଶ
• 欧拉公式
• 其他方向曲率𝜅ൌ𝜅ଵco𝑠ଶ𝜃൅𝜅ଶ𝑠𝑖𝑛ଶ𝜃
• 高斯曲率
• 𝜅ൌ𝜅ଵ𝜅ଶ
• 等距变换不变量
• 处处高斯曲率为0的曲面：可展曲面
• 三类：柱面、锥面、切线面
• 平均曲率
• 𝜅 ൌ
఑భା఑మ
ଶ
• 处处平均曲率为0的曲面：极小曲面
Principal Directions
Min Curvature Max Curvature
Surface Curvature
离散微分几何
三角网格曲面的光滑性？
However, meshes are only 
C0
• Meshes are piecewise linear surfaces
• Infinitely continuous on triangles
•
C0 at  edges and vertices
Discrete Differential Geometry
• How to apply the traditional differential geometry 
on discrete mesh surfaces?
• Normal estimation
• Curvature estimation
• Principal curvature directions
•
…
Estimation of Differential Measures
• Approximate the (unknown) underlying surface
• Continuous approximation
• Approximate the surface & compute continuous differential 
measures (normal, curvature)
• Discrete approximation
• Approximate differential measures for mesh
Continuous Approximation
Quadratic Approximation
Quadratic Approximation (2)
Quadratic Approximation (3)
Quadratic Approximation (4)
Other approximation
• Cubic approximation
• J. Goldfeather and V. Interrante. A novel cubic‐order
algorithm for approximating principal direction vectors.
ACM Transactions on Graphics 23, 1 (2004), 45–63.
• Implicit surface approximation
• Yutaka Ohtake et al. Multi‐level partition of unity 
implicits. Siggraph 2003.
• Many others…
Discrete Approximation
Normal Estimation
• Normal estimation on vertices
• Defined for each face
• Average face normals
• Weighted:  face areas, angles at vertex
• What happen at edges/creases?
Mean Curvature
•
由Laplace‐Beltrami定理：
Gauss Curvature
•
由Gauss‐Bonnet定理：
Gaussian Curvature Estimate 
– Example
Mean Curvature Estimate 
– Example 
Mean Curvature
More…
• MEYER M., DESBRUN M., SCHRÖDER P., BARR A.: 
Discrete differential‐geometry operators for 
triangulated 2‐manifolds. In Visualization and 
Mathematics III, Hege H.‐C., Polthier K., (Eds.). 
Springer, 2003, pp. 35–58. (PDF)
References
• TAUBIN G.: Estimating the tensor of curvature of a surface from a polyhedral approximation. In Proc. 
International Conference on Computer Vision (1995), pp. 902–907.
• MEYER M., DESBRUN M., SCHRÖDER P., BARR A.: Discrete differential‐geometry operators for triangulated 2‐
manifolds. In Visualization and Mathematics III, Hege H.‐C., Polthier K., (Eds.). Springer, 2003, pp. 35–58.
• CAZALS F., POUGET M.: Estimating differential quantities using polynomial fitting of osculating jets. In 
Eurographics Symposium on Geometry Processing (2003), pp. 177–187.
• COHEN‐STEINER D., MORVAN J.: Restricted delaunay triangulations and normal cycle. In Proc. ACM 
Symposium on Computational Geometry (2003), pp. 312–321.
• GOLDFEATHER J., INTERRANTE V.: A novel cubic‐order algorithm for approximating principal direction vectors. 
ACM Transactions on Graphics 23, 1 (2004), 45–63.
• MARTIN R. R.: Estimation of principal curvatures from range data. International Journal of Shape Modeling 4, 
1 (1998), 99–109.
• OHTAKE Y., BELYAEV A., SEIDEL H.‐P.: Ridge‐valley lines on meshes via implicit surface fitting. ACM 
Transactions on Graphics 23, 3 (2004), 609–612. (Proc. SIGGRAPH’2004).
• PAGE D., SUN Y., KOSCHAN A., PAIK J., ABIDI M.: Normal vector voting: Crease detection and curvature 
extimation on large, noisy meshes. Graphical Models 64, 3‐4 (2002), 199–229.
极小曲面
极小曲面
• 平均曲率处处为
0的曲面
极小曲面


极小曲面的例子
建筑中的极小曲面：膜结构





极小曲面及平均曲率流
• 平均曲率处处为
0
 
( )
1
N i i d

i i
  
v
δ vv  
1
( )
ds
len




 i
v
v v
  () 0
1 lim ( ) ( ) len ds H
 len




 
 i ii
v
v v vn

H( ) 0, 

i
i
v
Laplace Operator (Umbrella Operator)
 
Q
P
n
PQ
n
L
P
n
i
i
n
i

 i 


1 1
1
1
Median direction
Pold
L
Qk
Qk
1
Qk
1
离散平均曲率流
Pnew

Pold

 H
(
Pold
)
n
(
Pold
)
Pold
Hn
Pold
Move each vertex
Hn
Pnew
Direction = normal 
Speed = discrete mean curvature 
Discrete Mean Curvature




2
P
Hn





j
H
j
j
j (cot cot )(
)
4
1
n


P
Q
P
Q
j
j
j
离散极小曲面的局部迭代法
• 找到边界
• 固定边界顶点
• 对每个内部顶点
• 找顶点1‐邻域
• 更新其坐标
• 迭代
• 更新所有顶点法向
• 【注】
• 只能对非封闭曲面（带一条边界）操作
• 更新坐标需要用老的顶点坐标
• 尝试试验不同的参数𝜆 
（𝜆 ൌ 0.1
）
例子
封闭曲面
• 不固定任何顶点
• 迭代结果如何？
作业6
• 任务：实现极小曲面的局部法
• 寻找非封闭三角网格曲面的边界
• 每个顶点更新坐标
• 迭代给定次数 或 迭代至收敛
• 目的
• 学习三角网格的半边数据结构及操作
• 框架：
• Utopia （推荐）
• 其他
• 【可选】计算三角网格顶点的离散高斯曲率和平均曲率 并用颜色进行可视化
• Deadline：2020 年12 月5日晚
附加：如何构造曲面边界？
• 3D空间封闭曲线
• 已知的非封闭曲面
• 自己构造：平面曲线变形
• 初始网格
• 自己构造
• 平面：Delaunay三角化（学习Triangle库）
• 空间变形: Warping
Triangle
http://www.cs.cmu.edu/~quake/triangle.html

![](../assets/表达21-1.png)   

谢 谢！