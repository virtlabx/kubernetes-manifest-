# kubernetes-manifest
All kubernetes objects that I created in the AWS EKS cluster in yml format.

I created the following k8s objects:

- Namespace "sre-app-namespace" to contain all the resources.
- Secret "ecr-credentials" that creates a login token to docker-registry for pulling the docker images.
- Deployment "sre-app-flask-deployment" for the simple python web app.
- Deployment "sre-app-redis-deployment" for redis.
- Service "sre-app-flask-service" which is a LoadBalancer for sre-app-flask-deployment.
- Service "sre-app-redis-service" which is a ClusterIP for sre-app-redis-deployment internal communication.
