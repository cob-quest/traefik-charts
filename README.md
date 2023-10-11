# Deployment
Chart was deployed with default configurations and CRDs in ingress-routes.yaml
```bash
# deploy traefik
helm install traefik traefik/traefik

# apply ingress routes
kubectl apply -f ingress-routes.yaml
```

# Development
If you are deploying locally and wish to see the dashboard, you can do the following:
```bash
# find the traefik pod and copy the name
kubectl get pods -A

# forward pod's port 9000 to localhost:9000
kubectl port-forward <pod-id> 9000:9000
```

You may also want to forward the LoadBalancer of the traefik deployment:
```bash
# forwarding load balancer with minikube to 80/443
minikube tunnel
```

