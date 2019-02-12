# NavRos

### Autonomous Navigation for a Differential Drive Robot

- `cd catkin_ws/src`
- `catkin_create_pkg navros_pkg rospy rviz controller_manager gazebo_ros joint_state_publisher robot_state_publisher urdf`
-  Clone this repo here and replace the files in **navros_pkg**
- `cd ..` (Go back to catkin_ws/)
- `catkin_make`
- `source ./devel/setup.bash`


View [full documentation here ](https://github.com/YugAjmera/navros_pkg/blob/master/Documentation.md) 


Execute everything in different tabs :
* Change the [urdf file](https://github.com/YugAjmera/navros_pkg/blob/master/urdf/car.urdf.xacro) as per the dimensions of your robot.

1. To view the model in Gazebo: `roslaunch navros_pkg urdf_gazebo_view.launch `. Before this launch any of this or your custom environment:
   
   - To launch a custom cafe environment : 
    `roslaunch navros_pkg cafe_custom.launch`

   - To launch empty world :
    `roslaunch gazebo_ros empty_world.launch`

2. To control the car with keyboard : `rosrun teleop_twist_keyboard teleop_twist_keyboard.py `

3. To view the model in RVIZ (using joint_state_publisher gui): `roslaunch navros_pkg urdf_rviz_view.launch`
   
4. To view kinect sensor readings in RVIZ : 
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d kinect.rviz
```

5. To get laser scan readings : `roslaunch navros_pkg pctl.launch`

6. To view laser scan readings in RVIZ :
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d laser.rviz
```

7. To read the map : `roslaunch navros_pkg gmapping.launch`
   
8. To view the map being built in RVIZ ( Move the car around an environment to scan it) :
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d map.rviz
```

9. To save the map built :
 ```
 cd catkin_ws/src/navros_pkg/maps
 rosrun map_server map_saver -f name_of_map
 ```

10. Shutdown the slam_gmapping node. (Number 7)(Press ctrl+c)

11. To localise of robot : `roslaunch navros_pkg amcl.launch map:='name_of_map'`

12. To view position and orientation of robot in RVIZ : 
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d navigate
```
   * Set initial pose (2D point estimate).
   * Move the car via teleop keyboard to get more precise localization of the robot.




