![](../assets/建模20.png)  


## 曲面设计(Design)   

## 建模(modeling)：设计与重建


 - 曲面设计(Design)      
    - 不存在的物体：通过人工交互凭空设计出新的物体     
      - CAGD (NURBS)、mesh modeling     
    - 存在的物体：通过人工交互编辑修改构建出新的物体    
      - Editing, deformation     
 - 曲面重建(Reconstruction)     
    - 存在的物体：对其采集并进行数字化构建    
    - 也称为：逆向工程、扫描重建     
      - Reverse engineering, scanning     



## 建模(modeling)：设计与重建    


 - 曲面设计(Design)    
    - 不存在的物体：通过人工交互凭空设计出新的物体    
      - CAGD (NURBS)、mesh modeling    
    - 存在的物体：通过人工交互编辑修改构建出新的物体    
     - Editing, deformation     
 - 曲面重建(Reconstruction)    
    - 存在的物体：对其采集并进行数字化构建     
    - 也称为：逆向工程、扫描重建    
      - Reverse engineering, scanning    
      

## Digitalization of Real ObjectsReverse


## Engineering
Real Object
CAD/Graphics model
Build new real objects


## Getting Meshes from Real Objects 


 - Many models used in Computer Graphics are 
obtained from real objects    
    - Ex.: Well known Stanford bunny model
?    
3D mesh surface Photo of real Stanford Bunny



## Designed Utah Teapot (NURBS)   


Photo of real Utah teapot


