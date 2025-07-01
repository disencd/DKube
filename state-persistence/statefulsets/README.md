A StatefulSet runs a group of Pods, and maintains a sticky identity for each of those Pods. This is useful for managing applications that need persistent storage or a stable, unique network identity.


k create -f statefulset-defenition.yaml

k scaler statefulset mysql --replicas=5

k scaler statefulset mysql --replicas=3


k delete stateful mysql

