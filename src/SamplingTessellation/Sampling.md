# 采样 (Sampling)   

## 从连续到离散    

* 对象的表达    
• 在数学上，连续表达与计算    
• 在计算机中，离散表达与计算    
* 数值方法：数值微分、数值积分、数值优化    
• 数值分析：离散计算对精确计算的近似程度    
• Fourier分析/变换：离散Fourier分析/变换    
• 卷积（滤波）    
* 在计算机科学（计算机图形学）中，采样无处不在     
• 计算机只能表达离散的数值    
• 例子：int型的数据（量化）    


## 曲线曲面的离散表达    

* 曲线的绘制：   
• GDI/OpenGL 绘制基本单元：点、线段    
• 曲线须离散成多边形    
* 曲面的绘制：  
• OpenGL 绘制基本单元：点、线、三角形   
• 曲面须离散成三角形网格   

![](../assets/采样1.png)    


## 离散的本质：采样 (Sampling)   

 - 曲线曲面的采样    
    - 在参数域上采样    
    - 直接在原始曲线曲面采样    
 - NURBS曲线曲面的采样误差估计    
    - 可进行理论上的误差分析    
 - 逆向工程：   
    - 采样点的获取    
      - 通过扫描硬件设备得到采样点     
      - 通过（多视点几何）重建算法计算得到采样点    
    - 重建问题：如何通过采样点重构原始曲线/曲面    
      - 连续重建：用连续函数来拟合表达    
      - **离散重建：直接得到离散基元表达**    


图像是对区域的采样，视频是对时间的采样    

# 采样与重建    

![](../assets/采样6.png)    


# Sampling Theorem    


• Nyquist–Shannon sampling theorem   

> If a function x(t) contains no frequencies higher than B hertz, it is completely determined by giving its ordinates at a series of points spaced 1/(2B) seconds apart.   

\\(\Rightarrow \\) Generally, **a amount of** samples are equired to **recover** complex signal    


## 采样与信号频率    

> Fourier Analysis   

![](../assets/采样7.png)    

Slide courtesy of Prof. Ren Ng, UC Berkeley   



## 欠采样产生频率的走样    


• 高频函数拟合低频信号：过拟合    
• 低频函数拟合高频信号：欠拟合    

![](../assets/采样8.png)    


# 采样举例

## 1D曲线的采样：分段线性逼近表达    

![](../assets/采样12.png)   


## 2D曲面的采样：分片线性逼近表达     

![](../assets/采样13.png)    

> 三角形面片拟合曲面：分片线性逼近面      
课程以2D为例。    


# 平面区域的采样

## 规则采样     

• 将一个区域分解为若干个小区域    

![](../assets/采样14.png)    


## 不规则采样    

![](../assets/采样15.png)    

> 如何根据不规则的采样点，把平面剖分成子区域（三角形）     

![](../assets/采样16.png)    

# Triangulation   

• 复杂函数的分片线性逼近 (piece‐wise linear approximation)   

![](../assets/采样17.png)    



# Blue Noise Sampling    

• (Left) A uniformly distributed yet randomly located point set    
• (Right) The typical power spectrum, radially averaged ower 
spectrum and anisotropy of blue noise distributions.    

![](../assets/采样18.png)    


> Blue Noise：不均匀且没有规整的 pattern 可通过频谱图来分析。    
