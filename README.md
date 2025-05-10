# **ROS 2 in Kubernetes with Guacamole**
### **Deploying the cluter (with kinD and Docker already installed, Ubuntu, amd64)**
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

**Turtlesim and Teleop keyboard controller on different k8s nodes:**  
Follow the instructions in the Turtlesim and Teleop folders to deploy the needed service and deployments. You can access the GUI with guacamole and use the keyboard controller from the teleop pod.

