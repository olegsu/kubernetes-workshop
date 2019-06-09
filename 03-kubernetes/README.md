# Kubernetes
In this section we will run the application from section #2 on a kubernetes cluster

* Make sure you are in a `microservices-demo` directory

1. Make sure you have a kubectl configured
    `kubectl config current-context`
2. Try list all namespaces in a cluster
    `kubectl get namespace`
3. Create services
    `kubectl apply -f release/kubernetes-manifests.yaml`
4. List the kubernetes service just created
    `kubectl get service`
5. List the kubernetes pods just created
    `kubectl get pods`
5. List the kubernetes deployments just created
    `kubectl get deployment`
6. Scale up one of the deployments
    `kubectl scale deployment currencyservice --replicas 3`
    `kubectl scale deployment currencyservice --replicas 1`
7. Modify currency service in github
    * Add some error
    * update the image in the spec
8. Build locally the docker image
9. Push it to dockerhub with new version tag ( docker login )
11. See the regression (kubectl get pods | kubectl get deploy)
12. Rollback to previous rollout
    `kubectl rollout history deployment/currencyservice`
    `kubectl rollout undo deployment/currencyservice`
    `kubectl rollout history deployment/currencyservice`
13. Build another image with fix (code + yaml spec)