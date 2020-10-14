# Kubectl Deployment cli examples #

```bash
# Create a deployment
kubectl create deployment --image=nginx nginx

# Create a deployment
kubectl run nginx-deploy --image=nginx:1.16 --replicas=1 --record

# Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)
kubectl create deployment --image=nginx nginx --dry-run -o yaml

# Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)
kubectl create deployment --image=nginx nginx --dry-run -o yaml > nginx-deployment.yaml

# kubectl create deployment does not have a --replicas option. You could first create it and then scale it using the kubectl scale command, or edit the nginx-deployment.yaml before using it.

# Set image
kubectl set image deployment/myapp-deployment nginx=nginx:1.9.1 --record

#Rollback
# You can rollback to previous revision.
kubectl rollout undo deployment/myapp-deployment

# View rollback history (record points)
kubectl rollout history deployment nginx-deploy

# Scale deployment / set replicas
kubectl scale deployment nginx --replicas=2
```
