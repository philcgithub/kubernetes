# Rolebinding cli #

```bash
# Create rolebinding
kubectl create rolebdining delveoper-role-binding --role=developer --user=john --namespace=development

# Check permissions
kubectl auth ca-i update pods --namespace=development --as=john
kubectl auth can-i list pods --namespace=development --as=john
```
