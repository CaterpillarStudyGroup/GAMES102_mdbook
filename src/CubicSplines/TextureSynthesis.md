


# 回顾：曲面重建或建模    

![](../assets/合成1.png) 


# Textured Surfaces    

![](../assets/合成2.png) 


# Texturing 3D Models    

![](../assets/合成3.png) 


# Texture Synthesis   

![](../assets/合成4.png) 



# 2D Texture Synthesis    

![](../assets/合成5.png) 


# Texture Synthesis    

* Given a sample texture *I*, the goal is to synthesize a new texture *J* that     
• looks like the input sample   
• no part of result is the duplicate of the sampl   

![](../assets/合成6.png) 



# Applications   

![](../assets/合成7.png) 


# 1. Textures    


# What is texture?    

• Characterized by appearance    
• Elements arranged quasi‐randomly    

![](../assets/合成8.png) 


# Image VS. Texture    

![](../assets/合成9.png) 

# Texture   

* Images containing repeating patterns   
• Locality: small parts look alike   
• Stochastic: they never look exactly the same     

![](../assets/合成10.png) 


# Dynamic Textures    

• Appearance similar even as texture evolves    

![](../assets/合成11.png) 


# Classification (Attribution)   

![](../assets/合成12.png) 


# 2. 2D Texture Synthesis   


Texture Synthesis:    
A Simple Solution … Tiling     

![](../assets/合成13.png) 



# Desirable Properties   

• Result looks like the input    
• Efficient    
• General   
• Easy to use    
• Extensible     

![](../assets/合成14.png) 


# Challenges   

* Texture analysis   
• how to capture the essence of texture?    
* Need to model the whole spectrum   
• from repeated to stochastic texture   
* This problem is at intersection of vision, graphics, statistics, and image compression    


# Example‐based Techniques    
* Parametric Techniques    
• Compute global statistics in feature space and sample images from texture ensemble directly     
* Non‐parametric Techniques    
• Estimate local conditional probability density function and synthesize pixels incrementally    



# Parametric Techniques   

• Hypothesize a **mathematical model** for texture representation     
• **Match** model parameters of input and output texture    


![](../assets/合成15.png) 



# Pyramid‐Based Texture Analysis/Synthesis    
[Heeger & Bergen, Siggraph 1995]


• Initialize J to noise    
• Create multiresolution pyramids for I and J    
• Match the histograms of J’s pyramid levels with I’s pyramid levels    
• Loop until convergence    
• Can be generalized to 3D    

# Results   

![](../assets/合成16.png)   


# Failures   

![](../assets/合成17.png) 



# Non‐Parametric Techniques   

* Synthesis by **copying** from the input    
* Markov‐Random Field Model     
• Pixel appearance depends only on neighborhood    

![](../assets/合成18.png) 


# Markov Random Field   

* [Shannon,’48] proposed a way to generate English‐looking text using N‐grams:     
• Assume a generalized Markov model    
• Use a large text to compute prob. distributions of each letter given N‐1 previous letters     
• Starting from a seed repeatedly sample this Markov chain to generate new letters    
• Also works for whole words    

WE NEED TO EAT CAKE    


# Synthesizing One Pixel   

![](../assets/合成19.png)   


• Assuming Markov property, what is conditional probability distribution of p, given the neighbourhood window?    
• Instead of constructing a model, let’s directly search the input image for all such neighbourhoods to produce a histogram for p     
• To synthesize p,  just pick one match at random    


# Really Synthesizing One Pixel    


&#x2705;  However, since our sample image is finite, an exact neighbourhood match might not be present     
&#x2705;  So we find the **best** match using SSD error (weighted by a Gaussian to emphasize local structure), and take all 
samples within some distance from that match     



# Pixel‐Based Texture Synthesis    

![](../assets/合成20.png)    


Select Best Neighborhood from all Candidates   



# Randomness Parameter   


![](../assets/合成21.png) 


# Results   

![](../assets/合成22-1.png)    




# Patch‐based Synthesis     
[Liang et al. TOG 2002]   



• Copy patches instead of single pixels     

