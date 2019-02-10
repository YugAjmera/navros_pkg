# Documentation

1. Created a urdf file for a car having chassis, castor wheel,right and left wheel.

2. Added Differential Drive Gazebo Plugin for the car.

3. Added Launch files to view in RVIZ and spawn in Gazebo. (Reference : Screenshot from 2019-02-09 13-43-49.png )

4. Added Kinect sensor and added Gazebo Plugins for it. 

5. Alligned kinect_link to view the models in the plane. (Reference : Screenshot from 2019-02-09 15-50-47.png )

6. Added PublishWheelTF in the plugin to get tfs of all the links fixed and non-fixed (Reference : Screenshot from 2019-02-10 11-58-40.png )

7. **/kinect/depth/points** topic gives a 3D point cloud. It needs to be converted into 2D laser scan in order to use slam_gmapping node. For that we need to you pointcloud_to_laserscan node. Install it : `sudo apt install ros-kinetic-pointcloud-to-laserscan ros-kinetic-rosbridge-server`. 

8. Created a launch file "pctl.launch" to launch the node. It provides the topic **/kinect/scan**.  ( Reference : Screenshot from 2019-02-10 13-49-50.png )

9. Created a launch file "kinect_gmapping.launch" to launch the slam_gmapping node. It provides **/map** topic. 


