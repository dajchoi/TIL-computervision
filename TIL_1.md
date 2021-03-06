## When making a kernel for filterization
#### filterization (Image Filtering)
  - noise reduction -> image restoration
  - structure extraction
##### Noise
[1] additive noise -> corrupted with random fluctuations
[2] salt & pepper noise -> can model errors through acquisition process

#### 1. numpy.arange ([start,] stop, [step,] dtype=None, *, like=None)
start has a default of 0
step has a default of 1
if dtype not give then it infers the data type from the other input arguments

-> return evenly spaced values within a give interval
*when using a non-int step value, it is better to use linspace

#### 2. numpy.linspace (start, stop, num=50, endpoint=True, retstep=False, dtype=None, axis=0)
num indicates the number of samples to generate
if retstep is true then returns (samples, step)
step is the spacing between samples

#### 3. numpy.zeros/numpy.ones(shape, [dtype= ] [order= ] [like= None]
returns a new array of given shape and type filled with zeros/ones
ex) numpy.zeros((1,1))

*applying kernel to images
img = cv2.filter2D(image, -1, kernel)

________________________________________________________________________________________

###### additional information about filtering
some 2D image filters can implemented as 2 1D filters,
one in the horizontal and the other in the vertical way
+) This implies lower complexity bringing up efficiency.

##### [Gaussian Filtering]
1D -> 1/(sqrt(2pi)*sigma)*np.exp(-x^2/(2*sigma^2))
2D -> 1/(2pi*sigma^2)*np.exp(-(x^2+y^2)/2*sigma^2)
##### [Median Filtering]
non-linear operation that is effective at removing salt and pepper noise
: replaces each pixel by the median of its neighbors
__________________________________________________
##### [Correlation Filtering] = symbol by x with a circle around
G[i,j] = sum(u: from -k to k)sum(v: from -k to k)H[u,v]F[i+u,j+v]
*kernel mask weights in the linear combination; replaces each pixel by weighted combination of its neighbors

##### [Convolution] -------- filter is flipped from bottom to top and from right to left; then cross-correlation applied = symbol by *
G[i,j] = sum(u: from -k to k)sum(v: from -k to k)H[u,v]F[i-u,j-v]
(+) Kernel => (for noise recuction) 
(1) Mean Kernel: smoothing by averaging entries; entries must add up to 1 
(2) Gaussian Kernel
___________________________________________________

*Correlation and Convolution relationship:
give the same response if the mask is symmetric



