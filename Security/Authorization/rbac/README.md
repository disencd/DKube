Authorization
Details of Kubernetes authorization mechanisms and supported authorization modes.
Kubernetes authorization takes place following authentication. Usually, a client making a request must be authenticated (logged in) before its request can be allowed; however, Kubernetes also allows anonymous requests in some circumstances.

Authorization modes
The Kubernetes API server may authorize a request using one of several authorization modes:

AlwaysAllow
This mode allows all requests, which brings security risks. Use this authorization mode only if you do not require authorization for your API requests (for example, for testing).
AlwaysDeny
This mode blocks all requests. Use this authorization mode only for testing.
ABAC (attribute-based access control)
Kubernetes ABAC mode defines an access control paradigm whereby access rights are granted to users through the use of policies which combine attributes together. The policies can use any type of attributes (user attributes, resource attributes, object, environment attributes, etc).
RBAC (role-based access control)
Kubernetes RBAC is a method of regulating access to computer or network resources based on the roles of individual users within an enterprise. In this context, access is the ability of an individual user to perform a specific task, such as view, create, or modify a file.
In this mode, Kubernetes uses the rbac.authorization.k8s.io API group to drive authorization decisions, allowing you to dynamically configure permission policies through the Kubernetes API.
Node
A special-purpose authorization mode that grants permissions to kubelets based on the pods they are scheduled to run. To learn more about the Node authorization mode, see Node Authorization.
Webhook
Kubernetes webhook mode for authorization makes a synchronous HTTP callout, blocking the request until the remote HTTP service responds to the query.You can write your own software to handle the callout, or use solutions from the ecosystem.


▶ k get roles
No resources found in default namespace.

~/Downloads/ioctl-logs
▶ k auth can-i create deployments
yes

