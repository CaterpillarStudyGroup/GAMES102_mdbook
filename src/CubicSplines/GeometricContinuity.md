# 曲线的几何连续性   

## 参数连续性  

* 在数学分析/高等数学中，我们所说的“连续性”（光滑性）是指“参数连续性”：   
• 给定 2 条曲线  

\\(x_1(t)\\)定义在\\([t_0,t_1]\\)     
\\(x_2(t)\\)定义在\\([t_1,t_2]\\)  


• 曲线\\(𝒙_1\\)和\\(𝒙_2\\)在\\(t_1\\)称为\\(C^r\\)**连续**的，如果它们的从\\(0^{th}\\)（\\(0\\)阶） 至\\(r^{th}\\)（\\(𝑟\\)阶）的导数向量在\\(𝑡_1\\)处完全相同。  


## 参数连续性  


* \\(C^0\\): position varies continuously    
* \\(C^1\\): First derivative is continuous across junction       
• In other words: the velocity vector remains the same   
* \\(C^2\\): Second derivative is continuous across junction    
• The acceleration vector remains the same   


## 参数连续性   

![](../assets/几何-23.png)

## 参数连续性的不足   
 
• 参数连续性过于严格，在几何设计中不太直观    
• 例子：一条直线   

![](../assets/几何-24.png)


$$
\varphi(t)=\begin{cases}
 v_{0}+\frac{v_{1}-v_{0}}{3} t, 0 \leq t \leq 1\\\\
v_{0}+\frac{v_{1}-v_{0}}{3}+\frac{2\left(v_{1}-v_{0}\right)}{3}(t-1), 1 \leq t \leq 2
\end{cases}
$$

• 但是，
$$
{\varphi }'(1-)=\frac{v_{1}-v_{0}}{3},{\varphi }' (1+)=\frac{2(v_{1}-v_{0})}{3}
$$

• \\(\varphi (t)\\)在\\(t=1\\)的左右导数不相等，因此，\\(\varphi(t)\\)在\\([0,2]\\)中**不是**\\(C^1\\)的，与直线的连续性应是\\(C^\propto\\)的矛盾。   


> 原因：连续**性依赖于参数**的选择，同一条曲线，参数不同，连续阶也不同。 


## 参数连续性的不足   


• 参数连续性过于严格，在几何设计中不太直观   
• 例子：一条直线   

![](../assets/几何-25-1.png)

$$
\varphi(t)=\begin{cases}
 v_{0}+\frac{v_{1}-v_{0}}{3} t, 0 \leq t \leq \frac{2}{3}\\\\
v_{0}+\frac{v_{1}-v_{0}}{3}+\frac{\left(v_{1}-v_{0}\right)}{3}(t-\frac{2}{3}), \frac{2}{3} \leq t \leq 2
\end{cases}
$$


• 则\\({\varphi }' (\frac{2}{3}- )={\varphi }' (\frac{2}{3}+ ),\varphi (t)\\)在\\([0,2]\\)就是\\(C^\infty \\)了。    

• 本质：是引入了**参数的一个变换**  

$$
t=\begin{cases}
 \frac{2}{3}s,0\le s\le \frac{2}{3},\\\\
\frac{3}{4}(s-\frac{2}{3})+1,\frac{2}{3}\le s\le 2.
\end{cases}
$$


• 使得原来不是\\(C^1 \\)的曲线变为\\(C^1 \\)的了。


## 几何连续性   

【**定义**】设\\(\varphi (t)(a\le t\le b)\\)是给定的曲线。若存在一个参数变换\\( t=p(s)(a_1\le s\le b_1)\\),
使得\\(\varphi (p(s))\in C^n[a_1,b_1]\\),且\\(\frac{d\varphi (p(s))}{ds} \ne 0\\),
则称曲线\\(\varphi (t)(a\le t\le b)\\)是\\(n\\)阶几何连续的曲线，记为
$$
\varphi (t)\in GC^n[a,b]
$$

或

$$
\varphi (t)\in G^n[a,b]
$$


## 几何连续性：性质   


【**定义**】设\\(\varphi (t)(a\le t\le b)\\)是给定的曲线。若存在一个参数变换\\( t=p(s)(a_1\le s\le b_1)\\)

使得\\(\varphi (p(s))\in C^n[a_1,b_1]\\),且\\(\frac{d\varphi (p(s))}{ds} \ne 0\\),   
则称曲线\\(\varphi (t)(a\le t\le b)\\)是𝑛阶几何连续的曲线，记为  

\\(\varphi (t)\in GC^n[a,b]\\)或\\(\varphi (t)\in G^n[a,b]\\)

【**性质**】
1. 条件 \\(\frac{d\varphi (p(s))}{ds} \ne 0\\)保证了曲线上无奇点；   
2. 几何连续性与参数选取无关，是曲线本身固有的几何性质； 
3. \\(𝐺^n\\) 的条件比\\(𝐺^n\\)的宽，曲线类型更多；


## 几何连续性的具体形式   

• \\(𝐺^0\\)：表示两曲线有公共的连接端点，\\(C^0\\)与的条件一致   
• \\(𝐺^1\\)：两曲线在连接点处有公共的**切线**，即切线方向连续   
• \\(𝐺^2\\)：两曲线在连接点处有公共的**曲率圆**，即曲率连续     

![](../assets/几何-26.png)


## 曲线设计及编辑工具   


* 矢量曲线设计工具：PPT, Word, Adobe Illustrator,
Corel Draw, …    
• 使用：PowerPoint的曲线编辑工具   

![](../assets/几何-27.png)

![](../assets/几何-28.png)

## 两种连续性的比较   

![](../assets/几何-29.png)