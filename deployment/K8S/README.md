create eks cluster using Udagram cluster name & node group
run using command 
```
    aws eks --region us-west-2 update-kubeconfig --name Udagram
```

deploy yaml files
```
    kubectl apply -f filename
```

connect to pod
```
    kubectl exec -it POD_NAME bash
```