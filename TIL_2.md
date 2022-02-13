### Edges - discontinuity
: a place of rapid change in the image intensity function 
types (1) surface normal (2) depth (3) surface reflectance (4) illumination
##### Edge Detection 
: identify sudden changes in an image => more compact than pixels 
I(x) => changes of value (low -> high / high -> low)
I'(x) => extrema (minima/maxima) check
*whole idea is about computing spatial derivatives which will be approximated by convolution
###### [1] Good detection
minimize the probability of false positives + false negatives
###### [2] Good localization
edges detected must be as close as possible to the true edges
_____________________________________________________________
Canny Edge Detector
<process>
  - filter image with derivative of Gaussian
  - find magnitude and orientation of gradient
  - non maximum suppression
  - linking + thresholding (hysteresis)
  *for thresholding (high: start edge curves, low: continue the mentioned edge curves)
 <non-maximum suppression>
   interpolate the dots if the value is larger than those at both the dots
 <hysteresis thresholding>
   check that max value of gradient value is sufficiently large
   (high threshold to start edge curve -> low threshold to continue them)
   high threshold: more clear and thin (strong edges)
   low threshold: (weak edges)
sigma: 
   large sigma (detects) large scale edges
   small sigma (detects) fine features

_____________________________________________________________
   
### Feature Extraction - set of dot products
feature types (1) points (2) edges-line and step (3) contours-closed(boundaries) (4) regions
##### Gradient of an Image
gradient direction -> ceta = tan^(-1)(sigma(f)/sigma(y))/(sigma(f)/sigma(x))
edge strength -> gradient magnitude
##### Second derivative detector
(LoG = Lapacian of Gaussian)
   
   