## Outline


Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
Postprocessing
• Repairing
• Smoothing
• Simplification1. Acquisition1. Acquisition （数据采集）
Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction Postprocessing
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
采集设备
采集算法
• Repairing
• Smoothing
• SimplificationStructure of DataSensing devices (scanner)More sensing devices…
深度相机
激光扫描仪(LiDAR)
车载激光扫描仪
遥感
倾斜摄影
单个相机
多个相机 全站仪1.1 Volume Scanning
• Input: a sequence of slice images
• Output: 3D models of human organs 1.1 Volume Scanning
• Input: a sequence of slice images
• Output: 3D models of human organs 3D Imaging
• Wave based sensors
• Ultrasound
• Magnetic Resonance Imaging (MRI)
• X‐Ray
• Computed Tomography (CT)
• Alternative ‐ slice object, take photographs of slices
• Outputs
• volumetric data (voxels)
• contour lines (use imaging techniques)医学图像的三维重建医学图像三维重建的软件
Materialise Mimics, Simpleware, Able 3D‐DOCTOR, Visage Imaging Amira, Medical Imaging 
ToolKit (MITK), …Reconstruction from 2D contours1.2 Shape from shading (SFS)
• Input: a single image
• Output: a 3D model (with albedo, normal, etc.)
• Method: Inverse of rendering
• Solving from rendering equation [Horn 1980]
rendering
SFSShape from shading (SFS)
• Solving from the Phong shading equation
• Reflectance models: Lambertian modelsShape from shading
• From multiple imagesShape from a single image
Jiang et al. 3D Face Reconstruction with Geometry Details from a Single Image. IEEE Transactions on 
Image Processing, 2018.
Xu et al. Shading-based Surface Detail Recovery under General Unknown Illumination. IEEE Transactions 
on Pattern Analysis and Machine Intelligence, 2018.Shape from a single image –
Learning based method
Wu et al. Unsupervised learning of probably symmetric deformable 3D objects fro images in the wild. CVPR 2020. 
(Best paper award)Shape from a single image –
Learning based method
Wu et al. Unsupervised learning of probably symmetric deformable 3D objects fro images in the wild. CVPR 2020. 
(Best paper award)
抽象图片与动漫图片Shape from a single image –
Learning based method
Wu et al. Unsupervised learning of probably symmetric deformable 3D objects fro images in the wild. CVPR 2020. 
(Best paper award)1.3 Image based modeling (IBM)
• Input: multiple photos from different views
• Output: 3D modelsMathematics: projective imaging
• A 3D point corresponds different pixels in different images
• Key: Finding pixel correspondence between images
+ +
=Theory: Multi‐view geometryImage 1
Image 2
Image 3
R1,t1
R2,t2
R3,t3
X1 X2 X3
X4
X5
X6
X7
x11
x12 x13
Theory: Multi‐view geometryMulti‐view Capturing SystemsIBM Commercial Software
Autodesk 123D Catch Smart3D, Altizure
（倾斜摄影）倾斜摄影案例（Altizure
）1.4 Structured light （结构光/白光）结构光3D扫描仪：多用于CAD建模1.5 SfM & SLAM
• SfM: Structure from Motion
• SLAM: Simultaneous Localization and Mapping
SfM SLAM
Vision Robotics
Structure Mapping
Camera poses Location
3D reconstruction Localization
Feature tracking PredictionSLAM的主要流程机器人扫描与重建三维场景
SLAM + Guidance
Frontier-based exploration
[Yamauchi et al. 1997]
Object-guided exploration
[Liu et al. Siggraph 2018]
Liu et al. Object‐aware Guidance for Autonomous Scene Reconstruction. Siggraph 2018.1.6 Laser Radar （激光雷达测距）
• Light Detection And Ranging, LiDAR
• 原理：主动向目标发射探测信号（激光束）,然
后将接收到的从目标反射回来的信号（目标回波）
与发射信号进行比较（三角测距）激光测点车载移动激光测距与扫描设备1.7 Depth Images
• Microsoft Kinect
• Apple Primesense
• Intel RealSense
• Google Project Tango
• Asus Xtion
• iPhone XI/XII
RGBD数据
(R,G,B) DDepth Data: Grid Points
• 2.5D image深度相机原理 (Time of flight, TOF)
3D scene Sensor
Distance = time * speed / 2深度相机原理 (Kinect)
• 当激光穿透毛玻璃后形成随机衍射斑点，这些散斑（laser 
speckle）具有高度的随机性，而且会随着距离的不同变换
图案。空间中任意两处散斑图案都不同
• Light coding打出了一个具有三维纵深的“体编码”，只要看
物体表面的散斑图案，就可以知道这个物体在什么位置基于Kinects的人体扫描
Tong et al. Scanning 3D Full Human Bodies using Kinects. IEEE Transactions on Visualization and 
Computer Graphics, 2012KinectFusion [2013]1.8 Shape from Silhouette/Contours
Intersection of visual hulls1.9 Probing
• Probing
• position probe on object
• record the location
• Output
• point cloud data
• Problematic
• Labour intensive
• Error prone1.10 全景相机 (Panorama)
• 多张图片拼接而成（拟三维：非真三维）千亿像素图片2. Registration2. Registration
Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
Postprocessing
• Repairing
• Smoothing
• SimplificationGoal: Reconstruction from scans
Set of raw scan data ReconstructionAcquisition Planning
Selecting the set of views is not easy多个视点的扫描
• 每个视点得到分片3D数据
• 问题：如何将这些分片数据
合并成一个整体数据？
当前视点
下一个视点
?
?
?Registration
Acquisition RegistrationPairwise RegistrationRegistration as energy minimizationAlignment ErrorAlignment ErrorAlignment Error
weights corresponding 
point on targetPrior Error – 1 (Rigid objects)Prior Error – 2 (Elastic objects)Prior Error – 3 (Articulated objects)Iterative Closest Point (ICP) Algorithm
[Besl+92]Implementations
• Iterative Closest Point (ICP) Algorithm
• Implementations
• (approximate) closest points→ (more) efficient data structures
• weight accounts for importance and confidence
• heuristics to prune or down‐weight bad correspondences
• Error norm
• squared Euclidean distance is sensitive to outliers
• robust norms reduce this sensitivityMore…
• Pairwise Sequential vs. Global  [Pulli99]
• Global: loop closure problem
• Using Color in registration [Bernardini00]3. Consolidation3. Consolidation
Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
Postprocessing
• Repairing
• Smoothing
• SimplificationImperfect Acquisition
• Outliers
• Noisy data
• Orientation
• Large missing parts
• Non‐uniform sampling
• Blurred features
•
…
Raw Scan DataConsolidation
• Goal: obtain a surface/point‐cloud with good quality (noise‐
free, orient‐consistent, complete, continuous…)Point Cloud Consolidation
Unorganized
Noisy
Thick
Outliers
Non‐uniform
Un‐oriented
Input
Consolidated
Clean
Thin
Outlier‐free
Uniform
Oriented
Output
Input OutputThick cloud Non‐uniform distribution
Close‐by surface sheets
ChallengesOutlier Removal and Denoising
Input 3D points
Outlier removal
Denoising
Photo of the building
Wu et al. Deep points consolidation. Siggraph Asia 2015.
Wang et al. Consolidation of Low‐quality Point Clouds from Outdoor Scenes. SGP 2013.
Huang et al. Consolidation of Unorganized Point Clouds for Surface Reconstruction. Siggraph Asia 2009.Normal (Oriented) Consistency
• Based on angles between unsigned normals
• May produce errors on close‐by surface sheets 
Zhang et al. Multi‐Normal Estimation via Pair Consistency Voting. IEEE TVCG, 2019.
Liu et al. Quality Point Cloud Normal Estimation by Guided Least Squares Representation. SMI 2015.
Huang et al. Consolidation of Unorganized Point Clouds for Surface Reconstruction. Siggraph Asia 2009.Normal Propagation


