# sigyn_description

The URDF for the Sigyn robot, and related files for use with Sigyn2.

This package contains:
- Robot URDF/xacro files
- Mesh files for robot visualization
- Launch files for robot state publisher and visualization
- Gazebo world files for simulation
- Materials and textures

The launch file will also launch the joint state publisher and robot state publisher so you can use rviz2 to
visualize the robot without needing other packages.

Launch parameters:

- use_sim_time
    
    See [Clock and Time](https://design.ros2.org/articles/clock_and_time.html)

Example:

    ros2 launch sigyn_description description.launch.py
