# EECE5550 Mobile Robotics

## Final Project Submission

### Commands On Raspi :
ssh ubuntu@192.168.1.106
turtlebot

cd ~/catkin_ws
source devel/setup.bash
roscore

cd ~/catkin_ws
source devel/setup.bash
roslaunch turtlebot3_bringup turtlebot3_robot.launch

cd ~/catkin_ws
source devel/setup.bash
roslaunch raspicam_node camerav2_1280x960_10fps.launch enable_raw:=true

cd ~/catkin_ws
source devel/setup.bash
rosrun tf static_transform_publisher 0.03 0 0.1 -1.57 0 -1.57 base_link camera 100

cd ~/catkin_ws
source devel/setup.bash
roslaunch turtlebot3_mr apriltag_gazebo.launch

### Commands on Local:

cd ~/catkin_ws

source devel/setup.bash
roscore

source devel/setup.bash
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_navigation move_base.launch 

source devel/setup.bash
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

source devel/setup.bash
roslaunch explore_lite explore_test.launch

Check camera feed:
rqt_image_view --force-discover

Transfer yaml from local to remote:
scp <file name> ubuntu@172.20.10.4:/home/ubuntu/.ros/camera_info

Launch calibrator on local:
python3 /opt/ros/noetic/lib/camera_calibration/cameracalibrator.py --size 7x6 --square 0.0254 image:=/raspicam_node/image camera:=/raspicam_node

