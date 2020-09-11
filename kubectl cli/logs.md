# Kubectl Logs cli examples #

# View logs of a running pod #
kubectl logs event-simulator-pod

# Follow logs of a running pod #
kubectl logs -f event-simulator-pod

# Follow logs of specific container in a running pod #
kubectl logs -f event-simulator-pod event-simulator