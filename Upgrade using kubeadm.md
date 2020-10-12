# Upgrade using kubeadm #

1.  Upgrade kubeadm on master node

    ```bash
    apt-get upgrade -y kubeadm=1.12.0-00
    OR
    apt install kubeadm=1.12.0-00
    ```

2.  Then plan the upgrade:

    ```bash
    kubeadm upgrade plan
    ```

3.  Perform the upgrade

```bash
kubeadm upgrade apply v1.18.0
```

4.  Check the nodes

    ```bash
    kubectl get nodes
    ```

    They will still show the old version as the kubelet     has not been upgraded yet.
    
    Remember, you may or may not have kubelet's running     on the master node depending on how it was setup.

5.  Upgrade the kubelet on the master node:

    ```bash
    apt install kubelet=1.12.0-00
    systemctl restart kubelet
    ```

6.  Uncordon the master.

```bash
kubectl uncordon master
```

7.  Then upgrade worker nodes.  One at a time:

    7a.  Starting on master node

    ```bash
    master> kubectl drain node-1
    ```
    
    7b.  Then on the individual node:
    
    ```
    ssh node-1
    
    node-1> apt install kubeadm=1.12.0-00
    node-1> apt install kubelet=1.12.0-00
    
    node-1> systemctl restart kubelet
    
    exit
    ```
    
    7c.  Uncordon the node using the master
    
    ```
    master> kubectl uncordon node-1
    ```

Repeat the above for each node.