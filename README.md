# service-helm

## add to helm repo where you wish to deploy from
```bash
helm repo add service-helm https://mb-wali.github.io/service-helm/

# check 
helm search repo service-helm
```

## install
```bash
helm install --set storageClassName=openebs-hostpath --set namespace=jupyter grader service-helm/grader-service --namespace jupyter

# --set storageClassName
# --set namespace
# grader (name of deployment)
# --namespace (set namespace)

```