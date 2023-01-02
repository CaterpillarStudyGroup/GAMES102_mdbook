# 平面三角网格

给定平面上一些点，如何生成**比较好**的三角剖分？   

## 什么是好的三角剖分？   

![](../assets/采样19.png)    

• Minimal angle   
• Mean ratio   
• Aspect/radius ratio   
• **Singular values**    

> Singular values：奇异值    
计算当前三角形到正三角形的变换矩阵。 A 对奇异值做分解，得到2或3个奇异值。   
奇异值越接近，表明三角形越正。质量越好。     

• …   

