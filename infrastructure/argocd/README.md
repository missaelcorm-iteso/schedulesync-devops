# ArgoCD

## Install
```shell
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Applications
The `./applications/` directory have the definitons for the applications managed with GitOps by `ArgoCD`, these files should contain git repos, helmcharts, sync policies, etc.

## Ingress
File `./ingress-argocd.yaml` is the ingress for accessing to the web UI for managing `ArgoCD` applications.

## Resources
- https://medium.com/@chirayukapoor/running-argo-cd-locally-with-kind-and-nginx-ingress-26b31cece300
