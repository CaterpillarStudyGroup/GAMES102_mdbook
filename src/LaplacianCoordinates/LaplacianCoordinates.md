

# 3D网格曲面：二维流形曲面的离散    

• 平面图在3D空间中的嵌入 \\(f:R^2\to R^3\\)    

![](../assets/网格1.png)   


# Cardinal Coordinates   

 - (x,y,z) coordinates    
> v 1.5 -0.960751 -1.2232    
  v 0.81 -0.891238 -3.74258   
  v 0.16 -0.233535 -2.28405   
  v 1.49 -2.44325 -3.6962   
  v 1.59 -2.98815 -4.15761   
  v 1.66 -2.81016 -4.10777   
  v 1.41 -1.14861 -1.92823   
  v 1 -1.40023 -3.80159   
  v 0.88 -1.33122 -3.83517   
  …   
  f 1 2 3   
  f 2 4 5   
  …   

![](../assets/网格2.png)   

# 图的连接关系：点、边、面    

![](../assets/网格3.png)   


# 存储数据结构：半边结构    

![](../assets/网格4.png)   

# Local Structure   

 - Small‐sized Cells    
    - 1‐ring neighborhood （1‐邻域）    
    - 一般“流形”结构也是通过局部邻域来定义   

    ![](../assets/网格5.png)   

> 一个点的信息通常由它周围的顶点和面片来决定。     
对于离散几何来说，无穷小邻域性质就通过 l 邻域来分近似。   
­离散观点：直接取邻域点的特征来计算酯前点的特征     
连续观点：取邻域点拟合成曲面，然后分析曲面在该点处的特征。   

# 局部特征度量：1‐邻域   

 - Detail = surface – smooth (surface)     
 - Smoothing = averaging    
![](../assets/网格6.png)   

> 黄点、蓝点的加权平均，可以用各种加权方式。    
黄色向量：拉普拉斯算子，可以描述红点的尖锐承度。   

# Laplace算子(operator)    

• \\(n\\)维欧几里得空间的二阶微分算子（椭圆型算子）   
• 梯度 \\(\nabla f\\) 的散度 \\(\nabla \cdot f\\)   

$$
\Delta f=\nabla \cdot \nabla f=\nabla^{2} f
$$

• 在笛卡尔坐标系中，为所有非混合二阶偏导数：

$$
\Delta f=\sum_{i=1}^{n} \frac{\partial^{2} f}{\partial x_{i}^{2}}
$$


• 特别地，对二元实函数\\(f(x,y)\\)：    

$$
\Delta f=\frac{\partial^{2} f}{\partial x^{2}}+\frac{\partial^{2} f}{\partial y^{2}}
$$

> 梯度是一个向量，散度指向量各个分量之和。    
此页中是连续形式的 Laplace 算子。   

# Laplace‐Beltrami 算子    


• 推广：定义在黎曼流形上的椭圆型算子    

$$
\nabla ^2f=\nabla \cdot \nabla f
$$

$$
\Downarrow 
$$

$$
\nabla ^2f=\frac{1}{\sqrt{|g|} } \partial _i(\surd |g|g^{ij}\partial _jf).
$$



# Differential Coordinates （微分坐标）    

• 离散形式的 Laplacian 算子 (Umbrella Operator，
伞型算子):   

$$
\delta _i=\nu _i-\sum _{j\in N(i)}w_j\nu _j
$$

![](../assets/网格7.png)    

> 如何理解离散曲面的Laplace比算子？[23:40]    
2D场景： （图[24:39]）      
后向差分： 
$$
{f}' x=\frac{y_{i+1}-y_i}{x_{i+1}-x_i} 
$$
前向差分：
$$
{f}' x=\frac{y_i-y_{i-1}}{x_i-x_{i-1}} 
$$
3D的场景：
![](../RAW/75.1.png)  
① ② ③ ④ 看作是⑤的 l 邻域。    
推广到一般形式可得：\\(\delta _i\\)     
\\(\delta _i\\)称为 Laplace 算子，也叫 Laplace 坐标、微分坐标。    

# 平均曲率流定理   

![](../assets/网格8.png)    

> \\(\gamma \\)代表红点的邻域外围封闭曲线。    
\\(V_i 是红点， V是\gamma \\)手上的点。    
\\( len(\gamma) \\)代表曲线长度。    
\\(H(V_i)为 V_i\\) 的平均曲率。     
将此定理公式写成离散形式，与\\(\delta _i\\)公式相通。    
\\(\delta _i\\) 可以作为平均曲率的近似。    

