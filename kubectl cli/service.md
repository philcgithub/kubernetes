# Kubectl service cli examples #

```bash
#Create a Service named redis-service of type ClusterIP to expose pod redis on port 6379
kubectl expose pod redis --port=6379 --name redis-service --dry-run -o yaml

# (This will automatically use the pod's labels as selectors)

# Or
kubectl create service --type=clusterip redis --tcp=6379:6379 --dry-run -o yaml

# (This will not use the pods labels as selectors, instead it will assume selectors as app=redis. You cannot pass in selectors as an option. So it does not work very well if your pod has a different label set. So generate the file and modify the selectors before creating the service)

# Create a Service named nginx of type NodePort to expose pod nginx's port 80 on port 30080 on the nodes:
kubectl expose pod nginx --port=80 --name nginx-service --dry-run -o yaml

# (This will automatically use the pod's labels as selectors, but you cannot specify the node port. You have to generate a definition file and then add the node port in manually before creating the service with the pod.)

# Or
kubectl create service nodeport nginx --tcp=80:80 --node-port=30080 --dry-run -o yaml

# (This will not use the pods labels as selectors)

# Both the above commands have their own challenges. While one of it cannot accept a selector the other cannot accept a node port. I would recommend going with the `kubectl expose` command. If you need to specify a node port, generate a definition file using the same command and manually input the nodeport before creating the service.

# Expose pod / create service and specify target port
kubectl expose pod messaging --name messaging-service --port 6379 --target-port 6379

#Expose deployment
kubectl expose deployment hr-web-app --name hr-web-app-service --type=NodePort --port 8080 --target-port 8080 --dry-run=client -o yaml > svc.yaml

# Note: Cannot specify the NodePort, so need to edit the yaml file
```