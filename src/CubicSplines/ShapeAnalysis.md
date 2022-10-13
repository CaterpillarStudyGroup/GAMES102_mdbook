![](../assets/建模100.png)    


# Recap: 3D Content Creation    

• Surface reconstruction    
• Geometric modeling    
• Geometry processing    
• Creative generation    
• …     


# Analyzing and Understanding 3D Contents    


• Organize Geometric Data    
• Understand Structure and Relationships    
• Understand Semantics and Functionality    
• Synthesizing New Shapes    
• …     



# 三维几何处理：从局部到**全局**    




# From low‐ to high‐level processing     

* Local level analysis    
• purely geometry/content‐driven    
• mathematical formulation of objectives    
• Examples: curvature and normal estimation, mesh smoothing, simplification, remeshing, parameterization…    
* High level analysis    
• non‐local analysis    
• not easy to formulate objectives mathematically    
• **Semantics** is hard!    


# Problems of Shape Analysis   


# Understanding Shapes    

* Shape features     
• Feature points     
• Feature lines    
• Saliency    



# Understanding Shapes    

• Alignment (upright)    



# Understanding Shapes     

• Shape segmentation (components)    



# Understanding Shapes    

* Co‐segmentation of a set of shapes     
• More knowledge can be inferred from multiple shapes rather than an individual shape     


# Understanding Shapes    

• Labeling    




# Understanding Shapes    

• Symmetries    




# Understanding Shapes    

• Skeleton    




# Understanding Shapes    

* Shape matching    
• Similarity    
• Correspondences    



# Understanding Shapes   


• Shape retrieval    





# Understanding Shapes   

• Classification     




# Understanding Shapes    

• Structures   
• Hierarchical structures     



# Understanding Shapes    

• Functionality    



# Understanding Shapes     

• Object affordance    



# Understanding Shapes     

* Abstraction of shapes    
• [Mehra et al. SIGAsia 2009]    


* Understanding assemblies    
– [Mitra et al. SIG 2010]    



# Shape Descriptors    


# 核心问题：形状表征（描述子、特征）    
(Shape representation/descriptor/feature)    




# 例子：模型分割‐根据特征的聚类     
(Clustering/Labeling)    





# 三维数据的信息    



* 点坐标(x,y,z)    
* 几何量    
• 长度、角度、面积、 体积    
* 微分量     
• 法向量    
• 曲率     
* 拓扑量    
• 连接关系    
• Laplace谱    
* 映射度量    
• 雅可比（变形量）   
• 共形比   
* …    



# Shape Descriptors    


* Shape Descriptors     
• Fixed dimensional vector    
• Independent of model representation    
• Easy to match     




# Shape Descriptors    

* Representation:    
• **What can you represent**?    
• What are you representing?    
* Matching:    
• How do you align?   
• Part or whole matching?    





# Shape Descriptors    

* Representation:    
• What can you represent?    
• What are you representing?    


* Matching:    
• How do you align?    
• Part or whole matching?    




# Shape Descriptors    

* Representation:    
• What can you represent?    
• What are you representing?    



* Matching:    
• **How do you align**?    
• Part or whole matching?   





How do you represent models across the space of 
transformations that don’t change the shape?



# Shape Descriptors    


* Representation:    
• What can you represent?    
• What are you representing?    


* Matching:   
• How do you align?   
• Part or whole matching?   


Can you match part of a shape to the 
whole shape?


# Extended Gaussian Image     
[Horn, 1984]    


• Represent a model by a spherical function by binning 
surface normals      




# Extended Gaussian Image    
[Horn, 1984]

* Properties:    
• Invertible for convex shapes    
• 2D array of information    
• Can be defined for most models    
* Limitations:    
• Too much information is lost    
• Normals are sensitive to noise    



# Shape Histograms    
[Ankerst et al., 1999]   

• Shape descriptor stores a histogram of how much surface resides at different bins in space    




# Gaussian Euclidean Distance Transform    
[Kazhdan et al., 2003]


• The value at a point is obtained by summing the Gaussian of the closest point on the model surface.    
> &#x2705; Distributes the surface into adjacent bins    
> &#x2705;Maintains high‐frequency information    





# Spherical Extent Function    
[Vranic et al. 2002]

• For every view direction, store the distance to the first 
point a viewer would see when looking at the origin.    




# Spherical Extent Function    

* A model is represented by its star‐shaped envelope:
• The minimal surface containing the model with the property that the center sees every point on the surface    
• Transforms arbitrary genus models to genus‐0 surfaces    








# Spherical Extent Function    

* Properties:    
• Can be defined for most models    
• Invertible for star‐shaped models    
• 2D array of information    
* Limitations:    
• Distance only measures angular proximity    


# Light Field Descriptor    
[Chen et al. 2003]    


• For every view direction, store the image the viewer 
would see when looking at the origin.    



# Light Field Descriptor    

• Hybrid boundary/volume representation    



