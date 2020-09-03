# k8s-wordpress

## Usage

Create namespace

```
kubectl create namespace wp-staging
kubectl create namespace wp-production
```

Add secret vars

```
kubectl config set-context --current --namespace=wp-staging
kubectl create secret generic wp-auth-secret-vars \
  --from-literal=mysql-user=YYYYYYYYYYY \
  --from-literal=mysql-password=XXXXXXXXXXXXX

kubectl config set-context --current --namespace=wp-production
kubectl create secret generic wp-auth-secret-vars \
  --from-literal=mysql-user=YYYYYYYYYYY \
  --from-literal=mysql-password=XXXXXXXXXXXXX
```

Create resource

```
kubectl apply \
  -f prod-nfs-pvc.yml \
  -f prod-nfs-pv.yml \
  -f prod-wp.yml \
  -f stg-nfs-pvc.yml \
  -f stg-nfs-pv.yml \
  -f stg-wp.yml
```
