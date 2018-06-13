# Install cert-manager
To get automatic Let's Encrypt certificates, we should install [cert-manager](https://cert-manager.readthedocs.io/en/latest/getting-started/2-installing.html)

```
helm install --name cert-manager --namespace kube-system stable/cert-manage
```

# Create certificate Issuer
```
kubectl create -f issuer.yml
```

# References
https://cert-manager.readthedocs.io/en/latest/reference/issuers.html

HTTP tutorial: https://cert-manager.readthedocs.io/en/latest/tutorials/acme/http-validation.html
