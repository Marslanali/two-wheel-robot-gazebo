# swarm-gazebo-simulations
testing of swarm algorithms in gazebo simulation
**All the credit for original package, simulations and controller goes to https://github.com/yangliu28 .

### package dependencies
* rospy
* roscpp
* geometry_msgs

### Brief Explanation

* **swar_robot_description** specifies the entire robot structure as links and joints and can launch the model in rviz.
* **swarm_robot_gazebo** launches the model in the gazebo environment and contains different simulation worlds.


## Install gazebo-ros control

`sudo apt-get install ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-ros-control`



### complining the package
In new terminal 
`mkdir -p ~/catkin_ws/src`
`cd catkin_ws/src`
`git clone https://github.com/Marslanali/swarm-gazebo-simulations.git`
`catkin_make`


### Run the Models
Load the Gazebo simulator and rviz in separate terminals using the following commands:

`roslaunch swarm_robot_gazebo two_wheel_robot.launch`

`roslaunch swarm_robot_description swarm_robot_rviz.launch `


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


## Spwan single URDF robot without launch file
spwarn urdf of two wheel robot

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`roslaunch swarm_robot_gazebo swarm_robot.launch `


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`rosrun gazebo_ros spawn_model -file `rospack find swarm_robot_description`/urdf/two_wheel_robot.urdf -urdf -x 1 -y 1 -z 1 -model two_wheel_robot`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`rosservice call gazebo/delete_model '{model_name: two_wheel_robot}' `

