# 隐式曲线拟合   


# 问题   

* 输入：平面上的一些点（设采样自封闭曲线）    
• 一般还需给定或估计点的法向信息       
* 输出：拟合这些点的一个隐式函数       
• 该隐式函数所表达的曲线就是拟合曲线       

![](../assets/瘾曲10.png)    


# 拟合问题的求解步骤    

• 1. 估计法向：利用邻近点来估计切平面   

![](../assets/瘾曲11.png)    


# 拟合问题的求解步骤   

• 1. 估计法向：利用邻近点来估计切平面     
• 2. 拟合一个二元函数：在型值点上值为0，外部（法向方向的点）为正，内部为负    

![](../assets/瘾曲12.png)    


# 隐式函数构造方法   

• Blobby molecules    
• Metaball     
• RBF based method     
• Multi‐level partition of unity implicits (MPU)     
• Poisson reconstruction method     
• Screened Poisson method     
• …       
![](../assets/瘾曲13.png)    
