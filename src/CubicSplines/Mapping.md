# 几何映射
 

# 回顾：曲面参数化   

• 问题：将空间曲面展开到二维平面    
• 本质：寻求一个映射\\(f:S\subset R^3\to\Omega \subset R^2\\)   

![](../assets/映射1.png)  

# 映射（ Mapping / Map ）   

![](../assets/映射2.png)  



# 映射（ Mapping / Map ）   

![](../assets/映射3.png)  



# 本节课：平面几何映射   

• 映射表达：

$$
f:\mathbb{R} ^2\to\mathbb{R} ^2
$$

$$
f(X)=\begin{pmatrix}u(x)
 \\\\v(x)
\end{pmatrix}
$$

$$
X=(u,v)\overset{f}{\rightarrow} (u(X),v(X))
$$


# 映射的表达    


# 映射的表达：化繁为简   

* 映射表达为基本映射（基函数）的线性组合    
• 函数的分解   

* 映射表达为小区域（三角形区域）上映射的拼接   
• 区域的分解（映射的离散）   



# 映射：基函数的线性组合    


• 基函数(basis functions):   

$$
f_1,f_2,f_3,\cdots ,f_n
$$

• 基函数的线性组合：   

$$
f(X)=\begin{pmatrix}u(X)
 \\\\v(X)
\end{pmatrix}=\begin{pmatrix}\sum a_if_i(X)
 \\\\\sum b_if_i(X)
\end{pmatrix}
$$

![](../assets/映射4.png)  

![](../assets/映射5.png)  

![](../assets/映射6.png)  


# 映射的表达：化繁为简   

* 映射表达为基本映射（基函数）的线性组合    
• 函数的分解    

* **映射表达为小区域（三角形区域）上映射的拼接**    
• **区域的分解**（**映射的离散**）    



# 映射：简单区域上映射的连续组合   


• \\(f\\) is approximated by **piecewise linear maps** between pairs of triangles    

![](../assets/映射7.png)  

# 几何映射的例子    

# 例1：2D变形   

![](../assets/映射8.png)  


# 本质：插值问题   

![](../assets/映射9.png)  

$$
f(P_i)=\sum c_if_i(X)
$$

$$
c_i=?
$$

$$
f(P_i)=q_i,\forall i
$$

$$
\sum c_if_i(P_i)=q_i,\forall i
$$


# 求解    

• 插值法（比如，RBF插值）    

$$
f(p_i)=C_0+c_xx+c_yy+\sum c_i\phi (||X-P_i||)
$$

$$
\phi (r)=r^2\log r
$$

$$
f(P_i)=q_i,\forall i
$$

• 逼近法（能量极小法）    

$$
\min E_{TPS}(f)=\iint [(\frac{\partial ^2f}{\partial x^2} )^2+2(\frac{\partial ^2f}{\partial x\partial y} )^2+(\frac{\partial ^2f}{\partial y^2} )^2]
$$

Bending energy   

$$
s.t. f(P_i)=q_i,\forall i
$$


# 更多约束   

• Hermite插值：插值梯度    

![](../assets/映射10.png)  

$$
f(P_i)=q_i            
$$

$$
Df(P_i)=D_i            
$$


# 例2: Barycentric Coordinates   

Stages:    
• Source shape    
• Polygonal cage    
• Coordinates   

![](../assets/映射11.png)  

$$
f(X)=\sum_{i=1}^{n} \alpha _i(X)q_i
$$


# 例2: Barycentric Coordinates    

Stages:    
• Source shape    
• Polygonal cage    
• Coordinates    

![](../assets/映射12-1.png)  

$$
f(X)=\sum_{i=1}^{n} \alpha _i(X)q_i
$$


# 例2: Barycentric Coordinates   


Stages:   
• Source shape    
• Polygonal cage    
• Coordinates    
• Manipulate cage    
• Apply deformation    

![](../assets/映射13.png)  

$$
f(X)=\sum_{i=1}^{n} \alpha _i(X)q_i
$$


# 映射的性质   


# What are good maps?   

![](../assets/映射14.png)  


# Flip (foldover) triangles in mapping    

![](../assets/映射15.png)  


# Locally injective mappings    

![](../assets/映射16.png)  

Flip‐free (foldover‐free) mapping   



# Globally Bijective VS. Locally Bijective   


![](../assets/映射15-1.png)  


# Globally Bijective VS. Locally Bijective   

![](../assets/映射15-1.png)    

![](../assets/映射17.png)  


  

# Globally Bijective VS. Locally Bijective   

![](../assets/映射15-1.png) 


![](../assets/映射18.png)  


# Globally Bijective VS. Locally Bijective   

![](../assets/映射15-1.png) 

![](../assets/映射19.png)  


# Globally Bijective VS. Locally Bijective    

![](../assets/映射20.png)  

Only Locally Bijective   

![](../assets/映射21.png)  


# Locally Bijection – Non‐example   

![](../assets/映射22.png)  


# Locally Bijection – Non‐example    

![](../assets/映射23.png)  


# Locally Bijection – Non‐example    

![](../assets/映射24.png)   


# Locally Bijection – Non‐example    

![](../assets/映射25.png)  



# Locally Bijection – Sufficient condition  

![](../assets/映射26.png)  


# Globally Bijective VS. Locally Bijective   

![](../assets/映射15-2.png)  


Globally Bijective VS. Locally Bijective

![](../assets/映射27.png)  



Google: “Global inversion theorems”    


# What are good maps?   

![](../assets/映射28.png)  