# Geometric Meaning   


 - DCs represent the **local** detail / local shape description   
    - The direction approximates the normal    
    - The size approximates the mean curvature    

![](../assets/网格9.png)    


# Weighting Schemes     
(Barycentric coordinates)    


• Uniform weight (geometry oblivious)     

$$
w_i=1
$$

• Cotangent weight (geometry aware)     

$$
w_j=(\cot \alpha +\cot \beta )
$$

• Normalization    

$$
w_j=\frac{w_j}{\sum _jw_j} 
$$

![](../assets/网格10.png)    

$$
\delta _i=\frac{1}{d_i} \sum _{j\in N(i)}(\nu_i-\nu_j)
$$

> \\(l\\)邻域点加权平均的权有讲究,通常使用 cotangent.  

# Local Laplacian Smoothing    

# Differential Coordinates (Laplace Coordinates)    


 - Represent local detail at each surface point    
    - better describe the shape    
 - Linear transition from global to differential   
 - Useful for operations on surfaces where **surface details** are important   

![](../assets/网格10.png)    
$$
\delta _i=\frac{1}{d_i} \sum _{j\in N(i)}(\nu_i-\nu_j)
$$    


# Laplacian Smoothing Flow   

![](../assets/网格11.png)    

> 上节课的任意曲面到极小曲面的过程,是一种特殊的    
Local Lapluàn Smoothing.    
也可以看作是去噪、滤波。

# Laplacian Smoothing    

$$
P^{new}=P^{old}+\lambda L(P^{old})
$$

 - Equivalent to box filter in signal processing    
 - Apply to all vertices on mesh    
 - Typically repeat several times    
 - Can describe as energy minimization    
    - Energy = sum of squared edge lengths in mesh
    - Parameter \\(\lambda >0\\) controls convergence "speed"    

# Laplacian Smoothing – Example 

![](../assets/网格12.png)    


# Problem of Over‐smoothing   

How to find appropriate \\(\lambda\\) and number of iterations?   

![](../assets/网格13.png)    


# Mean Curvature Flow   

![](../assets/网格14.png)    

$$
\delta _i=\frac{1}{d_i} \sum _{\nu\in N(i)}(\nu_i-\nu)
$$

$$
\frac{1}{len(\gamma )} \int _{\nu\in \gamma }(\nu_i-\nu)ds
$$

$$
\lim_{len(\gamma ) \to 0} \frac{1}{len(\gamma )} \int _{\nu\in \gamma }(\nu_i-\nu)ds=H(\nu_i)n_i
$$


# Discrete Mean Curvature Flow   

![](../assets/网格15.png)    

 
# Discrete Mean Curvature   

$$
Hn=\frac{\nabla _PA}{2A} 
$$

$$
Hn=\frac{1}{4A} \sum _j(\cot \alpha _j+\cot \beta _j)(P-Q_j)
$$

![](../assets/网格16.png)    

# Properties of Mean Curvature Flow   

![](../assets/网格17.png)    

> Mean Curvature Flow 使用 cotangent 权，因此是Laplacian Smoothing 的特殊形式。     
对于 low densily mesh,\\(\delta _i\\) 比较长，如果使用普­通权，这种情况会收缩快。如果使用 cotangent 权，则不会。  

# Global Laplacian Smoothing    

> Local 方法存在的问题：  
> 1. 不同位置收敛速度不同    
2. 自交    

# 极小曲面(minimal surface)    

• 平均曲率处处为0   

![](../assets/网格18.png)    


# 局部迭代光顺方法的问题？   


• 注：通过作业6中已发现    

![](../assets/网格19.png)    


# 微分坐标一致为0    

![](../assets/网格20.png)    

 - 所有顶点的方程联立，得到网格曲面的整体
Laplacian方程：
$$
Ax = 0
$$

> 
$$
\alpha=(V_1,V_2,\dots ,V_n)^\tau 
$$
\\(A 的第 i 行为 L(V_i)的系数，即 V_i 的系数为1，V_j的系数为 — w_{ij}\\),其余为0.整体上非常稀疏。     
增加将边界点固定的约束。

# Laplacian Matrix   

• The transition between the \\(\delta and xyz\\)  is linear:     

![](../assets/网格21.png)    

$$
A_{ij}=\begin{cases}
 1 ,     i\in N(j)\\\\
  \\\\
0, otherwise
\end{cases}
$$

$$
D_{ij}=\begin{cases}
 d_i,     i=j\\\\
  \\\\
0, otherwise
\end{cases}
$$

$$
L=I-D^{-1}A
$$


# Laplacian matrix    
• The transition between the \\(\delta \\) and \\(xyz\\) is linear:    

