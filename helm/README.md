# Node Disk Manager Installation Through Helm3

## Helm3

See helm docs for setting up helm v3. Installed helm version can be obtained by using the following command:
```bash
helm version
```

## Install NDM

- Helm v3 takes the current namespace from the local kube config and use that namespace the next time the user executes helm commands. If it is not present, the default namespace is used. Assign the openebs namespace to the current context and run the following commands to install openebs in openebs namespace. 

- To view current context, run the following:
```bash
kubectl config current-context
```

- Assign openebs namespace to the current context:
```bash
kubectl config set-context <current_context_name> --namespace=openebs
```

- Add NDM helm repo:
```bash
helm repo add openebs https://openebs.github.io/charts/ndm
helm repo update
```

- Install NDM
If the configured namespace does not exist, run the following command:

```bash
helm install <release-name> ndm --create-namespace
```

Else if the configured namespace already exists, run the following command:

```bash
helm install <release-name> ndm
```

