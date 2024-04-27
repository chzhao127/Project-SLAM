#  Visual SLAM
## &bull; Step 1 of summary
1. The system begins by creating a map using two key frames from video data. It uses ORB  features to find correspondences between these frames.
The relative positions and orientations of the camera are estimated from these correspondences using triangulation.
2.As new frames are processed, the system estimates the camera's movement by matching new ORB features to the existing map. 
This continuous process adjusts the camera's trajectory based on the observed features.
3. When a frame is identified as a key frame (a frame with significant new information), it triggers an update to the map. New points are added, 
and a bundle adjustment is performed to optimize the map's accuracy by minimizing errors in the camera's predicted and observed positions.
4.The system periodically checks if the current frame revisits a previously mapped area. If it detects a loop,
it adjusts the map and camera trajectory to ensure consistency across the entire map.
5. Once a loop is closed, a global optimization process refines the entire map and trajectory to reduce long-term drift and improve overall accuracy.

## &bull; Step 1 of Results
![Figure1(1)](https://github.com/chzhao127/Project-SLAM/assets/161893598/34409bb3-5e88-4c82-970c-5eea0ed06723)

![Figure2(1)](https://github.com/chzhao127/Project-SLAM/assets/161893598/e213c0a4-cc66-49ac-a0ac-2398a1fd28ef)

![Figure3(1)](https://github.com/chzhao127/Project-SLAM/assets/161893598/19198a99-44a3-417a-9be2-b64372281470)

## &bull; Step 1 of Discussion
To build a visual-SLAM application, I would start with choosing a good feature detection method like ORB because it is fast and accurate.
This step is important for recognizing and matching features between different pictures, which is necessary for creating a map and finding the location.
First, I would set up the system by using two pictures to start the map. This involves finding matching features between these two pictures and using them to estimate their 3D positions. This initial step is very important because it sets the foundation for the rest of the system.
Then, as the camera takes more pictures, I would use a tracking process to estimate where the camera is by matching new pictures with the map that is already made. This step updates the camera's position each time a new picture is taken.
When there are enough changes in the scene, or after a certain number of pictures, I would add new key points to the map. This helps to keep adding details to the map and makes it more accurate.
Another important part is loop closure, which helps correct errors in the map. This happens when the camera sees a part of the scene it has seen before. To do this, I would need a way to recognize these places, probably by keeping a database of features.
Lastly, I would put all these parts together in a system, probably using software that can handle real-time data, like MATLAB or Python with OpenCV. It would also be important to test the system in different places to make sure it works well and make adjustments based on what I find.
By following these steps and improving based on testing, I hope to make a visual-SLAM system that works well and is reliable, based on the project example.
