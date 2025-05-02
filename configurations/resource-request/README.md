When you specify the resource request for containers in a Pod, the kube-scheduler uses this information to decide which node to place the Pod on. When you specify a resource limit for a container, the kubelet enforces those limits so that the running container is not allowed to use more of that resource than the limit you set. The kubelet also reserves at least the request amount of that system resource specifically for that container to use.

CPU can be limited to VCPU
if reached limit, throttles

In case of memory, if running out OOM

controlplane ~ ➜  kubectl get pods
NAME       READY   STATUS      RESTARTS      AGE
elephant   0/1     OOMKilled   2 (23s ago)   26s

