# Prometheus & Grafana

```
helm repo add stable https://kubernetes-charts.storage.googleapis.com
helm repo update
```

Ставим прометей с графаной в качестве оператора.

```
helm install prom stable/prometheus-operator -f prometheus.yaml --atomic
```

Устанавливаем через хелм ингресс.

```
helm install nginx stable/nginx-ingress -f nginx-ingress.yaml --atomic
```

Портфорвард для прометея и графаны.

```
kubectl port-forward service/prom-grafana 9000:80
kubectl port-forward service/prom-prometheus-operator-prometheus 9090
```

Устанавливаем приложение.

```
helm install myapp ./users-api --atomic
```

Метрики

```
curl -s http://localhost:31990/metrics
```

Другое

```
curl -H arch.homework http://arch.homework/otusapp/sergeyyurkin/metrics
while 1; do ab -n 50 -c 5 http://localhost:31439/api/users ; sleep 3; done
```
