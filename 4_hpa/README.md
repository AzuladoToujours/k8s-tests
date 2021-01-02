# HPA (Horizontal Pod Autoscaling) 

Se hacen reglas basados en CPU y Memoria y Kubernetes crece o disminuye basados en esas reglas.

### Used Commands

```shell
#Create nodeport service
kubectl apply -f 01-php-apache-service-nodeport.yaml

#Create deployment 
kubectl apply -f 02-php-apache-deployment.yaml 

#Add the metrics-server in kind
kubectl apply -f components.yaml

#Verify that the metrics-server is running
kubectl get deployment metrics-server -n kube-system

#Apply the HBA
kubectl apply -f 03-php-apache-hpa.yaml

#Send traffic
sh traffic.sh
```
### Recomendaciones:

Utilizar un nodo para ver el verdadero poder de HBA

Video: 
https://www.youtube.com/watch?v=T6wRsmrm_gk&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=5&ab_channel=PeladoNerd



