

Before these files can be used, the system should have [Docker](https://docs.docker.com/engine/install/ubuntu/) and [NVIDIA Container Toolkit](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/k8s/containers/container-toolkit) (that is, if you have an NVIDIA GPU) installed. After that is done, we need to save these files inside some folder and run the following commands inside the folder to create an image and create and run a container using this image:

    docker build -t osrf/ros2:foxy-desktop-nvidia .
    bash run.bash

To test whether everything is installed correctly, create another container using the command:
bash run.bash

and run a talker in one of the containers and a listener in the other container using these commands:

    ros2 run demo_nodes_cpp talker
    ros2 run demo_nodes_py listener

Also, check if RViz can run by running the following command inside one of the containers created:
ros2 run rviz2 rviz2

Note: The first two commands should run without sudo.