![](../assets/网格22.png)    


# Reconstruction    

• From relative coordinates to absolute coordinates.    
• Solving a sparse linear system     

$$
Lv=\delta
$$

![](../assets/网格23.png)    

> 如果用L表示邻接关系，\\(\delta\\)已知，就可以重建出0.   
不断减小\\(\delta\\)而更新V,得到极小曲面。    

# Basic properties    

• Rank(L) = n‐c (n‐1 for connected meshes)    
• We can reconstruct the \\(xyz\\) geometry from delta up 
to translation   
$$
LX=\delta
$$

> L 非满秩， C 为 mesh 的联通个数，至少为1.    
必须增加额外约束是L满秩。 

# 极小曲面生成的全局方法    

* 检测边界，固定边界    
* 构建稀疏方程组\\((\delta=0)\\)     
* 求解稀疏方程组     
• 【注：有高效的求解方法，且有成熟的数学库可使用】    
* 更新内部顶点坐标    

![](../assets/网格24.png)    

> 更正一下，不是慢慢减\\(\delta\\)迭代更新V,而是直接令\\(\delta=0\\)     
数学库： MLK, Eigen  

# Mesh Parameterization (Mesh Flattening)     
曲面参数化   


# 2D Manifold Surfaces in \\(R^3\\)   

* A surface \\(S\\) in \\(R^3\\) has an **intrinsic dimension** of 2D   
•a patch \\(\Omega\\) in \\(R^2\\) is embedded into \\(R^3\\) (each point in \\(\Omega\\) is assigned a position in \\(R^3\\))    

![](../assets/网格25.png)    



# Parametric Surfaces    

![](../assets/网格26.png)    

$$
f:\Omega \to S
$$

$$
(u,v)\to \begin{cases}
 x= x(u,v),\\\\
 y= y(u,v),  \\\\
 z= z(u,v),
\end{cases}
$$

# 曲面展开（参数化）   

![](../assets/网格27.png)    


# 参数化：将曲面展开成平面    

* 每个3D顶点(\\(x,y,z\\))对应一个2D点(\\(u,v\\))    
• (\\(u,v\\)) 称为 (\\(x,y,z\\)) 的参数（2D流形曲面的本征维数）    

![](../assets/网格28.png)    

>   1. 三角形不能发生翻转。    
2. 三角形的扭曲能够保持。    
3. 边界不要自交。    
参数化的係用：1. 贴纹理     
  
# 但，球面是不可展的，必有形变    

![](../assets/网格29.png)    


> 思考：   
1.地图上的两点之间的距离是真实距离吗？哪些地方的距离可信度更高？    
2.地图上看，哪些区域的面积被放大了？    


# 传统横板地图    

![](../assets/网格30.png)    


沿经线切开    

# 新型竖板地图    

![](../assets/网格31.png)    
   


# 北京‐纽约的最短路径   

![](../assets/网格33.png)    


# 参数化是几何处理中的基本问题    

* 提供了三维曲面每个点的一个二维参数     
• 本征维数参数      

* 在低维来处理高维问题，减少复杂度    
• 降维    

* 三维曲面之间的相关问题可通过参数化空间来处理      


# 给定边界的极小曲面    

• 如果边界刚好在一个平面上（共面）？    

![](../assets/网格34.png)    

# 将边界映射到平面的凸多边形上    [Floater 97’]

• Fixing the boundary of the mesh onto   

![](../assets/网格35.png)    

M. Floater. Parametrization and smooth approximation of surface triangulations. CAGD, 1997.    
<http://www.cs.jhu.edu/~misha/Fall09/Floater97.pdf>    


# 方法：求解稀疏方程组   

![](../assets/网格36.png)    

\\(\Rightarrow\\) Forming a sparse linear system    

> 还是之前 Global Laplacian Smoothing 求极小曲面的原理。    
但是为什么要把边界点放右边呢？右边还是\\(\delta\\)吗？    

# Tutte’s Method: Why it Works   


 - Theorem [**Tutte**,63], [Maxwel,1864] :     
    - If G=<V,E> is a 3‐connected planar graph (triangular mesh) then any barycentric embedding provides a **valid** parameterization    

![](../assets/网格37.png)    

> 如果边界位于凸多边形上，则三角形一定不会发生翻转！   
 

# 参数化：操作步骤    

• 检测边界    
• **将边界映射到正方形边界或圆边界（凸边界）**   
• 构建稀疏方程组    
• 求解稀疏方程组    
• 更新顶点坐标    
• **连接纹理图像，更新显示**    


