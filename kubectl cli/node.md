# Kubectl Node cli examples #

```bash
# Add label to node
kubectl label nodes <node-name> <label-key>=<label-value>
kubectl label nodes node01 size=Large

# Adding a taint
kubectl taint nodes node-name key=value:taint-effect
kubectl taint nodes node01 app=blue:NoSchedule
# NoSchedule | PreferNoSchedule | NoExecute

# Removing a taint
kubectl taint nodes master node-role.kuberenetes.io/master-

# Get nodes info in JSON format
kubectl get nodes -o json > file.json

# Query osImages in JSON
kubectl get nodes -o=jsonpath='{.items[*].status.nodeInfo.osImage}' > /opt/outputs/nodes_os_x43kj56.txt
```