# Kubectl Node cli examples #

```bash
# Add label to node
kubectl label nodes <node-name> <label-key>=<label-value>
kubectl label nodes node01 size=Large

# Removing a taint
kubectl taint nodes master node-role.kuberenetes.io/master-

# Get nodes info in JSON format
kubectl get nodes -o json > file.json

# Query osImages in JSON
kubectl get nodes -o=jsonpath='{.items[*].status.nodeInfo.osImage}' > /opt/outputs/nodes_os_x43kj56.txt
```