# Floater参数化方法   [Floater 97’]

• Uniform parametrization    
• Weighted least squares parametrization    
• Shape‐preserving parametrization    

• 如何判断哪个参数化方法更好？    




M. Floater. Parametrization and smooth approximation of surface triangulations. CAGD, 1997.      
<http://www.cs.jhu.edu/~misha/Fall09/Floater97.pdf>   


# 曲面展开（参数化）   

![](../assets/网格38.png)    

# 纹理映射   

![](../assets/网格39.png)    

![](../assets/网格40.png)    

> 使用这种格子作为纹理，方便观察扭曲情况，仍建议用 cotangent 权，扭曲较小。   
图1：均匀权， 图3：cotangent权     

# 例子   

![](../assets/网格41.png)    

> 例子中产生了较大的扭曲。且耳朵处容易发生数值精度问题。   
算法优点：简单、有效、无翻转。    

# Parameterization    

![](../assets/网格42.png)    

> 复杂模型割成多块分别参数化，再 packing    
优点：1.减少扭曲。    2.具有语义。    
缺点：1.空间浪费。    

# 曲面纹理的保存：2D图像   

![](../assets/网格43.png)    

# 参数化应用：纹理映射    

![](../assets/网格44.png)    

# Constrained (Feature‐Preserving)
# Global Laplacian Smoothing


# Shrinkage    

• Global Laplacian smoothing results in shrinkages    

![](../assets/网格45.png)    


# Ideas: add constraints    

* 如何处理各种约束条件？    
• 顶点约束、面约束…    

![](../assets/网格46.png)    


# Soft Lapacian Smoothness    

 - Interpolation (hard constraints) \\(\to\\) Approximation (soft constraints)    

![](../assets/网格47.png)    

$$
L(\nu_i)=\nu_i-\sum _ {j\in N(i)}w_{ij}\nu_j = 0
$$

> 不带约束的 Laplacian 会导致maesh收缩，因此要固定几个
点作为约束。     
hard 约束：必须满足的约束，例如 \\(S.T.g(t)=0\\)    
Soft 约束: 尽量满足的约束，例如 \\(\min f(x)\\)   

# Laplacian of Mesh   

• Discrete Laplacians

![](../assets/网格48.png)    


# Laplacian of Mesh   

• Surface reconstruction    

![](../assets/网格49.png)    

$$
L(\nu_i)=\nu_i-\sum _ {j\in N(i)}w_{ij}\nu_j = 0
$$


# Properties of Laplacian    

![](../assets/网格50.png)    

$$
Rank(L) = n-k
$$

&#x2705; k is the number of connected components of the mesh    
&#x2705; Need to add some constraints     


# Vertex Constraints     

• Add position constraint for one vertex     

![](../assets/网格51.png)    

> hard 约束的问题是,fix点处会很突兀,因此通常使用软约束。   
每 fix 一个点，在矩阵下面增加三行。   

# Vertex Constraints    

• Add position constraints for more vertices    

![](../assets/网格52.png)    


# Adding Vertex Constraints    

