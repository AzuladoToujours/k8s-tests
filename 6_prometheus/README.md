# PROMETHEUS 

Servicio de monitoreo

### Used Commands

```shell
# Create namespace
kubectl apply -f 0-namespace.yaml
# Create prometheus cluster-role
kubectl apply -f 1-cluster-role.yaml
# Apply the configmap that prometheus can access
kubectl apply -f 2-prometheus-configmap.yaml
# Deploy prometheus pod
kubectl apply -f 3-prometheus-deployment.yaml
# Export prometheus with NodeService
kubectl apply -f 4-prometheus-service.yaml 
# Create the service for the alert manager
kubectl apply -f 5-alert-manager-service.yaml
# Create alert manager deployment
kubectl apply -f 6-alert-manager-deployment.yaml
# Persistent Volume Claim
kubectl -n monitoring apply -f 7-prometheus-alertmanager-pvc.yaml 
# Apply the alert's configmap to the third party apps (slack) 
kubectl -n monitoring apply -f 8-prometheus-alert-configmap.yaml 


```

## Configmaps

Son unos manifiestos que se le tiran al namespace, y cualquier contenedor que esté corriendo en ese namespace puede leer esos configmaps y puede generar su configuración dependiendo de esos configmaps.

## Alert Manager

Se encarga de manejar las alertas, Prometheus le manda las alertas y el Alert Manager se encarga de distribuirlas a los servicios que se tengan configurados con el alert manager(Canal slack, etc)

## WebHook de Slack

Perfil -> Administración -> Gestionar aplicaciones -> Integraciones personalizadas -> WebHooks entrantes.

Video: 
https://www.youtube.com/watch?v=yvUQMdgbz_c&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=7&ab_channel=PeladoNerd

