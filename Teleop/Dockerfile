FROM ros:jazzy-ros-base

RUN apt update && apt install -y ros-jazzy-teleop-twist-keyboard && apt clean

CMD ["bash", "-c", "source /opt/ros/jazzy/setup.bash && ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/turtle1/cmd_vel"]
