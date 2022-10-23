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