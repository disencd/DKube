


controlplane ~ ➜  kubectl get nodes
NAME           STATUS   ROLES           AGE     VERSION
controlplane   Ready    control-plane   2m21s   v1.32.0
node01         Ready    <none>          110s    v1.32.0


controlplane ~ ➜  kubectl describe node node01 | grep Taint
Taints:             <none>


controlplane ~ ➜  kubectl taint nodes node01 spray=mortein:NoSchedule
node/node01 tainted

controlplane ~ ➜  kubectl describe node node01 | grep Taint
Taints:             spray=mortein:NoSchedule

Remove the taint on controlplane, which currently has the taint effect of NoSchedule.

controlplane ~ ✖ kubectl taint nodes  controlplane node-role.kubernetes.io/control-plane:NoSchedule-
node/controlplane untainted