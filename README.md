# NavRos

- `cd catkin_ws/src`
- `catkin_create_pkg navros_pkg rospy rviz controller_manager gazebo_ros joint_state_publisher robot_state_publisher urdf`
-  Clone this repo here and replace the files in **navros_pkg**
- `cd ..` (Go back to catkin_ws/)
- `catkin_make`
- `source ./devel/setup.bash`
[ View full documentation here ](https://github.com/YugAjmera/navros_pkg/blob/master/Documentation.md) 

Execute everything in different tabs :

1. To view the model in Gazebo: `roslaunch navros_pkg urdf_gazebo_view.launch `

2. To control the car with keyboard : `rosrun teleop_twist_keyboard teleop_twist_keyboard.py `

3. To view the model in RVIZ (using joint_state_publisher gui): `roslaunch navros_pkg urdf_rviz_view.launch`
 (Add PointCloud2 and Camera in RVIZ to view Kinect readings)

4. To get laser scan readings : `roslaunch navros_pkg pctl.launch`

5. To read the map : `roslaunch navros_pkg kinect_gmapping.launch`
Add Map to RVIZ to view the map being built.


