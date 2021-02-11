create eks cluster using Udagram cluster name & node group
run using command 
```
    aws eks --region us-west-2 update-kubeconfig --name Udagram
```

deploy yaml files
```
    kubectl apply -f filename
```

see pods
```
    kubectl get pods
```

see services
```
    kubectl describe services
```
delete a pod
```
    kubectl delete pod POD_NAME
```

delete deployment and service
```
    kubectl delete -f filename
```

connect to pod
```
    kubectl exec -it POD_NAME bash
```

Example of exposing a port
```
    kubectl expose deployment/kubernetes-bootcamp --type="NodePort" --port 8080
```