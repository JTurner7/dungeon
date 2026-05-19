# Searxng

## Installation

Create the namespace

```bash
kubectl apply -f namespace.yaml
kubectl config set-context --current=dungeon
```

Create the storage for the configs and cache.

**NOTE**: Edit the `volumes/pv/` files to have the absolute path to your `data` and `config` folders.

```bash
kubectl apply -f local-storage-class.yaml
kubectl -R -f volumes
```

Create the deployment and then the loadbalancing service

```bash
kubectl apply -f deploy.yaml
kubectl apply -f service.yaml
```

## Usage

Search things at [http://localhost:8888](http://localhost:8888)

