Inspect the environment and identify the authorization modes configured on the cluster.

Check the kube-apiserver settings.

kubectl describe pod kube-apiserver-controlplane -n kube-system


How many roles

controlplane ~ ✖ kubectl get roles
No resources found in default namespace.

All NS

controlplane ~ ➜  kubectl get roles -A
NAMESPACE     NAME                                             CREATED AT
blue          developer                                        2025-07-03T13:08:48Z
kube-public   kubeadm:bootstrap-signer-clusterinfo             2025-07-03T13:05:34Z
kube-public   system:controller:bootstrap-signer               2025-07-03T13:05:34Z
kube-system   extension-apiserver-authentication-reader        2025-07-03T13:05:33Z
kube-system   kube-proxy                                       2025-07-03T13:05:35Z
kube-system   kubeadm:kubelet-config                           2025-07-03T13:05:34Z
kube-system   kubeadm:nodes-kubeadm-config                     2025-07-03T13:05:34Z
kube-system   system::leader-locking-kube-controller-manager   2025-07-03T13:05:34Z
kube-system   system::leader-locking-kube-scheduler            2025-07-03T13:05:34Z
kube-system   system:controller:bootstrap-signer               2025-07-03T13:05:33Z
kube-system   system:controller:cloud-provider                 2025-07-03T13:05:34Z
kube-system   system:controller:token-cleaner                  2025-07-03T13:05:34Z


What are the resources the kube-proxy role in the kube-system namespace is given access to?

kubectl describe role kube-proxy -n kube-system

controlplane ~ ✖ kubectl describe role kube-proxy -n kube-system
Name:         kube-proxy
Labels:       <none>
Annotations:  <none>
PolicyRule:
  Resources   Non-Resource URLs  Resource Names  Verbs
  ---------   -----------------  --------------  -----
  configmaps  []                 [kube-proxy]    [get]


Which account is the kube-proxy role assigned to?

controlplane ~ ✖ kubectl describe rolebinding kube-proxy -n kube-system
Name:         kube-proxy
Labels:       <none>
Annotations:  <none>
Role:
  Kind:  Role
  Name:  kube-proxy
Subjects:
  Kind   Name                                             Namespace
  ----   ----                                             ---------
  Group  system:bootstrappers:kubeadm:default-node-token  


A user dev-user is created. User's details have been added to the kubeconfig file. Inspect the permissions granted to the user. Check if the user can list pods in the default namespace.

Use the --as dev-user option with kubectl to run commands as the dev-user.

controlplane ~ ➜  kubectl get pods --as dev-user
Error from server (Forbidden): pods is forbidden: User "dev-user" cannot list resource "pods" in API group "" in the namespace "default"


Create the necessary roles and role bindings required for the dev-user to create, list and delete pods in the default namespace.


Use the given spec:

Create the necessary roles and role bindings required for the dev-user to create, list and delete pods in the default namespace.


Use the given spec:



Role: developer

Role Resources: pods

Role Actions: list

Role Actions: create

Role Actions: delete

RoleBinding: dev-user-binding

RoleBinding: Bound to dev-user

controlplane ~ ✖ kubectl create role developer --namespace default --verb=list,create,delete --resource=pods
role.rbac.authorization.k8s.io/developer created

controlplane ~ ➜  kubectl get roles
NAME        CREATED AT
developer   2025-07-03T13:23:11Z


controlplane ~ ➜  kubectl create rolebinding dev-user-binding --namespace=default --role=developer --user=dev-user
rolebinding.rbac.authorization.k8s.io/dev-user-binding created