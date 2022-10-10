FROM osrf/ros:humble-desktop

RUN mkdir -p /home/sim

ENV ROS2_WS /home/sim

RUN apt-get update
RUN apt-get install ros-humble-gazebo-ros-pkgs -y 
RUN apt install ros-humble-ros-core ros-humble-geometry2


RUN mkdir -p ${ROS2_WS}

WORKDIR ${ROS2_WS}

# Source the setup.bash file to allow you tu use ros2 commands
RUN echo "source /opt/ros/$ROS_DISTRO/setup.bash" >> /root/.bashrc

ENTRYPOINT ["/ros_entrypoint.sh"]
CMD ["bash"]

