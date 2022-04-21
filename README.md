# kubect-deployments

Helps you to get/restart deployments which deal with the key in the configmap. Sometimes config-key changes may require restart some applications. Using this method gives you a list of application which you concern. 

### Installation
```bash
curl -sLo kubectl-deployments https://raw.githubusercontent.com/emrahgenc/extended-kubectl/master/plugin/kubectl-deployments && \
  chmod +x kubectl-deployments && mv -i kubectl-deployments /usr/local/bin

# Verify
kubectl deployments version
```

### Help
```bash
kubectl deployments --help
# or
kubectl deployments --h
```

### Get
```bash
# simple
kubectl deployments get sample-config sample-config-key

kubectl deployments get sample-config sample-config-key -n custom-namespace

kubectl deployments get sample-config sample-config-key --custom-namespace


# advanced
kubectl deployments get \
  --configmap sample-config \
  --key sample-key \
  --namespace custom-namespace
```
:exclamation: - Without using a key this method gets the deployments which uses a config-map file inside.

### Restart
```bash
# simple
kubectl deployments restart sample-config sample-config-key

kubectl deployments restart sample-config sample-config-key -n custom-namespace

kubectl deployments restart sample-config sample-config-key --custom-namespace


# advanced
kubectl deployments restart \
  --configmap sample-config \
  --key sample-key \
  --namespace custom-namespace
```
:exclamation: -  Information: Without using a key this method restarts the deployments which uses a config-map file inside.
