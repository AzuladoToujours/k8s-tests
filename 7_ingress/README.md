# INGRESS - Load Balancer

Redirección de tráfico - Proxy Pass

### Used Commands

```shell
# Deploy the ingress-nginx
kubectl apply -f /ingress
# Hello v1
kubectl apply -f 1-hello-app-deployment-v1.yaml
# Hello v2
kubectl apply -f 2-hello-app-deployment-v2.yaml
# Hello v1 Service 
kubectl apply -f 3-hello-svc-v1.yaml 
# Hello v2 Service 
kubectl apply -f 4-hello-svc-v2.yaml
# Apply the ingress rules
kubectl apply -f 5-ingress.yaml

kubectl get ing
```


Documentación nginx-ingress para otra instalación: https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-manifests/

Video: 
https://www.youtube.com/watch?v=pzFirwIpMag&list=PLqRCtm0kbeHA5M_E_Anwu-vh4NWlgrOY_&index=8&ab_channel=PeladoNerd


Lástimosamente, este laboratorio se tendrá que realizar en Digital Ocean