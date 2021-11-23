### Install redis via helm
Get redis values
```bash
helm inspect values bitnami/redis > redis-yaml.yaml
```
Install with values
```bash
helm install my-release bitnami/redis -f redis-yaml.yaml
```