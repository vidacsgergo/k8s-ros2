# **Turtlesim, jazzy desktop**

**Start the Turtlesim pod**  
> kubectl apply -f turtlesim.yaml

**Set up Guacamole connection**  
Name: turtlesim (or anything else) 
Location: ROOT  
Protocol: VNC  

Hostname: turtlesim.guacamole.svc.cluster.local  
Port: 5901  

Username:  
Password: 1234

**Start the teleop deployment**  
Start the teleop keyboard controller at ./Teleop to controll the turtle.
