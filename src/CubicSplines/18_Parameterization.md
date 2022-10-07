![](../assets/采样46.png)    
几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
曲面参数化
GAMES 102在线课程：几何建模与处理基础
回顾：低维空间的参数曲线
/曲面
回顾：R3中的参数曲面
• 本质是二维的（二维流形）
• 曲面的每个点对应与参数域上的一个点（称为参数）
4
ሺ𝑢, 𝑣ሻ ↦ ቐ𝑥ൌ𝑥 𝑢, 𝑣 , 𝑦ൌ𝑦 𝑢, 𝑣 , 𝑧ൌ𝑧 𝑢, 𝑣 ,
𝑓: Ω → 𝑆 
Parameter domain Embedded (ambient) space
逆问题：参数化(Parameterization)
• 问题：给定一张曲面，如何找其二维的参数定义域？
• 又称为：曲面展开(flattening)
5
𝑅
ଷ
𝑅
ଶ
𝑆
Ω
𝑓
𝑓: 𝑆
⊂
𝑅
ଷ
→
Ω
⊂
𝑅
ଶ Find a mapping 𝑓: 𝑆 ⊂ 𝑅
ଷ →Ω⊂𝑅
参数化的重要性
• 例子：
B样条曲面拟合
参数化的应用‐1
• 地图绘制（地理学）
参数化的应用‐2
• 纹理映射
参数化的应用‐3
• 曲面绘画
参数化的应用‐4
• 大部分几何处理的基础（基本问题）
• Visualization
• Texture mapping
• Matching
• Compression
• Remeshing
• Reconstruction
• Rendering
• Animation
•
…
理想的参数化？
• But: only for developable surfaces
i.e., there will always be distortions!
A: One that preserves all the basic geometry  
length, angles, area, …
 Isometric parameterization
 Try to keep the distortion as small as possible
参数化期望保持的几何性质
• 保角映射(angle‐preserving)：conformal（共形）
• 保面积映射(area‐preserving)：authalic
• 等距映射(isometric)：conformal + authalic
𝑅
ଷ
𝑅
ଶ
𝑆
Ω
𝑓
Metric of Distortion
• is approximated by piecewise linear maps 
between pairs of triangles
𝑅
ଷ
𝑅
ଶ
𝑆
Ω
𝑓
Linear map
Isometric Flattening
Isometric Flattening
Isometric Flattening









0
1
L
t
Distortion Measure
*
2
1
0
0
L
U
V










𝜎ଵ
𝜎ଶ

2

1
Distortion Measure
𝜎ଵ
𝜎ଶ
• angle‐preserving (conformal
)
ଵ
ଶ
• area‐preserving (authalic)
ଵ
ଶ
• length‐preserving (isometric
)
ଵ
ଶ
Desired Property: Low distortion
High distortion
Problem Local Injectivity
Problem Local Injectivity
Flip / Foldover
Desired Property: Flip free triangles
Flip/Foldover triangles
Distortion
 2
1
Distortion
 2
1
Distortion
 2
1
Distortion (Flip/Foldover)

