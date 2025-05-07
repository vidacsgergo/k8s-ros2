# **Turtlesim, jazzy desktop + Teleop keyboard controller**

**Start the Turtlesim pod**  
> kubectl apply -f turtlesim-and-teleop.yaml

**Set up Guacamole connection**  
Name: turtle-teleop (or anything else)  
Location: ROOT  
Protocol: VNC  

Hostname: turtlesim-and-teleop.guacamole.svc.cluster.local  
Port: 5902  

Username:  
Password: 1234

**Open a terminal in the desktop environment and run the commands**  
> source /opt/ros/jazzy/setup.bash  

> ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/turtle1/cmd_vel
