controlplane ~ ➜  k describe deploy frontend
Name:                   frontend
Namespace:              default
CreationTimestamp:      Sun, 18 May 2025 13:13:30 +0000
Labels:                 app=myapp
                        tier=frontend
Annotations:            deployment.kubernetes.io/revision: 1
Selector:               app=frontend
Replicas:               5 desired | 5 updated | 5 total | 5 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=frontend
           version=v1
  Containers:
   webapp-color:
    Image:         kodekloud/webapp-color:v1
    Port:          <none>
    Host Port:     <none>
    Environment:   <none>
    Mounts:        <none>
  Volumes:         <none>
  Node-Selectors:  <none>
  Tolerations:     <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   frontend-8b5db9bd (5/5 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  68s   deployment-controller  Scaled up replica set frontend-8b5db9bd from 0 to 5


kubectl scale deployment --replicas=1 frontend-v2

controlplane ~ ➜  kubectl delete deployment  frontend
deployment.apps "frontend" deleted