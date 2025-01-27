# AMDCNet: An Attentional Multi-Directional Convolution Network for Stereo Matching

### Code
* `./AMDCNet-Figure Code/`: This folder contains Census model code which can produce the `Figure1.png` after running. It should run in vs2012 + pcl1.8.0 + boost environment.
* `./AMDCNet-Table Code/`: This folder contains the test code in middlebury. It will produce the information data of the proposed algorithm in `Table1.png` and `Table2.png`. I use opencv 2.4.8, other versions should be OK but not too low. Contain `./Data/` and `./Data_extended/`. `./Data/` folder contains the data folder contains Tsukuba, Venus, Teddy and cones datasets from Middlebury official test datasets. The current directory `images.xml` is the input item, it will read the contents of the file. In the previous directory `./sample/test_images`, the image in the images directory is the input item and the name is the same as the name in `images.xml` correspondingly. The output results are saved in the result directory under the current directory. `./Data_extended/` contains 27 data sets from Middlebury official test datasets. 
* `./model/`: This folder contains Census model code.
* `./model add smoothing filtering/`: This folder contains the model code which add a soothing filter based on the Cencus model.

98% codes are written in C++, 2% codes are written in C. Codes are written in Visual Studio 2013. The environment of OpenCV is 2.4.9. 


### Data
* `./Part 1-4 test data set and disparity map/`: This folder contains test data and disparity map which are standard images from Middlebury official test datasets.
* `./Training sets/`: This folder contains data used for training.
* `./Validation sets/`: This folder contains data used for validation.
* `./Testing sets/`: This folder contains data used for testing.

### Model
* `AMDCNet-architecture diagram.png`: It shows the architecture overview of proposed AMDCNet. We perform three operations on the image: (a) Perform convolution template to get the visual sensitivity factor; (b) Calculate the initial cost of the image and construct the multi-directional aggregation template. (c) Detect left and right consistency to optimize.
<div align=center><img src="https://github.com/WangHewei16/Stereo-Matching-Algorithm/blob/main/AMDCNet-architecture diagram.png?raw=true" width="1000"/></div>

In the sensitive points extraction stage, we propose a method to detects the edge points, contour points and other visual sensitive areas in the image, analyze the texture distribution difference between them and smooth areas, and guide the judgment weight of degree of freedom extension. In the multi-directional template matching stage, we first construct a multi-directional extension template, then, extended pixel length is guided according to the visual sensitivity, finally, we complete the whole image processing. In the optimization stage, we propose left and right consistency detection method to further reduce the error matching rate.

### Figure
* `Figure1.png`: This figure shows the comparison of different test results. The first column is the perspective image in the original image of the experimental data set, the second column is the ideal parallax image for reference, the third and fourth columns are the result images obtained by the classical algorithm census, and the fifth and sixth columns are stereo matching algorithms based on visual sensitive information. Among them, the red marks in the fourth and sixth columns indicate the mismatching areas of the marks when comparing the two result maps with the ideal disparity map. Through the display of subjective images, we can clearly see that the proposed algorithm can effectively calculate and generate the disparity of the original image, and the matching effect is better than that of the classical algorithm. 

<div align=center><img src="https://github.com/WangHewei16/Stereo-Matching-Algorithm/blob/main/Figure1.png?raw=true" width="700"/></div>


* `Figure2.png`: This figure shows the visual sensitive area retention. It shows that this algorithm has been improved and preserved in many visual sensitive areas, such as 'peak', 'lamp' and 'table'.
* `Figure3.png`: This figure shows the disparity image before and after optimization. It shows the results of further comparing the error matching rate of the optimized disparity map.
* `Figure4.jpg`: This figure shows the other processed images of propose algorithm. It shows the results that experimented with other images in the data set. From this figure, we can find that the algorithm proposed in this paper has good processing effect for most binocular vision images.
* `Figure5.png`: This figure shows a comparison of the other three images processed by the algorithm in this paper and Pyramid Stereo Matching Network, Richer Convolutional Features Network. The first column is the original left view image, which are art, baby and Book respectively, the second example is the real parallax image, the third column is the algorithm image in this paper, the fourth column is the result diagram of Pyramid Stereo Matching Network, and the fifth column is the result generated by the algorithm in literature of Richer Convolutional Features Network.

<div align=center><img src="https://github.com/WangHewei16/Stereo-Matching-Algorithm/blob/main/Figure5.png?raw=true" width="700"/></div>

* `Figure6-Scene Flow.png`: This figure shows a comparison of the other three images processed by the algorithm in this paper and Pyramid Stereo Matching Network, Richer Convolutional Features Network. The first column is the original image from the left perspective, the second column is the real parallax image, the third column is the algorithm diagram in this paper, and the fourth and fifth columns are the result diagrams obtained by the PSMNet and RCF.

<div align=center><img src="https://github.com/WangHewei16/Stereo-Matching-Algorithm/blob/main/Figure6-Scene Flow.png?raw=true" width="700"/></div>

* `Figure7-KITTI.png`: This figure shows a comparison of the other two images processed by the algorithm in this paper and GWC-Net and Attention-guided aggregation stereo matching network. The first column is the left view image of the original image, and the second column is the result image obtained by the algorithm in this paper. The third column is the parallax image obtained by GWC-Net. The fourth column is the parallax image obtained by Attention-guided aggregation stereo matching network.

<div align=center><img src="https://github.com/WangHewei16/Stereo-Matching-Algorithm/blob/main/Figure7-KITTI.png?raw=true" width="700"/></div>

### Table
* `Table1.png`: This table shows the error matching rate obtained by various algorithms. It shows that error matching rate of the proposed algorithm is lower than that of the same kind of algorithm, and the overall matching effect is better.
* `Table2.png`: This table shows the mismatch rate under different Gaussian noise concentrations. It shows that show that when the noise concentration increases, the change degree of the error matching rate of this algorithm is lower, and the sensitivity to noise is lower.
* `Table3.png`: This table shows the comparison results of different algorithms. From this table, we can see the difference between NOCC and all. NOCC is the non occluded area mentioned above, and all is the matching of all areas of the image, including the blind area of parallax. The data of mismatch rate in the table objectively proves the effectiveness of this algorithm, which has more advantages than the same kind of classical algorithms.
* `Table4.png`: This table shows the comparison with different algorithms before and after optimization in non occluded area.
