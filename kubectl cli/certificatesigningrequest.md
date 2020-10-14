# Certificate Signing Request cli commands #

```bash
# Create request body from .csr file
cat john.csr | base64 | tr -d "\n"

# show list of csr's
kubectl get csr

# approve a csr
kubectl certificate approve john-developer
```