2
1
Methods of Mesh Parameterization
• Tutte’s method and its variants
• Tutte’s method [Tutte 1963; Floater 1997, 2003]
• Variants [Weber and Zorin 2014; Aigerman and Lipman 2015,  2016; Aigerman et al. 2017; Bright et al. 2017; ]
• Geometry‐based optimization methods
• Representation based methods [Sheffer and Sturler 2001;  Sheffer et al. 2005; Chien et al. 2016b; Fu and Liu 2016]
• ARAP [Sorkine and Alex 2007; Liu et al. 2008]
• Bounded distortion methods [Lipman 2012; Aigerman et al.  2014; Kovalsky et al. 2015]
• Foldover free guaranteed optimization methods
• [Smith and Schaefer 2015; Kovalsky et al. 2016; Jiang et al.  2017; Claici et al. 2017; Rabinovich et al. 2017; Shtengel et al.  2017; Zhu et al. 2018]
Methods of Mesh arameterization
• Tutte’s method and its variants
• Tutte’s method [Tutte 1963; Floater 1997, 2003]
• Variants [Weber and Zorin 2014; Aigerman and Lipman 2015,  2016; Aigerman et al. 2017; Bright et al. 2017; ]
• Geometry‐based optimization methods
• Representation based methods [Sheffer and Sturler 2001;  Sheffer et al. 2005; Chien et al. 2016b; Fu and Liu 2016]
• ARAP [Sorkine and Alex 2007; Liu et al. 2008]
• Bounded distortion methods [Lipman 2012; Aigerman et al.  2014; Kovalsky et al. 2015]
• Foldover free guaranteed optimization methods
• [Smith and Schaefer 2015; Kovalsky et al. 2016; Jiang et al.  2017; Claici et al. 2017; Rabinovich et al. 2017; Shtengel et al.  2017; Zhu et al. 2018]
Tutte’s embedding method
Map the triangulation within a convex boundary by 
solving a sparse linear system
[Floater. Parametrization and smooth approximation of surfaces. CAGD 1997.]
, 1, , 0 1
,
{ :( , ) edges}

 , 




k
i
k
k i j
d
k
i j
j i j
pi i j
p
k


Tutte’s embedding method
Map the triangulation within a convex boundary by 
solving a sparse linear system
Foldover‐free result with a theoretical guarantee
Theorem [Tutte,63], [Maxwel,1864] : 
• If G=<V,E> is a 3‐connected planar graph (triangular mesh) 
then any barycentric embedding provides a valid 
parameterization.
Tutte’s embedding method
Map the triangulation within a convex boundary by 
solving a linear system
Foldover‐free result with a theoretical guarantee
Usually high distortion
Convex boundary High distortion
High
Low
[Tutte 1963; Floater 1997, 2003]
Variants of Tutte’s embedding method
Foldover‐free result with theoretical guarantees
Euclidean‐orbifold
[Aigerman et al. 2015]
Spherical‐orbifold
[Aigerman et al. 2017]
Hyperbolic‐orbifold
[Aigerman et al. 2016]
Methods of Mesh arameterization
• Tutte’s method and its variants
• Tutte’s method [Tutte 1963; Floater 1997, 2003]
• Variants [Weber and Zorin 2014; Aigerman and Lipman 2015,  2016; Aigerman et al. 2017; Bright et al. 2017; ]
• Geometry‐based optimization methods
• Representation based methods [Sheffer and Sturler 2001;  Sheffer et al. 2005; Chien et al. 2016b; Fu and Liu 2016]
• ARAP [Sorkine and Alex 2007; Liu et al. 2008]
• Bounded distortion methods [Lipman 2012; Aigerman et al.  2014; Kovalsky et al. 2015]
• Foldover free guaranteed optimization methods
• [Smith and Schaefer 2015; Kovalsky et al. 2016; Jiang et al.  2017; Claici et al. 2017; Rabinovich et al. 2017; Shtengel et al.  2017; Zhu et al. 2018]
Angle Based Flattening (ABF) & ABF++ 
[Sheffer and Sturler 2001; Sheffer et al. 2005]
• Triangular 2D mesh is defined by its angles
• Define problem in angle space
• Angle based formulation
• Distortion as function of angles
• Validity ‐ set of angle constraints
Constrained Minimization
• Notations:
• Objective: minimize (relative) deviation of angles
Initial choice for weights:
Constraints
• To avoid flipped triangles
Solution
• Use Lagrange Multipliers
• Solve the min‐max problem (minimum on α, maximum 
on µ)
• Reached when all derivatives are zero
• Have non‐linear system of equations
• Use Newton method to solve
Examples
As‐rigid‐as‐possible (ARAP) [Liu et al. 2008]
• Measuring the approximation between the linear 
mapping and the rigidity (the optimal rotation)
• Local/global optimization
• Local: compute singular values
• Global: solve linear systems
• No theoretically guaranteed to avoid foldovers
[Ligang Liu et al. A Local/Global Approach to Mesh Parameterization.  SGP 2008.]
Simplex Assembly [Fu and Liu 2016]
Instead of vertex positions, treat the affine 
transformation as variables
Use a barrier function to prevent the inversion
No theoretically guaranteed to avoid foldovers
[Fu and Liu. Computing Inversion‐Free Mappings by Simplex Assembly. Siggraph Asia 2016]
Methods of Mesh arameterization
• Tutte’s method and its variants
• Tutte’s method [Tutte 1963; Floater 1997, 2003]
• Variants [Weber and Zorin 2014; Aigerman and Lipman 2015,  2016; Aigerman et al. 2017; Bright et al. 2017; ]
• Geometry‐based optimization methods
• Representation based methods [Sheffer and Sturler 2001;  Sheffer et al. 2005; Chien et al. 2016b; Fu and Liu 2016]
• ARAP [Sorkine and Alex 2007; Liu et al. 2008]
• Bounded distortion methods [Lipman 2012; Aigerman et al.  2014; Kovalsky et al. 2015]
• Foldover free guaranteed optimization methods
• [Smith and Schaefer 2015; Kovalsky et al. 2016; Jiang et al.  2017; Claici et al. 2017; Rabinovich et al. 2017; Shtengel et al.  2017; Zhu et al. 2018]
Flip‐free parameterization methods
• Start with a flip‐free (valid) initialization
• Reducing the distortion while guaranteeing the validity
• Generally non‐convex nonlinear optimization
Valid Initialization Optimized result Optimization
Low distortion cost functions
 Conformal
