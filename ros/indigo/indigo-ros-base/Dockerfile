# This is a Dockerfile for ros:indigo-ros-core

FROM ubuntu:14.04
MAINTAINER Fabian Prinzing <scheik.todeswache@googlemail.com>

# setup environment
RUN locale-gen de_DE.UTF-8
ENV LANG de_DE.UTF-8

# setup keys
RUN apt-key adv --keyserver ha.pool.sks-keyservers.net --recv-keys 421C365BD9FF1F717815A3895523BAEEB01FA116

# setup sources.list
RUN echo "deb http://packages.ros.org/ros/ubuntu trusty main" > /etc/apt/sources.list.d/ros-latest.list

# install bootstrap tools
ENV ROS_DISTRO indigo
RUN apt-get update && apt-get install --no-install-recommends -y \
    python-rosdep \
    python-rosinstall \
    python-vcstools \
    && rm -rf /var/lib/apt/lists/*

# bootstrap rosdep
RUN rosdep init \
    && rosdep update

# install ros packages
RUN apt-get update && apt-get install -y \
    ros-indigo-ros-base=1.1.4-0* \
    git \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

RUN echo "source opt/ros/indigo/setup.bash" >> /etc/bash.bashrc

CMD ["bash"]
