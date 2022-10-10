FROM osrf/ros:humble-desktop

ENV ROS2_WS /home/ros2_ws

RUN mkdir -p ${ROS2_WS}

WORKDIR ${ROS2_WS}

COPY . ${ROS2_WS}/src/capra_listener

# Build the package using colcon. Change for the name of your package
RUN colcon build --symlink-install --packages-select capra_listener

# Source the setup.bash file to allow you tu use ros2 commands
RUN echo "source install/setup.bash" >> /opt/ros/$ROS_DISTRO/setup.bash
RUN echo "source /opt/ros/$ROS_DISTRO/setup.bash" >> /root/.bashrc

CMD ["bash"]