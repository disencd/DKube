controlplane ~ ➜  kubectl get clusterrole
NAME                                                                   CREATED AT
admin                                                                  2025-07-09T12:32:19Z
cluster-admin                                                          2025-07-09T12:32:19Z
clustercidrs-node                                                      2025-07-09T12:32:24Z
edit                                                                   2025-07-09T12:32:19Z
k3s-cloud-controller-manager                                           2025-07-09T12:32:23Z
local-path-provisioner-role                                            2025-07-09T12:32:24Z
system:aggregate-to-admin                                              2025-07-09T12:32:19Z
system:aggregate-to-edit                                               2025-07-09T12:32:19Z
system:aggregate-to-view                                               2025-07-09T12:32:19Z
system:aggregated-metrics-reader                                       2025-07-09T12:32:24Z
system:auth-delegator                                                  2025-07-09T12:32:19Z
system:basic-user                                                      2025-07-09T12:32:19Z
system:certificates.k8s.io:certificatesigningrequests:nodeclient       2025-07-09T12:32:19Z
system:certificates.k8s.io:certificatesigningrequests:selfnodeclient   2025-07-09T12:32:19Z
system:certificates.k8s.io:kube-apiserver-client-approver              2025-07-09T12:32:19Z
system:certificates.k8s.io:kube-apiserver-client-kubelet-approver      2025-07-09T12:32:19Z
system:certificates.k8s.io:kubelet-serving-approver                    2025-07-09T12:32:19Z
system:certificates.k8s.io:legacy-unknown-approver                     2025-07-09T12:32:19Z
system:controller:attachdetach-controller                              2025-07-09T12:32:19Z
system:controller:certificate-controller                               2025-07-09T12:32:20Z
system:controller:clusterrole-aggregation-controller                   2025-07-09T12:32:20Z
system:controller:cronjob-controller                                   2025-07-09T12:32:20Z
system:controller:daemon-set-controller                                2025-07-09T12:32:20Z
system:controller:deployment-controller                                2025-07-09T12:32:20Z
system:controller:disruption-controller                                2025-07-09T12:32:20Z
system:controller:endpoint-controller                                  2025-07-09T12:32:20Z
system:controller:endpointslice-controller                             2025-07-09T12:32:20Z
system:controller:endpointslicemirroring-controller                    2025-07-09T12:32:20Z
system:controller:ephemeral-volume-controller                          2025-07-09T12:32:20Z
system:controller:expand-controller                                    2025-07-09T12:32:20Z
system:controller:generic-garbage-collector                            2025-07-09T12:32:20Z
system:controller:horizontal-pod-autoscaler                            2025-07-09T12:32:20Z
system:controller:job-controller                                       2025-07-09T12:32:20Z
system:controller:legacy-service-account-token-cleaner                 2025-07-09T12:32:20Z
system:controller:namespace-controller                                 2025-07-09T12:32:20Z
system:controller:node-controller                                      2025-07-09T12:32:20Z
system:controller:persistent-volume-binder                             2025-07-09T12:32:20Z
system:controller:pod-garbage-collector                                2025-07-09T12:32:20Z
system:controller:pv-protection-controller                             2025-07-09T12:32:20Z
system:controller:pvc-protection-controller                            2025-07-09T12:32:20Z
system:controller:replicaset-controller                                2025-07-09T12:32:20Z
system:controller:replication-controller                               2025-07-09T12:32:20Z
system:controller:resourcequota-controller                             2025-07-09T12:32:20Z
system:controller:root-ca-cert-publisher                               2025-07-09T12:32:20Z
system:controller:route-controller                                     2025-07-09T12:32:20Z
system:controller:selinux-warning-controller                           2025-07-09T12:32:20Z
system:controller:service-account-controller                           2025-07-09T12:32:20Z
system:controller:service-cidrs-controller                             2025-07-09T12:32:20Z
system:controller:service-controller                                   2025-07-09T12:32:20Z
system:controller:statefulset-controller                               2025-07-09T12:32:20Z
system:controller:ttl-after-finished-controller                        2025-07-09T12:32:20Z
system:controller:ttl-controller                                       2025-07-09T12:32:20Z
system:controller:validatingadmissionpolicy-status-controller          2025-07-09T12:32:20Z
system:coredns                                                         2025-07-09T12:32:24Z
system:discovery                                                       2025-07-09T12:32:19Z
system:heapster                                                        2025-07-09T12:32:19Z
system:k3s-controller                                                  2025-07-09T12:32:24Z
system:kube-aggregator                                                 2025-07-09T12:32:19Z
system:kube-controller-manager                                         2025-07-09T12:32:19Z
system:kube-dns                                                        2025-07-09T12:32:19Z
system:kube-scheduler                                                  2025-07-09T12:32:19Z
system:kubelet-api-admin                                               2025-07-09T12:32:19Z
system:metrics-server                                                  2025-07-09T12:32:24Z
system:monitoring                                                      2025-07-09T12:32:19Z
system:node                                                            2025-07-09T12:32:19Z
system:node-bootstrapper                                               2025-07-09T12:32:19Z
system:node-problem-detector                                           2025-07-09T12:32:19Z
system:node-proxier                                                    2025-07-09T12:32:19Z
system:persistent-volume-provisioner                                   2025-07-09T12:32:19Z
system:public-info-viewer                                              2025-07-09T12:32:19Z
system:service-account-issuer-discovery                                2025-07-09T12:32:19Z
system:volume-scheduler                                                2025-07-09T12:32:19Z
traefik-kube-system                                                    2025-07-09T12:32:40Z
view                                                                   2025-07-09T12:32:19Z

