## Istio Service Mesh Installation and implemenation 

## Create a namespace for istio
kubectl create ns istio-system

# Add the revalent helm charts
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update


## Helm Install istio base
helm install istio-base istio/base --set global.istioNamespace=istio-system