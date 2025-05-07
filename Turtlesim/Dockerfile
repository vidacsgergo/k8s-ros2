# turtlesim-vnc.Dockerfile
FROM osrf/ros:jazzy-desktop

RUN apt update && apt install -y \
    ros-jazzy-turtlesim \
    xfce4 xfce4-goodies x11vnc xvfb supervisor dbus-x11 xterm \
    && apt clean

RUN mkdir /root/.vnc && \
    x11vnc -storepasswd 1234 /root/.vnc/passwd

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 5901

CMD ["/usr/bin/supervisord"]
