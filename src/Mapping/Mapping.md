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

![](../assets/映射28-1.png)  

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
f(p_i)=c_0+c_xx+c_yy+\sum c_i\phi (||X-P_i||)
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

$$
\min_{V} E(V)=\sum _{t\in T}(\sigma _1^2+\frac{1}{\sigma _1^2} +\sigma _2^2+\frac{1}{\sigma _2^2}) 
$$

$$
s.t.\sigma _1\sigma _2>0,\forall t
$$

• The cost function is highly **nonlinear** and **nonconvex**    
• The constraints are **nonlinear**    
• The Heissian matrix is highly **non‐definite**    

> Computationally expensive for large scale meshes!   



# Computing maps   

• Imposing constraints    

![](../assets/映射32.png)  

• Finding maps that are most…   

![](../assets/映射33.png)  


# Constrained Optimization   

![](../assets/映射34.png)  


# Energy     


![](../assets/映射35.png)    

$$
E(\phi )=E(A_1,\cdots ,A_m)
$$


# Map optimization    

• In terms of differentials:     

argmin \\(E(A_1,\cdots ,A_m)\\)    

![](../assets/映射36.png)    



# Map optimization    


• In terms of differentials:

argmin \\(\sum _jf(A_j)\\)    separable     

![](../assets/映射37.png)    


# Map optimization    

argmin \\(\sum _jf(A_j)\\)

![](../assets/映射38.png)    

Must impose continuity!    



# Explicit continuity    

• Optimization variables: \\(A_1,A_2,\cdots ,A_m\\)     
• Adjacent \\(A_j\\)’s must agree     

![](../assets/映射39.png)    



# Explicit continuity    

• Optimization variables: \\(A_1,A_2,\cdots ,A_m\\)     
• Adjacent \\(A_j\\)’s must agree   

![](../assets/映射40.png)    

$$
A_i\nu _1=A_j\nu _1
$$

$$
A_i\nu _2=A_j\nu _2
$$


# Implicit continuity    

![](../assets/映射41.png)    

$$
A_i\overline{\begin{bmatrix}
 \nu_1 & \nu_2 &\nu_3
\end{bmatrix}} =\overline{\begin{bmatrix}
 u_1 & u_2 &u_3
\end{bmatrix}}
$$

$$
A_i=\overline{\begin{bmatrix}
 u_1 & u_2 &u_3
\end{bmatrix}} \overline{\begin{bmatrix}
 \nu_1 & \nu_2 &\nu_3
\end{bmatrix}}
$$

$$
A_i=A_i(U)
$$

> Linearly express \\(A_i\\) ’s in terms of U   


• Optimization variables: \\(u_1,u_2,\cdots ,u_n(U)\\)    

$$
E(\Phi )=\sum _jf(A_j(U))
$$


# 几何优化的求解    

# Popular energies    

argmin\\(\sum _jf(A_j)\\)    

![](../assets/映射42.png)    


# Dirichlet    

area / volume   \\(\Rightarrow E_D=\sum _jw_j||A_j||_F^2\\)   

![](../assets/映射43.png)   

# Dirichlet    

$$
E_D=\sum _jw_j||A_j||_F^2
$$

![](../assets/映射44.png)   



# Orthogonal and Similarity    

• R is <u>orthogonal</u> if \\(R^T=R^{-1}\\)    
(rotation if det 𝑅 > 0)    

![](../assets/映射45.png)   

• S is a <u>similarity</u> if \\(S =\alpha R\\)   

![](../assets/映射46.png)   



# Closest  R and S    


• \\(\Re(A)=\\) closest orthogonal/rotation matrix to \\(A\\)    
• \\(\varsigma  (A)\\)= closest similarity matrix to  \\(A\\)    

• Computable using SVD/SSVD:    

\\(A=U\sum V^T\\);\\(\sum\\) =diag\\((\sigma _1,\cdots ,\sigma _n)\\)    

![](../assets/映射46-1.png)   


# As‐Similar‐As‐Possible (ASAP)   

$$
E_L=\sum _jw_j||A_j-\varsigma (A_j)||_F^2
$$

![](../assets/映射47.png)   

Solving sparse linear system!    


# As‐Rigid‐As‐Possible (ARAP)     


$$
E_R=\sum _jw_j||A_j-\Re (A_j)||_F^2
$$

![](../assets/映射48.png)   


# ARAP vs. ASAP    

![](../assets/映射49.png)   


# Singular values perspective    

![](../assets/映射50.png)   


# ARAP: Alternating Optimization     

$$
E_R=\sum _jw_j||A_j-\Re (A_j)||_F^2
$$

* Iteratively:     
• Compute and fix \\( R_j = \Re (A_j) \\)    Local step    

• Minimize

\\(\sum _jw_j||A_j-R_j||_F^2\\)   Global step    


[Liu et al. A Local/Global Approach to Mesh Parameterization. SGP 2008]    

![](../assets/映射51.png)   

![](../assets/映射52.png)   

![](../assets/映射53.png)   

![](../assets/映射54.png)   

![](../assets/映射55.png)   

![](../assets/映射56.png)   

![](../assets/映射57.png)   

![](../assets/映射58.png)   



# Alternating optimization    

• Very general    

![](../assets/映射59.png)   

• Related jargon:    
**gradient descent, global‐local, alternating projections**    


# Summary: Geometric Mapping    

• Discrete Mapping   

![](../assets/映射60-1.png)   

• Discrete formulation   

argmin \\(E(\phi )\\)  Separable    
s.t. \\(\phi \in K\\)    

> • Nonlinear and nonconvex     
• Computationally expensive for large scale meshes!    


# eshless mappings    

![](../assets/映射61.png)   

• Low distortion    
• Flip‐free    
• Bijective    

$$
f(x)=\sum_{i=1}^{m} c_iB_i(x)
$$

# Geometric Mapping    


* 其他区域间的映射求解    
• 离散形式    
• 约束条件    

![](../assets/映射62.png)   
