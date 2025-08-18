# Ultimate Perception Workspace

This repository contains ultimate perception packages for autonomous systems, featuring:

- **Localization (MCL)**: Monte Carlo Localization for robust robot pose estimation
- **Object Detection with Map Cell Update**: Dynamic obstacle detection with real-time map updates

This repository uses submodules, so clone with recursive flag:

```bash
# Clone with submodules
git clone --recursive <repository-url>
cd ultimate_perception_ws

# If already cloned without submodules, initialize them:
git submodule update --init --recursive
```

## Update Repository

To pull latest changes including submodules:

```bash
# Pull main repository and all submodules
git pull --recurse-submodules
```

## Launch

The workspace contains ROS2 packages for perception tasks:

- **obstacle_detection_pkg**: Obstacle detection functionality
- **particle_filter_cpp**: Particle filter localization with separate modes

Build the workspace:

```bash
colcon build
source install/setup.bash
```

Launch obstacle detection:

```bash
ros2 launch obstacle_detection_pkg obstacle_detection.launch.py
```

Launch particle filter localization:

For simulation environment:
```bash
ros2 launch particle_filter_cpp localize_sim_launch.py
```

For real car with SLAM:
```bash
ros2 launch particle_filter_cpp localize_slam_launch.py
```