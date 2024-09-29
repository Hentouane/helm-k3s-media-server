# k3s-media-station
A simple helm chart to deploy jellyfin and *arr services to a k3s cluster with local storage.

Heavily based on https://greg.jeanmart.me/2020/04/13/self-host-your-media-center-on-kubernetes-wi

## Prerequisites
### VPN Secret
Create a secret containing your VPN connection:
```
kubectl create secret generic openvpn \
    --from-literal='username=<VPN_USERNAME>' \
    --from-literal='password=<VPN_PASSWORD>' \
    --namespace media
```

### Ingress
Expects an ingress nginx service to manage ingress.

## Installation
```
helm -n media install media . --create-namespace
```

## Upgrade
```
helm upgrade -n media media .
```
