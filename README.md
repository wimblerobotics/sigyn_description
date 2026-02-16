# sigyn_description

URDF description package for the Sigyn robot.

This package contains the complete URDF model for the Sigyn robot, including:
- Robot structure and kinematics
- Meshes and visual assets
- Gazebo simulation configuration
- ROS2 control interfaces

The launch file also launches the joint state publisher and robot state publisher so you can use rviz2 to
visualize the robot without needing other packages.

Launch parameters:

- use_sim_time
    
    See [Clock and Time](https://design.ros2.org/articles/clock_and_time.html)

Example:

    ros2 launch sigyn_description description.launch.py
