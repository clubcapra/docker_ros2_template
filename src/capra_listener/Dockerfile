FROM osrf/ros:humble-desktop

WORKDIR /ros2_ws

#RUN sed -i "$ d" /ros_entrypoint.sh
#RUN echo 'source "/ros2_ws/install/setup.bash"' >> /ros_entrypoint.sh
#RUN echo 'exec "$@"' >> /ros_entrypoint.sh

#RUN . /opt/ros/humble/setup.sh && colcon build --symlink-install --packages-select capra_listener

RUN colcon build
#RUN echo ". install/setup.bash" >> /opt/ros/humble/setup.bash

#RUN source install/setup.sh

COPY . /ros2_ws/src

RUN sed -i "$d" /ros_entrypoint.sh
RUN echo 'source "/ros2_ws/install/setup.bash"' >> /ros_entrypoint.sh
RUN echo 'exec "$@"' >> /ros_entrypoint.sh

ENTRYPOINT ["/ros_entrypoint.sh"]