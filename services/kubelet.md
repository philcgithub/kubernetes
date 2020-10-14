# Kubelet Service Info #

Runs as a systemd service

Service config is held here:

/etc/systemd/system/kubelet.service.d

## Find location of manifests / static pods ##

cd /var/lib/kubelet/
grep -i staticPod config.yaml

OR

systemctl status kubelet
And look for startup parameter