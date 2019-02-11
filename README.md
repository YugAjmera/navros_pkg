# NavRos

- `cd catkin_ws/src`
- `catkin_create_pkg navros_pkg rospy rviz controller_manager gazebo_ros joint_state_publisher robot_state_publisher urdf`
-  Clone this repo here and replace the files in **navros_pkg**
- `cd ..` (Go back to catkin_ws/)
- `catkin_make`
- `source ./devel/setup.bash`


View [full documentation here ](https://github.com/YugAjmera/navros_pkg/blob/master/Documentation.md) 


Execute everything in different tabs :

1. To view the model in Gazebo: `roslaunch navros_pkg urdf_gazebo_view.launch `. Before this launch any of this :
   
   - To launch a custom cafe environment : 
    `roslaunch navros_pkg cafe_custom.launch`

   - To launch empty world :
    `roslaunch gazebo_ros empty_world.launch`

2. To control the car with keyboard : `rosrun teleop_twist_keyboard teleop_twist_keyboard.py `.

3. To view the model in RVIZ (using joint_state_publisher gui): `roslaunch navros_pkg urdf_rviz_view.launch`.
   * Add PointCloud2 and Camera in RVIZ to view Kinect readings
   * Fixed Frame as odom

4. To get laser scan readings : `roslaunch navros_pkg pctl.launch`.
   * Add LaserScan in RVIZ to view Laser readings

5. To read the map : `roslaunch navros_pkg gmapping.launch`.
   * Add Map in RVIZ to view the map being built. Move the car around an environment to scan it.

6. To save the map built :
 ` cd catkin_ws/src/navros_pkg/maps`
 `rosrun map_server map_saver -f name_of_map`

7. Shutdown the slam_gmapping node. (Number 5)(Press ctrl+c)

8. To view the probable position and orientation of robot : `roslaunch navros_pkg amcl.launch map:='name_of_map'`.
   * Fixed Frame as map
   * Add PoseArray in RVIZ to view the arrows.
   * 2D point estimate may be added to get faster results.
   * Move the car via teleop keyboard to get more precise localization of the robot.




