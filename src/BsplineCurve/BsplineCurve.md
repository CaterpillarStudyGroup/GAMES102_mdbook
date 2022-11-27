# B样条曲线  

# 为什么引入B样条曲线

## Bezier曲线的不足   

\\(n\\)次Bezier曲线：\\(n+1\\)个控制顶点    

![](../assets/曲线1.png)   

$$
x(t)=\sum_{i=0}^{n} B_i^n(t)\cdot b_i
$$

> **全局性：牵一发而动全身，不利于设计**  
> 每个基函数在整平[0，1]作用域上都有值，因此具有全局性。
任意一个点的移动都会影响整条曲线。    

[?] 不是可以通过分段来解决吗？   
答：可以，但要分成多个函数来表达。B样条用统一的函数表达分段曲线。

[49:40 图 PDT上没有了]     
1. 参数化，建立 \\(d_i 与t_i\\)之间的关系。    
2. 构造基函数，第 i 个基函数是以\\(t_i\\)为中心的局部函数。    
3. 每个基函数是同一个基函数的平移或伸缩得到。

**原因：基函数是全局的**  

## 样条曲线的不足  

分段的多项式曲线（Bezier曲线）  
优点：分段表达，具有局部性   
缺点：要分成多个函数来表达。

**有无统一的表达方式？**

# 思考：样条曲线的统一表达  


* 形式类比：每个控制顶点用一个基函数进行组合   

$$
x(t)=\sum_{i=0}^{n} N_{i,k}(t)\cdot d_i
$$

* 性质要求：  
• 基函数须局部性（局部支集）  
• 基函数要有正性+权性   
• …    

* 如何构造？   

## 启发： 

Bernstein基函数的递推公式：  

$$
B_i^n(t)=(1-t)B_{i}^{(n-1)}(t)+tB_{i-1}^{(n-1)}(1-t)
$$

with \\(B_0^0(t)=1,B^n_i(t)=0\\) for \\(i\notin \\){ \\(0\dots n\\)}

思路：   
- 局部处处类似定义，由一个基函数平移得到    
- 高阶的基函数由2个低阶的基函数“升阶”得到，利于保持一些良好的性质，比如提高光滑性   

## Key Ideas   

![](../assets/曲线5.png)  

以三次为例    
- We design one basis function 𝑏(𝑡)      
- Properties:   
  - 𝑏(𝑡) is \\(C^2\\) continuous    
  - 𝑏(𝑡) is piecewise polynomial, degree 3 (cubic)   
  - 𝑏(𝑡) is has local support   
   - Overlaying shifted \\(𝑏 (𝑡+i)\\) forms a partition of unity   
  - \\(𝑏(𝑡)\ge 0 \\) for all 𝑡      

In short:   
- All desirable properties build into the basis   
- Linear combinations will inherit these  

# Shifted Basis Functions   

• 型值点参数化：节点向量    

![](../assets/曲线6.png)

Courtesy of Renjie Chen   

> 图中是均匀参数化的例子。 i 是参数， i 的取值构成节点向量基函数通过结点向量来定义，每个基函数定义在几个特定的节点上。    

# Repeated linear interpolation  


• Another way to increase smoothness:    

![](../assets/曲线7.png)  
![](../assets/曲线8.png)  
![](../assets/曲线9.png)  

> 怎么构造基函数？   
从O阶（水平直线）开始，使用t和(1-t)进行线性组合、即升阶每升一次阶，曲线会更光滑，跨度区间会多覆盖一个结点。    

# De Boor Recursion: uniform case       
• The **uniform** B‐spline basis of order 𝒌 (degree 𝒌-𝟏) is given as       

![](../assets/曲线10.png)  

> Uniform:使用均匀参数化     

## B‐spline curves: general case   

* Given: knot sequence \\(t_o < t_1 < \cdots < t_n < \cdots < t_{n+k}\\)
\\((t_0,t_i,\cdots,t_{n=k})\\) is called knot vector)      

* Normalized B‐spline functions \\(N_{i,k}\\)of the order (degree \\(k-1\\)) are defined as:   

$$
N_{i,1}(t)=\begin{cases}
 1,t_i\le t<t_{i+1}\\\\
