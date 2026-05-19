# Homarr

## Installation

[From docs](https://homarr.dev/docs/getting-started/installation/helm#traditional)

#### Create Namespace

```bash
kubectl apply -f namespace.yaml
kubectl config setcontext --current --namespace=homarr
```

#### Create Storage

```bash
kubectl create secret generic db-encryption --from-literal=db-encryption-key=$(openssl rand -hex 32) --namespace homarr
kubectl apply -f storage.yaml
```

#### Create Homarr

```bash
helm repo add homarr-labs https://homarr-labs.github.io/charts/
helm repo update
helm install -n homarr homarr-labs/homarr --values values.yaml
```

#### Create Local Loadbalancer Forward

```bash
kubectl apply -f loadbalancer-service.yaml
```

## Usage

Create a user at [http://localhost:7575](http://localhost:7575), create a dashboard, add your apps

## Storage

To get the db-encryption secret do

```
kubectl get secret db-encryption -o jsonpath="{.data.db-encryption-key}" | base64 --decode; echo
```
