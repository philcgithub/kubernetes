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
