# k8s-wordpress

## Usage

Create namespace

```
kubectl create namespace wp-staging
kubectl config set-context --current --namespace=wp-staging
```

Add secret vars

```
kubectl create secret generic wp-auth-secret-vars \
  --from-literal=mysql-user=YYYYYYYYYYY \
  --from-literal=mysql-password=XXXXXXXXXXXXX
```

Create resource

```
kubectl apply -f stg-nfs-pvc.yml -f stg-nfs-pv.yml -f stg-wp.yml
```
