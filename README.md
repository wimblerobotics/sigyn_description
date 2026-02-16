# sigyn_description

URDF description package for the Sigyn robot.

This package contains the complete URDF model for the Sigyn robot, including:
- Robot structure and kinematics
- Meshes and visual assets
- Gazebo simulation configuration
- ROS2 control interfaces

The launch file also launches the joint state publisher and robot state publisher so you can use rviz2 to
visualize the robot without needing other packages.

## Launch Parameters

- **use_sim_time** (default: `false`)  
  Use simulation (Gazebo) clock. See [Clock and Time](https://design.ros2.org/articles/clock_and_time.html)

- **do_rviz** (default: `true`)  
  Launch RViz2 for visualization

- **gui** (default: `false`)  
  Enable joint_state_publisher_gui for manual joint control

- **publish_joints** (default: `true`)  
  Launch joint_state_publisher

- **urdf_file_name** (default: `sigyn.urdf.xacro`)  
  URDF file to load from the urdf/ directory

- **on_a_mac** (default: `false`)  
  Set to `true` when running on Mac Silicon. This switches the lidar sensor from `gpu_lidar` (which requires GPU acceleration) to `ray` sensor type for compatibility with software OpenGL rendering.

## Usage Examples

Basic launch:
```bash
ros2 launch sigyn_description description.launch.py
```

Launch on Mac Silicon:
```bash
ros2 launch sigyn_description description.launch.py on_a_mac:=true
```

Launch with simulation time:
```bash
ros2 launch sigyn_description description.launch.py use_sim_time:=true
```

## Mac Silicon Compatibility

When running on Mac Silicon (Apple M1/M2/M3) in a Parallels VM with software OpenGL rendering, use the `on_a_mac:=true` parameter. This switches the lidar sensor type from GPU-accelerated `gpu_lidar` to the software-compatible `ray` sensor type, avoiding issues with GPU passthrough in the VM environment.
