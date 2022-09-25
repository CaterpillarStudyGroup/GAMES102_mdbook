
# Bezier曲线

# 回顾：函数/曲线拟合

• **逆向工程**中的建模问题：给定产品，用测量的方法得到产品外形上的一些采样点，然后通过拟合的方法得到产品外形的表达。   

![](../assets/B曲-1.png)  

# 回顾：函数/曲线拟合

* 从**代数观点**来看：从一组基函数所张成的函数空间中，找一个“好”的函数来拟合给定的采样点。     
* 比如幂基{\\(1,x,x^2,\cdots ,x^n\\)}      
• \\((n^2) \\)二次多项式：\\(𝑓(t)=at^2+bt+c\\)    
• 参数曲线形式：\\(f(t)=\binom{x(t)}{y(t)} \\)    

# 使用幂基来表达曲线   

• 二次多项式曲线（抛物线）:

$$
𝑓(t)=at^2+bt+c
$$

![](../assets/B曲-2.png)  

Courtesy of Renjie Chen    

# 使用幂基来表达曲线   

• 二次多项式曲线（抛物线）:   
$$
𝑓(t)=at^2+bt+c
$$

![](../assets/B曲-3.png)   

> 系数顶点与曲线本身无直观的联系：无几何意义！ 

> 不利于用户来交互修改曲线：设计建模    


# 建模的两种形式

$$
𝑓(t)=at^2+bt+c
$$

* 1.重建（Reconstruction）       
• 逆向工程：形状已有，要将其“猜”出来    
• 采样\to 拟合：需要函数空间足够丰富（表达能力够）   
• 代数观点：{\\(a,b,c\\)}作为基函数的组合权系数     
* 2.设计（Design）    
• 自由设计：凭空产生，或从一个简单的形状编辑得到     
• 交互式编辑：几何直观性要好    
• **几何观点**：基函数{\\(t^2,t,1\\)}作为控制点的组合权系数   


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

# 使用Bernstein基函数表达   
• 系数顶点与曲线关联性强，具有很好的几何意义     

• 对于交互式曲线设计更观     

![](../assets/B曲-4.png)  


# Bernstein基函数
• \\(n\\)次Bernstein基函数:\\(B=\\){\\(B_0^{(n)},B_1^{(n)},\cdots ,B_n^{(n)}\\)}    
$$
B_i^{(n)}(t)=\binom{n}{t}t^i(1-t)^{(n-i)}=B_{i-th basis function}^{degree} 
$$

