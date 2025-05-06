# Base image: ROS2 Jazzy + Desktop
FROM osrf/ros:jazzy-desktop


# Install XFCE + x11vnc + rqt
RUN apt update && apt install -y \
   xfce4 xfce4-goodies \
   x11vnc xvfb supervisor \
   dbus-x11 xterm sudo \
   ros-jazzy-rqt \
   ros-jazzy-rqt-common-plugins \
   && apt clean


# Setup VNC password
RUN mkdir /root/.vnc && \
   x11vnc -storepasswd 1234 /root/.vnc/passwd


# Copy supervisor config
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf


# Expose VNC port
EXPOSE 5900


# Start with Supervisor
CMD ["/usr/bin/supervisord"]
