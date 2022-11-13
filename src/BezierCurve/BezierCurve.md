# Bezier曲线   

• \\(n\\)次Bezier曲线:\\(n+1\\)个控制顶点    
$$
x(t)=\sum_{i=0}^{n} B^n_i(t)\cdot b_i
$$

**控制顶点     
控制多边形**

![](../assets/B曲-8.png)    



> Bezier曲线的性质来源于Bernstein**基函数**的性质
（曲线是控制顶点的线性组合构成的，基函数提供了组合系数）


# 例子：3次Bezier曲线    

![](../assets/B曲-9.png) 

$$
• f(t)=\sum_{i=1}^{3} B^3_ip_i,t\in [0,1]
$$

![](../assets/B曲-10.png) 


# 例子：更复杂的Bezier曲线    

![](../assets/B曲-11.png) 


# 例子：3D空间的Bezier曲线（单参数）   

$$
• f(t)=\sum_{i=1}^{n} B^n_ip_i,t\in [0,1]
$$

![](../assets/B曲-12.png) 
