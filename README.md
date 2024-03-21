To use this repository, clone the repository to the 'src' directory of your workspace.
In your workspace directory, type:
colcon build --packages-select vander_bot --symlink-install
to build this specific package.
After building the package, type the following command in your terminal while being in the workspace directory:
ros2 launch vander_bot launch_sim.launch.py world:=./src/vander_bot/worlds/first.world
This will launch the gazebo world.
To visualize in rviz, open a separate terminal and type *rviz2*.
To control the bot, type this in a new terminal:
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_cont/cmd_vel_unstamped
Change the odometry topic to "/odometry/filtered" to visualize the filtered odometry in rviz. 
To tune the ekf node, you can edit the ekf.yaml file in the config directory of the package.
To read the messages being published to "/odometry/filtered", type the following command:
ros2 topic echo /odometry/filtered
