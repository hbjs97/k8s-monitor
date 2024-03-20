# k8s-monitor

## SetUp

```sh
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update

kubectl create ns monitoring
```

### install loki

```sh
helm upgrade --install loki grafana/loki -f loki-values.yaml -n monitoring
```

### install mimir

```sh
helm upgrade --install mimir grafana/mimir-distributed -n monitoring
```

### install grafana

```sh
helm upgrade --install grafana grafana/grafana -f grafana-values.yaml -n monitoring
```
