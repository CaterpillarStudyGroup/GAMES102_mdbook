# Mesh Generation    

Given a **fixed point set**, Delaunay triangulation will try to make the triangulation more shape regular and thus is considered as a “good” structured mesh.    

![](../assets/采样33.png)    

**如果点集的位置本身就不好？**

![](../assets/采样34.png)    

> &#x1F446; The **distribution of points** is more important for a good mesh.    

How to sample points to generate high‐quality meshes?    

![](../assets/采样35.png)    

# Centroidal Voronoi Tessellation     

## 定义

**定义**: The VT is a centroidal Voronoi tessellation (CVT) , if each seed coincides with the **centroid** of its Voronoi cell     

![](../assets/采样36.png)    

> &#x1F446; CVT:满是“点与所在区域的重心重合”的 Voronoi 图。    

## 方法

![](../RAW/83-1.png)

• Construct the  VT associated with the points    
• Compute the centroids of the Voronoi regions    
• Move the points to the centroids    
• Iterate until convergent    

## 效果

![](../assets/采样38.png)    

## CVT理论    

CVT energy function:    

$$
F(X)=\sum_{i=1}^{N} \int _{V_i}\rho (X)||X-X_i||^2dX
$$

CVT is a critical point of \\(F(X)\\), an optimal CVT is a global minimizer of \\(F(X)\\)    

### Geometric interpretation     

The CVT energy with \\(\rho (X)\\) identical to 1, is the volume difference between the circumscribed polytope and the araboloid.    

> \\(\rho (x)\\)是种加权，用于内容相关。    
当 \\(\rho =I 时， X为 V_i \\)的重心时能量最小。    

![](../assets/采样39.png)    

The gradient of \\(F(X)\\) is [Iri et al. 1984; Asami 1991; 
Du et al. 1999]:    

$$
\frac{\partial F}{\partial \chi _i} =2m_i(\chi _i-C_i),
$$
where 
$$
m_i=\int _{\chi\in \Omega _i }\rho (\chi )d\sigma
$$

Lloyd’s method is a gradient descent method, thus has linear convergence    
 
 

### Smoothness of F(X)    

Can BFGS method be applied to computing CVT? Or does CVT energy F(X) have required \\(C^2\\) smoothness?    

Results:   
- It has been noted that F(X) is non‐smooth [Iri et al. 
1984], but without proof    
- It has been proved that F(X) is \\(C^1\\) [Cortes et al. 2005]    
- F(X) is \\(C^2\\) in a convex domain in 2D and 3D [Liu et al. 2009]     


### C2 Continuity of F(X)    

![](../assets/采样40.png)    

**Figure**: Illustration of \\(C^2\\) smoothness of CVT energy in 2D     


## CVT的应用

- CVT on Surface    
- CVT for Remeshing    

> [1:20:59]    
把 CVT 算法推广到曲面，可以把距离改为测地线度量     
连续曲面测地距离：表面上的孤长    
离散网格的测地距离：可参数化到平面再计算 


# Optimal Delaunay Triangulation    

ODT energy function:    

$$
E(X)=||f-f_{I,T }||L^1(\Omega)
$$

$$
=\sum _{\tau \in T}\int _\tau f_I(X)dX-\int _\Omega f(X)dX
$$

![](../assets/采样43.png)    



# CVT VS ODT Energy    

• CVT energy    

$$
F(X)=\sum _{i=1}^N\int _{V_i}||X-X_i||^2dX
$$

• ODT energy    

$$
E(X)=\sum _{\tau \in T}\int _\tau f_I(X)dX-\int _\Omega f(X)dX
$$

![](../assets/采样44.png)    

**比较：**
![](../assets/采样46.png)    

本文出自CaterpillarStudyGroup，转载请注明出处。
https://caterpillarstudygroup.github.io/GAMES102_mdbook/  
