# Deployments

### Used Commands

```shell
#Create deployment
kubectl apply -f 01-hello.yml

#Scale deployment
kubectl scale --replicas=5 deployment/hello

#Apply Nodeport
kubectl apply -f 01-hello-nodeport.yml

#Put a pod in quarentine
kubectl label pod [POD-id] role=cuarentena --overwrite

#Deploy a new version of the app
kubectl apply -f 02-hello.yml 
```

Video: 
https://www.youtube.com/watch?v=q-ZicDSb3Cc&ab_channel=PeladoNerd




