# Role cli #

```bash
# Create Role
kubectl create role developer --resource=pods --verb=create, list,get,update,delete --namespace=development
```