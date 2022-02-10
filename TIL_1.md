## When making a kernel for filterization

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

