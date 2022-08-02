# Usage
```
# create namespace
kubectl create namespace kong
# deploy postgers
helm install postgres bitnami/postgresql -n kong -f postgres-values.yaml
# get postgres secrets
kubectl get secret --namespace kong postgres-postgresql -o jsonpath="{.data.password}"
# add secret to secrets.yaml
kubectl apply -f secrets.yaml
# deploy kong
helm install kong kong/kong -n kong -f kong-values.yaml
```
