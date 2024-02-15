#FROM osrf/ros:humble-desktop
FROM ros:humble
#LABEL maintainer =""

RUN useradd --create-home --home-dir /home/ubuntu --shell /bin/bash --user-group --groups adm,sudo ubuntu && \
    echo ubuntu:ubuntu | chpasswd && \
    echo "ubuntu ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN apt update && \
    apt install -y --no-install-recommends python3-pip python3-apt && \
    apt install -y --no-install-recommends ros-humble-gazebo-ros-pkgs ros-humble-rviz2&& \
    apt install -y --no-install-recommends xvfb x11vnc x11-apps && \
    pip3 install -U setuptools colcon-common-extensions colcon-ros-bundle && \
    rm -rf /var/lib/apt/lists/*
RUN echo '/opt/ros/humble/lib/python3.8/site-packages' > /usr/local/lib/python3.8/dist-packages
RUN apt update && apt install -y curl
RUN curl http://repo.ros2.org/repos.key | sudo apt-key add -
RUN curl http://packages.osrfoundation.org/gazebo.key | sudo apt-key add -

ENV USER ubuntu
