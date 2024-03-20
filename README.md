# k8s-monitor

## SetUp Helm Repo

```sh
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

### SetUp Loki

```sh
kubectl create ns loki
helm upgrade --install loki grafana/loki -f loki-values.yaml -n loki
```

### install mimir

```sh
kubectl create ns mimir
helm upgrade --install mimir grafana/mimir-distributed -n mimir
```

### install grafana

```sh
kubectl create ns monitoring
helm upgrade --install grafana grafana/grafana -f grafana-values.yaml -n monitoring
```
