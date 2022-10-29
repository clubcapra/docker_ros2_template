FROM osrf/ros:humble-desktop

ENV ROS2_WS /home/ros2_ws

RUN mkdir -p ${ROS2_WS}

WORKDIR ${ROS2_WS}

RUN apt update
RUN apt install ros-humble-navigation2 -y
RUN apt install ros-humble-nav2-bringup -y
RUN apt install ros-humble-turtlebot3* -y

# Source the setup.bash file to allow you tu use ros2 commands
RUN echo "source /opt/ros/$ROS_DISTRO/setup.bash" >> /root/.bashrc

# Set env variables TUTLEBOT3_MODEL to waffle
ENV TURTLEBOT3_MODEL waffle
ENV GAZEBO_MODEL_PATH $GAZEBO_MODEL_PATH:/opt/ros/humble/share/turtlebot3_gazebo/models

CMD ["bash"]