# StorageClass cli #

```bash
# list storageclasses and see what is default
kubectl get storageclass

#make a storageclass not the default
kubectl patch storageclass standard -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"false"}}}'

# make a storageclass the default
kubectl patch storageclass gold -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'
```