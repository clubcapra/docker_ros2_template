FROM osrf/ros:humble-desktop


# update
RUN apt-get update -y

COPY ./dds.xml /root/dds.xml

# install cyclonedds
RUN apt install ros-humble-rmw-cyclonedds-cpp -y -qq

RUN apt install iputils-ping -y
RUN apt install iproute2 -y

ENV RMW_IMPLEMENTATION="rmw_cyclonedds_cpp"
ENV HOST_ADDR="192.168.0.64"

#ENV CYCLONEDDS_URI=/root/dds.xml


ENV CYCLONEDDS_URI="<CycloneDDS><Domain id='any'><General><ExternalNetworkAddress>${HOST_ADDR}</ExternalNetworkAddress><AllowMulticast>false</AllowMulticast></General><Discovery><ParticipantIndex>auto</ParticipantIndex><Ports><Base>7500</Base></Ports><Peers><Peer address='192.168.0.64:7410'/><Peer address='192.168.0.125:7410'/></Peers></Discovery><Tracing><Verbosity>config</Verbosity><Out>stderr</Out></Tracing></Domain></CycloneDDS>"


CMD ["ros2", "run", "demo_nodes_cpp", "talker"]
