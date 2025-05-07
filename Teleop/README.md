# **Teleop keyboard controller**

**Start the Teleop deployment**  
> kubectl apply -f teleop.yaml

**Exec into the pod and start the teleop controller**  
> kubectl exec -it -n guacamole TELEOP-POD-NAME -- bash

> source /opt/ros/jazzy/setup.bash  

> ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/turtle1/cmd_vel
