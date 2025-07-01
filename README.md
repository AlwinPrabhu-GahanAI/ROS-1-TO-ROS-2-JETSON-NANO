# ROS 2 Foxy SLAM + Navigation2 Package

This repository contains a minimal example to run SLAM and Nav2 using `slam_toolbox` and `nav2_bringup` in ROS 2 Foxy.

## 🧱 Structure

- `launch/nav2_slam_launch.py` — Launches `slam_toolbox` and Nav2 stack.
- `config/nav2_params.yaml` — Sample configuration for Nav2 nodes.

## ✅ Requirements

- ROS 2 Foxy (Ubuntu 20.04)
- `ros-foxy-slam-toolbox`
- `ros-foxy-navigation2`
- `ros-foxy-nav2-bringup`

## 🚀 Usage

From inside your ROS 2 workspace:

```bash
source /opt/ros/foxy/setup.bash
ros2 launch your_package_name nav2_slam_launch.py
```

If using a pre-saved map instead of SLAM:

```bash
ros2 launch nav2_bringup bringup_launch.py   map:=/path/to/map.yaml   use_sim_time:=false   slam:=false
```

## 📍 Send a Goal

```bash
ros2 action send_goal /navigate_to_pose nav2_msgs/action/NavigateToPose   "{pose: {header: {frame_id: 'map'}, pose: {position: {x: 1.0, y: 0.5, z: 0.0}, orientation: {w: 1.0}}}}"
```

---
Happy mapping and navigating!
