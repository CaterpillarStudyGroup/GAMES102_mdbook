# 算法描述   
    
Input: points  \\(𝒃_0,𝒃_1,\dots 𝒃_n∈ \mathbb{R} ^3\\)       
Output: curve \\(x(t),t∈ [0,1]\\)    


# 过程示例    

Repeated convex combination of control points   

$$
b_i^{(r)}=(1-t)b_i^{(r-1)}+tb_{i+1}^{(r-1)}
$$

![](../assets/B曲2-2.png) 

> 点 \\(b_0^{(0)},b_0^{(1)},b_0^{(2)},b_0^{(3)}是曲线 b_0^{(0)},b_0^{(3)}\\)的控制点。    

![](../assets/B曲-23-1.png)   

# 总结   

![](../assets/B曲-27.png)   

* 给定t，计算Bezier曲线\\(x(t)\\)上参数为\\(t\\)的点    

> [30:18]局限性：一次只能针对一个\\(t\\)值计算。    

* 良好的几何意义：该点将曲线一分两条子Bezier 曲线，其控制顶点是中间生成的点    
* 可用于Bezier曲线的离散及求根等许多应用    

