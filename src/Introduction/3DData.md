# 几何的表达方式

几何的表达方式分为隐式表达和显式表达。  

隐式表达[46:35]是指，不提供点的具体位置，只提供点应满足的约束f(x,y,z)=0。  
隐式表达可以快速判断一个点在不在物体表面上。但是难以列举所有在表面上的点。  

显式表达有两种方式：  
1. 直接给出所有点的具体位置
2. 给出一些点，以及这些点到另一些点的映射关系，例如\\(f:R^2 \rightarrow R^3\\)
显式表达可以快速地列出所有在表面上的点，但难以判断一个点在不在表面上。  

实际场景中，会根据需要使用不同的表达方式

# 隐式表达举例

【P10，1:02:05】

|类型|举例|表达方式|
|---|---|---|
|Algebraic Surface|![](../assets/Intro_49.PNG)| \\(x^2 + y^2 + z^2 = 1\\)|
|Constructive solid Geometry|![](../assets/Intro_50.PNG)| 通过基本几何之间的运算来定义新的几何 |
|Distinct Function| [1:01:23]![](../assets/Intro_51.PNG)|定将一个函数，来描述任意一个点到物体表面的最近的距离。距离为0的点就是边界。|
|Distinct Function|[1:02:20]![](../assets/Intro_52.PNG)|可对距离函数做blending|
|Fractals 分形 |[1：12：44]![](../assets/Intro_56.PNG)|自相似。容易引入走样|

距离函数blend相关的补充：
1. 距离函数blend可以用于物体运动过程的插值。  
![](../assets/Intro_53.PNG)  
图中A和B代表模型在两个动态状态的效果，如果用非SDF(signed distance field)的方式表达，对A和B做线性混合之后会得到这样的效果：  
![](../assets/Intro_54.PNG)  
我们实际想到的是物体从A状态运动到B状态的效果。这个效果与我们预期的不一致。  
如果用SDF来描述A和B，对两个SDF做blend就能够达到目的了。  
2. 两个SDF做blend得到新的SDF，怎么再根据SDF恢复出物体的表面？  
答：marching cube。在格子上找出f(x)=0的点，然后把点连起来。  
![](../assets/Intro_55.PNG)  

> &#x1F4A1; 基于骨骼动作的mesh blending也能达到这个效果。因此重要的不是隐式或显式，而是有没有抓住运动的来源。  

优点：  
- 容易描述
- compact 表达
- 容易判断一个点是否在模型的内部/外部
- 容易计算离表面的距离
- 容易计算光线与表面的夹角  
缺点：
- 难以描述复杂对象

# 显式几何

## 映射[P10]

![](../assets/Intro_57.PNG)  

## 点云 point cloud

list of points

足够可以表示任意的几何形状

常用于扫描输出

常被转换为其它表达方式再使用

## Polygon Mesh

应用最广泛。

以三角形、四边形为主

**obj 文件格式**：
- v：顶点坐标
- vn:顶点法向量，数量同v
- vt：纹理坐标，最多为（顶点数 * 面片数）个
- f：面片，v/vt/vn

----------------------------

> 本文出自CaterpillarStudyGroup，转载请注明出处。  
> https://caterpillarstudygroup.github.io/GAMES101_mdbook/
