# Kubectl ReplicaSet cli example #

```bash
# Scale replicaset
kubectl scale --replicas=6 -f replicaset-definition.yml
kubectl scale --replicas=6 replicaset myapp-replicaset
```