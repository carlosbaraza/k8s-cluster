# Setup

## Create GCP Cluster
Use the UI/SDK to create a cluster.

## Configure kubectl to connect to cluster
```
gcloud container clusters get-credentials cluster-3
```

## Install Dashboard
Follow the instructions in the [dashboard/README.md](dashboard/README.md)

## Setup Helm
```bash
# Create Service Account for Tiller
kubectl create serviceaccount -n kube-system tiller

# Add priviledges to the account
kubectl create clusterrolebinding tiller-binding --clusterrole=cluster-admin --serviceaccount kube-system:tiller

# Install helm client (Tiller) in the cluster
helm init --service-account tiller
```

## Install cert-manager
To get automatic Let's Encrypt certificates, we should install [cert-manager](https://cert-manager.readthedocs.io/en/latest/getting-started/2-installing.html)

```
helm install --name cert-manager --namespace kube-system stable/cert-manage
```
