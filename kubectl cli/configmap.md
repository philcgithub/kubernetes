# Kubectl ConfigMap cli examples #

```bash
#Imperative way
kubectl create configmap <config-name> --from-literal=<key>=<value>
kubectl create configmap app-config --from-literal=APP_COLOR=blue
kubectl create configmap app-config --from-literal=APP_COLOR=blue --from-literal=APP_MOD=prod
```