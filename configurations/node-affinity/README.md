  https://kubernetes.io/docs/tasks/configure-pod-container/assign-pods-nodes-using-node-affinity/
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: size
            operator: In
            values:
            - large
            - medium
          - key: size
            operator: NotIn
            values:
            - small


operator - Exists

2 types of affinity

requiredDuringSchedulingIgnoredDuringExecution
preferredDuringSchedulingIgnoredDuringExecution

In future
requiredDuringSchedulingrequiredDuringExecution


kubectl get pods -o wide