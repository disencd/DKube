controlplane ~ ✖ k describe networkpolicy payroll-policy
Name:         payroll-policy
Namespace:    default
Created on:   2025-06-06 12:43:06 +0000 UTC
Labels:       <none>
Annotations:  <none>
Spec:
  PodSelector:     name=payroll
  Allowing ingress traffic:
    To Port: 8080/TCP
    From:
      PodSelector: name=internal
  Not affecting egress traffic
  Policy Types: Ingress