# Mesh (surface) Denoising    

Meshes obtained from real world objects are often noisy.    

![](../assets/去躁2.png)    

• Mesh denoising    
• Mesh smoothing    
• Mesh filtering     
• Mesh improvement     
• Surface fairing (*)    

> 这几个词都是去噪的不同表达。    
在连续几何中， fairing 代表光顺，与 smoothing 不同。   
在离散几何中， fairing 与 smoothing 通用。     

## What is noise?   

• High‐frequent tiny parts     
• Small bumps on the surface     
• High curvature parts    
• High fairing energy parts   
• …    

![](../assets/去躁3.png)    

> No Precise Mathematical Definition!    



## Denoising / Smoothing [From Wiki]    


 - In statistics and image processing, to smooth a data set is to create **an approximating function** that attempts to capture **important patterns** in the data, while leaving out noise or other fine‐scale structures/rapid phenomena.    
    - Eliminate high frequency    
    - Preserve global features    

![](../assets/去躁4.png)    


# Smoothing / Denoising Problem    

## 问题定义

 - Input:\\(M\\) （含噪声的网格曲面）     
 - Output:\\(M^0\\) （无噪声的网格曲面）     
 - Denoising model:  \\(M=M^0+\varepsilon \\)      

## Challenges    
    - Both the ideal mesh \\(M^0\\) and the noise \\(𝜀\\) are unknown    
    - “ill‐posed” problem!    


## 原理    

* 假定：网格顶点的数据及连接关系不变    
* 问题转化为：求顶点的新位置，使得“噪声”减少！    
• 顶点进行适当的扰动或偏移    

![](../assets/去躁5.png)    

* 问题：顶点偏移的方向？    


# Mesh Smoothing Problem     

## 定义

* Input: \\(M\\)（含噪声的网格曲面）     
* Output:  \\(M^0\\)（无噪声的网格曲面）    
* Mesh smoothing model:  \\(\nu=\nu^0+\varepsilon n\\) (for all \\(\nu\in M\\))    

* Questions:    
• What is the displacement vector \\(n\\) for vertex \\(𝒗\\) ?   


## Mesh Smoothing Model    

 \\(\nu=\nu^0+\varepsilon n\\) (for all \\(\nu\in M\\))    
     
 - Displacement vector \\(n\\)     
    - The normal of \\(𝒗^0\\)?   ‐‐ unknown! ill‐posed too!    
    - The normal of \\(𝒗\\) : doable     
 - New model: \\(\nu^0=\nu-\varepsilon n\\)    

 - Key: \\(\varepsilon\\) =?   

 ![](../assets/去躁6.png)    

> \\(V是带噪声曲面上的点，V_0\\)是无噪声曲面上的点。    
假设：   
① \\(V是V_0\\)沿几方向上做了一点偏移。    
② \\(n是V_0\\)的法方向。   
③ 当\\(V接近V_0\\)时， \\(V 的法国方向接近 n\\)    

# Filtering   


• Convolution \\((x*h)(t)=\int_{-\infty }^{\infty } x(\tau )h(t-\tau )d\tau\\)     


• Discrete form \\((x*h)(t)= {\textstyle \sum_{𝜏=-\infty }^{\infty }}  x(𝜏 )h(t-𝜏 ) \\)   

![](../assets/去躁7.png)    

几何意义：将函数\\(ℎ(𝑡)\\)作为权来对\\(𝑥(𝑡)\\)进行加权平均（滤波）    
• 将\\(𝑥(𝑡)\\)的局部信息进行混合平均    


## Image Filtering   

![](../assets/去躁8.png)    

## Gaussian Filtering    

• 使用Gauss函数作为权函数   

$$
{I}' (u)=\sum _{p\in N(u)}e^{\frac{||u-P||^2}{2\sigma ^2} }I(P)
$$

![](../assets/去躁9.png)    

> Gauss 函数的好处：   
① 概率密度函数，积分和为1.     
② 具有对称性    
③ 与距离相关    

## Discrete Filtering (mask)    

