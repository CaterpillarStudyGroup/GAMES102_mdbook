# 极小曲面    

• 平均曲率处处为0的曲面   

![](../assets/微分38.png)    

> 每个点都是马鞍点     
常见的极小曲面肥皂泡。    

> 建筑中使用极小曲面，好看、省材料、不积水   

# 极小曲面的平均曲率流    

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

## Laplace Operator (Umbrella Operator)    

$$
L(P)=\frac{1}{n} \sum_{i=1}^{n} \overrightarrow{PQ_i} =\frac{1}{n} \sum_{i=1}^{n}Q_i-P
$$

![](../assets/微分50.png)    


## 离散平均曲率流   

![](../assets/微分51.png)  

> [?] 这个公式还不理解？    
\\(\lambda \\)太大会不收敛。\\(\lambda \\)取小一点多走几步。     

## Discrete Mean Curvature     

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

# 封闭曲面    

• 不固定任何顶点    
• 迭代结果如何？   

![](../assets/微分54.png)  


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