[Degener et al. 2003]
𝜎ଶ
𝜎ଵ
 MIPS
[Hormann and Greiner 2000]
𝜎ଵ
𝜎ଶ
൅
𝜎ଶ
𝜎ଵ
 Maximal Isometric Distortion 
[Sorkine et al. 2002]
max ሺ𝜎ଶ,
1
𝜎ଵ
ሻ
 Isometric
[Aigermann et al. 2014]
𝜎ଶ
ଶ ൅
1
𝜎ଵ
ଶ
 Symmetric Dirichlet energy
[Smith and Schaefer 2015]
𝜎ଵ
ଶ ൅
1
𝜎ଵ
ଶ ൅ 𝜎ଶ
ଶ ൅
1
𝜎ଶ
ଶ
Formulation of Optimization
• The cost function is highly nonlinear and nonconvex
• The constraints are nonlinear
• The Heissian matrix is highly non‐definite
s.t
.
min
௏ 𝐸ሺ𝑉ሻ ൌ ෍ሺ𝜎ଵ
ଶ
൅
1
𝜎ଵ
ଶ ൅ 𝜎ଶ
ଶ
൅
1
𝜎ଶ
ଶ
ሻ
௧∈்
𝜎ଵ
𝜎ଶ ൐ 0, ∀𝑡
Computationally expensive for large scale meshes!
Solver for the optimization
Input: a valid parameterization initialization 
𝑥
଴
Repeat 
𝒑ൌെ
𝐻ିଵ𝛻𝐸
𝒙
𝛼௠௔௫
← injective maximal search step
𝛼 ←line search by backtracking from 
𝛼௠௔௫
𝒙 ← 𝒙 ൅ 𝛼𝒑
Until converged
Output: a locally injective parameterization
Optimization formulation:  min௫
𝐸 𝑥 ൌ
∑
𝐸
௧ሺ𝑥ሻ
௧
How to find a good decent direction?
Maximal Search Step
Explicitly limit the maximal line search step to 
prevent foldover
Use a locally supported barrier function to 
prevent the boundary collision
Solver: L‐BFGS
Smith and Schaefer. Bijective Parameterization with Free Boundaries. Siggraph 2015.
𝑑𝑒𝑡
𝑈ଶ ൅ 𝑉ଶ𝑡 െ ሺ𝑈ଵ ൅ 𝑉ଵ𝑡ሻ
𝑈ଷ ൅ 𝑉ଷ𝑡 െ ሺ𝑈ଵ ൅ 𝑉ଵ𝑡ሻ ൌ 0
max 0,
𝜖
𝑑𝑖𝑠𝑡
𝑈௜, 𝑈ଵ𝑈ଶ
െ 1
ଶ
Kovalsky et al. Accelerated Quadratic Proxy for Geometric Optimization. Siggraph 2016.
 discrete Laplacian L
