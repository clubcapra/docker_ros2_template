FROM osrf/ros:humble-desktop


RUN mkdir -p /ros2_ws/src/capra_talker

COPY . /ros2_ws/src

WORKDIR /ros2_ws

#RUN /opt/ros/humble/setup.sh 
RUN colcon build

#RUN source install/setup.sh

RUN sed -i "$d" /ros_entrypoint.sh
RUN echo 'source "/ros2_ws/install/setup.bash"' >> /ros_entrypoint.sh
RUN echo 'exec "$@"' >> /ros_entrypoint.sh

#RUN source /ros2_ws/src/install/setup.sh

ENTRYPOINT ["/ros_entrypoint.sh"]