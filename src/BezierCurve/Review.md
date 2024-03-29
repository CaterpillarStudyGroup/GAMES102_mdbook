# 函数/曲线拟合     

* 从**代数观点**来看：从一组基函数所张成的函数空间中，找一个“好”的函数来拟合给定的采样点。     
比如幂基{\\(1,x,x^2,\cdots ,x^n\\)}      
\\((n=2) \\)二次多项式：\\(𝑓(t)=at^2+bt+c\\)   

* 参数曲线形式：\\(f(t)=\binom{x(t)}{y(t)} \\)    

# 建模的两种形式   

$$
𝑓(t)=at^2+bt+c
$$

1. 重建（Reconstruction/Fitting）       
• 逆向工程：形状已有，要将其“猜”出来    
• 采样\\(\to \\)拟合：需要函数空间足够丰富（表达能力够）   
• 代数观点：{\\(a,b,c\\)}作为基函数的组合权系数     
• 输入：采样点{\\(S_j,j=0\sim m\\)} 及基函数{\\(b_i(t),i=0\sim n\\)}     
• 输出：拟合函数的系数{\\(p_i,i=0\sim n\\)}       

2. 设计（Design）    
• 自由设计：凭空产生，或从一个简单的形状编辑得到     
• 交互式编辑：几何直观性要好，具有好性质的基函数使得交互设计更直观    
• **几何观点**：基函数{\\(t^2,t,1\\)}作为控制点的组合权系数   
• 输入：交互输入（或者反求）控制顶点{\\(p_i,i=0\sim n\\)}     
• 输出：曲线\\(f(t)\\)   

---  

> 本文出自CaterpillarStudyGroup，转载请注明出处。
https://caterpillarstudygroup.github.io/GAMES102_mdbook/


