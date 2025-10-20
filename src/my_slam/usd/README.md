# Nav2 for Unitree H1

ROS 2 Nav2 for Unitree H1 humanoid robot.

## Prerequisites

- ROS 2 Humble 
- Unitree H1 ROS drivers
- Nav2 packages

## Prerequisitions to run the USD file in Isaac Sim

1. Go to the usd directory and update the config file
```bash

cd ~/Unitree-H1-Isaac-Sim-Navigation/src/my_slam/usd
nano config.yaml
```
2. Change directories in config file
    -command_file: /(path_to_current_usd_directory)/command.txt
    -output_dir: ~/ReplicatorResult
    -command_file: /(path_to_current_usd_directory)/robot_command.txt
    -asset_path: /(path_to_current_usd_directory)/h1_ros.usd

3. Open USD file in Isaac Sim & enable extensions
    Window -> Extensions -> search for "agent" and "navigation" respectively
    enable "ACTOR SDG", "ACTOR SDG UI", "NAVIGATION BUNDLE (BETA)", "NAVIGATION CORE (BETA)", "NAVIGATION UI (BETA)"

4. bake NavMesh
    locate and click on NavMesh prim
    click on edit NavMesh on property tab
    enable auto-bake
    the floor should turn blue after enabling

5. Open Command Injection tab (If character does not move on play)
    Tools -> Actions and Event Data Generation -> Command Injection
```bash
Character GoTo 5 -5 0.0 _
Character_01 GoTo 5 5 0.0 _
```
    press injection after play to get the character move