\\\\
0,otherwise
\end{cases}
$$


$$
N_{i,1}(t)=\frac{t-t_i}{t_{i+k-1}-t_i} N_{i,k-1}(t)+\frac{t_{i+k}-t}{t_{i+k}-t_{i+1}}N_{i+1,k-1}(t)
$$

for  \\(k>1\\), and \\(i=0,...,n\\)   

> 此页公式定义在非均匀结点上。      

## Example 1

![](../assets/曲线11.png)    

$$
N_{i,1}(t)=\begin{cases}
 1,t_i\le t<t_{i+1}\\\\
0,otherwise
\end{cases}
$$

$$
N_{i,1}(t)=\frac{t-t_i}{t_{i+k-1}-t_i} N_{i,k-1}(t)+\frac{t_{i+k}-t}{t_{i+k}-t_{i+1}}N_{i+1,k-1}(t)
$$

for\\( k>1,\\) and \\(i=0,...,n\\)

> \\(N_{i, k}:K 代表阶数，i代表第i\\)个基函数。    
\\(N_{1, 1}和 N_{2, 1}组合，得到 N_{1, 2}\\)    
\\(N_{1, 2}和 N_{2, 2}组合，得到 N_{1, 3}\\)     

## Example  2

![](../assets/曲线12.png)  

## Example  3

![](../assets/曲线13.png)  

# Basis properties   

* For the so defined basis functions, the following properties can be shown:    
• \\(𝑁_{i,k}(t)\\) > 0 for \\(𝑡_i\\) < 𝑡 < \\(t_{i+k}\\)    
•\\(𝑁_{i,k}(t)\\) > 0 for \\(𝑡_0\\) < 𝑡 < \\(t_i\\) or \\(t_{i+k}\\) <t < \\(t_{n+k}\\)    
• \\(\sum_{i=0}^{n} N_{i,k}(t)=1 \\)for \\(t_{k-1}\le t\le t_{n+1} \\)     

* For \\(t_i\le t_j\le t_{i+k}\\), the basis functions  \\(N_{i,k}(t)\\) are \\(C^{k-2} \\) at the knots \\(t_j\\)      


* The interval \\([t_i,t_{i+k}]\\), is called support of \\(N_{i,k}\\)      

> 1.1和1.2以说明了基函数的局部性     
1.3说明权性和凸包性      
2.说明光滑性     

# B‐spline curves  


* B‐spline curves    
• Given:\\(𝑛+1\\) control points \\(𝒅_0,\dots,d_n∈\mathbb{R} ^3\\)     
knot vector \\(𝑇=(t_0,\dots,t_n,\dots,t_{n+k})\\)    

• Then, the B‐spline curve 𝒙(𝑡) of the order 𝑘 is defined as    

$$
x(t)=\sum_{i=0}^{n} N_{i,k}(t)\cdot d_i
$$

• The points \\(𝒅_i\\) are called de Boor points    

**Carl R. de Boor**     
German‐American mathematician        
University of Wisconsin‐Madison   

> B样条本质是分段曲线、但通过 local basis funchion 的方法，有一个公式统一了所有分段曲线。    

例子  

• \\(k=4,n=5\\)     

![](../assets/曲线14.png)  

Support intervals of \\(𝑁_{i,k}\\)  

Curve defined in interval \\(t_3\le t\le t_6\\)    

> 结点重合会导致连续性下降，每增加一重、连续性减一。可以以此方法控制曲线的连续性。     

# B‐spline curves

## B‐spline curves的性质

* Multiple weighted knot vectors  
• So far: \\(𝑇=(t_0,\dots,t_n,\dots,t_{n+k})\\) with \\(t_0< t_1< \dots< t_{n+k}\\)     
• Now: also multiple knots allowed, i.e. with  \\(t_0\le t_1\le \dots\le t_{n+k}\\)   
• The recursive definition of the B spline function \\(𝑁_{i,k}(i=0,\dots,n) \\) works nonetheless as long as no more than 𝑘 knots coincide    

* Effect of multiple knots:   
• set: \\(t_0=t_1=\dots=t_{k-1}\\)    
• and \\(t_{n+1}=t_{n+2}=\dots=t_{n+k}\\)   

