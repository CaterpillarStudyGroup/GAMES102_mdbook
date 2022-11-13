# 使用Bernstein基函数表达   

• 使用Bernstein基函数来改写    

$$
f(t)=\binom{1}{1} t^2+\binom{-2}{0} t+\binom{1}{0} 
$$

$$
\downarrow 
$$

$$
f(t)=\binom{1}{0} (1-t)^2+\binom{0}{0} 2t(1-t)+\binom{0}{1} t^2
$$

• 系数顶点与曲线关联性强，具有很好的几何意义     

• 对于交互式曲线设计更观     

![](../assets/B曲-4.png)  


# Bernstein基函数   
• \\(n\\)次Bernstein基函数:\\(B=\\){\\(B_0^{(n)},B_1^{(n)},\cdots ,B_n^{(n)}\\)}   

$$
B_i^{(n)}(t)=\binom{n}{t}t^i(1-t)^{n-i}=B_{i-th basis function}^{(degree)} 
$$

where the binomial coefficients are given by:
$$
\binom{n}{t}=
\begin{cases}
 \frac{n!}{(n-i)!i!} for 0\le i\le n \\\\
0          otherwise
\end{cases}
$$

# Examples: The first few   

$$
B^{(n)}_i(t)=\binom{n}{t}t^i(1-t)^{n-i}
$$

![](../assets/B曲-5.png)  

# 另一个例子   

![](../assets/B曲-6-1.png)    
  
$$
b_0=\binom{0}{1},b_1=\binom{1}{1},b_2=\binom{0}{2}
$$


**用Bernstein基函数所表达的曲线具有非常好的几何意义！** 


![](../assets/B曲-7.png) 