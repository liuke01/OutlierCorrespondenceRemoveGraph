# GROR
***GROR: A New Outlier Removal Strategy Based on Reliability of Correspondence Graph for Fast Point Cloud Registration***
## News
* [2022-12-05] The paper has been accessed online (Early Acess)! Check [here](https://doi.org/10.1109/TPAMI.2022.3226498) to get it.
* [2022-11-26] Our paper has been accpeted by ***TPAMI*** (IEEE Transactions on Pattern Analysis and Machine Intelligence)(IF:24.314) !
# About
![image](https://user-images.githubusercontent.com/32131223/158051652-8494f83e-4439-4034-a5ff-ff28920b088f.png)

(a): correspondences generated by correspondence matching strategy (green and red lines represent the inlier and outlier correspondences according to the ground truth respectively). (b) remaining correspondences after using our Outlier Removal Strategy (c) registration result by GROR.

GROR can solve the 6-dof registration problem between two point clouds in 3D. It performs well (fast and robust) even if the input correspondences have an extremely large number of outliers. For more information, please refer to our papers:

[A New Outlier Removal Strategy Based on Reliability of Correspondence Graph for Fast Point Cloud Registration](https://doi.org/10.1109/TPAMI.2022.3226498)

![image](https://user-images.githubusercontent.com/32131223/158198857-c878d438-2e13-4ed2-99ab-528b4bdb294b.png)
# Getting Started
## Environment:
Our program is lightweight and can be included in any project that adds the PCL library. We've tested it on Windows (VS2015) and Ubuntu (vscode)
## Dependencies:
Building GROR requires the following libraries installed
1. A compiler that supports OpenMP.
2. CMake >= 3.5
3. PCL >= 1.8.1
## Compilation
 ### On Windows:  
  You can easily compile it using CMake.
 ### On Ubuntu:
 ```
mkdir build
cd build
cmake ..
make
./ GrorReg "source path" "target path" resolution K(Such as "arch/s1.ply" "arch/s2.ply" 0.1 800)
```
## Parameter configuration
1. GROR needs to get the correspondences before running, we adopt the strategy of (downsampling) + (key point extraction) + (FPFH descriptor) + (correspondences matching). All parameters can be kept as default except for the key point extraction stage for Data Office and Railway where iss_non_max_radius_is set to 2 and 9 to get a better registration result.
2. There are two parameters of GROR：downsampling resolution and K. Usually K is kept around 800. The resolution is generally set to 0.1m, but some adjustments need to be made according to the size of the scene and the larger the resolution setting, the faster the algorithm efficiency.
## Data preparation
 You can test on the online available point cloud data and registration dataset such as [WHU TLS Registration Dataset](http://3s.whu.edu.cn/ybs/en/benchmark.htm), [ETH PRS TLS Registration Dataset](https://prs.igp.ethz.ch/research/completed_projects/automatic_registration_of_point_clouds.html), [ETH ASL Robotics Registration Dataset](https://projects.asl.ethz.ch/datasets/doku.php?id=laserregistration:laserregistration), [3D Match](http://3dmatch.cs.princeton.edu/), [Robotic 3D Scan Repository](http://kos.informatik.uni-osnabrueck.de/3Dscans/), etc.

You may apply the format transform tool to get the data ready for registration.

## Citation
If you find our code or paper helps, please consider citing:


 ```
@ARTICLE{9969937,
  author={Yan, Li and Wei, Pengcheng and Xie, Hong and Dai, Jicheng and Wu, Hao and Huang, Ming},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence}, 
  title={A New Outlier Removal Strategy Based on Reliability of Correspondence Graph for Fast Point Cloud Registration}, 
  year={2022},
  volume={},
  number={},
  pages={1-17},
  doi={10.1109/TPAMI.2022.3226498}}
```
#
