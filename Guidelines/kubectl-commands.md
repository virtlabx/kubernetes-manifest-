# Apply all resources in EKS cluster.

### Create and verify the sre-app-namespace
```
kubectl apply -f sre-app-namespace.yml
kubectl get namespace
```
### Switch to sre-app-namespace and run everything in it
```
kubectl config set-context --current --namespace=sre-app-namespace
```
### Create a secret that creates a login token to AWS ECR repo for pulling the docker images
```
kubectl create secret docker-registry ecr-credentials --docker-server=422434854706.dkr.ecr.eu-west-1.amazonaws.com --docker-username=AWS --docker-password=$(aws ecr get-login-password) --namespace=sre-app-namespace
```
### Create sre-app-flask-deployment
```
kubectl apply -f sre-app-flask-deployment.yml
kubectl get deployment
kubectl get pods
kubectl logs sre-app-flask-deployment-<container_id>
kubectl describe sre-app-flask-deployment-<container_id>
```
### Create sre-app-flask-service
```
kubectl apply -f sre-app-flask-svc.yml
```
### Create sre-app-redis-deployment
```
kubectl apply -f sre-app-redis-deployment.yml
```
### Create sre-app-redis-service
```
kubectl apply -f sre-app-redis-svc.yml
```