![](../assets/合成23.png) 



# Patch‐Based Texture Synthesis    

![](../assets/合成24.png) 

**Select** ***Best*** **Neighborhood from all Candidates**   


# Synthesis Result   
— High‐quality Texture     

![](../assets/合成25.png)    

• Efros’ algorithm has a tendency to grow garbage and Wei’s TSVQ acceleration further aggravates this problem. In Contrast, patch‐based sampling avoids growing garbage      


# Advantages    

* Speed    
• Orders of magnitude faster than existing texture synthesis algorithm    
• Real‐time synthesis    
* Quality    
• Synthesize high‐quality textures ranging from regular to stochastic     
• Avoid growing garbage     
• Synthesize subjectively better natural textures     



# Mincut: Graph-cut based     
[Efros&Freeman, Siggraph 2002]     

![](../assets/合成26-1.png)    



# Minimal error boundary    

![](../assets/合成27.png)    


# Seam Optimization    

![](../assets/合成28.png)    

Construct graph such that:    
Graph Mincut \\(\Leftrightarrow\\) Best Seam     

![](../assets/合成29.png)    

![](../assets/合成30.png)    


# Results: Natural Images    

![](../assets/合成31.png)    


# Interactive Merging     

![](../assets/合成32.png)    


# Results: Interactive Merging    

![](../assets/合成33.png)    


# Application: Seam Carving    
[Avidan and Shamir, Siggraph 2007]    

• Removing/adding unimportant seams    
• Content‐aware image resizing/retargetting    

![](../assets/合成34.png)    

# Seam Carving    

![](../assets/合成35.png)    


# Texton‐based Synthesis    
[Zhang et al., Siggraph 2003]    



• Texton: texture element    
• Texture elements don’t break apart using texton synthesis     


![](../assets/合成36.png)     

# Feature Map + Texture Map   
   

![](../assets/合成37.png)     


# Synthesis with Local Size Control    

![](../assets/合成38.png)     


# Synthesis with Vector Field Control    

![](../assets/合成39.png)     


# 3. 3D Texture Synthesis   

# Texture Synthesis on Surfaces   

![](../assets/合成40.png)     


# Analogy    

![](../assets/合成41.png)     


# Desired Properties    

* Share advantages of 2D algorithm    
• Quality    
• Efficient    
• General    
• Easy to use    
* Minimum distortion    
* Minimum discontinuity    

![](../assets/合成42.png)     


# 3D Texture Synthesis
• **Procedural texture synthesis**    
• Sample‐based texture synthesis    
• Geometry synthesis    


# Procedural Textures    

* Use 3D functions to define texture properties of objects    
• Non‐trivial programming    
• Flexibility    
• Parametric control    
• Unlimited resolution, antialiasing possible     
• Low memory requirements    
• Low‐cost visual complexity    
• Adapts to arbitrary geometry   

![](../assets/合成43.png)     



# Procedural Textures    

 - **Analytic scalar function of world coordinates**  (**x, y, z**)    
 - **Texturing: evaluation of function on object surface**    
    - Ray tracing: 3D intersection point with surface    
 - **Textures of natural objects**    
    - Similarity between different patches    
      - Repetitiveness, coherence    
    - Similarity on different resolution scales    
      - Self-similarity    
    - But never completely identical    
      - Additional disturbances, turbulence, noise    
 - **Procedural texture function**    
    - Mimics statistical properties of natural textures    
    - Purely empirical approach    
      - Looks convincing, but has nothing to do with material's physics    


# Perlin’s Noise   
[Perlin, Siggraph 1985]    

 - **Noise**  (**x,y,z**)    
    - Statistical invariance under rotation    
    - Statistical invariance under translation    
    - Narrow bandpass limit in frequency    
 - **Integer lattice**  (**i, j,k**)    
    - Random number at each lattice point  (i, j,k)     
      - Look-up table or hashing function    
    - Gradient lattice noise    
      - Random gradient vectors    
 - **Evaluation at** (**x,y,z**)    
    - Tri-linear interpolation    
    - Cubic interpolation (Hermite spline \\(\to\\) later)    
 - **Unlimited domain**    
    - Lattice replicated to fill entire space    
 - **Fixed fundamental frequency of \\(\sim\\) 1 Hz over lattice**    
 - **Smooth interpolation of interim values**   

 ![](../assets/合成44.png)     



