# sam_bot motion with nav2
This is a simulation of a differential drive robot capable of navigating it's way through obstacles in a virtual world. It uses ROS Navigation stack [Nav2](https://navigation.ros.org/) to receive goal position in [rviz](http://wiki.ros.org/rviz) and find it's way to that place in the [Gazebo Simulator](https://gazebosim.org/home). This project uses the "Kitchen Dining" world provided by osrf. I've included the dockerfile if someone wants to run it on [docker](https://docs.docker.com/engine/install/ubuntu/) since ROS installation is cumbersome.

Make sure `~/.gazebo/models` contains all the models provided [here](https://github.com/osrf/gazebo_models). All the dependencies required for it are installed by the DOCKERFILE.

Add the `sam_bot_nav2` package inside the src folder of your workspace.

To start the simulation in rviz and gazebo, build the package using:

	cd ~/<your-workspace-where-sam_bot_nav2-is-located>
	colcon build
	. install/setup.bash

Then, Run the following command

	ros2 launch sam_bot_nav2 new_world2.launch.py

The following screen with Gazebo and Rviz should pop up.
![First Step](https://i.imgur.com/qzwgupD.png)


We first need to specify the robot's initial position. To do that click on "2D Pose Estimate" on Rviz top bar and then click, hold and release on the (0, 0) position with the orientation as you can see in gazebo.

![Second step](https://i.imgur.com/3ZFGNIY.png)


A bird-eye view of the model should appear in Rviz. Since the model is same color as the Rviz background, it appear transparent but the transforms are clearly visible.

![Third Step](https://i.imgur.com/LtKrd8v.png)


We are done! Click "Navigation2 Goal" on the top bar and provide any goal position on the map and watch it go!

![Final 1](https://i.imgur.com/2phHK0Y.png)


![Final 2](https://i.imgur.com/GM7Ocio.png)
