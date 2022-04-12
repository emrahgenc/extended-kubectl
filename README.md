# kubect-pods

Helps you to get deployments which deal with the key in the configmap. Sometimes config-key changesmay require restart some applications. Using this method gives you a list of application which you concern. 

### Installation
```bash
curl -sLo kubectl-pods https://raw.githubusercontent.com/emrahgenc/extended-kubectl/master/plugin/kubectl-pods && \
  chmod +x kubectl-pods && mv -i kubectl-pods /usr/local/bin

# Verify
kubectl pods version
```

# Help
kubectl pods --help

kubectl pods --h

### Usage
```bash
# simple
kubectl pods get sample-config sample-config-key

kubectl pods get sample-config sample-config-key -n custom-namespace

kubectl pods get sample-config sample-config-key --custom-namespace


# advanced
kubectl pods get \
  --configmap sample-config \
  --key sample-key \
  --namespace custom-namespace
```
