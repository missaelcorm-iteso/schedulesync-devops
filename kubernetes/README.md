## Sealed Secrets

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: schedulesync-api
  namespace: schedulesync-api
data:
  MONGO_PROTOCOL: cHJvdG9jb2w=      # MONGO_PROTOCOL B64 encoded
  MONGO_HOST: aG9zdA==              # MONGO_HOST B64 encoded
  MONGO_DB: ZGI=                    # MONGO_DB B64 encoded
  MONGO_USER: dXNlcg==              # MONGO_USER B64 encoded
  MONGO_PASS: cGFzc3dvcmQ=          # MONGO_PASS B64 encoded
  APP_PORT: MzAwMAo=                # APP_PORT B64 encoded
  SECRET_KEY: cGFzc3dvcmQ=          # SECRET_KEY B64 encoded
```

```shell
kubeseal --fetch-cert > public-key-cert.pem
```

```shell
kubeseal --format=yaml --cert=public-key-cert.pem < secret.yaml > sealed-secret.yaml
```

```shell
kubectl apply -f sealed-secret.yaml
```