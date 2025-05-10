# **ROS 2 in Kubernetes with Guacamole**
### **Deploying the cluter (with kinD and Docker already installed)**
start Docker daemon  
>kind create cluster --config kind-config.yaml  

if port 8080 is already in use:  
> sudo lsof -i :8080  
> sudo kill PID

>(deleting the cluster is: kind delete cluster -n kind-guac-cluster)

**Applying the Weavenet CNI**   
>kubectl apply -f https://reweave.azurewebsites.net/k8s/v1.32/net.yaml

### **Deploying Guacamole (guacamole, guacd, db)**  
>kubectl apply -f guacamole-config.yaml  

**Port forward to be able to reach guacamole from localhost**  
>kubectl port-forward -n guacamole svc/guacamole 8080:8080

**Guacamole is now accessible at:**
http://localhost:8080/  
**Username:** guacadmin  
**Password:** guacadmin  
(if it is not working try using Google Chrome)

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