Huang et al. Consolidation of Unorganized Point Clouds for Surface Reconstruction. Siggraph Asia 2009.Resampling
• More locally regular point distribution
• Locally Optimal Projection (LOP) and WLOP
Huang et al. Consolidation of Unorganized Point Clouds for Surface Reconstruction. Siggraph Asia 2009.Edge‐Aware Resampling (2D)
Huang et al. Edge‐Aware Point Set Resampling. ACM TOG 2013.Edge‐Aware Resampling (3D)
Huang et al. Edge‐Aware Point Set Resampling. ACM TOG 2013.Filling Holes (Completion)
Sharf et al. Context‐based Surface Completion. Siggraph 2004.4. Reconstruction4. Reconstruction
Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
Postprocessing
• Repairing
• Smoothing
• SimplificationSurface Reconstruction
• Input
• A set of points in 3D that sampled from a model surface
• Output
• A 2D manifold mesh surface that closely approximates 
the surface of the original modelDesirable Properties
• No restriction on topological type
• Representation of range uncertainty
• Utilization of all range data
• Incremental and order independent updating
• Time and space efficiency
• Robustness
• Ability to fill holes in the reconstructionSolutions
• Approximation methods: Constructing continuous 
functions (Scattered data interpolation schemes)
• NURBS surfaces
• Signed distances [Hoppe et al. 1992]
• Radial basis function reconstruction [Carr et al. 2001] 
• Poisson reconstruction [Kazhdan et al. 2006] 
• Discrete methods: Constructing triangle meshes 
directly 
• [Amenta & Bern 1998]
• Power‐crust [Amenda et al. 2001]
• Cocone [Dey & Giesen 2001]
• [Cazals & Giesen 2006] 
• …Solutions
• Approximation methods: Constructing continuous 
functions (Scattered data interpolation schemes)
• NURBS surfaces
• Signed distances [Hoppe et al. 1992]
• Radial basis function reconstruction [Carr et al. 2001] 
• Poisson reconstruction [Kazhdan et al. 2006] 
• Discrete methods: Constructing triangle meshes 
directly 
• [Amenta & Bern 1998]
• Power‐crust [Amenda et al. 2001]
• Cocone [Dey & Giesen 2001]
• [Cazals & Giesen 2006] 
• …NURBS Approximation
• 须分解为四边形区域
• 拼接光滑性约束（角点光滑性约束）T‐Spline ApproximationImplicit Approximation Methods
(similar to GAMES 102‐9)
• Convert point cloud into a signed distance field
• Construct an implicit function whose iso‐surface 
with iso‐value 0 to approximate the field
• Extract the mesh surfaces from the implicit 
function
• Marching cube methodsSigned Distance Fields
• For every point, add two off‐
surface points, one inside and 
one outside the surface in the 
direction of the normal
• Add a point only if it is closest to 
its source
• N≈3n pointsSigned Distance Fields
Outward 
normal points
On-surface points
Inward
normal pointsSigned Distance Fields(1) Radial Bases Function (RBF)
• RBF function:
• Φ is a radially symmetric function
• The trivial solution is wi=0
  




