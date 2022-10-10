
# 离散曲线处理   


# 回顾：\\(R^2\\)和 \\(R^3\\)中的曲线/曲面   

![](../assets/离散1.png)  


# 映射的维数   

$$
f:X → Y
$$


|一元函数 |
|------| 

$$
\begin{array}{l} 
  f:R^1\to R^1    \\\\    
  y=f(x) \\\\ 
\end{array} 
$$


|多元函数 |
|------| 

$$
\begin{array}{l} 
  f: R^m \to R^1    \\\\    
  y=f (x_1, x_2, \cdots, x_m) \\\\ 
\end{array} 
$$

 

|高维（单参数）曲线 |
|------| 

$$
\begin{array}{l} 
  f: R^1 \to R^n \\\\
  y_1=f_1(x) \\\\
  y_2=f_2(x) \\\\ 
  \vdots \\\\
y_n=f_n(x) \\\\ 
\end{array} 
$$

|高维曲面(\\(𝑚 <𝑛\\))/降维映射(\\(m>n\\\)) |
|------|   

$$
\begin{array}{l} 
  f: R^m \to R^n \\\\
  y_1=f_1(x_1,x_2,\cdots,x_m) \\\\
  y_2=f_2(x_1,x_2,\cdots,x_m) \\\\ 
  \vdots \\\\
y_n=f_n(x_1,x_2,\cdots,x_m) \\\\ 
\end{array} 
$$






# Curve Modeling in \\(R^2\\)（建模/造型）   

![](../assets/离散3.png)    

* **Fitting** (Reconstruction) for reverse engineering (interpolation, approximation, aggression…)     
• 从代数观点：需要函数空间表达能力足够      
• 输入：采样点{\\(S_j,j=0\sim m\\)} 及基函数{\\(b_i(t),i=0\sim n\\)}     
• 输出：拟合函数的系数{\\(p_i,i=0\sim n\\)}       
* **Design** for interactive modeling      
• 从几何观点：具有好性质的基函数使得交互设计更直观     
• 输入：交互输入（或者反求）控制顶点{\\(p_i,i=0\sim n\\)}     
• 输出：曲线\\(f(t)\\)   



# 曲线（形状）的不同表达方法    


**优劣比较？**

* 显式函数曲线   

$$
\begin{array}{l} 
  f:R^1\to R^1    \\\\    
  y=f(x) \\\\ 
\end{array} 
$$

![](../assets/离散4-1.png)    

* 参数曲线    

$$
\begin{array}{l} 
  p:R^1\to R^1    \\\\    
  x=x(t) \\\\ 
  y=y(t) \\\\ 
\end{array} 
$$

![](../assets/离散5-1.png)    

* 隐式曲线    
• Level set (水平集)    

$$
f(x,y)=0
$$

![](../assets/离散6-1.png)    


* 细分曲线      

![](../assets/离散7.png)    



# 几何迭代法（渐进迭代逼近）     
(progressive‐iterative approximation, PIA)     

![](../assets/离散8.png)    

齐东旭、de Boor、蔺宏伟    



# 曲线的离散   


# 从连续到离散   

* 对象的表达     
• 在数学上，连续表达与计算      
• 在计算机中，离散表达与计算     
* 数值方法：数值微分、数值积分、数值优化    
• 数值分析：离散计算对精确计算的近似程度     
• Fourier分析/变换：离散Fourier分析/变换    
• 卷积（滤波）    
* 在计算机科学（计算机图形学）中，采样无处不在    
• 计算机只能表达离散的数值    
• 例子：int型的数据（量化）    



# 曲线的离散化   

• 将连续性表达转化为**多边形**表达（分段线性）    

![](../assets/离散9.png)    

# 为何要离散化？   

* 渲染的必要性    
• 算法和硬件：线段/圆的光栅化     

![](../assets/离散10.png)    

* 计算的必要性     
• 直线求交、多项式求根    

![](../assets/离散11.png)    


* 制造的必要性      
• 刀具轨迹只能走直线段和圆弧     


# 曲线的离散：采样    

• Nyquist–Shannon采样定理      

> If a function \\(x(t)\\) contains no frequencies higher than B hertz, it is completely determined by giving its ordinates at a series of points spaced 1/(2B) seconds apart.      

![](../assets/离散12.png)    


# Bezier曲线的离散定理    


• 曲线到弦的最大距离<控制顶点到弦的最大距离     
• 给定误差，估计离散层级     

![](../assets/离散13.png)    

# 离散曲线的几何量的计算     

* 如果有连续表达，利用连续表达的曲线来计算    

* 如无连续表达     
• 差分法：利用差分形式来近似微分属性    
• 拟合法：利用光滑函数来拟合估计属性     

* Tylor展开及估计     



# 重心坐标     


# Free‐form Deformation (FFD)    
[Sederberg et al. 86]


