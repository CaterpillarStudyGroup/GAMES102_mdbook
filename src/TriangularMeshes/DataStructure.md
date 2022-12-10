# 网格曲面的数据结构    


# Uses of Mesh Data     


* Rendering     
• Triangle trip     
* Geometry queries     
• What are the vertices of face #k ?      
• Are vertices #i and #j adjacent?     
• Which faces are adjacent face #k ?    
* Geometry operations    
• Remove/add a vertex/face    
• Mesh simplification     
• Vertex split, edge collapse     



# Storing Mesh Data     

* Storage of generic meshes     
• Hard to implement efficiently     
* Assume     
• Triangular     
• Orientable     
• Manifold        

## Define a Mesh

* Geometry     
• Vertex coordinates     
* Connectivity     
• How do vertices connected?     

![](../assets/表达12.png)   

• List of Edge      
• Vertex‐Edge     
• Vertex‐Face      
• Combined      


# 3D Mesh Surface     

* Surface & material properties       
• Material color      
• Ambient, hightlight coefficients      
• Texture coordinates     
• BRDF, BTF    
* Rendering properties      
• Lighting      
• Normals       
• Rendering modes     


# General Used Mesh Files    

* General used mesh files     
• Wavefront OBJ ( *. obj)     
• 3D Max ( *. max, *. 3ds)     
• VRML ( *. vrl)     
• Inventor (  *.  iv)      
• PLY ( *. ply, *. ply2)     
• User‐defined ( *. m, *. liu)     
* Storage     
• Text – (Recommended)     
• Binary     



## Wavefront OBJ File Format    

* Vertices     
• Start with char ‘v’    
• (x,y,z) coordinates     
* Faces     
• Start with char ‘f’     
• Indices of its vertices in the file     
* Other properties     
• Normal, texture coordinates, material, etc.     

![](../assets/表达13.png)   


