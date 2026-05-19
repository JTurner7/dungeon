# kube-prometheus-stack

## Installation

Make your Grafana password

```bash
cp values.yaml values-secret.yaml
```

edit the `values-secret.yaml` file to have your secret admin password, then install the apps

```bash
helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace=monitoring --create-namespace --values values-secret.yaml
kubectl apply -f grafana-loadbalancer-service.yaml
kubectl apply -f prometheus-loadbalancer-service.yaml
```

## Usage

Log into Grafana using [https://localhost:3000](https://localhost:3000)

Log into Prometheus using [https://localhost:9090](https://localhost:9090)

