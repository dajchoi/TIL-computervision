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



### Feature Extraction - set of dot products
feature types (1) points (2) edges-line and step (3) contours-closed(boundaries) (4) regions
##### Gradient of an Image
gradient direction -> ceta = tan^(-1)(sigma(f)/sigma(y))/(sigma(f)/sigma(x))
edge strength -> gradient magnitude
