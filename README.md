# Basic-Image-Recognition
Learning how to decompose and compare base data pictures with an unknown observed image. This is a rough form of image identification based on SVD decompition that i learned in math class.

SVD decomposition takes any N x M matrix and break it down into a N x N matrix of eigenvectors,
multiplied by a rank one matrix of eigenvalues, multiplied by a M x M matrix of eigenvetors. 
Using CV2, any image is grabbed and its pixel data is converted into a numpy array. 
The array is then statistically centered to avoid any outliers, such as a picture that has a very red
filter on it, and it multiplied my itself to create a very large rank one matrix M. From this large matrix M, its 
core data it taken ( the M x M eigenvector array) and stored. Any image that is to be identified is
simply multiplied by this core data, which in this code results in 2 numbers, representing x and y coordinates and 
if that resulting point is sufiiciently close to other core data points, than it can be said that the image is
similar to the rest of the core data. Outliers are treated as foreign images.

this is obvioulsy not as elegant or sophisticated as something like FACE ID, however, its fun to see how image can
be manipulated like raw numbers.
