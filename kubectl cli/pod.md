# Kubectl POD cli examples #

```bash
# Simple run a pod
kubectl run nginx-pod --image=nginx

# Run a pod with a label
kubectl run messaging --image=redis:alpine -l tier-msg

# To run pod and see logs in stdout (actually creates a deployment?)
docker run kodekloud/event-simulator

# To run pod in background, and not see the logs (actually creates a deployment?)
docker run -d kodecloud/event-simulator

# Create a pod
kubectl run --generator=run-pod/v1 nginx --image=nginx

# Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)
kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml

# Run a basic pod and pass in a command
kubectl run --restart=Never --image=busybox static-busybox --dry-run -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml

# Create pod in manifests folder
kubectl run --restart=Never --image=busybox static-busybox --dry-run -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
```