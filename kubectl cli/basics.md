# Kubectl basics #

```bash
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
```
