# Kubectl POD cli examples #

## Simple run a pod ##

```bash
kubectl run nginx-pod --image=nginx
```

## Run a pod with a label ##

```bash
kubectl run messaging --image=redis:alpine -l tier-msg
```

## To run pod and see logs in stdout (actually creates a deployment?)##

```bash
docker run kodekloud/event-simulator
```

## To run pod in background, and not see the logs (actually creates a deployment?) ##

```bash
docker run -d kodecloud/event-simulator
```

## Create a pod ##

```bash
kubectl run --generator=run-pod/v1 nginx --image=nginx
```

## Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run) ##

```bash
kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml
```

## Run a basic pod and pass in a command ##

```bash
kubectl run --restart=Never --image=busybox static-busybox --dry-run -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
```

## Create pod in manifests folder ##

``bash
kubectl run --restart=Never --image=busybox static-busybox --dry-run -o yaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml
```