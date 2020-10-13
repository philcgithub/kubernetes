# Kubectl Deployment cli examples #

## Create a deployment ##

```bash
kubectl create deployment --image=nginx nginx
```

## Generate Deployment YAML file (-o yaml). Don't create it(--dry-run) ##

```bash
kubectl create deployment --image=nginx nginx --dry-run -o yaml
```

## Generate Deployment YAML file (-o yaml). Don't create it(--dry-run) ##

```bash
kubectl create deployment --image=nginx nginx --dry-run -o yaml > nginx-deployment.yaml
```

kubectl create deployment does not have a --replicas option. You could first create it and then scale it using the kubectl scale command, or edit the nginx-deployment.yaml before using it.

## Set image ##
```bash
kubectl set image deployment/myapp-deployment \
                                    nginx=nginx:1.9.1
```

## Rollback ##

You can rollback to previous revision.

```bash
kubectl rollout undo deployment/myapp-deployment
```

## Scale deployment / set replicas ##

```bash
kubectl scale deployment nginx --replicas=2
```
