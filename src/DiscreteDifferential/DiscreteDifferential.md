# 曲面的微分几何    

# Differential Geometry of a Surface    

![](../assets/微分25.png)  

## Point p

Point p on the surface at \\((u_0,v_0)\\)     

> \\(S_u 和 S_v\\) 张成一个平面，称为切平面。     
N 所在平面与曲面相交，得到平面曲线，有对应的曲率空间曲面的切线和曲率都是基于特定方向的。    

## Tangent \\(S_u\\)

Tangent \\(S_u\\) in the u direction      

\\(S_u=\frac{\partial S(u,v)}{\partial u} \\)     

S(u,v)


## Tangent \\(S_v\\)

Tangent \\(S_v\\) in the v direction     

\\(S_v=\frac{\partial S(u,v)}{\partial v} \\)     

## Plane of tangents T    

\\(T=uS_u+vS_v\\)     

## Normal N    

\\(N=\frac{S_u\times S_v}{||S_u\times S_v||} \\)    

## Curvature

方向曲率：曲率是随着方向变化的    


# 曲面的曲率   


## 主曲率 Principal Directions   
• 两个方向（正交）曲率：最大曲率\\(𝜅_1\\)和最小曲率\\(𝜅_2\\)     
* 欧拉公式     
• 其他方向曲率\\(k=k_1\cos ^2\theta +k_2\sin ^2\theta \\)     

![](../assets/微分28.png)  
![](../assets/微分29.png)

## 高斯曲率     
• \\(k=k_1k_2\\)    
• 等距变换不变量     
• 处处高斯曲率为0的曲面：可展曲面     
• 三类：柱面、锥面、切线面      

![](../assets/微分26.png)  

## 平均曲率    
• \\(k=\frac{k_1+k_2}{2} \\)    
• 处处平均曲率为0的曲面：极小曲面      

![](../assets/微分27.png)  

> \\(\theta \\)是当前曲率方向与\\(K_1\\)方向的夹角。   
等距变换：曲面发生变形，但曲面上任意两点间距离不变。   
切线面：任意空间曲线的所有切线构成的面。     
微分几何研究曲面无穷小邻域上的微分属性（导数、曲率）    

# 离散微分几何    


# 三角网格曲面的光滑性？   

![](../assets/微分30.png)   


# However, meshes are only \\(C^0\\)    


* Meshes are piecewise linear surfaces   
• Infinitely continuous on triangles   
• \\(C^0\\) at edges and vertices    

![](../assets/微分31.png)    

> \\(C^0\\)连续不光滑、不可微，如何讨论微分性质？
通过采样点估计出原始曲面的微分属性。

# Discrete Differential Geometry    

* How to apply the traditional differential geometry on discrete mesh surfaces?     
• Normal estimation    
• Curvature estimation    
• Principal curvature directions   
• …   


# Estimation of Differential Measures    


 - Approximate the (unknown) underlying surface    
    - Continuous approximation    
      - Approximate the surface & compute continuous differential 
measures (normal, curvature)   
    - Discrete approximation   
      - Approximate differential measures for mesh    



# Continuous Approximation   

# Quadratic Approximation     

 - Approximate surface by quadric    
 - At each mesh vertex (use surrounding triangles)   
    - Compute normal at vertex    
      - Typically average face normals    
    - Compute tangent plane & local coordinate system    
      - (node = (0,0,0))    
    - For each neighbor vertex compute location in local system    
      - relative to node and tangent plane   

![](../assets/微分32.png)    


# Quadratic Approximation (2)    

* Find quadric function approximating vertices    

$$
F(x, y, z)=ax^{2}+bxy+cy^{2}-z=0 
$$

* To find coefficients use least squares fit    

$$
\min \sum_{i}^{} (ax_i^2+bx_iy_i+cy_i^2-z_i) 
$$

 


# Quadratic Approximation (3)   

Finding the quadric function approximating points     

$$
F(x,y,z)=ax^2+bxy+cy^2-z=0
$$

To find coefficients use least square \\(\min \sum _i(ax_i^2+bx_iy_i+cy_i^2-z_i)\\) fit to find minimum:    

$$
\begin{pmatrix}x_1^2  & x_1y_1 &y_1^2
 \\\\ \cdots  &\cdots   &\cdots
  \\\\ x_n^2 &x_ny_n  &y_n^2
