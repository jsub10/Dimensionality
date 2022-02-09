## Approach 1 - What happens to the Euclidean distances between points in a hypercube as the number of dimensions of that hypercube increases? 

 - Generate an array of vectors with array size m rows and n columns
 - These arrays can be of two kinds.
  - Case 1: The first kind of array is when each vector in the array is the same as every other vector in the array. This is the case in which we start out with n points in a one-dimensional space and ask how these same points are distributed as we increase the dimensions. Same points, 
  - Case 2: The second kind of array is when each vector in the array is different from every other vector in the array. This is the general case of having the same number of points but the points in each dimension are different from the points in the higher dimension. Intuitively, this is not the case that we want. 
 - Case 1
  - Generate an m x n array where the row vectors are exactly the same. Use the repeat_array function with repeat_array=1.
  - Find the average distance between the points on a single vector. 
  - Then take a 2, 3, 4, ... m vectors and transpose them. This will render them in the form that the same set of points are being put into higher dimensions. Find the average pairwise distance between these vectors. This measures the way in which dimensionality makes distances greater and washes out similarity because ultimately everything is sufficiently far from everthing.
 - Case 2
  - Generate an m x n array where the row vectors are different. Use repeat_array=0. The rest of the steps are the same as Case 1.
  - Since there can be different points in different dimensions, the results are less stable in terms of the conclusions we can draw about the rate of change of average distance, for example.
  
## Approach 2 - Density of points in an n-dimensional hypercube

Another way to think about this is as a measure of density where density is the number of points in the hypercube divided by the volume of the hypercube. The volume of an n-dimensional hypercube with edge length r is $r^n$. So we can ask: if we have N points in a single dimension of edge length L, how many points will we need in m dimensions if we want to preserve the same density of points? 