![](../assets/去躁10.png)    


## Mesh Vertex Filtering: Laplacian operator / Umbrella Operator    

$$
P_{new}\gets P_{old}+\lambda L(P_{old})
$$


![](../assets/去躁11.png)    

> [26:48] Laplace 光顺===极小化所有边长平方和     

## 滤波对象    

* Vertex   
* Normal   
* Curvature    
* Color   
* Other physical properties (texture, albedo, … )     

* Challenges:    
• Iteration number   
• Shrinkage      

![](../assets/去躁12.png)   



# 1. Vertex Filtering    

# 1.1 Laplacian Smoothing    

$$
P_{new}\gets P_{old}+\lambda L(P_{old})
$$

![](../assets/去躁13.png)   

> 存在的问题：    
① 过平滑   
② 不同密度收缩速度不同  

# Laplacian Smoothing    

$$
P^{new} = P^{old}+\lambda L(P^{old})
$$

* Equivalent to box filter in signal processing     
* Apply to all vertices on mesh    
* Typically repeat several times     
* Can describe as energy minimization    
• Energy = sum of squared edge lengths in mesh     
• Parameter\\(\lambda >0\\)controls convergence "speed"     



# Problem of Over‐smoothing   


How to find appropriate and number of iterations?   

![](../assets/去躁14.png)   


# Shrinkage Problem     


>&#x2705;Increases mesh regularity    
>&#x2705;Develops unnatural deformations    


![](../assets/去躁15.png)   


# Improved Laplacian   


* Laplacian   

$$
P^{new} = P^{old}+\lambda L(P^{old})
$$

* Taubin’95    
• Laplacian + Expansion     

$$
P^{new} = P^{old}-(\mu -\lambda )L(P^{old})-\mu \lambda L^2(P^{old}),\mu >\lambda >0
$$


* Bilaplacian    
• Special case of Taubin’s    

$$
P^{new} = P^{old}+\lambda L^2(P^{old})
$$


# Comparison    

![](../assets/去躁16.png)   

 - Drawbacks   
    - Slow    
    - No stoping criteria    

> 图1：原图    
图2：普通 Laplace    
图3：Laplace + 扩张。    
图3去噪同时保留一些特征。 

# 1.2 Mean Curvature Flow    

![](../assets/去躁17.png)   

> 引入平均曲率、考虑了几何特征。    

# Mean Curvature Filtering   

> &#x2705; Increases mesh irregularity.    
> &#x2705; Doesn’t develop unnatural deformations     

![](../assets/去躁18.png)   


# Discrete Mean Curvature    

![](../assets/去躁19.png)   

$$
Hn=\frac{\nabla _PA}{2A} 
$$

$$
Hn=\frac{1}{4A} \sum _j(\cot \alpha _j+\cot \beta _j)(P-Q_j)
$$


# Comparisons   

![](../assets/去躁20.png)   


# 1.3 Bilateral filtering    

![](../assets/去躁21.png)   


# Bilateral filtering    

![](../assets/去躁22.png)   

![](../assets/去躁23.png)   

> Bilateral:双边     
U 和 P 代表U点与P点的位置     
I(U) 和I(P)代表U和P点的值    
分子：U 点对 P 点的影响表现I(P)前面的系数上。     
系数考虑了两方面因素：     
(1) U 与 P 的距离，反映了U 对 P 的影响力。    
(2) I(U) 与I(P)的距离，反映了I(P)的特征性。    
二者都是距离越大权重越小。     
分母，归一化     
除了U和I(U)，还可以根据实际情况加入更多的特征考量。    

# Bilateral filtering of meshes   


 - Height above surface is equivalent to the gray level 
values in images   
 - Apply the bilateral filter to heights     

![](../assets/去躁24.png)   

> 灰线：理想曲面，实际位置未知。    
黄点：曲面上的点，由于带噪声呈上下分布。     
蓝点：黄点中取的任意一点作为例子。

# Bilateral filtering of meshes   


 - Height above surface is equivalent to the gray level 
