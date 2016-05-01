# Hough Transform

##Finding Lines - Linear Hough Transform
Directory: Linear Hough Transform

Formula: xcos(θ)+ysin(θ) = r,0≤θ<π

Input: 
  - Canny edge points. 
  - Gradient magnitude and orientation.
  
Output:
  - All straight lines in image(Or one most specific line).

In this implementation, LinearHoughAccum function get the accumulator arrays, which keeps (r, θ) pair array. And show_lines only shows one most specific line. Any detail implementation process, please refer to "doc_Linear Hough Transform.pdf". 

### Comment
An alternative to the Linear Hough Transform is the RANdom SAmple Consensus(RANSAC) algorithm. In brief, RANSAC randomly chooses pairs of edgels to form a line hypothesis and then tests how many other edgels fall onto this line. Lines with sufficiently large numbers of `inliers`(matching edgels) are then selected as the desired line segments. 

And advantage of RANSAC is that no accumulator array is needed and so the algorithm can be more space efficient and potentially less prone to the choice of bin size as in Linear Hough Transform. 

The disadvantage of RANSAC is that many more hypotheses may need to be generated and tested than those obtained by finding peaks in the accumulator array.

