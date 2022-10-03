

# 隐式曲线   


# 回顾：参数曲线   

• 曲线定义在一个单参数 的区间上，有 上的基函数来线性组合控制顶点来定义    

$$
x(t)=\sum_{i=0}^{n} B^n_i(t)b_i
$$

![](../assets/瘾曲1.png) 

> 曲线的性质来源于**基函数**的性质


# 回顾：平面曲线的定义方法  
* 显式函数
 $$
 f:R^1\longrightarrow R^1
 $$
 
 $$
  y=f(x)
 $$

• 点\\((𝑥,𝑓(𝑥)),𝑥∈[a,b]\\)的轨迹     

![](../assets/瘾曲2.png) 

 * 参数曲线   
\\(p:R^1\longrightarrow R^2\\)      
\\(x=x(t)\\)    
\\(y=y(t)\\)     
• 点\\((𝑥(𝑡),𝑦(𝑡)),𝑡∈[𝑎,𝑏]\\)的轨迹    

![](../assets/瘾曲3.png) 


# 隐式函数    

* 自变量 和应变量 的关系非显式关系，是一个隐式的关系（代数方程）：

$$
f(x,y)=0
$$

* 比如：
• \\(𝑎𝑥+𝑏𝑦+𝑐=0\\)    
• \\(𝑥^2+𝑦^2=1\\)   
• \\(𝑦^2=𝑥^3+𝑎𝑥+𝑏\\)   
• \\(𝑥𝑦^2+ln(𝑥 sin𝑦-𝑒^{y-\sqrt{x} })=\cos (x-\sqrt{x^3-2y} )\\)

> 所有满足该代数方程的点的轨迹是条曲线  


# 隐函数定理   

Implicit Function Theorem:
• Given a **differentiable** function     

$$
𝑓:ℝ^n ⊇ 𝐷 → ℝ, 𝑓(𝒙^{(0)})=0,\frac{\partial }{\partial x_n} f(x^{(0)})=\frac{\partial }{\partial x_n} f(x_1^{(0)},\cdots ,x_n^{(0)})\ne 0
$$


• Within an 𝜀‐neighborhood of\\( 𝒙^{(0)}\\) we can represent the
zero level set of 𝑓 completely as a heightfield function \\(𝑔 𝑔:ℝ^{(n-1)} → ℝ\\)such that for \\(𝒙-𝒙^{(0)}<𝜀 \\)we have:     

$$
f(x_1,…,x_{n-1},g(x_1,…,x_{n-1}))=0 
$$

and   

