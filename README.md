# swarm-gazebo-simulations
testing of swarm algorithms in gazebo simulation
**All the credit for original package, simulations and controller goes to https://github.com/yangliu28 .


## Demo
spwarn urdf of two wheel robot

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`roslaunch swarm_robot_gazebo swarm_robot.launch `

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `rosrun gazebo_ros spawn_model -file `rospack find swarm_robot_description`/urdf/two_wheel_robot.urdf -urdf -x 1 -y 1 -z 1 -model two_wheel_robot'

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`rosservice call gazebo/delete_model '{model_name: two_wheel_robot}' `

