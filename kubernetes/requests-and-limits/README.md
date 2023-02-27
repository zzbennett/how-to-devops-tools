# Grafana Setup
1. Add the Helm repo
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts;helm repo update```

2. Install Grafana
```
helm upgrade --namespace grafana --install kube-stack-prometheus prometheus-community/kube-prometheus-stack --set prometheusSpec.scrapeInterval="5"
```

3. Login
```
kubectl port-forward --namespace grafana svc/kube-stack-prometheus-grafana 8080:80
```

4. Credentials
Username: admin
Password: prom-operator

5. Add the Grafana dashboard:
Go to [add a new dashboard](http://127.0.0.1:8080/dashboard/import)
Import [the dashboard](grafana-dashboard.json)

6. Start the workshop!

