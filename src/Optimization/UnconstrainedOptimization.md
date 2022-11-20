# 无约束的优化问题    


# Unconstrained Optimization    

$$
\min_xf(x)
$$

• Gradient descent    
• Newton    
• Quasi‐Newton    
• Coordinate descent    

![](../assets/优化9.png)   



# 梯度下降法   
(Gradient descent)   

![](../assets/优化10.png)   

$$
x_{k+1}=x_k-\alpha _k\nabla f(x_k)
$$

# 梯度下降法   
(Gradient descent)   

**Line search**    
\\(\Downarrow \\)    
\\(x_{k+1}=x_k-\alpha _k\nabla f(x_k)\\)    

> **Gradient descent**    

# 牛顿法 (Newton’s method)    

![](../assets/优化11.png)   


# 拟牛顿法 (Quasi‐Newton)    

![](../assets/优化12.png)   

* Estimate the Hessian based on previous gradients    
* Recursively inverse Hessian    
 > • BFGS (Broyden–Fletcher–Goldfarb–Shanno algorithm)    
  • L‐BFGS    


# 坐标下降法 (Coordinate descent)    

**Obj**: minimize\\(_{x,y},𝐸(𝑥, 𝑦)\\)     

• Alternating variables    

Repeat    
1. \\( y_{k+1}=\min_yE(x_k,y)\\)  
2. \\(x_{k+1}=\min_xE(x,y_{k+1})\\)    


