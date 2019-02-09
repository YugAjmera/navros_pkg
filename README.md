# NavRos

- `cd catkin_ws/src`
- `catkin_create_pkg navros_pkg rospy rviz controller_manager gazebo_ros joint_state_publisher robot_state_publisher urdf`
-  Clone this repo here and replace the files in **navros_pkg**
- `cd ..` (Go back to catkin_ws/)
- `catkin_make`
- `source ./devel/setup.bash`

1. To view the model in RVIZ (using joint_state_publisher gui): `roslaunch navros_pkg urdf_rviz_view.launch`

2. To view the model in Gazebo: `roslaunch navros_pkg urdf_gazebo_view.launch `

3. To control the car with keyboard (with 2 running): `rosrun teleop_twist_keyboard teleop_twist_keyboard.py `

### (Add PointCloud2 and Camera in RVIZ to view Kinect readings)

![](Screenshot%20from%202019-02-09%2013-43-49.png)
