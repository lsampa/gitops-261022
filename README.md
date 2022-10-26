# itba-261022
## kind https://kind.sigs.k8s.io/docs/user/quick-start/
## ArgoCD https://argo-cd.readthedocs.io/en/stable/getting_started/
## stern (logs) https://github.com/wercker/stern

Crear cluster: 
```
kind create cluster --name octubre
```
Ver namespaces 
```
kubectl get namespaces
```
Ver pods en todos los namespaces
```
kubectl get pods -A
```
Ver servicios en todos los namespaces
```
kubectl get svc -A
```
Ver pods en un namespce
```
kubectl get pods -n namespace_name
```
Ver secrets
```
kubectl get secrets -n namespace_name
```
Ver lo que contiene un secret: 
```
kubectl get secret secret_name -o yaml -n namespace_name
```
Ver un pod o deployment
```
kubectl describe pod pod_name -n namespace_name
kubectl describe deployment deployment_name -n namespace_name
```
```

Instalar Argocd: 
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
Port fowarding: 
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
kubectl port-foward service/service-name -n namespace-name localport:serviceport
```
Ver un secret:
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
kubectl -n namespace_name get secret secret_name  -o jsonpath="{.data.password}" | base64 -d


```
