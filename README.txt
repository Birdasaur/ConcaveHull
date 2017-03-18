Format of Excution
dku_ch [option] ([convex list file]) [original data file] [output file] ([threshold])

Parameters:
1. Options
-p  using original data file
you have to use this option when you have only dataset. we will make convex hull list by qhull algorithm.
and then make concave hull. the options of qhull algorithm is fixed.
 
-f  using existing convex list file
if you already have convex hull list via MATLAB or another methods, you can use this option. we will make
concave hull.

2. Convex list file
If you can get convex hull list file through other program and use '-f' option. Then You can skip convex hull algorithm.
'Requirements of Format of Input Data' section describe details of data format.

3. Original data file
Original data file is necessary parameter. 
'Requirements of Format of Input Data' section describe details of data format.

4. Output file
You can set the output file name which is automatically modified and adding '_ccvList', which means concave list, at the end of output file name.

5. Threshold
Threshold affect concave hull shape. Default value of threshold is 2. If you don't set threshold value. Then program will use default value.

Examples of Excution
dku_ch -p 3dDataset concaveResult
dku_ch -p 3dDataset concaveResult 0.9
dku_ch -f convexList.txt 3dDataset concaveResult
dku_ch -f convexList.txt 3dDataset concaveResult 1.2

Requirements of Format of Input Data:
-original data file
Each feature must be separated by ','(comma).
example of original data
1.97 ,0.3557 ,-0.407    ;(it is composed with 3 features and separated by comma)

-convex list file
The value of index must start at 1, not 0. and convex list also must be separeated by comma.
1, 2, 3    ;(This is example of triangular pyramid. Each line means triangle face of triangluar pyramid.)
1, 2, 4    ;(The indexes of points that is start at 1. Therefore there is no 0.)
2, 3, 4
3, 1, 4

Format of Output:
This is almost same with Input Data.

-concave list file
concave list form is exactly same with convex list form.
concave hull list file has exactly same format with convex hull list.

