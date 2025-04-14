A ReplicaSet's purpose is to maintain a stable set of replica Pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical Pods.

https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/

Errors:
apiVersion: v1
Error from server (BadRequest): error when creating "replica-sets/rs-defenition.yml": ReplicaSet in version "v1" cannot be handled as a ReplicaSet: strict decoding error: unknown field "replicas", unknown field "selector"