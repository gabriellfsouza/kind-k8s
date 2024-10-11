Declarative form
```bash
kind create cluster --config kind.yaml --name=cluster-name
kubectl apply -f namespace.yaml
kubectl apply -f pod.yaml --namespace first-app

kubectl apply -f replicaset.yaml --namespace first-app
kubectl delete replicasets.apps nginx
kubectl apply -f deployment.yaml -n first-app
kubectl apply -f service.yaml -n first-app
kubectl delete services nginx-svc
kubectl delete deployments.apps nginx

kind delete cluster --name=cluster-name
```


Imperative forms
```bash
kind create cluster --name=cluster-name
kubectl create namespace first-app
kubectl run nginx --image=nginx:alpine3.20-slim
kubectl delete pod nginx
```


Utility commands
```bash
kubectl logs nginx
kubectl port-forward
 pod/nginx -n first-app 8080:80
kubectl top pods -n 
first-app

kubectl port-forward svc/nginx-svc 8080:80 -n first-app
kubectl port-forward service/nginx-svc 8080:80 -n first-app
```