\\(f(x_1,…,x_{n}\ne 0 \\)everywhere else     
• The heightfield is a diffrentiable \\((𝑛 -1)\\)‐manifold and
its surface normal is the colinear to the gradient of 𝑓.     


# 隐式曲线    


• 将隐函数升高一维，看成是\\(x\\)和\\(y\\)的二元函数    
\\(z=f(x,y),  x,y\in [a,b]\times [c,d]\\)

• 则该隐式曲线为上述二元函数的0等值线（平面\\(z=0\\)与\\(z=f(x,y)\\)的交线）   

$$
f(x,y)=0
$$
• \\(f(x,y)=0\\),曲线上；    
• \\(f(x,y)<0\\),曲线的左侧（内部）；    
• \\(f(x,y)>0\\),曲线的右侧（外部）；   

![](../assets/瘾曲4.png) 



# 隐式函数表达    

 - 已知一条封闭曲线，如何构造隐式函数表达？     
    - General case     
      - Non‐zero gradient at zero crossings     
      - Otherwise arbitrary     
    - Signed implicit function:    
      - sign (𝑓): negative inside and positive outside the object (or the other way round, but we assume this orientation- here)
    - Signed distance field (SDF)    
      - |𝑓|= distance to the surface    
      - sign(𝑓): negative inside, positive outside    
    - Squared distance function    
      - 𝑓 = \\((distance to the surface)^2\\)   

![](../assets/瘾曲5.png) 


# Differential Properties   

  - Some useful differential properties:       
  - look at a surface point 𝒙, i.e.\\( 𝑓(𝒙)=0\\).      
      - We assume \\(𝛻𝑓(𝒙)\ne 0\\).     
    - The unit normal of the implicit surface is given by:    
 \\( 𝑛(𝒙)=\frac{\nabla  f(x) }{||\nabla f(x)|| } \\)
     - For signed functions, the normal is pointing outward      
      - For signed distance functions, this simplifies to 𝒏(𝒙)=𝛻𝑓(𝒙)     



# Differential Properties   


  - Some useful differential properties:
    - The mean curvature of the surface is proportional to the divergence of the unit normal:   
\\(-2𝐻(𝒙)=𝛻⋅𝒏(𝒙)=\frac{𝜕}{𝜕𝑥} n_x(x)+\frac{𝜕}{𝜕y}ny(x)+\frac{𝜕}{𝜕z}n_z(x)\\)
\\(=𝛻 ⋅\frac{𝛻𝑓(𝒙)}{||𝛻𝑓(𝒙)||} \\)

    - For a signed distance function, the formula simplifies to:     

$$
-2𝐻(𝒙)=𝛻 ⋅ 𝛻𝑓(𝑥)=\frac{𝜕^2}{𝜕𝑥^2} f(x)+\frac{𝜕^2}{𝜕y^2}f(x)+\frac{𝜕^2}{𝜕z^2}f(x)=𝛻𝑓(𝑥)
$$


# 隐式曲线的绘制   


# 如何找隐式函数表达的点的集合？   

* 自变量 和应变量 的关系非显式关系，是一个隐式的关系（代数方程）：     

$$
f(x,y)=0
$$

* 比如：    
• \\(𝑎𝑥+𝑏𝑦+𝑐=0\\)    
• \\(𝑥^2+𝑦^2=1\\)      
• \\(𝑦^2=𝑥^3+𝑎𝑥+𝑏\\)     
• \\(𝑥𝑦^2+ln(𝑥 sin𝑦-e^{y-\sqrt{x} }=\cos (x-\sqrt{x^3-2y} )\\)     


# 等值线抽取   

* 输入：一个二元隐式函数\\(z=f(x,y)\\)     
* 输出：值为\\(0(或a)\\)的等值线\\(z=0\\)（或\\(z-a=0\\)）    

* 目的：     
• 将隐式曲线转化为参数形式、离散曲线（多边形）形式     
• 绘制曲线    


# Marching Cubes算法 [Siggraph1987]    

* 隐式曲线绘制的最常用方法    
• 网上能找到很多开源实现代码    
* 思想（2D: Marching Squares）    
• 在一些离散格子点上求值     
• 然后利用局部连续性插值出值为0的点     
• 按一定的顺序连接这些点形成离散曲线    

![](../assets/瘾曲6.png)    

![](../assets/瘾曲7.png)    



# 歧义情况   

  - There is a (minor) technical problem remaining:     
    - The triangulation can be ambiguous    
    - In some cases, different topologies are possible which are all locally plausible:      
![](../assets/瘾曲8.png) 
    - This is an undersampling artifact. At a sufficiently high
resolution, this cannot occur.     
    - Problem: Inconsistent application can lead to holes in the surface (non‐manifold solutions)        



# Adaptive Grids  

Adaptive / hierarchical grids:
• Perform a quadtree / octree
tessellation of the domain (or any
other partition into elements)
• Refine where more precision is
necessary (near surface, maybe
curvature dependent)
• Associate basis functions with each
cell (constant or higher order)   

![](../assets/瘾曲9.png) 


# 隐式曲线拟合   


# 问题   

* 输入：平面上的一些点（设采样自封闭曲线）    
• 一般还需给定或估计点的法向信息       
* 输出：拟合这些点的一个隐式函数       
• 该隐式函数所表达的曲线就是拟合曲线       

![](../assets/瘾曲10.png)    


# 拟合问题的求解步骤    

• 1. 估计法向：利用邻近点来估计切平面   

![](../assets/瘾曲11.png)    


# 拟合问题的求解步骤   

• 1. 估计法向：利用邻近点来估计切平面     
• 2. 拟合一个二元函数：在型值点上值为0，外部（法向方向的点）为正，内部为负    

![](../assets/瘾曲12.png)    


# 隐式函数构造方法   

• Blobby molecules    
• Metaball     
• RBF based method     
• Multi‐level partition of unity implicits (MPU)     
• Poisson reconstruction method     
• Screened Poisson method     
• …     
![](../assets/瘾曲13.png)    
