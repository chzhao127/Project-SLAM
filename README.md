# DHT-11 Module

1. The system begins by creating a map using two key frames from video data. It uses ORB  features to find correspondences between these frames.
The relative positions and orientations of the camera are estimated from these correspondences using triangulation.
2.As new frames are processed, the system estimates the camera's movement by matching new ORB features to the existing map. 
This continuous process adjusts the camera's trajectory based on the observed features.
3. When a frame is identified as a key frame (a frame with significant new information), it triggers an update to the map. New points are added, 
and a bundle adjustment is performed to optimize the map's accuracy by minimizing errors in the camera's predicted and observed positions.
4.The system periodically checks if the current frame revisits a previously mapped area. If it detects a loop,
it adjusts the map and camera trajectory to ensure consistency across the entire map.
5. Once a loop is closed, a global optimization process refines the entire map and trajectory to reduce long-term drift and improve overall accuracy.

##Results
