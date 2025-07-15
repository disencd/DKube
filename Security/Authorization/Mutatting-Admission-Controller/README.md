Create TLS secret webhook-server-tls for secure webhook communication in webhook-demo namespace.


We have already created below cert and key for webhook server which should be used to create secret.

Certificate : /root/keys/webhook-server-tls.crt

Key : /root/keys/webhook-server-tls.key

 kubectl create secret tls webhook-server-tls --help

controlplane ~ ✖ kubectl create secret tls webhook-server-tls --cert=/root/keys/webhook-server-tls
.crt --key=/root/keys/webhook-server-tls.key -n webhook-demo
secret/webhook-server-tls created


controlplane ~ ➜  kubectl get po pod-with-defaults -o yaml | grep -A2 " securityContext:"
  securityContext:
    runAsNonRoot: true
    runAsUser: 1234