# Light Field Descriptor    

 - Properties:    
    - Can be defined for most models    
    - Invertible for star‐shaped models    
    - 4D array of information    
    - Similarity = sum of area and contour similarities    
      - There is a well defined interior    
      - Can parameterize contours in 2D     



      

# 各种人工定义的3D形状特征    







# Methodology    

# Traditional Methods     



# 特征工程的两个主要问题    





# 如何选择合适的特征？   





# 想法：稀疏学习选择合适的特征    
[Hu et al. SGP 2012]    



• 稀疏学习的本质：聚类    
• 子空间聚类(Subspace clustering)    




# Subspace Clustering     
[Vidal 2010]    


* Input: 
• high dimensional datasets having low intrinsic dimensions
• {\\(x_j\\)}\\(_{j=1,…,N,}x_t ∈ ℝ^D\\)
 

* Output:    
– multiple low‐dimensional linear subspaces    
– 𝐿, \\(𝑃_1, 𝑃_2\\)   



# Formulation: Group Lasso    

* Our solution:
• apply subspace clustering in each feature space
• add the <u>consistent multi‐feature penalty<\u>      


$$
\underset{W_{1}, \ldots, W_{H}}{\min} \quad \sum_{h=1}^H \mathcal{F}(W_{h})+P_{\text {cons }}\left(W_{1}, W_{2}, \ldots, W_{H}\right)
$$ 

$$
s.t.  \quad W_h \ge 0, \operatorname{diag}(W_{h})=0, \quad h=1,2, \ldots, H
$$

$$
where \quad \mathcal {F} (W_h) =||X_h W_h-X_h||_{F}^{2}+ \lambda||W_{h}^{T} W_{h}||_{1,1} 
$$

$$
where \quad \mathcal {F} (W_h) =||X_h W_h-X_h||_{F}^{2}+ \lambda
$$

$$
||W_{h}^{T} W_{h}||_{1,1} 
$$



# Consistent multi‐feature penalty    


1. Find the most similar patch pairs 
2. Corresponding patches need not be similar in all features   



𝑃௖௢௡௦
𝑊ଵ, 𝑊ଶ,…,𝑊ு ൌ α
𝑊 ଶ,ଵ ൅ 𝛽
𝑊 ଵ,ଵ
𝑊 ൌ 
ሺ𝑊ଵ
ሻଵଵ ሺ𝑊ଵ
ሻଵଶ … ሺ𝑊ଵ
ሻ
ே
మ
ሺ𝑊ଶ
ሻଵଵ ሺ𝑊ଶ
ሻଵଶ … ሺ𝑊ଶ
ሻ
ே
మ
⋮
ሺ𝑊ு
ሻଵଵ
⋮
ሺ𝑊ு
ሻଵଶ
⋱
…
⋮
ሺ𝑊ு
ሻ
ே
మ
Results
Deep Learning based Methods
Hand‐crafted Features are not Enough
• “Hand‐crafted” feature descriptor need domain 
knowledge
• Too many feature descriptor, which is the best
?
• Concatenation of the features may result in over‐
fitting in feature space
Use deep leaning to extract 
good feature descriptors!
深度学习方法：端到端
人工设计
特征
Tasks
学习
特征
Tasks
传统学习方法
深度学习方法
Deep Neural Networks (DNN)
Regression problem:
Input: Given training set (x
1, y
1), (x
2, y
2), (x
3, y3 ), …. 
Output: Adjust parameters 
 (for every node) to make: 
௜
௜
三维数据的深度学习的三种方法
关于深度学习
• 通用拟合器（较大的逼近函数空间）
• 应用三部曲
• 在哪找（网络构造）、哪个好（损失函数）、怎么找（优化）
• 仅拟合了大量样本：可能只是“虚假关系”
• 并没有“理解”或“认知”真正的规律
• 不可解释性
• 性能依赖训练样本（数据集）
• 当数据集足够密：近似“最近邻”算法
• 训练数据集不够完备：缺乏泛化能力
• 大部分是过拟合
• 基于深度神经网络的深度学习并不是真正的AI，离 真正的“智能”仍很遥远
稀疏学习与深度学习：殊途同归
• 方法的不同性
• 压缩感知：基于模型的，有很好的结构和数学模型；
来自于数学理论的突破
• 深度学习：基于实证的，模型灵活，须通过数据进行
监督学习；来自于求解速度的突破
• 一致性
• 目标：高维数据的信息(特征)提取
• 结果：从局部信息来处理全局信息
• 类似的网络结构：求解L1优化的IST (Iterative Soft‐
Thresholding)算法实质上是多层网络优化
Trends
3D Data: Big Data Era?
Cross‐Domain （跨模态）
多模态
Creative Design
• How can computational tools support human creativity?
• –What stimulates creative design?
• –How can computers help?
• –Requires something more than just structural/functional/semantic 
analysis of shapes
• 3D content creation is still far from solved!
谢 谢！