* Embed the object into a domain that is more easily parametrized than the object.     
* Advantages:      
• You can deform arbitrary objects    
• Independent of object representation     

![](../assets/离散14.png)    


# 图像变形    

• 交互：boundary editing    

![](../assets/离散15.png)    


# 图像变形     

![](../assets/离散16.png)    

**问题**：给定一个包含物体的边界多边形，改变边界时，如何计算物体的变形？      
即，内部点与边界点（**控制顶点**）之间的关联关系？     

![](../assets/离散17.png)    



# 三角形的重心坐标     

![](../assets/离散18.png)    


# 四边形？   

![](../assets/离散19.png)    

# 多边形的重心坐标？   

![](../assets/离散20.png)    


# Warping with BC      

![](../assets/离散21.png)    


# Coordinates    

 - Homogeneous coordinates
    - Given points \\(v_\Sigma \\) = {\\(v_1,\cdots ,v_i,\cdots \\)}    
    - Express a new point \\(x\\) as affine combination of \\(v_\Sigma \\)    

         \\(x=\Sigma b_i v_i,\\) where \\(\Sigma b_i = 1\\)    

    - \\(b_i\\) are called homogeneous coordinates      
    - Barycentric if all       

   $$
   b_i \ge 0
   $$

    ![](../assets/离散22.png)    

# Applications    

* Boundary interpolation    
\\(f(x)=\Sigma b_if_i\\)     
• Color/Texture interpolation      
* Mapping     
\\({x}' =\Sigma b_i{v}' _i\\)     
• Shell texture      
• Image/Shape deformation     

![](../assets/离散23.png)    



# Coordinates In A Polytope     

* Points \\(v_\Sigma\\) form vertices of a closed polytope     
• \\(x\\) lies inside the polytope     

* Example: A 2D triangle     
• Unique (barycentric):     

  $$
  b_1=\frac{A_{xv_2v_3}}{A_{v_1v_2v_3}} 
  $$
• Can be extended to any N‐D simplex        
* A general polytope     
• Non‐unique      
• The triangle‐trick can not be applied.       

![](../assets/离散24.png)    




# BC of 2D Polygons   

 -  2D Polygons     
    - Wachspress [Wachspress 75][Loop 89][Meyer 02][Malsch 04]    
      - Barycentric within convex shapes      
    - Mean value [Floater 03][Hormann 06]      
      - Homogeneous within any closed shape, barycentric within convex shapes and kernels of star‐shapes      
    - Discrete harmonic [Desbrun 02][Floater 06]     
      - Homogeneous within convex shapes     
 - A general construction in 2D [Floater 06]      
    - <u>Complete</u>: a single scheme that can construct all possible homogeneous coordinates in a convex polygon      
    - Reveals a simple connection between known coordinates via a parameter        
      - Wachspress      
      - Mean value       
      - Discrete harmonic     


# 各种重心坐标的计算方法     

\\(\star \\) Wachspress (WP) coordinates    

$$
w_{i}=\frac{\cot \gamma_{i-1}+\cot \beta_{i}}{r_{i}^{2}}
$$

![](../assets/离散40.png)    

\\(\star \\) mean value (MV) coordinates     

$$
w_{i}=\frac{\tan \left(\alpha_{i-1} / 2\right)+\tan \left(\alpha_{i} / 2\right)}{r_{i}}
$$

![](../assets/离散41.png)    


\\(\star \\) discrete harmonic (DH) coordinates     

$$
w_{i}=\cot \beta_{i-1}+\cot \gamma_{i}
$$

![](../assets/离散42.png)    







# • 1.imge warping     

![](../assets/离散26.png)    


# • 2. shading     

![](../assets/离散27.png)    


# 3. Transfinite Interpolation: Interpolating height function to model a surface    

![](../assets/离散28.png)    


# • allow directly updating on interpolation when resampled.     

![](../assets/离散29-1.png)     


# Transfinite Interpolation    
 
• 问题：给定4条边界曲线，构造插值这4条曲线的一张曲面     
• Coons surfaces      

![](../assets/离散30.png)     



# 广义重心坐标的学习资料   

• <http://www.inf.usi.ch/faculty/hormann/barycentric>     




# 2D形状（离散曲线）处理    
 


# 离散曲线的去噪/滤波    


• Denoising, smoothing, fairing     

![](../assets/离散31.png)     

# 曲线简化(Simplification)    

![](../assets/离散32.png)     

# 曲线编辑/变形(Editing/Deformation)     

![](../assets/离散33.png)     

# 形状插值(Morphing)     

![](../assets/离散34.png)     

# 形状的对称性检测(Symmetry)      

![](../assets/离散35.png)     


# 形状分割(Segmentation)      

![](../assets/离散36.png)     

# 形状匹配(Matching/Correspondences)        

![](../assets/离散37.png)     

# 形状检索(Retrieval)       

![](../assets/离散38.png)     

# 形状描述子(Descriptors)      

![](../assets/离散39.png)     


