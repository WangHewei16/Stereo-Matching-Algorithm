## Code
* `./model/`: This folder contains Census model code.
* `./model add smoothing filtering/`: This folder contains the model code which add a soothing filter based on the Cencus model.

98% codes are written in C++, 2% codes are written in C. Codes are written in Visual Studio 2013. The environment of OpenCv is 2.4.9. 

## Data
* `./Part 1-4 test data set and disparity map/`: This folder contains test data and disparity map which are standard images from Middlebury official test datasets.

## Figure
* `./Figure1.png`: This figure shows the comparison of different test results. The first column is the perspective image in the original image of the experimental data set, the second column is the ideal parallax image for reference, the third and fourth columns are the result images obtained by the classical algorithm census, and the fifth and sixth columns are stereo matching algorithms based on visual sensitive information. Among them, the red marks in the fourth and sixth columns indicate the mismatching areas of the marks when comparing the two result maps with the ideal disparity map. Through the display of subjective images, we can clearly see that the proposed algorithm can effectively calculate and generate the disparity of the original image, and the matching effect is better than that of the classical algorithm. 
* `./Figure2.png`: This figure shows the visual sensitive area retention. It shows that this algorithm has been improved and preserved in many visual sensitive areas, such as 'peak', 'lamp' and 'table'.
* `./Figure3.png`: This figure shows the disparity image before and after optimization.
* `./Figure4.png`: This figure shows the other processed images of propose algorithm.

## Table
* `./Table1.png`: This table shows the error matching rate obtained by various algorithms.
* `./Table2.png`: This table shows the mismatch rate under different Gaussian noise concentrations.
* `./Table3.png`: This table shows the comparison results of different algorithms.
