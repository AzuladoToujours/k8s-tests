# Services and LoadBalancers

### Used Commands

```shell
#Create a new namespace
kubectl apply -f 00-namespace.yaml

#Set the context to the last namespace
kubectl config set-context --current --namespace=testing

#Create the service for wordpress
kubectl apply -f 01-word-press-svc.yaml

#Create the pod for wordpress
kubectl apply -f 02-wordpress-rc.yaml

#Configure service to be nodeport
kubectl apply -f 02-wordpress-node-port.yaml

#Delete the Nodeport service
kubectl delete svc  wordpress

#Create Load Balancer service
kubectl apply -f 03-wordpress-svc-lb.yaml

```

### Selector: 

La forma en que Kubernetes sabe dónde dirigir el tráfico, se define en los svc y apuntan al role definido
en los replication controllers o deployments.

Este laboratorio está dispuesto para realizarse en Digital Ocean, debido a que la plataforma nos provee un Load Balancer.

Video: 
https://www.youtube.com/watch?v=0iMEcrcfG5A&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=2&ab_channel=PeladoNerd