values in images   
 - Apply the bilateral filter to heights    
 - Move the vertex to its new height     

![](../assets/去躁25.png)   


# Bilateral filtering of meshes   


 - Height above surface is equivalent to the gray level 
values in images    
 - Apply the bilateral filter to heights    
 - Move the vertex to its new height    
 - In practice:   
    - Sharp features    
    - The noise‐free    
      surface is unknown    

![](../assets/去躁26.png)   


# Solution    


 - A plane that passes through the point is the 
estimator to the smooth surface      
 - Plane \\(L=(p,n)\\)    

![](../assets/去躁27.png)   

> 对蓝点做以下估计：    
取P点邻域内的点，做PCA，最大特征值对应的向量为 P点的法向。    
所有点向切平面上投影，得到距离1。    
所有点向法线上投影，得到距离2。     
由于同时考虑了距离1和距离2，因此称双边。   
[>] 前面提到的， feature 和 noise 很难区分。     
比如例子中的棱角和噪声一样，具有高频、曲率大的特点。    
但特征有连续性，在大的区间里表现出规律，而噪声不具备这个特点，可以据此区分。     

# Computing the plane    


* The approximating plane should be:     
• A good approximation to the surface    
• Preserve features   
* Average of the normal to faces in the 1‐ring neighborhood     

![](../assets/去躁28.png)   


# Parameters   


* The two parameters to the weight function: \\(σ_c, 
σ_s\\)    
• Interactively select a  point p and the neighborhood radius ρ       
• \\(σ_c\\) = 1/2 ρ     
• \\(σ_s\\) = stdv ( Nbhd (p, ρ))    
* Number of Iterations     

![](../assets/去躁29.png)   



# Results   

![](../assets/去躁30.png)   



# 1.4 Implicit Mesh Evolutions   


Shape evolution  \\(\frac{\partial P}{\partial t} =F(P)\\)   

\\(M_{n+1}=M_n+\lambda L(M_n)\\) explicit scheme   

\\(M_{n+1}=M_n+\lambda L(M_{n+1})\\) implicit scheme   

$$
\Rightarrow (I-\lambda L)M_{n+1}=M_n
$$

> 认为噪声是沿着法向的偏移，本身就是一种猜测、为什么说用真实曲面的法向会更好呢？[?]     
隐通过求解线性稀疏方程组得到结果（类似全局法）    

# 2. Normal Filtering    


# Normal Filtering   

• 先对法向进行滤波：可使用顶点滤波的任何方法    
• 根据滤波后的法向重建网格顶点    

![](../assets/去躁31.png)   



# 由法向重建顶点   

• 输入：滤波后的法向量场    
• 输出：重建网格顶点，使得其法向量接近输入    
• 优化方法：  
Vertex Updating:   

$$
\begin{cases}
 n_f^T\cdot (x_j-x_i)=0\\\\
n_f^T\cdot (x_k-x_j)=0  \\\\
n_f^T\cdot (x_i-x_k)=0
\end{cases}
$$

Energy:   

$$
E=\sum _{fk}\sum _{i,j\in fk}(n^T_k\cdot (x_j-x_i))^2
$$

**求解线性方程组**   

See more in [Zhang et al. Guided Mesh Normal Filtering. PG 2015.]

> 法向是一阶微分量，可以通过积分求出顶点。    
离散情况下，积分过程变成了线性方程组，方程依据是法向与边垂直。  

# 3. Global Smoothing   


Liu et al. Non‐Iterative Approach for Global Mesh  Optimization. CAD 2007.    



# Smoothing Formulation   

![](../assets/去躁32.png)   