Acceleration
First‐order method
Accelerated Quadratic Proxy (AQP)
Rabinovich et al. Scalable Locally Injective Mappings. Siggraph 2017.
 reweighted Laplacian L
Compute the weight matrix 
௃ by the matching  gradients condition
௃
ௐ
ோ
௃ ோூ
Quickly recovers from a bad initialization, but 
slowly converge to a local minimum
First‐order method
Scalable Locally Injective Mappings (SLIM)
Claici et al. Isometry‐Aware Preconditioning for Mesh Parameterization. SGP 2017.
 approximate killing vector field operator 
 converts the local distortion gradient into 
a global near‐rigid decent direction
First‐order method
Isometry‐Aware Preconditioning (AKVF)
Shtengel et al. Geometric Optimization via Composite Majorization. Siggraph 2017.
Use a tight convex proxy to approximate the 
objective function by convex‐concave 
decomposition
 ଶ ା
Second‐order method
Composite Majorization (CM)
𝐸ൌ𝐸ା ൅ 𝐸ି
Zhu et al. Blended Cured quasi‐Newton for Distortion Optimization. Siggraph 2018.
Blended Cured Quasi‐Newton (BCQN)
Blended quasi‐Newton method
Barrier‐aware line search filtering
Second‐order method
Progressive Paramerization
• Key observations
• Near‐degenerate triangles (i.e., large distortion) in the initializations 
by Tutte’s method
• Small iterative step and slow convergence in existing methods
• Key: even one extremely large distortion term can restrict the line 
search step size!
[Ligang Liu et al.  Progressive Parameterizations. Siggraph 2018]
Idea: If we kill extremely large distortion 
terms, we may obtain larger line search 
step size and thus faster convergence!
Input: a 3D 
triangular mesh 
+ initialization
Construct 
new 
references
Update 
Parameterization
Final 
Optimization
Output 2D 
parameterization
Progressive Paramerization
[Ligang Liu et al.  Progressive Parameterizations. Siggraph 2018]


