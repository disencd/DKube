

logs of kubectl

kubectl -n elastic-stack logs kibana



kubectl -n elastic-stack logs app

kubectl -n elastic-stacl exec -it app -- cat /log/app.log


Init containers


you may want to run a process that runs to completion in a container. For example a process that pulls a code or binary from a repository that will be used by the main web application. That is a task that will be run only one time when the pod is first created. Or a process that waits for an external service or database to be up before the actual application starts. That's where initContainers comes in.

https://kubernetes.io/docs/concepts/workloads/pods/init-containers/