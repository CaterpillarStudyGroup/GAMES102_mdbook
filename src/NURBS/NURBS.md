# NURBS: Non‐Uniform Rational B‐Spline （非均匀有理B样条）   

NURBS: Rational B‐Splines   
 - Formally:(\\(𝑁^{(d)}_i\\)
:B‐spline basis function 𝑖 of degree d)     

$$
f(t)=\frac{\sum_{i=1}^{n}N_i^{(d)}(t)w_ip_i }{ \sum_{i=1}^{n}N_i^{(d)}(t)w_i} 
$$

 - Knot sequences etc. all remain the same    
 - De Boor algorithm – similar to rational de Casteljau alg.   
    - option 1. – apply separately to numerator, denominator   
    - option 2. – normalize weights in each intermediate result   
      - the second option is numerically more stable     

# NURBS曲线
* 影响NURBS曲线建模的因素   
• 控制顶点：用户交互的手段   
• 节点向量：决定了B样条基函数   
• 权系数：也影响曲线的形状，生成圆锥曲线等    

![](../assets/有理曲线-9.png)   

* NURBS曲线的性质    
• 大部分与Bezier/B样条曲线类同：具有良好的几何直观性     