n
i
i i f
x
w
x
x 1
(
)Radial basis functions
  




n
i
i i f
x
w
x
x 1
(
)
Minimizes 2nd derivative in 3D
Minimizes 2nd derivative in 2D

(
r
)

r
(
r
)
r log
r
2


3 
(
r
)

r
Minimizes 3nd derivative in 3DComputing the weights
• Input : {xi}, {fi} 
• Compute {wi
}
  




n
i
i i f
x
w
x
x 1
(
)
  A

W


f
 NxN

Unknowns to compute
Function values
Matrix dependent on the locations of 
the data pointsSolving the linear system
• Symmetric positive matrix






     
      






















































































N
N
N
N
N
N
N
N
f
f
f
W
W
W
x
x
x
x
x
x
x
x
x
x
x
x
x
x
x
x
x
x
 

 

2
1
2
1
1 2
1 2
2
2
2
1 1 2 1 1Alternative
Alternative:
• Use locally supported basis functions (e.g. B‐Splines)
• Employ an additional regularization term to make the 
solution smoother
• Optimize the energy function
𝐸 𝜆 ൌ ෍𝑓 𝒙௜ ଶ ൅𝜇න 𝜕ଶ 𝜕𝑥ଶ ൅ 𝜕ଶ 𝜕𝑦ଶ ൅ 𝜕ଶ 𝜕𝑧ଶ ൅ 2𝜕ଶ 𝜕𝑥𝜕𝑦 ൅ 2𝜕ଶ 𝜕𝑦𝜕𝑧 ൅ 2𝜕ଶ 𝜕𝑥𝜕𝑧 𝑓 𝒙 ଶ 𝑑𝒙
ஐ
௡
௜ୀଵ
with 𝑓 𝒙 ൌ ∑ 𝜆௜𝑏 𝒙െ𝒙௝ ௠௜ୀଵ
• The critical point is the solution to a linear systemSimplification (center reduction)
• Reduce the number of centers (points)
• Greedy algorithm, reduce points as long as the surface is 
close enough
Carr et al. Reconstruction and representation of 3D objects with Radial Basis Functions, SIGGRAPH 2001.Complexity
Straight‐forward method:
• Storage O(N2)
• Solving the Wi O(N3)
• Evaluating f(x) O(N)
Fast method [Carr01]
• Storage O(N)
• Solving the Wi O(NlogN)
• Evaluating f(x) 
O(1) + O(NlogN) setup
Carr et al. Reconstruction and representation of 3D objects with Radial Basis Functions, SIGGRAPH 2001.Sensitive to Normals(2) MPU Implicits
Multi‐level partition of unity 
implicits:
• Hierarchical implicit function 
approximation
• Given: data points with normal
• Computes: hierarchical approximation 
of the signed distance function
Ohtake et al. Multi‐level Partition of Unity Implicits, SIGGRAPH 2003MPU Implicits
Multi‐level partition of unity implicits: • Octree decomposition of space
• In each octree cell, fit an implicit  quadratic function to points
•
𝑓
𝒙௜ ൌ 0 at data points
• Additional normal constraints
• Stopping criterion:
• Sufficient approximation accuracy
(evaluate 
𝑓 at data points to calculate  distance)
• At least 15 points per cell.MPU Implicits
Multi‐level partition of unity implicits:
• This gives an adaptive grid of local 
implicit function approximations
• Problem: How to define a global 
implicit function?
• Idea: Just blend between local 
approximants using a windowing 
functionMPU Implicits
Multi‐level partition of unity  implicits: • Windowing function:
• Use smooth windowing function 
𝑤
• B‐splines / normal distribution
• Original formulation: quadratic  tensor product B‐spline function, 
support = 1.5 ൈ cell diagonal
• Renormalize to form partition of 
unity:
𝑓 𝒙 ൌ
∑
𝑤 𝒙െ𝒙௜ 𝑓௜ 𝒙
௡
௜ୀଵ
∑
𝑤 𝒙െ𝒙௜ ௡௜ୀଵMPU Implicits
Multi‐level partition of unity implicits:
• Sharp features:
• If a leaf cell with a few points has strongly 
varying normal, this might be a sharp feature.
• Multiple functions can be fitted to parts of 
the data
• Boolean operations to obtain composite 
distance fieldExamples(3) Possion reconstruction
• Idea: fitting an indicator function
Kazhdan et al. Poisson surface reconstruction. SGP 2006.Solving Possion Equation(4) Marching CubeMarching CubesProblems & Many ImprovementsSolutions
• Approximation methods: Constructing continuous 
functions (Scattered data interpolation schemes)
• NURBS surfaces
• Signed distances [Hoppe et al. 1992]
• Radial basis function reconstruction [Carr et al. 2001] 
• Poisson reconstruction [Kazhdan et al. 2006] 
• Discrete methods: Constructing triangle meshes 
directly 
• [Amenta & Bern 1998]
• Power‐crust [Amenda et al. 2001]
• Cocone [Dey & Giesen 2001]
• [Cazals & Giesen 2006] 
• …Curve from Points
‐ Connect the Dots (1)
• Given unordered set of points P 
• connect them by linear segmentsCurve from Points
‐ Connect the Dots (2)
• Can be ambiguous
• Harder when topology not knownCurve from Points
‐ Connect the Dots (3)
• Use Voronoi Diagram
• Construct Delaunay triangulation
• Which edges to choose?Medial Axis
• Medial axis of (d‐1)‐dimensional surface in Rd ‐ set 
of points with more than one closest point on the 
surface
• Alternative definition: locus of centers of maximal 
inscribed spheresMedial Axis and Voronoi Diagram 
• Voronoi diagram of set of points on curve 
approximates Medial Axis 
• if points sampled densely enoughSampling Criterion
• Good sample ‐ sampling density (at least) inversely 
proportional to distance from medial axis
• r‐sample : distance from any point on surface to nearest 
sample point ≤ r * distance from point to medial axis
• In general, r 
∈ (0,1] 
• r=0.5 good enough
• Inherently takes into account
• curvature of the surface
• proximity of other parts of the surface2D Crust Algorithm
• Idea
• Adopt Delaunay edges which are 
“far
” from MA
• To represent MA use Voronoi vertices
• Edge e in crust <=> circumcircle of e contains no other 
sample points or Voronoi vertices of SCrust Algorithm
• Compute Voronoi diagram of S 
• let V be set of Voronoi vertices
• Compute Delaunay triangulation of SUV
• Return all Delaunay edges between points of STheory
• Theorem: The crust of an r‐sample from a smooth curve F, 
for r ≤ 0.25 connects only adjacent samples of F
Smooth Curve F r-sample (r ≤ 0.25) The crustTheory
• The algorithm may fail when r is too large(1) 3D Crust Algorithm
• Extend 2D approach
• Voronoi cells are polyhedra
• Voronoi vertex is equidistant from 4 sample points
• BUT in 3D not all Voronoi vertices are near medial 
axis (regardless of sampling density)
Amenta et al. A New Voronoi‐Based Surface Reconstruction Algorithm. Siggraph 1998Concepts
• Poles
• Farthest Voronoi vertices for a sample point that are on 
opposite sides
• Crust
• Shell created to represent the surfaceProblem
• But some vertices of the Voronoi cell are near 
medial axis
• Intuitively – cell is closed not just from the sides 
but also from both sides of the surfaceObservation
• p+ ≡ pole of p = point in the 
Voronoi cell farthest from p
• ε < 0.1 → 
• the vector from p to p+ is within 
π/8 of the true surface normal
• The surface is nearly flat within the 
cell
Voronoi cell of p
p+
pSolution
• Solution
• use only two farthest vertices of Vs ‐ one on each side of 
the surface
• Call vertices poles of s: p+(s), p‐(s)3D Algorithm
• Compute Voronoi diagram of S
• For each s ∈ S, identify the poles p+(s) and p‐(s)
• p+(s) is the vertex of Vs most distant from s
• p‐(s) is the vertex of Vs most distant from s in the 
opposite direction
• Let P be the set of all poles
• Compute Delaunay triangulation T of S U P
• Add to crust all triangles in T with vertices only in SPost‐processing
• Delete triangles whose normals differ too much 
from the direction vectors from the triangle 
vertices to their poles
• Orient triangles consistently with its neighbors and 
remove sharp dihedral edges to create a manifoldExample
• Crust of set of points and poles used in its 
reconstructionExamplesExamples
Foot images from Prof. DeyAdvantages
• No need for experimental parameters in basic 
algorithm
• Not sensitive to distribution of pointsProblems
• Sampling of points needs to be dense
• Undersampling causes holes
• Problems at sharp corners
• Another way to choose poles gives better 
reconstruction
• choosing the farthest and the second farthest Voronoi 
vertices, regardless of direction
• Correct, BUT slowRevised (1)
• Co‐cones 
• Cone with apex at sample point 
and aligned with poles
• Algorithm only requires one 
Voronoi diagram computation
• Eliminates normal trimming step
• Still does not support sharp 
edgesRevised (2)
• The power crust 
• Use polar balls and power 
diagrams to separate the inside 
and outside of the surface
• Approximates medial axisRevised (3)
• Detecting Undersampling 
• Fat Voronoi cells or dissimilarly oriented 
neighboring Voronoi cells imply 
undersampling.  Add sample points to 
accommodate
• This accounts for sharp edges and 
boundaries
• Tight Co‐cone
• After detecting undersampling, stitch up 
holes(2) 基于字典学习的
曲面重建
Xiong et al. Robust Surface Reconstruction via Dictionary Learning. Siggraph Asia 2014.• 输入：三维点集（蓝色点）
问题• 输入：三维点集（蓝色点）
• 输出
• 采样点集（红色点）
问题• 输入：三维点集（蓝色点）P
• 输出
• 采样点集（红色点）V
• V构成的三角网格M，使得M逼近P
问题• 如何度量点集P与网格M之间的误差？
误差度量Pi
f
P’i
vr
vs
vt
: P’i 相对与 f的重心坐标
某个点到三角形的距离Pi
f
P’i
vr
vs
vt
某个点到三角形的距离
Vertex matrix of M输入点集Ｐ 字典Ｖ 投影矩阵B
重建网格Ｍ的顶点
重建网格Ｍ的顶点的连接关系Approximation Error
152
Denote
then
From the dictionary learning perspective: 
P: the given signal
V: the dictionary
B: the sparse coding matrix
Z: the approximation residual全局误差
153
s.t.数学优化模型
V: the vertices  (geometry)
B: encodes the connectivity of V (topology)优化方法
155Experimental ResultsInput Point Cloud
157Iter 1
158Iter 2
159Iter 3
160Iter 4
161Iter 5
162Iter 6
163Iter 7
164Iterative RefinementResistant to NoiseFeature Preserving
Implicit methods need normal information, while 
normal estimation is another challenging problem.ComparisonsReal Scanned DataConclusion
• Model the surface reconstruction problem 
via dictionary learning
• VS Implicit method
• Straightforward
• Approximation error is considered
• VS Existing Explicit method
• Denoising the input point cloud
• Global approximation errorHybrid Methods(1) Competing Fronts
• Deformable model reconstruction
• Implicit coarse guidance field or attraction field
• Explicit deformable model (a mesh)
• Property
• Watertight guarantee
• Topology control
Sharf et al. Competing Fronts for Coarse–to–Fine Surface Reconstruction. Eurographics 2006.(2) Cooperative Evolutions 
• Two deformable models 
• One from interior
• The other from exterior
• Alternative evolutions
Lu and Liu. Surface Reconstruction via Cooperative Evolutions. CAGD 2020.(2) Cooperative Evolutions 
Evolution of interior mesh Alternative evolutions of both meshes5. Post‐processing5. Post‐processing
Sensing
devices
Partial
point cloud
Complete
point cloud
Reconstructed
Surface
Surface
for applications
Registration
Consolidation
Shape from X Reconstruction
Multi‐view
geometry
LiDAR
Camera
Depth 
Camera
Scanner
Postprocessing
• Repairing
• Smoothing
• SimplificationPost‐processing
• Repairing, denoising, smoothing, simplification…
Repairing (completion, hole‐filling, restoration)Hole Generation
• Occlusion“Digital Image Inpainting is an iterative method for 
repairing damaged pictures or removing 
unnecessary elements from pictures”
“Fast Digital Image Inpainting”, 
Manuel M. Oliveira, Brian Bowen, Richard McKenna and Yu-Sung Chang
Image InpaintingPhoto Restoration 
“Image Inpainting : An Overview”,
Guillermo Sapiro(1) Filling Holes in Meshes 
[Liepa, SGP 2003]Pipeline
1. Hole identification
2. Hole triangulation
3. Mesh refinement 
4. Mesh fairingTriangulation of 3D Polygons
• Minimum area triangulation
• Min‐max dihedral angel triangulationMesh Refinement
1. Subdivision 2. Edge RelaxationFairing
• Weighted umbrella‐operator
 Uniform :
 Scale-dependent :