# Jacobian的几何意义   

• 函数在某点的Jacobian度量了其局部的形变量    

![](../assets/映射29.png)  


# Distortion Measure    

$$
L=U\begin{pmatrix}
\sigma _1  & 0\\\\
0  &\sigma _2 
\end{pmatrix}V^*
$$

$$
\sigma _2\ge \sigma _1
$$

![](../assets/映射30.png)  


• angle‐preserving (conformal) \\(\sigma _1= \sigma _2\\)    

• area‐preserving (authalic) \\(\sigma _1\sigma _2=1\\)    

• length‐preserving (isometric) \\(\sigma _1=\sigma _2=1\\)   



# Distortion Metric   

![](../assets/映射31.png)  



# 映射的优化模型    


# Recap: Formulation of Parameterization   


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
Computing maps
Computing maps
Computing maps
Computing maps
Computing maps
Computing maps
• Imposing constraints
• Finding maps that are most…
Energy
Constraints
Constrained Optimization
஍
Φ
Energy
Φ
Energy
Φ
uଵ
uଶ uଷ
vଵ
vଶ
vଷ
Energy
Φ୨ 𝑥 ൌ𝐴௝𝑥൅𝛿௝
𝐸 𝛷 ൌ𝐸 𝐴ଵ,…,𝐴௠
Map optimization
• In terms of differentials:
ଵ
୫
A୨
Map optimization
• In terms of differentials:
௝
௝
Separable
A୨
Map optimization
Must impose continuity!
Φ
௝
௝
Explicit continuity
• Optimization variables: 
ଵ
ଶ
௠
• Adjacent 
௝’s must agree
𝐴௜
𝐴௝
𝑣
ଵ
𝑣
ଶ
𝐴௜𝑣
ଵ
𝐴௜𝑣
ଶ
𝐴௝
𝑣
ଶ
𝐴௝
𝑣
ଵ
Explicit continuity
• Optimization variables: 
ଵ
ଶ
௠
• Adjacent 
௝’s must agree
𝐴௜
𝐴௝
𝑣
ଵ
𝑣
ଶ
௜
ଵ
௝
ଵ
௜
ଶ
௝
ଶ
Implicit continuity
௜
ଵ
ଶ
ଷ
ଵ
ଶ
ଷ
௜
ଵ
ଶ
ଷ
ଵ
ଶ
ଷ
ற
௜
௜
𝐴௜
𝑣
ଵ
𝑣
ଶ
𝑣
ଷ
𝑢
ଵ
𝑢
ଶ
𝑢
ଷ
Linearly express 
௜’s in terms of 
Implicit continuity
• Optimization variables: 
ଵ
ଶ
௡
(
)
𝐴௜
𝑣
ଵ
𝑣
ଶ
𝑣
ଷ
𝑢
ଵ
𝑢
ଶ
𝑢
ଷ
௝
௝
几何优化的求解
Popular energies
௝
௝
Dirichlet
஽ ௝ ௝ ி
ଶ
௝
Φ
area / volume
Dirichlet
஽ ௝ ௝ ி
ଶ
௝
Φ
Dirichlet
஽ ௝ ௝ ி
ଶ
௝
Φ
𝐴௝ ⇢ 0
Orthogonal and Similarity
• is orthogonal if 
் ିଵ
(rotation if det 𝑅 ൐ 0)
• is a similarity if 
Closest  and 
• = closest orthogonal/rotation matrix to 
• = closest similarity matrix to 
• Computable using SVD/SSVD:
்;         ଵ ௡
• ் ்
• ்
mean of SVs
As‐Similar‐As‐Possible (ASAP)
௅
௝
௝
௝
ி
ଶ
௝
closest similarity
Solving sparse linear system!
As‐Rigid‐As‐Possible (ARAP)
ோ
௝
௝
௝
ி
ଶ
௝
closest rigid transformation
ARAP vs. ASAP
ARAP ASAP
Singular values perspective
Dirichlet
𝐴
ி
ଶ
∑
𝜎௞
ଶ
௞
LSCM 𝐴െ𝒮
𝐴
ி
ଶ
∑
𝜎௞ െ 𝜎
ଶ
௞
ARAP 𝐴െℛ
𝐴
ி
ଶ
∑
𝜎௞ െ 1
ଶ
௞
mean of SVs
ARAP: Alternating Optimization 
Local step
Global step
ோ
௝
௝
௝
ி
ଶ
௝
• Iteratively:
• Compute and fix 
𝑅௝ ൌ ℛ
𝐴௝
• Minimize
෍ 𝑤௝
𝐴௝
െ
𝑅௝
ி
ଶ
௝
[Liu et al. A Local/Global Approach to Mesh Parameterization. SGP 2008]












Alternating optimization
• Very general
• Related jargon:
gradient descent, global‐local, alternating projections
[Bouaziz et al. 2012]
Summary: Geometric Mapping
• Discrete Mapping
• Discrete formulation
Separable
• Nonlinear and nonconvex
• Computationally expensive for large scale meshes!
஍
Meshless mappings
116
• Low distortion
• Flip‐free
• Bijective
௜
௜
௠
௜ୀଵ
Geometric Mapping
• 其他区域间的映射求解
• 离散形式
• 约束条件
𝑓: 𝕄 → 𝕊
ଶ
𝑓:𝕄 → 𝕄ᇱ 𝑓: ℝ
ଷ → ℝ
ଷ
Fu et al. Inversion‐free Geometric Mapping Construction: A Survey. CVM, 2021
谢 谢！