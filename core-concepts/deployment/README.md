Deployments
A Deployment manages a set of Pods to run an application workload, usually one that doesn't maintain state.

https://kubernetes.io/docs/concepts/workloads/controllers/deployment/

kubectl create deployment httpd-frontned --image=httpd --replicas=3
kubectl get deploy