# README2


### Execute everything in different tabs :

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

7. To read the map (slam_gmapping): `roslaunch navros_pkg gmapping.launch`
   
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

11. To localise the robot (acml): `roslaunch navros_pkg amcl.launch map:='name_of_map'`

12. To perform path planning : `roslaunch navros_pkg move_base.launch `

13. To view position and orientation of robot in RVIZ : 
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d navigate
```
   * Set initial pose (2D pose estimate).
   * Move the car via teleop keyboard to get more precise localization of the robot.
   * Set goal for the robot in RVIZ (2D Nav goal)
   * Green line indicates the path planned.

