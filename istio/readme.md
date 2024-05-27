## Istio Service Mesh Installation and implemenation 

## Create a namespace for istio
kubectl create ns istio-system

# Add the revalent helm charts
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update


## Helm Install istio base
helm install istio-base istio/base -n istio-system

## Helm install istiod
helm install istiod istio/istiod -n istio-system --set telemetry.enabled=true \
    --set global.istioNamespace=istio-system \ 
    --set meshConfig.ingressService=istio-gateway \ 
    --set meshConfig.ingressSelector=gateway

## Helm install istio Gateway
kubectl create ns istio-ingress
helm install istio-gateway istio/gateway -n istio-ingress 
