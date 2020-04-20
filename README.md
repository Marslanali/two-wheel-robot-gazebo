# two-wheel-robot-gazebo

two wheel differential drive robot simulation in gazebo

### Brief Explanation

* **two_wheel_robot_description** specifies the entire robot structure as links and joints and can launch the model.
* **two_wheel_robot_gazebo** launches the model in the gazebo environment and contains different simulation worlds.

## Install gazebo-ros control
```
sudo apt-get install ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-ros-control
```

### complining the package
In new terminal
```
mkdir -p ~/catkin_ws/src

cd catkin_ws/src

git clone https://github.com/Marslanali/two-wheel-robot-gazebo.git

catkin_make
```

### Run the Models
Load the Gazebo simulator using the following command:
```
roslaunch two_wheel_robot_gazebo two_wheel_robot.launch
```

#### moving in a circle:
In a new terminal use the following command to make the robot drive incessantly along a circle of user-defined diameter.
(Here diameter = 4 m. So, radius = 2m. Thus linear and angular velocities are set accordingly)
```
rostopic pub /cmd_vel geometry_msgs/Twist "linear:
  x: 0.2
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 0.1"
```

#### Running keyboard teleop:
The ~/catkin_ws/src/turtlebot3_teleop/nodes folder contains the *turtlebot3_teleop_key* node, which is the teleop node.

Start the teleop node:
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

## Spwan single URDF robot without launch file
spwarn urdf of two wheel robot
```
roslaunch two_wheel_robot_gazebo two_wheel_robot_urdf_spwan.launch


rosrun gazebo_ros spawn_model -file `rospack find two_wheel_robot_description`/urdf/two_wheel_robot.urdf -urdf -x 1 -y 1 -z 1 -model two_wheel_robot

rosservice call gazebo/delete_model '{model_name: two_wheel_robot}'
```

## Launching turtlebot play ground gazebo
```
roslaunch two_wheel_robot_gazebo rosbot_world.launch
```

## Contribution

## License
See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).

