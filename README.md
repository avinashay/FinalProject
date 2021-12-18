# EECE5550 Mobile Robotics

## LAB2

Problem2: 

Step1: Open 2 terminals and source devel/setup.bash in catkin_ws folder

Step2: On one of the terminals, start a empty gazebo simulation using the command : roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch

Step3: On the second terminal, publish the message : rostopic pub /cmd_vel geometry_msgs/Twist -r 10 '[0.2,0,0]' '[0,0,0.1333]'

Expected result: The turtlebot moves CCW in a circle with radius 1.5m and at linear velocity of 0.2m/s.

Problem3:

Step1: Open 3 terminals and source devel/setup.bash in catkin_ws folder

Step2: On the first terminal, start a gazebo simulation with apriltag using the command: roslaunch turtlebot3_mr apriltag_gazebo.launch

Step3: On the second terminal, start a gazebo visualizer using the command: roslaunch turtlebot3_mr turtlebot3_lab2.launch

Step4: On the third terminal, run the ros node using the command: rosrun mobile_robotics problem3.py

Expected Result: The turtlebot moves towards the apriltag and stops at a position 12cm in front of it.