where the binomial coefficients are given by:
𝑛
𝑖 ൌ ቐ 𝑛! 𝑛 െ 𝑖 ! 𝑖! for 0 ൑ 𝑖 ൑ 𝑛 0 otherwise
Examples: The first few
• 𝐵
଴
ଷ
≔ 1െ𝑡
ଷ
• 𝐵
ଵ
ଷ ≔ 3𝑡 1െ𝑡
ଶ
• 𝐵
ଶ
ଷ ≔ 3𝑡
ଶ 1െ𝑡
• 𝐵
ଷ
ଷ ≔ 𝑡
ଷ
𝐵௜
௡ 𝑡 ൌ
𝑛
𝑖
𝑡௜ 1െ𝑡 ௡ି௜
𝐵
଴
଴ ≔ 1
𝐵
଴
ଵ ≔1െ𝑡
𝐵
ଵ
ଵ ≔ 𝑡
𝐵
଴
ଶ
≔ 1െ𝑡
ଶ
𝐵
ଵ
ଶ ≔ 2𝑡 1െ𝑡
𝐵
ଶ
ଶ ≔ 𝑡
ଶ
另一个例子
𝒃
଴
ൌ
0
1 , 𝒃
ଵ
ൌ
1
1 , 𝒃
ଶ
ൌ
0
2
用Bernstein基函数所表达的
曲线具有非常好的几何意义！
Curve     basis function     control points
௜ ௜
௡
௜ୀଵ
Notations
Bezier曲线
• 次Bezier曲线： 个控制顶点
𝑥 𝑡 ൌ෍𝐵௜௡ 𝑡 ⋅𝑏௜
௡
௜ୀ଴
Bezier曲线的性质来源于Bernstein基函数的性质
（曲线是控制顶点的线性组合构成的，基函数提供了组合系数）
控制顶点
控制多边形
例子：3次Bezier曲线
• ௜ଷ ௜ ଷ௜ୀଵ
例子：更复杂的Bezier曲线
分段Bezier曲线
3D空间的Bezier曲线（单参数）
• ௜௡ ௜ ௡௜ୀଵ
Bernstein基函数及
Bezier曲线的性质
Bernstein基函数
• Bernstein基函数:  ଴௡ ଵ௡ ௡௡
• 𝑛次（ 𝑛൅1阶）Bernstein基函数:
𝐵௜ ௡ 𝑡 ൌ 𝑛𝑖 𝑡௜ 1െ𝑡 ௡ି௜ ൌ 𝐵௜ି୲୦ ୠୟୱ୧ୱ ୤୳୬ୡ୲୧୭୬ ୢୣ୥୰ୣୣ
• 对称性：𝐵௜௡ 𝑡 ൌ𝐵௡ି௜ ௡ 1െ𝑡
• 𝐵௜ ௡ 𝑡 在𝑡 ൌ ௜௡ 达到最大值
性质1. 正权性
• 正性（非负性）+  权性
• 𝐵௜ ௡ 𝑡 ൒ 0 , ∀𝑡 ∈ ሾ0,1ሿ
• ∑ 𝐵௜ ௡ 𝑡 ൌ1 ௡௜ୀଵ , ∀𝑡 ∈ ሾ0,1ሿ
• Bezier曲线的凸包性
性质2.  基性
•
଴
௡
ଵ
௡
௡
௡ 是次数不高于 的多项式
集合（空间）的一组基
• 与幂基可以相互线性表达：
性质3. 递推公式
• 基函数的递推公式
௜
௡
௜
௡ିଵ
௜ିଵ
௡ିଵ
with  ଴଴ ௜௡ for 
• 由 𝑛െ1 𝑖 ൅ 𝑛െ1 𝑖െ1 = 𝑛𝑖 可推导得到
• 高阶的基函数由2个低阶的基函数“升阶”得到
• 利于保持一些良好的性质
性质4. 端点插值性
• 𝐵଴௡ 0 ൌ 1, 𝐵ଵ௡ 0 ൌ⋯ൌ𝐵௡௡ 0 ൌ0
• 𝐵଴௡ 1 ൌ⋯ൌ𝐵௡ିଵ ௡ 1 ൌ 0, 𝐵௡௡ 0 ൌ1
• Bezier曲线经过首末两个控制顶点 ଴ ௡
性质5. 导数
•
ௗ
ௗ௧
𝐵௜ ௡ 𝑡 ൌ𝑛 𝐵௜ିଵ௡ିଵ 𝑡 െ𝐵௜ ௡ିଵ 𝑡 
•
ௗమ
ௗ௧మ 𝐵௜ ௡ 𝑡 ൌ𝑛 𝑛െ1 𝐵௜ିଶ௡ିଶ 𝑡 െ 2𝐵௜ିଵ௡ିଶ 𝑡 ൅𝐵௜ ௡ିଶ 𝑡
• Bezier曲线的导数（切线）
• Given:   ଴ ௡,  ௜ ௡ ௡ ௜ୀ଴ ௜
• 𝒇ᇱ 𝑡 ൌ𝑛 ∑ 𝐵௜௡ିଵ 𝑡 ௡ିଵ ௜ୀ଴ 𝒑௜ାଵ െ 𝒑௜
• 𝒇 ௥ 𝑡 ൌ ௡! ௡ି௥ ! ⋅ ∑ 𝐵௜௡ି௥ 𝑡 ⋅Δ௥𝒑௜ ௡ି௥ ௜ୀ଴
Bezier曲线的端点性质
• 端点插值：
𝒇 0 ൌ𝒑଴
𝒇 1 ൌ𝒑௡
• 端点的切线方向与边相同：
𝒇ᇱ 0 ൌ𝑛 𝒑ଵ െ 𝒑଴
𝒇ᇱ 1 ൌ𝑛 𝒑௡ିଵ െ 𝒑௡
• 端点的2阶(k)切线与3点(k+1)相关：
𝒇ᇱᇱ 0 ൌ𝑛 𝑛െ1 𝒑ଶ െ 𝟐𝒑ଵ ൅ 𝒑଴
𝒇ᇱᇱ 1 ൌ𝑛 𝑛െ1 𝒑௡ െ 2𝒑௡ିଵ ൅ 𝒑௡ିଶ
结合几何意义来理解
性质6. 升阶
1െ𝑡 𝐵௜௡ 𝑡 ൌ ሺ1 െ 𝑖 𝑛൅1ሻ𝐵௜௡ାଵ 𝑡
𝑡𝐵௜௡ 𝑡 ൌ 𝑖൅1 𝑛൅1𝐵௜௡ାଵ 𝑡
• Bezier曲线的升阶
𝒇 𝑡 ൌ෍𝐵௜௡ାଵ 𝑡 𝑛൅1െ𝑖 𝑛൅1 𝑷௜ ൅ 𝑖 𝑛൅1𝑷௜ିଵ
௡ାଵ
௜ୀ଴
Bezier曲线的
de Casteljau算法
（Bezier曲线的作图算法与细分）
De Casteljau algorithm
• Algorithm description
• Input: points           
𝒃
଴, 𝒃
ଵ,…𝒃
௡ ∈ ℝ
ଷ
• Output: curve             
𝒙 𝑡 ,𝑡 ∈ 0,1
• Geometric construction of the points 
𝒙
𝑡 for given 
𝑡:
𝒃௜
଴ 𝑡 ൌ𝒃௜, 𝑖 ൌ 0, … , 𝑛
𝒃௜
௥ 𝑡 ൌ 1െ𝑡 𝒃௜௥ିଵ 𝑡 ൅ 𝑡 𝒃௜ାଵ ௥ିଵ
𝑡
𝑟 ൌ 1, … , 𝑛 𝑖 ൌ 0, … , 𝑛 െ 𝑟
• Then 
𝒃
଴
௡
𝑡 is the searched curve point 
𝒙
𝑡 at the 
parameter value 
𝑡
De Casteljau algorithm
• Repeated convex combination of control points
௜
௥
௜
௥ିଵ
+
௜ାଵ
௥ିଵ
𝒃
଴
଴
𝒃
ଵ
଴
𝒃
ଶ
଴
𝒃
ଷ
଴
De Casteljau algorithm
• Repeated convex combination of control points
௜
௥
௜
௥ିଵ
+
௜ାଵ
௥ିଵ
𝒃
଴
଴
𝒃
ଵ
଴
𝒃
ଶ
଴
𝒃
ଷ
଴
𝑡
𝒃
଴
ଵ
𝒃
ଵ
ଵ
𝒃
ଶ
ଵ
𝑡
𝑡
De Casteljau algorithm
• Repeated convex combination of control points
௜
௥
௜
௥ିଵ
+
௜ାଵ
௥ିଵ
𝒃
଴
଴
𝒃
ଵ
଴
𝒃
ଶ
଴
𝒃
ଷ
଴
𝑡
𝒃
଴
ଵ
𝒃
ଵ
ଵ
𝒃
ଶ
ଵ
𝑡
𝑡
𝑡
𝑡
𝒃
଴
ଶ
𝒃
ଵ
ଶ
De Casteljau algorithm
• Repeated convex combination of control points
௜
௥
௜
௥ିଵ
+
௜ାଵ
௥ିଵ
𝒃
଴
଴
𝒃
ଵ
଴
𝒃
ଶ
଴
𝒃
ଷ
଴
𝑡
𝒃
଴
ଵ
𝒃
ଵ
ଵ
𝒃
ଶ
ଵ
𝑡
𝑡
𝑡
𝑡
𝒃
଴
ଶ
𝒃
ଵ
ଶ
𝑡
𝒃
଴
ଷ
ൌ
𝑥
ሺ
𝑡
ሻ
De Casteljau scheme
De Casteljau algorithm
• Algorithm:
• for r=1..
n
• for i=0..
n
‐
r
•
𝒃௜
௥
ൌ 1 െ
𝑡
𝒃௜௥ିଵ
൅ 𝑡 
𝒃௜ାଵ௥ିଵ
• end
• end
• return 
𝒃
଴
௡
只有线性运算，计算稳定
复杂度：
𝑂
𝑛
ଶ time
𝑂
𝑛 memory
De Casteljau algorithm
• 计算Bezier曲线 上参数为 的点
• Bisect control polygon in ratio 
𝑡: 1 െ
𝑡
• 良好的几何意义：该点将曲线一分两条子Bezier 曲线，其控制顶点是中间生成的点
• 可用于Bezier曲线的离散及求根等许多应用
De Casteljau algorithm
• 计算Bezier曲线 上参数为 的点
• Bisect control polygon in ratio 
𝑡: 1 െ
𝑡
• 良好的几何意义：该点将曲线一分两条子Bezier 曲线，其控制顶点是中间生成的点
• 可用于Bezier曲线的离散及求根等许多应用
De Casteljau algorithm
• 计算Bezier曲线 上参数为 的点
• Bisect control polygon in ratio 
𝑡: 1 െ
𝑡
• 良好的几何意义：该点将曲线一分两条子Bezier 曲线，其控制顶点是中间生成的点
• 可用于Bezier曲线的离散及求根等许多应用
De Casteljau algorithm
• 计算Bezier曲线 上参数为 的点
• Bisect control polygon in ratio 
𝑡: 1 െ
𝑡
• 良好的几何意义：该点将曲线一分两条子Bezier 曲线，其控制顶点是中间生成的点
• 可用于Bezier曲线的离散及求根等许多应用
几何样条曲线
用分段Bezier曲线来插值型值点
• 给定型值点:
𝒌଴,…,𝒌௡ ∈ ℝଷ
• 每两点间生成一段Bezier曲线，使得整体曲线满足一
定的连续性(𝐶଴, 𝐶ଵ, 𝐶ଶ)
问题：两Bezier曲线的拼接条件
• 𝐶଴, 𝐶ଵ, 𝐶ଶ?
回顾：Bezier曲线的端点性质
• 端点插值：
𝒇 0 ൌ𝒑଴
𝒇 1 ൌ𝒑௡
• 端点的切线方向与边相同：
𝒇ᇱ 0 ൌ𝑛 𝒑ଵ െ 𝒑଴
𝒇ᇱ 1 ൌ𝑛 𝒑௡ିଵ െ 𝒑௡
• 端点的2阶(k)切线与3点(k+1)相关：
𝒇ᇱᇱ 0 ൌ𝑛 𝑛െ1 𝒑ଶ െ 𝟐𝒑ଵ ൅ 𝒑଴
𝒇ᇱᇱ 1 ൌ𝑛 𝑛െ1 𝒑௡ െ 2𝒑௡ିଵ ൅ 𝒑௡ିଶ
两Bezier曲线的拼接条件
𝐶଴连续
𝐺ଵ连续：三点共线
𝐶ଵ连续：三点共线
且等长
两Bezier曲线的拼接条件
• ଶ 连续
• 𝑑ଶ 𝑑𝑡ଶ ⁄ 为 𝒑ଶ െ 2𝒑ଵ ൅ 𝒑଴ ,  𝒑௡ െ 2𝒑௡ିଵ ൅ 𝒑௡ିଶ
• 阴影三角形相似
• ଶ 连续？
构造3次插值Bezier曲线
的几何方法
在作业4中也实现下
广义样条曲线
• 分段的多项式曲线（Bezier曲线）
谢 谢！