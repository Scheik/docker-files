##ROS Indigo ros-base on Ubuntu trusty

This docker container has a ros-base installation on a clean Ubuntu 14.04 installation.

It can be used as a base to construct ROS Indigo containers.

###To build the image:

- cd ~

- git clone https://github.com/scheik/docker-files

- cd ~/docker-files/ros/indigo/indigo-ros-base

- docker build -t ros-indigo-base .

###To run the container

- docker run -i -t ros-indigo-base
