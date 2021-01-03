# LIVENESS AND READINESS 

### Used Commands

```shell
#Apply the pod with livenes exec
kubectl apply -f 1-liveness-exec.yaml

#Describe the pod to see how it fails
kubectl describe pod liveness-exec

#Apply the pod with livenes http
kubectl apply -f 2-liveness-http.yaml 

#Describe the pod to see how it fails
kubectl describe pod liveness-http

#Apply the pod with livenes tcp
kubectl apply -f 3-liveness-tcp.yaml

#Describe the pod to see how it fails
kubectl describe pod goproxy

#Apply the pod with readiness http
kubectl apply -f 4-readiness-http.yaml

#Apply a service to connect with the pod
kubectl apply -f 5-service-nginx.yaml 

#Check the pod
curl http://172.19.0.3:30000/

#Apply the pod with readiness http that fails
kubectl apply -f 6-readiness-http.yaml 

#Describe the pod to see how it fails
kubectl describe pod nginx-fail

#See the logs of the good pod
kubectl logs pod/nginx

#See the logs of the bad pod
kubectl logs pod/nginx-fail
```
## Liveness: Vivo

Se tiene una aplicación que tarda en iniciar, por tanto, se configura en el liveness probe sí la aplicación falla,
para que la aplicación pueda hacer restart (matar el proceso y crear de nuevo el pod).

Se puede ejecutar de tres maneras:

1. **Exec:** Ejecutar un comando para ver sí un archivo está presente.
2. **Http Get:** Realizar un get a una ruta web dentro del contenedor.
3. **TCP Port:** Check al puerto tcp que queramos.

## Readiness: Listo

Sirve para decirle a Kubernetes sí el pod está listo para recibir tráfico.

Una aplicación tarda un rato en iniciar, el proceso corre bien pero la aplicación aún no está lista para recibir peticiones
(El primer request carga toda la aplicación en memoria, conexión a base de datos).

### ¿Cómo se usa?

Se tiene un */path* en la aplicación que checkea que la configuración sea correcta (hacer un select simple en la base de datos), checkea conexiones, internet, etc... Todo lo necesario para saber que la aplicación está lista para recibir tráfico se hace en ese */path*.
Dada la ocasión que la DB bloquea la IP a ese pod, ese */path* deja de funcionar, por lo tanto Kubernetes se percata y no le manda más tráfico a ese pod afectado, por consiguiente los clientes nunca llegan al pod que tiene un problema con la aplicación. 

Video: 
https://www.youtube.com/watch?v=5gSc1ouW8rM&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=6&ab_channel=PeladoNerd