controlplane ~ ➜  


ontrolplane ~ ➜  kubectl get clusterroleBinding
NAME                                                            ROLE                                                                        AGE
cluster-admin                                                   ClusterRole/cluster-admin                                                   5m4s
clustercidrs-node                                               ClusterRole/clustercidrs-node                                               5m
helm-kube-system-traefik                                        ClusterRole/cluster-admin                                                   5m
helm-kube-system-traefik-crd                                    ClusterRole/cluster-admin                                                   5m
k3s-cloud-controller-manager                                    ClusterRole/k3s-cloud-controller-manager                                    5m1s
k3s-cloud-controller-manager-auth-delegator                     ClusterRole/system:auth-delegator                                           5m1s
kube-apiserver-kubelet-admin                                    ClusterRole/system:kubelet-api-admin                                        5m
local-path-provisioner-bind                                     ClusterRole/local-path-provisioner-role                                     5m
metrics-server:system:auth-delegator                            ClusterRole/system:auth-delegator                                           5m
system:basic-user                                               ClusterRole/system:basic-user                                               5m4s
system:controller:attachdetach-controller                       ClusterRole/system:controller:attachdetach-controller                       5m4s
system:controller:certificate-controller                        ClusterRole/system:controller:certificate-controller                        5m4s
system:controller:clusterrole-aggregation-controller            ClusterRole/system:controller:clusterrole-aggregation-controller            5m4s
system:controller:cronjob-controller                            ClusterRole/system:controller:cronjob-controller                            5m4s
system:controller:daemon-set-controller                         ClusterRole/system:controller:daemon-set-controller                         5m4s
system:controller:deployment-controller                         ClusterRole/system:controller:deployment-controller                         5m4s
system:controller:disruption-controller                         ClusterRole/system:controller:disruption-controller                         5m4s
system:controller:endpoint-controller                           ClusterRole/system:controller:endpoint-controller                           5m4s
system:controller:endpointslice-controller                      ClusterRole/system:controller:endpointslice-controller                      5m4s
system:controller:endpointslicemirroring-controller             ClusterRole/system:controller:endpointslicemirroring-controller             5m4s
system:controller:ephemeral-volume-controller                   ClusterRole/system:controller:ephemeral-volume-controller                   5m4s
system:controller:expand-controller                             ClusterRole/system:controller:expand-controller                             5m4s
system:controller:generic-garbage-collector                     ClusterRole/system:controller:generic-garbage-collector                     5m4s
system:controller:horizontal-pod-autoscaler                     ClusterRole/system:controller:horizontal-pod-autoscaler                     5m4s
system:controller:job-controller                                ClusterRole/system:controller:job-controller                                5m4s
system:controller:legacy-service-account-token-cleaner          ClusterRole/system:controller:legacy-service-account-token-cleaner          5m4s
system:controller:namespace-controller                          ClusterRole/system:controller:namespace-controller                          5m4s
system:controller:node-controller                               ClusterRole/system:controller:node-controller                               5m4s
system:controller:persistent-volume-binder                      ClusterRole/system:controller:persistent-volume-binder                      5m4s
system:controller:pod-garbage-collector                         ClusterRole/system:controller:pod-garbage-collector                         5m4s
system:controller:pv-protection-controller                      ClusterRole/system:controller:pv-protection-controller                      5m4s
system:controller:pvc-protection-controller                     ClusterRole/system:controller:pvc-protection-controller                     5m4s
system:controller:replicaset-controller                         ClusterRole/system:controller:replicaset-controller                         5m4s
system:controller:replication-controller                        ClusterRole/system:controller:replication-controller                        5m4s
system:controller:resourcequota-controller                      ClusterRole/system:controller:resourcequota-controller                      5m4s
system:controller:root-ca-cert-publisher                        ClusterRole/system:controller:root-ca-cert-publisher                        5m4s
system:controller:route-controller                              ClusterRole/system:controller:route-controller                              5m4s
system:controller:selinux-warning-controller                    ClusterRole/system:controller:selinux-warning-controller                    5m4s
system:controller:service-account-controller                    ClusterRole/system:controller:service-account-controller                    5m4s
system:controller:service-cidrs-controller                      ClusterRole/system:controller:service-cidrs-controller                      5m4s
system:controller:service-controller                            ClusterRole/system:controller:service-controller                            5m4s
system:controller:statefulset-controller                        ClusterRole/system:controller:statefulset-controller                        5m4s
system:controller:ttl-after-finished-controller                 ClusterRole/system:controller:ttl-after-finished-controller                 5m4s
system:controller:ttl-controller                                ClusterRole/system:controller:ttl-controller                                5m4s
system:controller:validatingadmissionpolicy-status-controller   ClusterRole/system:controller:validatingadmissionpolicy-status-controller   5m4s
system:coredns                                                  ClusterRole/system:coredns                                                  5m
system:discovery                                                ClusterRole/system:discovery                                                5m4s
system:k3s-controller                                           ClusterRole/system:k3s-controller                                           5m
system:kube-controller-manager                                  ClusterRole/system:kube-controller-manager                                  5m4s
system:kube-dns                                                 ClusterRole/system:kube-dns                                                 5m4s
system:kube-scheduler                                           ClusterRole/system:kube-scheduler                                           5m4s
system:metrics-server                                           ClusterRole/system:metrics-server                                           5m
system:monitoring                                               ClusterRole/system:monitoring                                               5m4s
system:node                                                     ClusterRole/system:node                                                     5m4s
system:node-proxier                                             ClusterRole/system:node-proxier                                             5m4s
system:public-info-viewer                                       ClusterRole/system:public-info-viewer                                       5m4s
system:service-account-issuer-discovery                         ClusterRole/system:service-account-issuer-discovery                         5m4s
system:volume-scheduler                                         ClusterRole/system:volume-scheduler                                         5m4s
traefik-kube-system                                             ClusterRole/traefik-kube-system                                             4m44s

controlplane ~ ➜  


A new user michelle joined the team. She will be focusing on the nodes in the cluster. Create the required ClusterRoles and ClusterRoleBindings so she gets access to the nodes.

controlplane ~ ✖ kubectl create clusterrolebinding  node-admin  --clusterrole=node-admin --user=mi
chelle 
clusterrolebinding.rbac.authorization.k8s.io/node-admin created

controlplane ~ ➜  k edit -f clusterrolebinding.rbac.authorization.k8s.io/node-admin
error: the path "clusterrolebinding.rbac.authorization.k8s.io/node-admin" does not exist

controlplane ~ ✖ kubectl auth can-i list nodes --as michelle
Warning: resource 'nodes' is not namespace scoped

yes