# Turbulence Function    

 - **Noise function**    
    - “White” frequency spectrum    
 - **Natural textures**    
    - Decreasing power spectrum towards high frequencies    
 - **Turbulence from noise**    
    - Turbulence \\((x)=\sum_{i=0}^{k}\\) abs ( noise \\((2^i x ) / 2^{i}\\))      
    - Summation truncation    
       -  \\(1 / 2^{k+1}\\) <  size of one pixel (band limit)    
    - 1. Term: noise  (x)     
    - 2. Term: noise  (2 x) / 2    
    - \\(\dots\\)     
    - Power spectrum:  1 / f    
    - (Brownian motion: \\(1/f^2\\))    

    ![](../assets/合成45.png)     


# Synthesis of Turbulence (1D)    

![](../assets/合成46.png)     



# Synthesis of Turbulence (2D)    

![](../assets/合成47.png)     



# Example: Marble Texture Function    

 - **Overall structure: alternating layers of white and colored marble**    
    - \\(f_{marbie}(x,y,z)\\):= marble_color (sin (x))     
    - marble_color : transfer function    

    ![](../assets/合成48.png)     

 - Realistic appearance: simulated turbulence    
    - \\(f_{matibie}(x,y,z)\\):= marble_color (sin (x +  turbulence (x,y,z)))     
 - **Moving object: turbulence function also transformed**    

 ![](../assets/合成49.png)     



# Reaction Diffusion Based Method    
[Turk, Siggraph 1991]   


• Two‐chemical reaction‐diffusion system    

$$
\begin{array}{l}
\frac{\partial a}{\partial t}=F(a, b)+D_{a} \nabla^{2} a \\\\
\frac{\partial b}{\partial t}=G(a, b)+D_{b} \nabla^{2} b
\end{array}
$$

• Discrete computation

$$
\begin{array}{l}
\Delta a_{i j}=s\left(16-a_{i j} b_{i j}\right)+D_{a}\left(a_{i+1 j}+a_{i-l j}+a_{i j+1}+a_{i j-1}-4 a_{i j}\right) \\\\   
\Delta b_{i j}=s\left(a_{i j} b_{i j}-b_{i j}-\beta_{i j}\right)+D_{b}\left(b_{i+1 j}+b_{i-1 j}+b_{i j+1}+b_{i j-1}-4 b_{i j}\right)
\end{array}
$$



# Examples of Reaction‐Diffusion    

![](../assets/合成50.png)     

# Results   

![](../assets/合成51.png)     


# Solid Textures    
[Peachey, Siggraph 1985]    

* Solid texture functions in 3D space    
* Nonhomogeneous materials    
• wood and stone    

![](../assets/合成52.png)     



# Examples    

![](../assets/合成53.png)     



# 3D Texture Synthesis    

• Procedural texture synthesis     
• **Sample‐based texture synthesis**    
• Geometry synthesis    


# Methodology    

 - Synthesize a surface texture by **coloring mesh vertices**    
 - Extensions from 2D texture synthesis    
 - Key issues    
    - Resampling    
    - Local flattening    
      - Size    
      - Orientation    


![](../assets/合成54.png)     

Vertex colors on three levels in the mesh hierarchy    



# Neighborhood Sampling on Surface    

![](../assets/合成55.png)     


# Resampling    

![](../assets/合成56.png)     



# Mesh Neighborhood    

![](../assets/合成57.png)     



# Recap: Texture Synthesis by Neighborhood Search     

![](../assets/合成58.png)     



# Surface Texture Synthesis by Neighborhood Search     

![](../assets/合成59.png)     



# Differences between 2D and 3D    

![](../assets/合成60.png)     



# Sampling on Surface: Retiling   
[Turk, Siggraph 1992]    


• Distribute a set of vertices over surface as uniformly as possible     

