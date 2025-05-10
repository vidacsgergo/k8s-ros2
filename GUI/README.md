# **ROS 2 rqt pod, desktop GUI accessible with guacamole**

**Start the ROS 2 pod**  
> kubectl apply -f ros2-gui.yaml

**Set up Guacamole connection**  
Name: ros2-rqt-demo  
Location: ROOT  
Protocol: VNC  

Hostname: ros2-rqt.guacamole.svc.cluster.local  
Port: 5900  

Username:  
Password: 1234