vv v U()   Summary
• Easy to implement
• Focus algorithm on holes
• Triangulation may self‐intersect
• Can’t fill holes with islands
• Fairing weaken original surface feature(2) Robust Repair of Polygonal 
Models
[Ju, Siggraph 2004]Pipeline
I. Scan‐conversion
II. Sign generation
III. Surface reconstructionSign Generation
• Cell faces containing an odd number of intersection 
edgesPatch Boundary Circles
Patching dual 
surface
Edges intersected with the 
model and the corresponding 
dual surfaceMarching Cubes
• Cube with signs at eight cornersMarching CubesResultsResultsSummary
• Employ a space‐efficient octree grid
• Produce closed, manifold surface for any input 
model (3) Context‐based Surface 
Completion
[Sharf et al., Siggraph 2004]Motivation
Complete the missing region with patches that 
conform with its context 
Smooth Context-basedMethod
Import patches with matching context  from the surface itself :
• Analyze surface characteristics.
• Find best matching patch.
• Fit imported patch to boundary.Algorithm
• Create initial spatial subdivision
• For each cell
• Compute a local shape representation.
• Compute a shape signature.
• For each empty cell:
• Find matching nonempty cell ω’.
• Copy patch of ω’ into ω.
• Subdivide cells and repeat
• Until completed region matches its 
neighborhoodCompletion Process
Original
Initial 
approximation
Final resultManual Editing of Bunny ModelScan of “Youth” Statue
Original Smooth ResultScan of Human Bone
Original
Smooth
ResultLimitations: SemanticsSummary
• A fully automatic method to complete a missing 
region in a surface from its context.
• Completed patches geometrically conform with 
neighborhood.
• Incremental scale‐space framework for finer 
approximation of the unknown region.(4) Example‐based Surface 
Completion
[Pauly et al., SGP 2005]Solution
• Use 3D model database to provide geometric priors for 
shape completion
• Apply non‐rigid transforms on the models
• More deformation  less likely completion
• Consistently combine geometric information from 
multiple context models
• Final result comes with confidence valuesShape Completion PipelineData Classification
Local analysis
• quality of fit
• uniformity of sample distribution
Scored Point Cloud
• confidence value assigned to 
each point
High
LowDatabase Retrieval
1.93 1.71 1.46 1.27 1.0Non‐rigid Alignment
Similar to the approaches proposed by:
• Allen, Curless and Popovic, 2003.
• Sumner and Popovic, 2004.Non‐rigid Alignment
Deformation Model
• Piecewise linear.
Each vertex of the mesh assigned an independent 
displacement vector.
Optimize for smallest Shape Matching Penalty
• Distortion Measure
• Geometric Error
Feature Correspondence
Derived in the continuous setting to allow 
consistent comparison between different 
context models.Warped Models
High
Low
Context Model Warped Model Matching PenaltyInitial Segmentation
Input Data Warped Context ModelPatch Growing
Initial Segmentation Final SegmentationResult Segmentation
Giraffe Example
Context Models
Deformed ModelsFinal Model
Giraffe Example
Context Models
Deformed ModelsEvaluation
Input Data Context Model Final Model EvaluationEnriching the DatabaseAdditional Constraints
Physical Model Acquired Data Context Model
No Constraints Symmetry Constraints(5) Atomic Volumes for 
Mesh Completion 
[ Podolak and Rusinkiewicz, SGP 2005]Atomic Volumes
• A volume is atomic if 
it doesn’t intersect
the polygons of the
mesh.Spatial PartitioningPipeline
In Cube
Out Cube
Hole CubePipelinePipeline
Sink
(outside)
Source
(inside)PipelineUser ConstraintsResultsSummary
• Avoid changing, approximating or re‐sampling the 
original mesh data
• Incorporate user constraints
• Can’t process holes with islands(6) Geometry Completion by 
Texture Synthesis
[Nguyen et al., PG 2005]Geometry Imagecut Gu et al. Siggraph 02
parametrize
Basic ideaBasic idea
cut
sampleBasic idea
cut
[
r,g,b] = [
x,y,z
]
render
store(7) OthersTemplate based Solution 
(Allen, Curless, Popovic, 2003; Kraevoy and Sheffer, 2005)More…
• Marco Attene, Marcel Campen, Leif Kobbelt. 
Polygon Mesh Repairing: An Application 
Perspective. ACM Computing Surveys, 2012.
• Learning based 3D data completion in recent years
• Han et al. High Resolution Shape Completion Using Deep Neural Networks 
for Global Structure and Local Geometry Inference. ICCV 2017.
• Han et al. Deep Reinforcement Learning of Volume‐guided Progressive 
View Inpainting for 3D Point Scene Completion from a Single Depth Image. 
CVPR 2019.
• Nie et al. Skeleton‐bridged Point Completion: From Global Inference to 
Local Adjustment. NeuIPS 2020.动态物体的3D重建3D 动态重建的困难性
• 数据量大
• 数据采集困难
• Single‐Camera
• Multi‐Camera
• 数据结构复杂
• Geometry
• Color
• Topology
• 硬件需求高 [Colletet al. 2015] Multi‐view [Guo.2016] Single‐viewGeneral Pipeline
• 数据采集
系统建立
• 各视角相机坐标系对齐校
准
• 各相机颜色一致性调整
• 各相机拍照频率一致
数据采集
• Kinect
• 自定义的相机组
数据预处理
• 生成Depth 
map/image
• Depth 去噪
/补洞
• 背景或无用信息剔
除
输出
Depth image/color 
imageGeneral Pipeline
• 生成3D mesh/surface
Reference Mesh
Input data
计算Motion
Updated Reference 
volume
Fusion
Motion人体动态重建
（Human Performance Capturing
）
• 离线高质量的动态重建方法
• 实时动态的人体重建方法
• 基于深度学习的人体重建方法2.1 离线高质量动态重建离线高质量动态重建
High-quality streamable free-viewpoint video (SIGGRAPH 2015)2.2 实时动态人体重建
[Motion2Fusion 2017]实时动态人体重建2.3 基于深度学习的动态人体重
建方法
Volumetric performance capture from minimal camera viewpoints (ECCV 2018)
Volume表示基于深度学习的动态人体重建
方法SummaryStatistics About the Scan of David
• 480 individually aimed scans
• 0.3 mm sample spacing
• 2 billion polygons
• 7,000 color images
• 32 gigabytes
• 30 nights of scanning
• 22 peopleReconstruction is still hard…
• Still no fully automatic tools
• Many many corner cases in practice!!!作业10
• 任务（3选1）
• 实现曲面重建的Crust算法
• 实现RBF重建算法
• 实现Poisson重建算法 (*)
• 目的
• 学习曲面重建的基本算法
• 注：如需要，可参考使用现成的Marching Cubes代码
• Deadline：2021年1 月16日晚谢 谢！