# Requests and Limits in Pods 

Using only one worker node.

### Used Commands

```shell
#Create nodeport service
kubectl apply -f 01-hello-nodeport.yml

#Create deployment 
kubectl apply -f 02-hello-app-deployment.yaml

#Enter to pod
kubectl exec -it [POD-NAME] sh

#Inside the pod retrieve the proccess running
ps fax

#Inside the pod see the env
env | grep MYSQL

#See resources
kubectl describe node [NODE-NAME]

#Scale deployment

kubectl scale --replicas=10 deployment hello

```
### Milicores: 

1000Milicores -> 1CPU
Sí tenemos una máquina virtual que tiene 4 cores, tenemos disponible 4000 milicores.
Se le asigna al contenedor 200Milicores, es decir, el 20% de un core.

### Requests:

El CPU y la Memoria que le garantizamos a ese contenedor, es decir, sí tenemos 1000 Milicores en la máquina y le garantizamos 200 milicores de request al contenedor, Kubernetes sólo podrá meter 5 pods en la máquina.

### Limits:

El techo de lo que puede llegar a utilizar el contenedor, puede ser memoria o CPU. Se podría no colocar límite, eso hará que el contenedor utilice todo lo que tenga disponible para usar.

Video: 
https://www.youtube.com/watch?v=xTTJg1aJ4kg&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=4&ab_channel=PeladoNerd




