# Kubectl basics #

```bash
# Create useful aliases
alias ka='kubectl apply'
alias kc='kubectl create'
alias kd='kubectl describe'
alias kexec='kubectl exec'
alias kdel='kubectl delete'
alias kg='kubectl get'
alias kl='kubectl logs'
alias kr='kubectl run'
alias ks='kubectl set'

# List all api resources known to kube-apiserver
kubectl api-resources

# List the api versions known to kube-apiserver
kubectl api-versions

# Apply a yaml file new or updated
kubectl apply -f file.yaml

# Update annotation with record of the change
kubectl apply -f file.yaml --record

# Explain object, shows the field options
kubectl explain pv --recursive | less

# Get cluster events
kubectl get events

# Get pods in all namespaces
kubectl get pods --all-namespaces
kubectl get pods -A
```
