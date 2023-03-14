# 封闭曲面的割缝问题    

> 封闭曲面要展开必须先割缝     

![](../assets/参数49.png)     


# Existing Works 

## Mesh segmentation approaches    

[Julius et al. 2005; Lévy et al. 2002; Sander et al. 2002, 2003; Zhang et al. 2005; Zhou et al. 2004]    

# Minimum spanning tree methods   

*[Sheffer 2002; Sheffer and Hart 2002; Chai et al. 2018]*

**Nodes: extrema points with high curvature/distortion etc**.    

![](../assets/参数50.png)     

> MST 算法1:     
找最大扭曲→找边界最短路径→路径对应割缝      
MST 算法 2：
把曲面映射到球面，找最大扭曲的点，连起来   

# Simultaneous optimization     

*[Poranne et al. 2017; Li et al. 2018]* 

![](../assets/参数51.png)     

> OptCuts 算法     
通过割缝减少中心扭曲    
AutoCuts     
可以实时割开或合并    

# Variational Surface Cutting     

[Sharp and Crane 2018]  

![](../assets/参数52.png)     

扭曲小 && 割缝总长度小    

本文出自CaterpillarStudyGroup，转载请注明出处。
https://caterpillarstudygroup.github.io/GAMES102_mdbook/  
