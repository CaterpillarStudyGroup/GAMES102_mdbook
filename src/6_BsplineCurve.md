几何建模与处理基础
刘利刚
中国科学技术大学
GAMES 102在线课程
B样条曲线
GAMES 102在线课程：几何建模与处理基础
Bezier曲线的不足
• 次Bezier曲线： 个控制顶点
𝑥 𝑡 ? ?𝐵 ?
?
𝑡 ⋅ 𝑏 ?
?
???
全局性：牵一发而动全身，不利于设计
原因：基函数是全局的
样条曲线
• 分段的多项式曲线（Bezier曲线）
• 分段表达，具有局部性
有无统一的表达方式？
思考：样条曲线的统一表达
• 形式类比：每个控制顶点用一个基函数进行组合
?,?
?
???
?
• 性质要求：
• 基函数须局部性（局部支集）
• 基函数要有正性+权性
• …
• 如何构造？
B样条的产生
• Early use of splines on computers for data
interpolation
• Ferguson at Boeing, 1963
• Gordon and de Boor at General Motors
• B‐splines, de Boor 1972
• Free form curve design
• Gordon and Riesenfeld, 1974 → B‐splines as a
generalization of Bezier curves
启发：
• Bernstein基函数的递推公式：
?
?
?
???
???
???
with
?
?
?
?
for
• 思路：
• 局部处处类似定义，由一个基函数平移得到
• 高阶的基函数由2个低阶的基函数“升阶”得到
• 利于保持一些良好的性质，比如提高光滑性
Key Ideas
• 以三次为例
• We design one basis function 𝑏 𝑡
• Properties:
𝐶 ? continuous
is piecewise polynomial, degree 3 (cubic)
𝑏 𝑡 has local support
Overlaying shifted 𝑏 𝑡 ? 𝑖 forms a partition of unity
• 𝑏 𝑡 ? 0 for all 𝑡
• In short:
• All desirable properties build into the basis
• Linear combinations will inherit these
Shifted Basis Functions
• 型值点参数化：节点向量
Shifted basis function 𝑏 𝑡
Illustration only
Courtesy of Renjie Chen
Repeated linear interpolation
• Another way to increase smoothness:
Repeated linear interpolation
• Another way to increase smoothness:
Repeated linear interpolation
• Another way to increase smoothness
De Boor Recursion: uniform case
• The uniform B‐spline basis of order 𝒌 (degree 𝒌 ? 𝟏) is
given as
• 𝑁 ?
?
𝑡 ? ? 1,if 𝑖 ? 𝑡 ? 𝑖 ? 1
0, otherwise
• 𝑁 ?
?
𝑡 ?
?
????? ??
𝑁 ?
???
𝑡 ?
??? ??
??? ? ???
𝑁 ???
???
𝑡
• ?
?
???
𝑁 ?
???
𝑡 ?
?????
???
𝑁 ???
???
𝑡
B‐spline curves: general case
• Given: knot sequence
? ? ? ???
(
? ? ???
is called knot vector)
• Normalized B‐spline functions
?,?
of the order
(degree  ) are defined as:
?,?
? ???
?,?
??? ?
? ????? ?? ?
?,???
? ??? ??
? ??? ?? ???
???,???
for  and
Example
𝑁 ?,? 𝑡 ? ? 1, 𝑡 ?
? 𝑡 ? 𝑡 ???
0, otherwise
𝑁 ?,? 𝑡 ?
??? ?
? ????? ?? ?
𝑁 ?,??? 𝑡 ?
? ??? ??
? ??? ?? ???
𝑁 ???,??? 𝑡
for 𝑘 ? 1 and 𝑖 ? 0,…,𝑛
Example
Example
Basis properties
• For the so defined basis functions, the following
properties can be shown:
? ? 𝑡 ? 𝑡 ???
𝑁 ?,? 𝑡 ? 0 for 𝑡 ? ? 𝑡 ? 𝑡 ? or 𝑡 ??? ? 𝑡 ? 𝑡 ???
• ∑ 𝑁 ?,?
𝑡
?
???
? 1 for 𝑡 ??? ? 𝑡 ? 𝑡 ???
• For
? ? ??? , the basis functions  ?,?
are
???
at the knots
?
• The interval
? ???
is called support of
?,?
B‐spline curves
• B‐spline curves
• Given:  𝑛 ? 1 control points 𝒅 ? ,…,𝒅 ? ∈ ℝ ?
knot vector 𝑇 ? 𝑡 ? ,…,𝑡 ? ,…𝑡 ???
• Then, the B‐spline curve 𝒙 𝑡 of the order 𝑘 is defined
as
𝒙 𝑡 ? ?𝑁 ?,? 𝑡
?
???
⋅ 𝒅 ?
• The points 𝒅 ? are called de Boor points
Carl R. de Boor
German‐American mathematician
University of Wisconsin‐Madison
Example
•
Support intervals of 𝑁 ?,?
Curve defined in interval 𝑡 ? ? 𝑡 ? 𝑡 ?
B‐spline curves
• Multiple weighted knot vectors
• So far: 𝑇 ? 𝑡 ? ,…,𝑡 ? ,…,𝑡 ??? with 𝑡 ? ? 𝑡 ? ? ⋯ ?
𝑡 ???
• Now: also multiple knots allowed, i.e. with 𝑡 ? ? 𝑡 ? ?
⋯ ? 𝑡 ???
• The recursive definition of the B spline function 𝑁 ?,?
𝑖 ? 0,…,𝑛 works nonetheless, as long as no more
than 𝑘 knots coincide
B‐spline curves
• Effect of multiple knots:
set: 𝑡 ? ? 𝑡 ? ? ⋯ 𝑡 ???
• and 𝑡 ??? ? 𝑡 ??? ? ⋯ ? 𝑡 ???
𝒅 ? and 𝒅 ? are interpolated
B‐spline curves
• Example:
B‐spline curves
• Example:
B‐spline curves
• Further example
B‐spline curves
• Interesting property:
• B‐spline functions 𝑁 ?,? (𝑖 ? 0,…,𝑘 ? 1) of the order 𝑘
over the knot vector 𝑇 ? 𝑡 ? ,𝑡 ? ,…,𝑡 ???? ?
0,…,0,1,…,1
are Bernstein polynomials 𝐵 ?
???
of degree 𝑘 ? 1
𝑘 times 𝑘 times
B‐spline curves properties
• Given:
• 𝑇 ? 𝑡 ? ,…,𝑡 ? ,𝑡 ? ,…,𝑡 ? ,𝑡 ??? ,…,𝑡 ???
• de Boor polygon 𝒅 ? ,…,𝒅 ?
• Then, the following applies for the related B‐spline
curve  :
𝒌 times 𝒌 times
B‐spline curves properties
•
? ? ??? ?
(end point interpolation)
•
?
??
? ? ?? ?
? ?
(tangent direction at
? ,
similar in
? )
• consists of  polynomial curve
segments of degree  (assuming no multiple
inner knots)
B‐spline curves properties
• Multiple inner knots ⇒ reduction of continuity of 𝑥 𝑡 .
𝑙‐times inner knot (1 ? 𝑙 ? 𝑘? means
𝐶 ????? ‐continuity
• Local impact of  the de Boor points: moving of 𝑑 ? only
changes the curve in the region 𝑡 ? ,𝑡 ???
• The insertion of new de Boor points does not change the
polynomial degree of the curve segments
B‐spline curves properties
• Locality of B‐spline curves
B‐spline curves
• Evaluation of B‐spline curves
• Using B‐spline functions
• Using the de Boor algorithm
Similar algorithm to the de Casteljau algorithm for Bezier curves;
consists of a number of linear interpolations on the de Boor polygon
The de Boor algorithm
• Given:
𝒅 ? ,…,𝒅 ? : de Boor points
𝑡 ? ,…,𝑡 ??? ? 𝑡 ? ,𝑡 ? ,𝑡 ??? ,…,𝑡 ? ,𝑡 ??? ,…,𝑡 ??? ? 𝑡 ??? :
Knot vector
• wanted:
Curve point 𝒙 𝑡 of the B‐spline curve of the order 𝑘
The de Boor algorithm
1. Search index with
? ???
2. for
•
?
?
?
• for
• for
•
?
?
?
?
???
???
?
?
?
???
• with
?
? ??? ?
? ????? ?? ?
• Then: 
?
???
B样条曲线：分段Bezier曲线
•
B：Basic（亦称“基本样条”）
B样条的其他理论知识
• B样条的许多性质
• 局部凸包性、变差缩减性、包络性
• B样条的导数、积分递推式、几何作图
• 重节点的B样条基函数及B样条曲线
• Bezier样条曲线转换为B样条曲线
• B样条插值方法
• …
谢 谢 ！
