### Install redis via helm
Get redis values
```bash
helm inspect values bitnami/redis > redis-yaml.yaml
```
Install with values
```bash
helm install my-release bitnami/redis -f redis-yaml.yaml
```
## Working on HELM
### Secretes
Install secrets plugin of helm
```bash
helm plugin install https://github.com/zendesk/helm-secrets
```
Install gpg and create gpg key pair 
```bash
yum install gpg
gpg --gen-key
```
List gpg keys
```bash
gpg --list-keys
```
Create secret
```bash
sops -p <FingerPrint> secrets.yaml
```
Decrypt secrets with helm plugin
```bash
GPG_TTY=$(tty)
export GPG_TTY
helm secrets view secrets.yaml
```
