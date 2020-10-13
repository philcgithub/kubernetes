# Kubectl Node cli examples #

## Add label to node ##

```bash
kubectl label nodes <node-name> <label-key>=<label-value>

kubectl label nodes node01 size=Large
```

## Removing a taint ##

```bash
kubectl taint nodes master node-role.kuberenetes.io/master-
```

## Get nodes info in JSON format ##

```bash
kubectl get nodes -o json > file.json
```

## Query osImages in JSON ##

```bash
kubectl get nodes -o=jsonpath='{.items[*].status.nodeInfo.osImage}' > /opt/outputs/nodes_os_x43kj56.txt
```