\end{pmatrix}\begin{pmatrix}a
 \\\\b
 \\\\c
\end{pmatrix}=\begin{pmatrix}z_1
 \\\\\cdots 
 \\\\z_n
\end{pmatrix}A=\begin{pmatrix}x_1^2  & x_1y_1 &y_1^2
 \\\\ \cdots  &\cdots   &\cdots
  \\\\ x_n^2 &x_ny_n  &y_n^2
\end{pmatrix},X=\begin{pmatrix}a
 \\\\b
 \\\\c
\end{pmatrix},b=\begin{pmatrix}z_1
 \\\\\cdots 
 \\\\z_n
\end{pmatrix}
$$

Approximation can be found by:\\(\tilde{X}=\left(A^{T} A\right)^{-1} A^{T} b\\)     

![](../assets/微分7.png)    



# Quadratic Approximation (4)    

• Given surface \\(F\\) its principal curvatures \\(k_\min \\) and \\(k_\max\\) are real roots of:   

$$
k^{2}-(a+c)k + ac - b^{2} = 0
$$

• Mean curvature: \\(H = (k_\min + k_\max)/2\\)     
• Gaussian curvature:\\(K = k_\min  k_\max\\)    



# Other approximation     

* Cubic approximation     
• J. Goldfeather and V. Interrante. A novel cubic‐order algorithm for approximating principal direction vectors. ACM Transactions on Graphics 23, 1 (2004), 45–63.    
* Implicit surface approximation     
• Yutaka Ohtake et al. Multi‐level partition of unity implicits. Siggraph 2003.    
* Many others…      


# Discrete Approximation    

# Normal Estimation   

 - Normal estimation on vertices     
    - Defined for each face    
    - Average face normals    
      - Weighted:  face areas, angles at vertex      

 - What happen at edges/creases?     


# Mean Curvature     

• 由Laplace‐Beltrami定理：      

$$
K(x_i)=\frac{1}{2A_M} \sum_{j\in N_1(i)}^{} (\cot \alpha _{ij}+\cot \beta _{ij})(x_i-x_j)
$$

![](../assets/微分33.png)    

> \\(N_l(X_i)\\):表\\(X_i点的l\\)邻域点     
\\(A_m\\)：整个多边形的面积     

# Gauss Curvature     

• 由Gauss‐Bonnet定理：   


![](../assets/微分34.png)    


# Gaussian Curvature Estimate – Example    

![](../assets/微分35.png)    

 - Approximation always results in some noise    
 - Solution    
    - Truncate extreme values    
      - Can come for instance from division by very small area    
    - Smooth    
      - More later    

> color map：数据的可视化方法，红 > 绿 > 篮    

# Mean Curvature Estimate – Example    

![](../assets/微分36.png)    

# Mean Curvature    

![](../assets/微分37.png)    

# More…    

 - MEYER M., DESBRUN M., SCHRÖDER P., BARR A.: Discrete differential‐geometry operators for triangulated 2‐manifolds. In Visualization and Mathematics III, Hege H.‐C., Polthier K., (Eds.). Springer, 2003, pp. 35–58. (<u>PDF</U>)    

> 离散微分几何算子的开创性文章   

# References    

 - TAUBIN G.: Estimating the tensor of curvature of a surface from a polyhedral approximation. In Proc. International Conference on Computer Vision (1995), pp. 902–907.     
 - MEYER M., DESBRUN M., SCHRÖDER P., BARR A.: Discrete differential‐geometry operators for triangulated 2‐ manifolds. In Visualization and Mathematics III, Hege H.‐C., Polthier K., (Eds.). Springer, 2003, pp. 35–58.      
 - CAZALS F., POUGET M.: Estimating differential quantities using polynomial fitting of osculating jets. In Eurographics Symposium on Geometry Processing (2003), pp. 177–187.    
 - COHEN‐STEINER D., MORVAN J.: Restricted delaunay triangulations and normal cycle. In Proc. ACM Symposium on Computational Geometry (2003), pp. 312–321.    
 - GOLDFEATHER J., INTERRANTE V.: A novel cubic‐order algorithm for approximating principal direction vectors. ACM Transactions on Graphics 23, 1 (2004), 45–63.      
 - MARTIN R. R.: Estimation of principal curvatures from range data. International Journal of Shape Modeling 4, 1 (1998), 99–109.     
 - OHTAKE Y., BELYAEV A., SEIDEL H.‐P.: Ridge‐valley lines on meshes via implicit surface fitting. ACM 
