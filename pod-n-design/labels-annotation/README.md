


kubectl get pods -l 'bu in (finance)'

kubectl get pods -l 'env in (dev)'


How many objects are in the prod environment including PODs, ReplicaSets and any other objects?

controlplane ~ ➜  kubectl get all --selector env=prod
NAME              READY   STATUS    RESTARTS   AGE
pod/app-1-zzxdf   1/1     Running   0          4m31s
pod/app-2-45v8h   1/1     Running   0          4m31s
pod/auth          1/1     Running   0          4m31s
pod/db-2-5rkkp    1/1     Running   0          4m31s

NAME            TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
service/app-1   ClusterIP   10.43.192.60   <none>        3306/TCP   4m31s

NAME                    DESIRED   CURRENT   READY   AGE
replicaset.apps/app-2   1         1         1       4m31s
replicaset.apps/db-2    1         1         1       4m31s

controlplane ~ ➜  


Identify the POD which is part of the prod environment, the finance BU and of frontend tier?

```
 kubectl get pod --selector env=prod -l 'bu in (finance)'
NAME          READY   STATUS    RESTARTS   AGE
app-1-bwc4x   1/1     Running   0          6m10s
app-1-r5lgs   1/1     Running   0          6m10s
app-1-w646j   1/1     Running   0          6m10s
app-1-zzxdf   1/1     Running   0          6m10s
auth          1/1     Running   0          6m10s
db-2-5rkkp    1/1     Running   0          6m10s
```



kubectl get pod --selector env=prod -l 'bu in (finance)' -l 'tier in (frontend)'


controlplane ~ ➜  kubectl get all --selector env=prod,bu=finance,tier=frontend
NAME              READY   STATUS    RESTARTS   AGE
pod/app-1-zzxdf   1/1     Running   0          8m10s


controlplane ~ ➜  kubectl get all --selector env=prod,bu=finance,tier=frontend | wc -l