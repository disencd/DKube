CommonLabel - Add a common label to all the Kubernetes resources
namePrefix/Suffix
Namespace - Add NS
Common Annotation - to adds to all resources


Image Transformer

Kustomize supports multiple image transformations within the same kustomization.yaml file. 

This feature is particularly useful when you have workloads with multiple containers or when you need to transform images across different resource types. 

The image transformer rules can be applied to various resource manifests, including Deployments, Jobs, and more, ensuring consistent image updates throughout your Kubernetes cluster.

