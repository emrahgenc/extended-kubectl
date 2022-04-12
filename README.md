
### kubect-pods:
This is a plugin that allows you to learn which deployment uses key stored in a configmap.
kubectl itself has `rollout restart` subcommand [[1](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-em-restart-em-)] in version >1.15 which can be used as follow:

```
kubectl rollout restart deployment/nginx
```



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
