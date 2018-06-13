# Install Dashboard in cluster
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml
```

Run proxy

```
kubectl proxy
```

Open dashboard:
```
http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/
```

# Login
Based on this page: https://github.com/kubernetes/dashboard/wiki/Creating-sample-user

## Create admin-user in new cluster
```
kubectl create -f admin-user.yaml
```

## Get token
```
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}')
```

## Use token
Copy token and paste in the Dashboard


