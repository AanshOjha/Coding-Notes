## Problem
Even you installed minikube and docker, erro: 
```console
kubectl
Command 'kubectl' not found, but can be installed with:
sudo snap install kubectl
```

## Solution!!!
```
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version
```
