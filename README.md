# k8s-monitor

```sh
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update

kubectl create ns loki

helm upgrade --install logging grafana/loki -f loki-values.yaml -n loki
```

---

```sh
helm upgrade --install grafana grafana/grafana -f grafana-values.yaml -n loki
```
