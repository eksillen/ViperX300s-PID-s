# ViperX300s ROS1 Real Robot Launch Instructions


## Requirements

- Ubuntu **20.04**
- ROS1 **Noetic**
- Interbotix ROS Manipulators packages

## Installation (basic steps)

Make sure you have installed ROS Noetic and sourced the workspace properly.

```bash
# Setup ROS environment
source /opt/ros/noetic/setup.bash

# Navigate to your workspace (simulation)
cd ~/interbotix_ws_sim
# Or for the actual arm
cd ~/interbotix_ws_real

Dont forget to source the directory.

# Source your workspace
source devel/setup.bash


# If it is on the real arm use this launch command. Replace user with name you have on your linux machine. Also place the folder in the home directory.

roslaunch /home/user/interbotix_ws_real/src/interbotix_ros_manipulators/interbotix_ros_xsarms/interbotix_xsarm_ros_control/launch/xsarm_ros_control.launch robot_model:=vx300s use_sim:=false controller_config_file:=/home/user/interbotix_ws_real/src/interbotix_ros_manipulators/interbotix_ros_xsarms/interbotix_xsarm_descriptions/vx300s_controllers.yaml

# Else if it is in simulation

roslaunch interbotix_xsarm_gazebo xsarm_gazebo.launch robot_model:=vx300s use_sim_time:=true use_position_effort_controllers:=true



# Note that the PID script of the interbotix_ws_sim so you need to navigate to that directory and run 

python3 test0.py
