# 回顾

曲面参数化   
映射（ Mapping / Map ）   
平面几何映射   

# 映射的表达    

## 映射：基函数的线性组合    

映射表达为基本映射（基函数）的线性组合    


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



## 映射：简单区域上映射的连续组合   

映射表达为小区域（三角形区域）上映射的拼接

\\(f\\) is approximated by **piecewise linear maps** between pairs of triangles    

![](../assets/映射7.png)  

# 几何映射的例子    

## 例1：2D变形   

![](../assets/映射8.png)  

> [06:51] 2D变形问题：构造一个函数\\(f\\)， 使得拖拽点\\(f(P)\\)满足到达目标点的约束。   
[10:06] 或\\(f(P)\\)满足\\(f'(P)\\)为目标值的约束，就是法线插值。    
[10:43] mesh 点是指定点（例如重心坐标）的组合。通过移动指定点控制mesh.    

本质：插值问题   

## 例2: Barycentric Coordinates   

重心坐标：[link](../DiscreteCurves/BarycentricCoordinate.md)

# 映射的性质   

问：What are good maps?

![](../assets/映射14.png)  

答：（1）满足双射，即Source 与 target 一一 对应。local 双射（单射)：一一对应，但有翻转发生      
（2）扭曲尽量少，否则有鬼影现象 [21:28下图]    
   
## 翻转 Flip (foldover) - 单射

![](../assets/映射15.png)  

$$
f(x)=\begin{pmatrix}
u(x) \\\\
V(x)
\end{pmatrix}
$$
是映射关系，求\\(f\\)的 Jacobian,
\\(J\\)是每个分量分别对\\(x\\)和构成偏导     
det|J| >0，\\(\Rightarrow \\)未翻转。    
[23:35]有两个区域 \\(D_o, D_i, \Omega \\) 为\\(x_0\\)的无穷小邻域?     
\\(\Omega\\)映射到\\(D_2\\)后成为\\(f(\Omega)\\)     
A: signed area.
$$
y=\underset{A(\Omega )} {lim}=\frac{A(f(\Omega ))}{A(\Omega )} =J(f)l_{x=x_0}
$$
|y|>1：膨胀     
|y|<1:收缩     
|y|<0：翻转   



### Globally Bijective VS. Locally Bijective   


![](../assets/映射15-1.png)  

> 单射→双射：需要显式地判断是否发生碰撞      
[31:02] 3D空间则分解为\\(\sigma _1,\sigma _2,\sigma _3\\)     
[32:02图]  有一个矩形，希望把它边界变成红线形，求变形后的形状：      
期望：形变较小/夹角小\\(\dots\\) (看应用需求)   

![](../assets/映射17.png)  
![](../assets/映射18.png)  
![](../assets/映射19.png)  
![](../assets/映射20.png)  

Only Locally Bijective   

![](../assets/映射21.png)  


### Locally Bijection – Non‐example   

![](../assets/映射22.png)  
![](../assets/映射23.png)  
![](../assets/映射24.png)   
![](../assets/映射25.png)  



### Locally Bijection – Sufficient condition  

![](../assets/映射26.png)  

### Globally Bijective VS. Locally Bijective   

![](../assets/映射15-2.png)  
![](../assets/映射27.png)  

Google: “Global inversion theorems”    


# Jacobian的几何意义   

• 函数在某点的Jacobian度量了其局部的形变量    

![](../assets/映射29.png)  


## Distortion Measure    

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



## Distortion Metric   

![](../assets/映射31.png)  



# 映射的优化模型    


## Recap: Formulation of Parameterization   

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

## Computing maps   

• Imposing constraints    

![](../assets/映射32.png)  

• Finding maps that are most…   

![](../assets/映射33.png)  


## Constrained Optimization   

![](../assets/映射34.png)  


## Energy     


![](../assets/映射35.png)    

$$
E(\phi )=E(A_1,\cdots ,A_m)
$$


## Map optimization    

• In terms of differentials:     

argmin \\(E(A_1,\cdots ,A_m)\\)    

![](../assets/映射36.png)    



## Map optimization    


• In terms of differentials:

argmin \\(\sum _jf(A_j)\\)    separable     

![](../assets/映射37.png)    


## Map optimization    

argmin \\(\sum _jf(A_j)\\)

![](../assets/映射38.png)    

Must impose continuity!    



## Explicit continuity    

• Optimization variables: \\(A_1,A_2,\cdots ,A_m\\)     
• Adjacent \\(A_j\\)’s must agree     

![](../assets/映射39.png)    

$$
A_i\nu _1=A_j\nu _1
$$

$$
A_i\nu _2=A_j\nu _2
$$


## Implicit continuity    

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

## Popular energies    

argmin\\(\sum _jf(A_j)\\)    

![](../assets/映射42.png)    


## Dirichlet    

area / volume   \\(\Rightarrow E_D=\sum _jw_j||A_j||_F^2\\)   

![](../assets/映射43.png)   

$$
E_D=\sum _jw_j||A_j||_F^2
$$

![](../assets/映射44.png)   



## Orthogonal and Similarity    

• R is <u>orthogonal</u> if \\(R^T=R^{-1}\\)    
(rotation if det 𝑅 > 0)    

![](../assets/映射45.png)   

• S is a <u>similarity</u> if \\(S =\alpha R\\)   

![](../assets/映射46.png)   



## Closest  R and S    


• \\(\Re(A)=\\) closest orthogonal/rotation matrix to \\(A\\)    
• \\(\varsigma  (A)\\)= closest similarity matrix to  \\(A\\)    

• Computable using SVD/SSVD:    

\\(A=U\sum V^T\\);\\(\sum\\) =diag\\((\sigma _1,\cdots ,\sigma _n)\\)    

![](../assets/映射46-1.png)   


## As‐Similar‐As‐Possible (ASAP)   

$$
E_L=\sum _jw_j||A_j-\varsigma (A_j)||_F^2
$$

![](../assets/映射47.png)   

Solving sparse linear system!    


## As‐Rigid‐As‐Possible (ARAP)     


$$
E_R=\sum _jw_j||A_j-\Re (A_j)||_F^2
$$

![](../assets/映射48.png)   


## ARAP vs. ASAP    

![](../assets/映射49.png)   


## Singular values perspective    

![](../assets/映射50.png)   


## ARAP: Alternating Optimization     

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


# Meshless mappings    

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
