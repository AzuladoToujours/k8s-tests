# Daemonsets

Deployments que se ubican en cada uno de los nodos.

## Funciones:
Servicios de monitoreo, recolector de logs.

### Used Commands

```shell
# Aplicar nodeport
kubectl apply -f 1-hello-app-service-node-port.yaml
# Aplicar Deployment
kubectl apply -f 2-hello-app-deployment.yaml 
# Aplicar Daemon set
kubectl apply -f 3-fluentd-daemonset.yaml

```
## Loggly

Servicio de logs centralizados.

Account -> Account Overview -> API Tokens -> Customer Token -> Replace token


Video: 
https://www.youtube.com/watch?v=zKnJQ7A2pFM&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=10&ab_channel=PeladoNerd