Transactions on Graphics 23, 3 (2004), 609–612. (Proc. SIGGRAPH’2004).       
 - PAGE D., SUN Y., KOSCHAN A., PAIK J., ABIDI M.: Normal vector voting: Crease detection and curvature 
extimation on large, noisy meshes. Graphical Models 64, 3‐4 (2002), 199–229.     


# 极小曲面    


# 极小曲面   

• 平均曲率处处为0的曲面   

![](../assets/微分38.png)    

> 每个点都是马鞍点     
常见的极小曲面肥皂泡。    

# 极小曲面   

![](../assets/微分39.png)    
![](../assets/微分40.png)    
![](../assets/微分41.png)    

# 极小曲面的例子    

![](../assets/微分42.png)    

# 建筑中的极小曲面：膜结构    

![](../assets/微分43.png)    

![](../assets/微分44.png)    

![](../assets/微分45.png)    

![](../assets/微分46.png)    

![](../assets/微分47.png)    

![](../assets/微分48.png)    

> 优点：省材料，不积水   

# 极小曲面及平均曲率流    

• 平均曲率处处为0     

![](../assets/微分49.png)    

> Mean 曲率处处为0，代入 Mean Curve 的计算公式     
$$ 
K=\frac{1}{2A_m} \sum (\cot \alpha ij+\cot \beta ij)(x_i-x_j)=0
$$
以上公式可以看作是 V 与其 l 领域点的线性组合，得到 Q 平面内的重心坐标点。     
当满足\\(K=0时， L 的模长为0\\)。        
从任意取曲面优化成极小曲面的方法：
1. 计算出中间的黑点     
2. 响黑点移动       
（重心）

# Laplace Operator (Umbrella Operator)    

$$
L(P)=\frac{1}{n} \sum_{i=1}^{n} \overrightarrow{PQ_i} =\frac{1}{n} \sum_{i=1}^{n}Q_i-P
$$

![](../assets/微分50.png)    


# 离散平均曲率流   

![](../assets/微分51.png)  

> [?] 这个公式还不理解？    
\\(\lambda \\)太大会不收敛。\\(\lambda \\)取小一点多走几步。     

# Discrete Mean Curvature     

$$
Hn=\frac{\nabla_PA}{2A} 
$$

$$
Hn=\frac{1}{4A} \sum_{j}^{} (\cot \alpha _j+\cot \beta _j)(P-Q_j)
$$

![](../assets/微分52.png)  


# 离散极小曲面的局部迭代法    

 - 找到边界    
 - 固定边界顶点    
 - 对每个内部顶点    
    - 找顶点1‐邻域    
    - 更新其坐标    
 - 迭代   
 - 更新所有顶点法向   

 - 【注】   
    - 只能对非封闭曲面（带一条边界）操作   
    - 更新坐标需要用老的顶点坐标   
    - 尝试试验不同的参数\\(𝜆(𝜆 = 0.1)\\)    

> 假设输入遇开曲面，迭代前把边界位置固定。 

# 例子   

![](../assets/微分53.png)  

# 封闭曲面    

• 不固定任何顶点    
• 迭代结果如何？   

![](../assets/微分54.png)  

作业6    
* 任务：实现极小曲面的局部法    
• 寻找非封闭三角网格曲面的边界    
• 每个顶点更新坐标    
• 迭代给定次数 或 迭代至收敛    
* 目的   
• 学习三角网格的半边数据结构及操作   
* 框架：   
• Utopia （推荐）   
• 其他    
* 【可选】计算三角网格顶点的离散高斯曲率和平均曲率 并用颜色进行可视化    
* Deadline：2020 年12 月5日晚      


# 附加：如何构造曲面边界？   

 - 3D空间封闭曲线     
    - 已知的非封闭曲面   
    - 自己构造：平面曲线变形    

    ![](../assets/微分55.png)  

 - 初始网格    
    - 自己构造    
      - 平面：Delaunay三角化（学习Triangle库）    
      - 空间变形: Warping     

      ![](../assets/微分56.png)  

> 对于封闭曲面，不固定住的点，最后会收缩到一个点。    

# Triangle    

<http://www.cs.cmu.edu/~quake/triangle.html>   

![](../assets/微分57.png)  

![](../assets/微分58.png)  

![](../assets/微分59.png)  