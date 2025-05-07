# turtlesim-vnc.Dockerfile
FROM osrf/ros:jazzy-desktop

# Telepítés a szükséges csomagokhoz (turtlesim és teleop)
RUN apt update && apt install -y \
    ros-jazzy-turtlesim \
    ros-jazzy-teleop-twist-keyboard \
    xfce4 xfce4-goodies x11vnc xvfb supervisor dbus-x11 xterm \
    && apt clean

# VNC jelszó beállítása
RUN mkdir /root/.vnc && \
    x11vnc -storepasswd 1234 /root/.vnc/passwd

# Supervisord beállítások
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 5902

# Supervisord elindítása, hogy kezelje a folyamatokat
CMD ["/usr/bin/supervisord"]