\\(\min _{{X}'} \\){\\( ||L{X}' ||^2+\mu ^2\sum _{i\in C}|{\nu }'_i -\nu_i|^2\\)}


![](../assets/网格53.png)    

> 第一项： Laplace 尽量小，第二项：固定点尽量不动    

# Face Constraints    

![](../assets/网格54.png)    

> 除了固定顶点位置的约束，还可以对面加约束，例如：固定面片重心的位置。关键是要线性约束。    
加入约束之后. A 的行数远多于列数。只能求近似解。    
\\(\min \left \|| Ax- b \right \||^2\\),相当于软约束优化问题。  

# Adding Face Constraints    

![](../assets/网格55.png)    

# Other Constraints    

• Edge constraints   

![](../assets/网格56.png)    

• 1‐ring barycenter constraints    

![](../assets/网格57.png)    

• Other linear constraints    


# Minimizing Energy    

![](../assets/网格58.png)    



# Least Square Solution    

• An over‐determined system:   

$$
AX = b
$$

• Normal equation:   

$$
A^TAX = A^Tb
$$

$$
X = (A^TA)^{-1}A^Tb
$$

> 求逆比较麻烦，如果 A 不变，可对 \\(A^\tau A\\) 做Cholesky 分解。    

# One Channel Solution    

• Very efficient solution by Cholesky factorization of \\(A^TA\\):

$$
A^TA = R^TR
$$
R is upper‐triangular and sparse     
Once R is computed, solving for x, y, z by back‐
substitution:    

$$
R^Tξ = A^Tb
$$

$$
RX = ξ
$$


# Results   

![](../assets/网格59.png)    

**‘8’-like mesh model    
3070 vertices, 6144 triangles**


# Results   

![](../assets/网格60.png)    



# LoD Smoothing    

![](../assets/网格61.png)    


Applying our algorithm to the bunny model with different parameters.    


# Laplacian Editing     
[Sorkine et al. SGP 2004]


# Cardinal Coordinates    

• (x,y,z) coordinates    

> v 1.5 -0.960751 -1.2232    
  v 0.81 -0.891238 -3.74258   
  v 0.16 -0.233535 -2.28405    
  v 1.49 -2.44325 -3.6962   
  v 1.59 -2.98815 -4.15761   
  v 1.66 -2.81016 -4.10777    
  v 1.41 -1.14861 -1.92823   
  v 1 -1.40023 -3.80159   
  v 0.88 -1.33122 -3.83517  
  v 1.69 -2.60816 -4.12133   
  v 1.68 -2.36516 -4.13078   
  …    

![](../assets/网格2.png)    

**Pros and Cons?**



# What’s are Details?    

• Detail = surface – smooth (surface)    
• Smoothing = averaging    

![](../assets/网格62.png)    


# What’s the Difference?    

![](../assets/网格63.png)    



# Laplacian Editing   

 - Local detail representation – enables **detail preservation** through various modeling tasks    
 - Representation with **sparse** matrices    
 - Efficient **linear** surface reconstruction    

![](../assets/网格64.png)    


# Editing framework     

 - The spatial constraints will serve as modeling constraints    
 - Reconstruct the surface every time the modeling constraints are changed   


Detail constraints: \\(LX=\delta \\)    
Modeling constraints: \\(x_j=c_j,j\in\\) {\\(j_1,j_2,\dots j_k\\)}    

> 用户对 mesh 的一个点进行编辑，算法更新其他的点，得到合理结果。     
本质：保持 mesh 的 Laplace 不变，因为 Laplace 描述了曲面的特征。    
准确说是 Laplace 长度不变，方向有可能旋转。     

# Direct Detail Preserving     

![](../assets/网格65.png)    


# Rotation Transformation   

![](../assets/网格65-1.png)    

$$
\begin{pmatrix}b_1-b_i
 \\\\\vdots 
 \\\\b_N-b_i
\end{pmatrix}=\begin{pmatrix}a_1-a_i
 \\\\\vdots 
 \\\\a_N-a_i
\end{pmatrix}R_i
$$

# Reconstruction    

• Soft constraints     

$$
L^TLv=L^T\delta 
$$

![](../assets/网格66.png)    

# Variational Viewpoint    

• Laplacian Approximation    

$$
\tilde{X} =\underset{X}{argmin} (||LX-\delta ^{(x)}||^2+\sum _{j\in C}w^2||x_j-c_j||^2).
$$

• Gradient Approximation    

$$
\underset{\phi }{min} \iint _\Omega ||\nabla \phi -w||^2dA,
$$


# User Interfaces    

• ROI is bounded by a belt (static anchors)    
• Manipulation through handle(s)    

![](../assets/网格67.png)    

# Results    

![](../assets/网格68.png)    


# Detail transfer and mixing    
• “Peel“ the coating of one surface and transfer to 
another    

![](../assets/网格69.png)    

# Detail transfer and mixing    

 - Correspondence:    

    ![](../assets/网格70-1.png)    

    - Parameterization onto a common domain and elastic warp to align the features, if needed     


# Detail transfer and mixing    

• Detail peeling:    

![](../assets/网格71.png)    

$$
\xi _i=\delta _i-\tilde{\delta } _i
$$



# Detail transfer and mixing   


• Changing local frames:    

![](../assets/网格72.png)    

# Detail transfer and mixing    

• Reconstruction of target surface from: \\(\delta _{target}\\)    

$$
\delta _{target} ={\delta}' _i+{\xi}' _i
$$

![](../assets/网格73.png)    


# Examples    

![](../assets/网格74.png)    

# Examples    

![](../assets/网格75.png)    

# Mixing Laplacians    

• Taking weighted average of \\(\delta _i\\) and  \\(\delta ^‘_i\\)    

![](../assets/网格76.png)    


# Mesh transplanting   

* The user defines    
• Part to transplant   
• Where to transplant   
• Spatial orientation and scale    
* Topological stitching    
* Geometrical stitching via Laplacian mixing    

![](../assets/网格77.png)    


# Mesh transplanting    


• Details gradually change in the transition area    

![](../assets/网格78.png)    


