Use "kubectl api-resources" for a complete list of supported resources.

➜  DKube git:(main) ✗ k api-resources | grep -ie deployment -ie replicasets -ie cronjo -ie customerresource
deployments                         deploy       apps/v1                           true         Deployment
replicasets                         rs           apps/v1                           true         ReplicaSet
cronjobs                            cj           batch/v1                          true         CronJob

What is the preferred version for authorization.k8s.io api group?

Open proxy port

➜  DKube git:(main) ✗ k proxy 8001&                           
[1] 1652841



➜  DKube git:(main) ✗ curl localhost:8001/apis/authorization.k8s.io
{
  "kind": "APIGroup",
  "apiVersion": "v1",
  "name": "authorization.k8s.io",
  "versions": [
    {
      "groupVersion": "authorization.k8s.io/v1",
      "version": "v1"
    }
  ],
  "preferredVersion": {
    "groupVersion": "authorization.k8s.io/v1",
    "version": "v1"
  }
}%  

➜  DKube git:(main) ✗ curl localhost:8001/apis/rbac.authorization.k8s.io
{
  "kind": "APIGroup",
  "apiVersion": "v1",
  "name": "rbac.authorization.k8s.io",
  "versions": [
    {
      "groupVersion": "rbac.authorization.k8s.io/v1",
      "version": "v1"
    }
  ],
  "preferredVersion": {
    "groupVersion": "rbac.authorization.k8s.io/v1",
    "version": "v1"
  }
}%  