kubectl label nodes <node-name> <label-key>=<label-value>
kubectl label nodes node-1 size=large




add a section in pod-defentition.yml


spec:
    nodeSelector:
        size: large


If Large or medium, but not small

beta.kubernetes.io/arch=amd64
beta.kubernetes.io/os=linux

controlplane ~ ➜  kubectl describe node node01 
Name:               node01
Roles:              <none>
Labels:             beta.kubernetes.io/arch=amd64
                    beta.kubernetes.io/os=linux
                    kubernetes.io/arch=amd64
                    kubernetes.io/hostname=node01
                    kubernetes.io/os=linux

controlplane ~ ➜  kubectl describe node controlplane 
Name:               controlplane
Roles:              control-plane
Labels:             beta.kubernetes.io/arch=amd64
                    beta.kubernetes.io/os=linux
                    kubernetes.io/arch=amd64
                    kubernetes.io/hostname=controlplane
                    kubernetes.io/os=linux
                    node-role.kubernetes.io/control-plane=
                    node.kubernetes.io/exclude-from-external-load-balancers=