Bijective Parameterizations
Bijective Parameterization
• Globally intersection‐free
Intersection Intersection‐free 
Quasi‐Newton (QN) [Smith et al. 2015]
Quasi‐Newton solver  with slow convergence!
Energy: 1.027
Time: 8.57s
Iterations: 3553
Scaffold [Jiang et al. 2017]
Linear systems with updated 
nonzero structure matrices!
Energy: 1.027
Time: 3.22s
Iterations: 24
Efficient Bijective Parameterizations
[Su et al. Siggraph 2020]
[Smith et al. 2015] [Jiang et al. 2017]
Slow convergence Updated scaffold mesh
[Su et al. 2020]
Much more efficient
Comparisons
© 2020 SIGGRAPH. ALL RIGHTS RESERVED.
15
© 2020 SIGGRAPH. ALL RIGHTS RESERVED.
封闭曲面的割缝问题
割缝问题：封闭曲面的参数化
• A closed surface cannot be flattened 
• A cut is needed to cut it open into a disk‐like patch
Existing Works
• Minimum spanning tree method 
• [Sheffer 2002; Sheffer and Hart 2002; Chai et al. 2018]
• Mesh segmentation approaches 
• [Julius et al. 2005; Lévy et al. 2002; Sander et al. 2002, 2003; 
Zhang et al. 2005; Zhou et al. 2004]
• Simultaneous optimization 
• [Poranne et al. 2017; Li et al. 2018]
• Variational method 
• [Sharp and Crane 2018]
Minimum spanning tree methods
• Nodes: extrema points with high 
curvature/distortion etc.
[Gu et al. 2002] [Chai et al. 2018]
AutoCuts [Poranne et al. 2017] OptCuts [Li et al. 2018]
Simultaneous optimization 
Variational Surface Cutting 
[Sharp and Crane 2018]
Computational Peeling Art Design
Hao Liu, Xiao‐Teng Zhang, Xiao‐Ming Fu, Zhi‐Chao Dong, Ligang Liu
USTC
Peeling art design
Yoshihiro Okada’s method
Cut Generation Problem
• Finding a cut such that its unfolding approximates a 
given input shape
Input 2D shape
Key idea: map 2D shape onto the surface
Cut generation
Difficult
Mapping computation
Easier
Mapping Result
Real peeling
Real peeling
Comparison to Yoshihiro Okada
Okada
Ours
Dove Eagle Shrimp
More Results
Real peeling of middle/elementary 
school students
Real Peeling Results
纹理地图：多片参数化
Texture Atlas
Multi‐charts Parameterization
One chart Multiple charts
Texture Atlas
Color Normal
images courtesy of Hoppe
Atlas Generation: 
Minimizing Packing Efficiency (PE)
• A packing problem: NP hard!
PE=45.6% PE=86.1%
Atlas Generation 
• Low Distortion
• [Golla et al. 2018; Liu et al. 2018; Shtengel et al. 2017; Zhu et al. 2018]
• Consistent orientation 
• [Floater 2003; Tutte 1963; Claici et al. 2017; Hormann and Greiner 2000; 
Rabinovich et al. 2017; Schüller et al. 2013]
• Bijection
• [Jiang et al. 2017; Smith and Schaefer 2015]
• Low boundary length
• [Li et al. 2018; Poranne et al. 2017; Sorkine et al. 2002]
• Packing efficiency
• Box cutter [Limper et al. 2018]
• Bounded Packing Efficiency [Liu et al. 2019]
Atlas Refinement: Higher PE
Higher PE
Box Cutter [Limper et al. 2018]
• Atlas refinement
• Remove overlaps
• Improve packing efficiency
• No additional distortion
• Bounded boundary length elongation
Axis‐aligned
construction
Bounded Packing Efficiency
Input: a 3D 
triangular mesh 
with atlas
Rectangle 
decomposition 
and packing
Output: refined 
atlas with 
bounded PE
[Liu et al. Atlas Refinement with Bounded Packing Efficiency. Siggraph 2019.]
PE Bounds
PE=80.4% PE=92.6%
Different PE Bounds
Input PE=80% PE=85% PE=90%
球面参数化
问题：球面参数化
• 输入：亏格为
0的封闭曲面（拓扑同胚于球面）
C
球面参数化的主要方法
• Direct methods
• [Kent et al. 1992], [Kobbelt et al. 99], [Gu et al. 03]
• Optimization methods
• [Sheffer et al. 04], [Li et al.06&07], [Zayer et al.06], 
[Friedel et al., 07], [Kazhdan et al. 2012], [Wan et al. 
12&13], [Wang et al., 14&16]
• Coarse‐to‐fine methods
• [Praun and Hoppe 04], [Tang et al. 16], [Hu et al. 17]
Our Works on Spherical Parameterization
ARAP method [Wang et al. 2014] AMIPS method [Wang et al. 2016]
Hierarchical method [Hu et al. 2017]
http://staff.ustc.edu.cn/~lgliu
Mapping between Mesh Surfaces
 相容性网格（Compatible mesh）：一组具有相同连接关系且与给定模型形
状近似的网格
采样点一一对应
三角面片一一对应
Our Works on Compatible Mappings
Yang et al. Siggraph 2020 Yang et al. IEEE TVCG 2019
Yang et al. Pacific Graphics 2019 Su et al. Pacific Graphics 2019
http://staff.ustc.edu.cn/~lgliu
总结：曲面参数化
• 几何处理的基本问题：大量的应用
• 是一个从3D
到2D的降维问题：将几何数据表达
为图像
• 特殊的几何结构（三角网格）：特殊的优化方法
• Next: 大型场景的压缩、传输、调度、渲染
…
虚幻
5：宣传片 Virtual geometry
Future Work and Challenges
• Fundamental problem for CG 
(geometry/simulation/rendering)
• Trade‐of quality/efficiency/complexity
• Coupled solution
• Parameterizaiton, cutting, atlas
• Other methods
• Diffusion for optimization
• Better initializations than Tutte’s method
• Learning based methods
谢 谢！