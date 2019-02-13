# NavRos

## Autonomous Navigation for a Differential Drive Robot


### Getting Started

- `cd catkin_ws/src`
- `catkin_create_pkg navros_pkg rospy rviz controller_manager gazebo_ros joint_state_publisher robot_state_publisher urdf`
-  Clone this repo here and replace the files in **navros_pkg**
- `cd ..` (Go back to catkin_ws/)
- `catkin_make`
- `source ./devel/setup.bash`

If catkin_make fails :
```
sudo apt-get install ros-kinetic-controller-manager
```

### Gazebo Simulation

(Skip this while working with real robot)

Change the [urdf file](https://github.com/YugAjmera/navros_pkg/blob/master/urdf/car.urdf.xacro) as per the dimensions of your robot.

On a new terminal :

To launch the urdf model in Gazebo in a custom cafe environment :
```
roslaunch navros_pkg cafe_custom.launch
```
To launch the model in empty world in Gazebo :
```
roslaunch gazebo_ros empty_world.launch
roslaunch navros_pkg urdf_gazebo_view.launch
```
Keep this terminal running for all the next steps.


### Laser sensor
On a new terminal :

Run RVIZ :
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d laser.rviz
```
Check if the laser readings are seen in RVIZ.
After the laser readings are visible,close this terminal.


### Mapping
On a new terminal :

Run SLAM :
```
roslaunch navros_pkg gmapping.launch
```

Run RVIZ :
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d map.rviz
```

Run teleop_twist_keyboard :
```
rosrun teleop_twist_keyboard teleop_twist_keyboard.py 
```

Drive the robot around the environment you want to map.

Once mapping is complete,
Save the map:
```
 rosrun map_server map_saver ~/catkin_ws/src/navros_pkg/maps/name_of_map
 ```

Now,close this terminal.


### Autonomous Navigation
Run amcl.launch :

Replace `name_of_map` with the map name you saved in the previous step.
```
roslaunch navros_pkg amcl.launch map:='name_of_map'
```

Run move_base.launch :
```
roslaunch navros_pkg move_base.launch 
```

Run RVIZ :
```
cd catkin_ws/src/navros_pkg/rviz 
rviz -d navigate.rviz
```

* Set initial pose (Click "2D pose estimate" and pinpoint the approximate location of robot on map).
* Set goal for the robot in RVIZ (Click "2D Nav goal" and pinpoint the desired goal on the map).
* Green line indicates the path planned.

View [work-flow here](https://github.com/YugAjmera/navros_pkg/blob/master/workflow.md) 
