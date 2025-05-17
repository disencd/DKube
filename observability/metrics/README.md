kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml



controlplane ~ ➜  kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
serviceaccount/metrics-server created
clusterrole.rbac.authorization.k8s.io/system:aggregated-metrics-reader created
clusterrole.rbac.authorization.k8s.io/system:metrics-server created
rolebinding.rbac.authorization.k8s.io/metrics-server-auth-reader created
clusterrolebinding.rbac.authorization.k8s.io/metrics-server:system:auth-delegator created
clusterrolebinding.rbac.authorization.k8s.io/system:metrics-server created
service/metrics-server created
deployment.apps/metrics-server created
apiservice.apiregistration.k8s.io/v1beta1.metrics.k8s.io created

controlplane ~ ➜  k get pods
NAME       READY   STATUS    RESTARTS   AGE
elephant   1/1     Running   0          2m11s
lion       1/1     Running   0          2m11s
rabbit     1/1     Running   0          2m11s

controlplane ~ ➜  k top node
NAME           CPU(cores)   CPU(%)   MEMORY(bytes)   MEMORY(%)   
controlplane   326m         2%       866Mi           1%          
node01         38m          0%       233Mi           0% 