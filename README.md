# Nav2 for Unitree H1

ROS 2 Nav2 for Unitree H1 humanoid robot.

## Prerequisites

- ROS 2 Humble 
- Unitree H1 ROS drivers
- Nav2 packages

## Installation

```bash
# Clone repository 
git clone https://github.com/bobbylammy71446307/Unitree-H1-Isaac-Sim-Navigation.git h1_nav2_ws

# Create workspace
cd nav2_h1_ws

# Install dependencies
rosdep install -i --from-path src --rosdistro $ROS_DISTRO -y

# Build
colcon build
source /opt/ros/humble/setup.bash
source install/setup.bash

# Run H1 joint command policy
ros2 launch h1_fullbody_controller h1_fullbody_controller.launch.py

#Open another terminal and run nav2 bringups
source /opt/ros/humble/setup.bash
source install/setup.bash
ros2 launch my_slam humanoid.launch.py