\\(𝒅_0\\) and \\(𝒅_n\\) are interpolated      


- 例子1:\\(k=4,n=5\\)

![](../assets/曲线16.png)  


> 要使首未端点被插值，需要把首未端点设置为\\(K\\)重。把B-spline curve 的两个端点都设成\\(n-1\\)重，就会退化为 Bezier curve.      
[1:10:41] Locality     
在神经网络中把 acfivation 改为 local basis funchion. 这样，只需更新 N N 的部分参数。   

- 例子2

![](../assets/曲线17.png)  


## B‐spline curves的性质    

### 性质1：Interesting property:    
• B‐spline functions \\(𝑁_{i,k}(𝑖=0,…,𝑘-1)\\) of the order 𝑘 over the knot vector \\(𝑇=(t_0,t_1,...,t_{2k-1})\\)= 

![](../assets/曲线24-1.png)   


are Bernstein polynomials\\(𝐵_i^{k-1}\\) of degree \\(𝑘-1\\)    


### 性质2

  - Given:
![](../assets/曲线22-1.png )    
    - de Boor polygon \\(𝒅_0,…,𝒅_n\\)    
  - Then, the following applies for the related B‐spline curve \\(x(t)\\):   


### 性质3    

•\\(x(t_0)=d_0,x(t_{n+1})=d_n\\) (end point interpolation)    

•\\(\dot{x} (t_0)=\frac{k-1}{t_k-t_0} (d_1-d_0)\\) (tangent direction at \\(d_0,\\) similar in \\(d_n\\))    

• \\(x(t)\\) consists of \\(n-k+2\\) polynomial curve segments of degree \\(k-1\\) (assuming no multiple inner knots)    


### 性质4

• Multiple inner knots ⇒ reduction of continuity of\\(𝑥(𝑡)\\).    
𝑙‐times inner knot \\((1\le 𝑙 < 𝑘)\\) means         
\\(𝐶^{k-𝑙-1}\\) ‐continuity     
• Local impact of the de Boor points: moving of \\(𝑑_i\\) only changes the curve in the region \\([𝑡_i,t_{i+k}]\\)    
• The insertion of new de Boor points does not change the polynomial degree of the curve segments        


### 性质5

• Locality of B‐spline curves     
![](../assets/曲线19.png)   


## Evaluation of B‐spline curves   
• Using B‐spline functions   
• Using the de Boor algorithm
Similar algorithm to the de Casteljau algorithm for Bezier curves; consists of a number of linear interpolations on the de Boor polygon     


# The de Boor algorithm   

## 算法背景

• Given:     
\\(𝒅_0,…,𝒅_n\\): de Boor points     

$$
(t_0,\cdots ,t_{k-1}=t_0,t_k,t_{k+1},\dots ,t_n,t_{n+1},\dots ,t_{n+k}=t_{n+1})
$$

Knot vector

• wanted:     
Curve point \\(𝒙(𝑡)\\)       of the B‐spline curve of the order 𝑘    

> [?] 这个算法是要算什么？    

## 算法过程    

1. Search index with \\(t_r\le  t\le t_{r+1}\\)   
2. for \\(i=r-k+1,\cdots ,r\\)
$$
d^0_i=d_i
$$

• for \\(j=1,\cdots ,k-1\\)   
for \\(i=r-k+1+j,\cdots ,r\\)    

$$
d_i^j=(1-a^j_i) \cdot  d^{j-1}_{i-1}+a_j^i \cdot  d^{j-1}_i
$$

with \\(a_i^j=\frac{t-t_i}{t_{i+k-j}-t_i} \\)

• Then: \\(d^{k-1}_r=x(t)\\)    


# B样条曲线：分段Bezier曲线    
• \\(n=3\\)    

![](../assets/曲线20.png)   

> **B：Basic（亦称“基本样条”）**



# B样条的其他理论知识  

* B样条的许多性质   
• 局部凸包性、变差缩减性、包络性   
• B样条的导数、积分递推式、几何作图    
* 重节点的B样条基函数及B样条曲线   
* Bezier样条曲线转换为B样条曲线    
* **B样条插值方法**    
* …   

![](../assets/曲线21.png)   

> [?] 插值这一部分没听懂     