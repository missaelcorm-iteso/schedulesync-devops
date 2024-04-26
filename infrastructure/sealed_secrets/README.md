## Install

### Client
```shell
wget https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.19.4/kubeseal-0.19.4-linux-amd64.tar.gz
```

```shell
tar -xvzf kubeseal-0.19.4-linux-amd64.tar.gz kubeseal
```

```shell
install -m 755 kubeseal /usr/local/bin/kubeseal
```

### Server

```shell
helm repo add sealed-secrets https://bitnami-labs.github.io/sealed-secrets
```

```shell
helm install sealed-secrets -n kube-system --set-string fullnameOverride=sealed-secrets-controller sealed-secrets/sealed-secrets
```