> E(s')，第一项：光滑，第二项：数据保持，关键是如何度量光滑。  

# Smoothing Problem   

![](../assets/去躁33.png)   


# Local Lapacian Fairness   

Local discrete Laplacian smoothing operator   

![](../assets/去躁34.png)   

$$
L(\nu_i)=\nu_i-\sum_{j\in N(j)}w_{ij}\nu_j=0
$$

$$
\delta_{cotangent}:W_{ij}=cot\alpha_{ij}+cot\beta_{ij}
$$



# Laplacian of Mesh     

![](../assets/去躁35.png)   


# Laplacian of Mesh   

• Surface reconstruction    

![](../assets/去躁36.png)   

$$
L(\nu_i)=\nu_i-\sum_{j\in N(i)}w_{ij}v_j=0
$$


# Vertex Constraints     

• Add position constraints for more vertices    

![](../assets/去躁37.png)   

# Adding Vertex Constraints    

\\(min_{{X}'}\\){\\(||L{X}'||^2+\mu ^2\sum _{i\in C}|{\nu}'_i-\nu_i|^2\\)}     

![](../assets/去躁38.png)   


# Face Constraints   

![](../assets/去躁39.png)   



# Adding Face Constraints    

\\(min_{{X}'}\\){\\(||L{X}'||^2+\sum _{<i,j,k>\in T}\lambda ^2|({\nu}'_i+{\nu}'_j+{\nu}'_k)-(\nu_i+\nu_j+\nu_k)|^2\\)}     

![](../assets/去躁40.png)   



# Other Constraints    

• Edge constraints   

![](../assets/去躁41.png)   

• 1‐ring barycenter constraints    

![](../assets/去躁42.png)   

• Other linear constraints    


# Minimizing Energy   

\\(min_{{X}'}\\){\\(||L{X}'||^2+\sum _{i\in C }u ^2|{\nu }'_i-\nu _i|^2+\sum _{<i,j,k>\in T}\lambda ^2|({\nu}'_i+{\nu}'_j+{\nu}'_k)-(\nu_i+\nu_j+\nu_k)|^2\\)} 

$$
\Downarrow 
$$

$$
AX=b
$$


# Least Square Solution     


• An over‐determined system:    

$$
AX=b
$$

• Normal equation:    

$$
A^TAX=A^Tb
$$

$$
X=(A^TA)^{-1}A^Tb
$$


# One Channel Solution   

• Very efficient solution by Cholesky factorization of \\(A^TA\\):     

$$
A^TA=R^TR
$$

R is upper‐triangular and sparse Once R is computed, olving for x, y, z by back‐ substitution:    

$$
R^T\xi=A^Tb
$$

$$
RX=\xi
$$


# Results   

![](../assets/去躁43.png)   

**‘8’-like mesh model**    
**3070 vertices, 6144 triangles**     


# 4. Mesh Improvement    


# Smoothing Everywhere    

![](../assets/去躁44.png)   

* Real life applications    
• Sculpture    
• Decoration    

![](../assets/去躁45.png)   


* Methods    
• Corner cutting    

![](../assets/去躁46.png)   

* Geometric modeling    
• Chaikin's scheme     
• Bézier: de Castljau algorithm   
• B‐spline: knot insertion   
• Subdivision surface    

![](../assets/去躁47.png)   


# Mesh Improvement   

![](../assets/去躁48.png)   

> 什么是质量好？(1) 三角形接近正三角形     

# Mesh Improvement   

![](../assets/去躁49.png)   


# Mesh Improvement 

• Example   

![](../assets/去躁50.png)   


# 其他去噪方法    

* 基于稀疏优化的方法    
• He and Schaefer. Mesh denoising via L0 minimization. Siggraph 2013.    

* 基于压缩感知的方法    
• Wang et al. Decoupling Noises and Features via Weighted L1‐analysis Compressed Sensing.  ACM TOG, 2014.    
* 基于机器学习的方法    
• Wang et al. Mesh Denoising via Cascaded Normal Regression. Siggraph 2016.    
* 很多很多工作…    

> 点云：把点云去噪转化为前面学过的问题。例如取空间上的邻居点作为它的邻域。    
深度相机的数据质量很差，尤其是深度这一维度。    

# 其他数据的去噪   


• Point cloud   

• Volumetric data   

• Depth images    


# Many Problems Remain    

> Mesh smoothing remains to be an active research area   

![](../assets/去躁51.png)   
