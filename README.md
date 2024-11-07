## Buil and Run
```shell
docker compose up -d --force-recreate --build
```
### Build with args 
vi docker-compose.yaml
```yaml
build:
  args:
    URL: https://github.com/hufrea/byedpi/releases/download/v0.15/byedpi-15-x86_64.tar.gz
```
## Set proxy
```
localhost:1080
```
## Stop 
```shell
docker compose down
```

## k3s manifest apply
```shell
kubectl apply -f k3s-cnibuidpi.yaml
```
## Config traefik ingress entrypoint
```yaml
apiVersion: helm.cattle.io/v1
kind: HelmChartConfig
metadata:
  name: traefik
  namespace: kube-system
spec:
  valuesContent: |-
    ports:
      buydpi:
        port: 1080
        expose: true
        exposedPort: 1080
        protocol: TCP    
```


[Get Started with Docker](https://www.docker.com/get-started/)

[Rancher Desktop by SUSE](https://rancherdesktop.io/)

[Lightweight Kubernetes](https://k3s.io/)