![](../assets/合成61.png)     

# Retiling Density     

![](../assets/合成62.png)     



# Texture Orientation    

 - Methods for orienting textures    
    - user‐specified    
    - random (for isotropic textures)    
    - smooth or symmetric (for anisotropic textures)    
      - by relaxation     

![](../assets/合成63.png)     


# User Specified Vector Field    

![](../assets/合成64.png)     


# Texture Orientation Examples    

![](../assets/合成65.png)     



# Results: Other Orientations     

![](../assets/合成66.png)     


# Multiresolution Synthesis    


![](../assets/合成67.png)     



# Mesh Pyramid by Retiling    

![](../assets/合成68.png)     


# Examples    

![](../assets/合成69.png)     


# Results    

![](../assets/合成70.png)     


# Patch‐based Synthesis     


![](../assets/合成71.png)     

# Key Idea:  Patch Pasting    

![](../assets/合成72.png)     



# Algorithm   

![](../assets/合成73.png)     


# Algorithm    

![](../assets/合成74.png)     



# Texture Patch Creation    

![](../assets/合成75.png)     


# Less Structure \\(\to\\) Splotch     

![](../assets/合成76.png)     


# Patch Growth     

![](../assets/合成77.png)     

# Patch Growth     

![](../assets/合成78.png)     



# Patch Growth    

![](../assets/合成79.png)     


# Tangential Vector Field     

![](../assets/合成80.png)     



# Results: Splotches     

![](../assets/合成81.png)     

(***completely automatic: no direction field***)    




# Results: Anisotropic     

![](../assets/合成82.png)     


# Controlling Direction and Scale     

![](../assets/合成83.png)     

![](../assets/合成84.png)     



# Limitations    

![](../assets/合成85.png)     


# Feature‐aligned Texture Synthesis    
[Xu et al., Siggraph Asia 2009]    


![](../assets/合成87.png)     



# Curve Orientation and Vector Field    

![](../assets/合成88.png)     

# Results     

![](../assets/合成89.png)     


# Results     

![](../assets/合成90.png)     



# Progressively‐Variant Texture Synthesis     
[Zhang et al., Siggraph 2003]     

![](../assets/合成91.png)     



# BTF Synthesis     
[Tong et al., Siggraph 2002]     


• Bidirectional Texture Functions (BTF): A collection of images of the same surface under different lighting and viewing directions.     
&#x2705; 6D Function ( \\(x, y, l_θ, l_φ, v_θ, v_φ\\) )    
&#x2705; Dense Sampling in Viewing/Lighting Directions    
&#x2705; Capturing Appearance of Real World Surface    

![](../assets/合成92.png)     



# *Real World Texture from CuRet*      

![](../assets/合成93.png)     


•Geometry Details (Mesostructure) on Surface    
•Self-Occlusion, Self-Shadow, and Specularity     



# *Treating BTF as a 2D Texture Map*    

![](../assets/合成94.png)     


**Surface Texton**    



# Surface Texton Map & Rendering    

![](../assets/合成95.png)     



# K‐Coherent Search    

![](../assets/合成96.png)     



# Examples    

![](../assets/合成97.png)     


# Comparison    

![](../assets/合成98.png)     



# 3D Texture Synthesis    

• Procedural texture synthesis    
• Sample‐based texture synthesis    
• **Geometry synthesis**     



# Geometry Synthesis    


* Generating geometry over surfaces by texture (geometry) samples    
* Methods:     
• 3D distance field based method     
• Image analogies extended to volumes    
• Mesh‐based geometric texture synthesis technique    



# 3D Distance Field based Method     
[Lagae et al., TR 2004]      

![](../assets/合成99.png)     



# Results    

![](../assets/合成100.png)     

# Geometry Analogy    
    

![](../assets/合成101.png)     


# Mesh Quilting     
[Zhou et al., Siggraph 2006]     

![](../assets/合成102.png)     



# Results    

![](../assets/合成103.png)     

# Summary: Texture Synthesis    

• An important topic on content generation (2D/3D) textures or repeated geometries    
• A well‐studied topic    
• Many applications     
