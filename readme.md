# cloudshell-repo

Grafana loki setup guide

## kube-prometheus-stack
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

## grafana
helm repo add grafana https://grafana.github.io/helm-charts

## Create a namespace for monitoring 
kubectl create ns monitoring 

## install kube-prometheus-stack
helm upgrade --install prom-stack prometheus-community/kube-prometheus-stack -n monitoring --values prometheus-config.yaml.yaml
