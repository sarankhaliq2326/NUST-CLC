# Why-Visual-SLAM-is-missing-commonly-occurring-loop-closures
We investigate why ORB-SLAM is missing fre- quently occurring loop closures. Investigating failures in loop  closure module of ORB-SLAM is challenging since it consists of multiple building blocks. Our meticulous investigations have revealed few interesting findings. Contrary to reported results, ORB-SLAM frequently misses large fraction of loop closures on public (KITTI, TUM RGB-D) datasets. One common assumption is, in such scenarios, the visual place recognition (vPR) block of the loop closure module is unable to find a suitable match due to extreme conditions (dynamic scene, viewpoint/scale changes). We report that native vPR of ORB SLAM is not the sole reason for these failures. Interestingly, recent deep vPR alternatives achieve impressive matching performance. Replacing native vPR with these deep alternatives will partially improve the loop closure performance of visual SLAM. The other part of the problem is the subsequent relative  pose estimation module between the matching pair. Surpris- ingly, using off-the-shelf SIFT based relative pose estimation  manages to close most of the loops missed by ORB-SLAM. This finding advocates the use of multiple features for different SLAM modules instead of relying on a one-feature-for-all strategy. Furthermore, the performance of deep relocalization methods (MapNet) is worse than classic methods even in case of loop closures scenarios. This finding further supports the fundamental limitation of deep relocalization methods recently diagnosed. Finally, we provide a challenging loop closure dataset which enabled these findings. The dataset can be used to test future loop closing routines against challenging yet commonly occurring indoor navigation scenarios.

## ORB-SLAM missing Loop Closures in Kitti Dataset
https://user-images.githubusercontent.com/78947608/167349820-6ba8a2e5-8344-4eda-a35a-25ea215c943f.mp4

## ORB-SLAM missing Loop Closures in TUM-RGBD Dataset
https://user-images.githubusercontent.com/78947608/167350816-2f2a2f6b-8b6d-48ee-ad7b-f84564ec9689.mp4

## ORB-SLAM missing Loop Closures in NUST-CLC Dataset with Dynamic Change
https://user-images.githubusercontent.com/78947608/167351380-3980e9c3-a348-4051-ae09-87a276366b86.mp4

## ORB-SLAM missing Loop Closures in NUST-CLC Dataset with Viewpoint Change
https://user-images.githubusercontent.com/78947608/167351769-3df1596e-d365-4dee-b132-a935f07272c9.mp4


# NUST-CLC Dataset
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




