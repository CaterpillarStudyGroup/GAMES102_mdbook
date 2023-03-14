# 2. Global Simplification Strategies    

## 2.1 Mesh Re‐Tiling [Turk 92]    


Re‐tiling attempts to simplify as well as improve meshing by introducing new “uniformly spaced ” vertices   

![](../assets/简化26.png)    

> 本质上是在曲面上重采样  
把顶点看作曲面上流动的粒子，模拟粒子之间的作用力  
不能保持 Appearance 特征

## 2.2 Mesh Optimization [Hoppe et al 93]    

* Frames simplification as an optimization problem    
• Minimizes some **energy function**    
• Make simple changes to the topology of the mesh    
• Evaluate the energy before and after the change    
• Accept any change that reduces the energy     

$$
\min\int d^2(U,V)
$$

![](../assets/简化28.png)    

> 光顺能量    
minimize Laplacian 能量 [1:06:02图]  

# Basic Topological Operations    

• Edge Collapse   
• Edge Split    
• Edge Swap   

![](../assets/简化29.png)    

本文出自CaterpillarStudyGroup，转载请注明出处。
https://caterpillarstudygroup.github.io/GAMES102_mdbook/  


