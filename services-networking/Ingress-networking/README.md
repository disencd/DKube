Ingress
*******

Make your HTTP (or HTTPS) network service available using a protocol-aware configuration mechanism, that understands web concepts like URIs, hostnames, paths, and more. The Ingress concept lets you map traffic to different backends based on rules you define via the Kubernetes API.

Terminology
For clarity, this guide defines the following terms:

Node: A worker machine in Kubernetes, part of a cluster.
Cluster: A set of Nodes that run containerized applications managed by Kubernetes. For this example, and in most common Kubernetes deployments, nodes in the cluster are not part of the public internet.
Edge router: A router that enforces the firewall policy for your cluster. This could be a gateway managed by a cloud provider or a physical piece of hardware.
Cluster network: A set of links, logical or physical, that facilitate communication within a cluster according to the Kubernetes networking model.
Service: A Kubernetes Service that identifies a set of Pods using label selectors. Unless mentioned otherwise, Services are assumed to have virtual IPs only routable within the cluster network.






Ingress rules

Maily for http

    - An optional host. In this example, no host is specified, so the rule applies to all inbound HTTP traffic through the IP address specified. 

    - A list of paths (for example, /testpath), each of which has an associated backend defined with a service.name and a service.port.name or service.port.number. Both the host and path must match the content of an incoming request before the load balancer directs traffic to the referenced Service.

    - A backend is a combination of Service and port names as described in the Service doc or a custom resource backend by way of a CRD. HTTP (and HTTPS) requests to the Ingress that match the host and path of the rule are sent to the listed backend.


controlplane ~ ➜  kubectl get ingress --all-namespaces
NAMESPACE   NAME                 CLASS    HOSTS   ADDRESS         PORTS   AGE
app-space   ingress-wear-watch   <none>   *       172.20.119.53   80      8m38s

controlplane ~ ➜  kubectl get svc -n critical-space
NAME          TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
pay-service   ClusterIP   172.20.212.108   <none>        8282/TCP   2m20s


Ingress Networking

controlplane ~ ✖ kubectl create namespace ingress-nginx
namespace/ingress-nginx created

The NGINX Ingress Controller requires a ConfigMap object. Create a ConfigMap object with name ingress-nginx-controller in the ingress-nginx namespace.

controlplane ~ ➜  kubectl create configmap ingress-nginx-controller -n ingress-nginx
configmap/ingress-nginx-controller created


The NGINX Ingress Controller requires two ServiceAccounts. Create both ServiceAccount with name ingress-nginx and ingress-nginx-admission in the ingress-nginx namespace.


Use the spec provided below.

controlplane ~ ➜  kubectl create serviceaccount ingress-nginx -n ingress-nginx
serviceaccount/ingress-nginx created

controlplane ~ ➜  kubectl create serviceaccount ingress-nginx-admission -n ingress-nginx
serviceaccount/ingress-nginx-admission created