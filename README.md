# Investigating and Improving Common Loop Closure Failures in Visual SLAM
We analyse, for the first time, the popular loop closing module of a well known and widely used open-source visual SLAM (ORB-SLAM) pipeline. Investigating failures in the loop closure module of visual SLAM is challenging since it consists of multiple building blocks. Our meticulous investigations have revealed few interesting findings. 
Contrary to reported results, ORB-SLAM frequently misses large fraction of loop closures on public (KITTI, TUM RGB-D) datasets. One common assumption is, in such scenarios, the visual place recognition (vPR) block of the loop closure module is unable to find a suitable match due to extreme conditions (dynamic scene, viewpoint/scale changes). We report that native vPR of ORB-SLAM is not the sole reason for these failures. Although recent deep vPR alternatives achieve impressive matching performance, replacing native vPR with these deep alternatives will only partially improve loop closure performance of visual SLAM. 

Our findings suggest that the problem lies with the subsequent relative pose estimation module between the matching pair. Surprisingly, using off-the-shelf SIFT based relative pose estimation (non real-time) manages to close most of the loops missed by ORB-SLAM. This significant performance gap between the two available methods suggests that ORB-SLAM's pipeline can be further matured by focussing on the relative pose estimators, to improve loop closure performance, rather than investing more resources on improving vPR. We also evaluate deep alternatives for relative pose estimation in the context of loop closures. Interestingly, the performance of deep relocalization methods (e.g. MapNet) is worse than classic methods even in loop closures scenarios. This finding further supports the fundamental limitation of deep relocalization methods recently diagnosed. 

Finally, we expose the bias in the well known public dataset (KITTI) due to which these commonly occurring failures have alluded the community. We augment the KITTI dataset with detailed loop closing labels. In order to compentsate for the bias in the public datasets, we provide a challenging loop closure dataset which contains challenging yet commonly occurring indoor navigation scenarios with loop closures. We hope our findings and the accompanying dataset will help the community in further improving the popular ORB-SLAM's pipeline.

## Understanding and Loading KITTI Scene Graphs
Load the .mat files (e.g. scene-graph-kitti-00) to your MATLAB (or whatever you want) workspace. The data would be loaded to variable 'SG_00'. Values at locations e.g. SG_00(4,5), would indicate number of SIFT feature matches surviving RANSAC between images 4, and 5 when the sequence is sampled at 10 fps. For other sequences, only the sequence number changes e.g. SG_00 changes to SG_02 for sequence KITTI-02.

## ORB-SLAM missing Loop Closures in Kitti Dataset
https://user-images.githubusercontent.com/78947608/167349820-6ba8a2e5-8344-4eda-a35a-25ea215c943f.mp4

## ORB-SLAM missing Loop Closures in TUM-RGBD Dataset
https://user-images.githubusercontent.com/78947608/167350816-2f2a2f6b-8b6d-48ee-ad7b-f84564ec9689.mp4

## ORB-SLAM missing Loop Closures in NUST-CLC Dataset with Dynamic Change
https://user-images.githubusercontent.com/78947608/167351380-3980e9c3-a348-4051-ae09-87a276366b86.mp4

## ORB-SLAM missing Loop Closures in NUST-CLC Dataset with Viewpoint Change
https://user-images.githubusercontent.com/78947608/167351769-3df1596e-d365-4dee-b132-a935f07272c9.mp4


# NUST-CLC Dataset
Email for Dataset, if following link is not working
wajahat.hussain@seecs.edu.pk
latif.anjum@seecs.edu.pk
saran.khaliq@gmail.com

## Dynamic Sequences
Click [here](https://drive.google.com/drive/folders/1-4cPT6h8jgzjqVbbZInyp3XrXTaWNxBD?usp=sharing) to download Dynamice Sequences. To run with ROS, [rosbags](https://drive.google.com/drive/folders/1kaQB88lQgl7aUKUm0CVUlgg-bJI9Oda0?usp=sharing) are also available.

![50 - Dynamic Experiments](https://user-images.githubusercontent.com/78947608/167354052-be84e537-b1de-489a-ad14-66e3c5716653.jpg)

## Viewpoint Sequences
Click [here](https://drive.google.com/drive/folders/11bOqQBHUmLUUMoB6JfUlBQz8VKaIvWkL?usp=sharing) to download Viewpoint Sequences. To run with ROS, [rosbags](https://drive.google.com/drive/folders/1rt6WpCodpaPnXxQijNK9vOodPPHttQZx?usp=sharing) are also available. 

![50 - Viewpoint Experiments](https://user-images.githubusercontent.com/78947608/167355509-c94b5b28-68fa-4705-9093-c35a40f2dad5.jpg)

## Geometric Check is the main reason behined Loop Closure Failure in Dynamic and Viewpoint Sequences

https://user-images.githubusercontent.com/78947608/167362621-32d9eee3-abe0-46d4-bb3a-8a49dc335d53.mp4


# ORB-SLAM3 misses Loop Closures 

## Indoor Sequences 

https://user-images.githubusercontent.com/78947608/167363192-7827348e-f346-4d7c-9208-7243f1e47289.mp4

## Outdoor Sequences 

https://user-images.githubusercontent.com/78947608/167363950-b4483ab1-34ff-41ad-bcff-f545cb11e530.mp4


# Comparison of trajectories of ORB-SLAM and our pro-posed approach with ground truth

Loop closure and better alignment with ground truth with our approach is evident.
![Comparison](https://user-images.githubusercontent.com/78947608/167364467-c16e9c5c-c712-4a65-9321-2b30e6d79adb.png)




