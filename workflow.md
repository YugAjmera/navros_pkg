# Work-Flow

### Initial configuration

1. Created a urdf file for a car having chassis, castor wheel,right and left wheel.

2. Added Differential Drive Gazebo Plugin for the car.

3. Added Launch files to view in RVIZ and spawn in Gazebo. ![](screenshot/Screenshot%20from%202019-02-09%2013-43-49.png)

4. Added Kinect sensor and added Gazebo Plugins for it. 

5. Alligned kinect_link to view the models in the plane. ![](screenshot/Screenshot%20from%202019-02-09%2015-50-47.png)

6. Added PublishWheelTF in the plugin to get tfs of all the links fixed and non-fixed ![](screenshot/Screenshot%20from%202019-02-10%2011-58-40.png)


### Mapping

7. **/kinect/depth/points** topic gives a 3D point cloud. It needs to be converted into 2D laser scan in order to use slam_gmapping node. For that we need to use pointcloud_to_laserscan node. Install it : `sudo apt install ros-kinetic-pointcloud-to-laserscan ros-kinetic-rosbridge-server`. 

8. Created a launch file "pctl.launch" to launch the node. It provides the topic **/kinect/scan**. ![](screenshot/Screenshot%20from%202019-02-10%2013-49-50.png)

9. Created a launch file "gmapping.launch" to launch the slam_gmapping node. It provides **/map** topic. 

10. Created a custom cafe environment in gazebo and saved in worlds folder. Changed its extension to .world and created a launch file "cafe_custom.launch" to launch the world.

11. Scaned the cafe environment and saved the map in "maps" folder with name "map1". ![](screenshot/Screenshot%20from%202019-02-11%2012-28-27.png)


### Localization

12. Created a launch file "amcl.launch" to launch the amcl node. It provides **/particlecloud** topic to view the probable position and orientation of the robot on PoseArray in RVIZ.  ![](screenshot/Screenshot%20from%202019-02-11%2012-56-32.png)

**Note** : Before launching amcl node slam_gmapping node has to be killed. Fixed Frame while mapping has to be odom. While estimating robot position, Fixed Frame has to be map.

13. RVIZ config files added in "rviz" folder.


### Path Planning

14. Created a launch file "move_base.launch" to launch the move_base node and perform path planning. All parameters are listed in the param folder. Set **2D Nav Goal** on RVIZ and the robot will start moving to the goal.  
