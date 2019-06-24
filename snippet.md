# 01-docker
```bash
sudo su -
cd /workshop/docker-chat
docker build -t chat app
docker run -d --name db mongo
docker run --link db -p 80:3000 -d chat
```

# 02-composition
```bash
docker rm -f $(docker ps -aq)
cd /workshop/microservices-demo
git checkout docker-compose
docker-compose -f composition-manifests/docker-compose.yml up
```

# 03-kubernetes
```bash
cd /workshop/microservices-demo
export KUBECONFIG=/workshop/kube.json
git checkout kubernetes
kubectl config current-context
kubectl apply -f release/kubernetes-manifests.yaml
```

# 04-kubernetes(pod)
```bash
kubectl get pods
kubectl describe pods <NAME>
kubectl get pods -o yaml <NAME>
```

# 05-kubernetes(service)
```bash
kubectl get service -o wide
kubectl describe service <NAME>
```
# 06-kubernetes(scale)
## Current terminal
```bash
kubectl scale deployment currencyservice --replicas 2
kubectl delete pods <NAME>
kubectl scale deployment currencyservice --replicas 1
```
## New terminal
```bash
sudo su -
export KUBECONFIG=/workshop/kube.json
watch kubectl get pods 
```
# 07-kubernetes(upgrade)
```bash
git checkout regression
kubectl apply -f release/kubernetes-manifests.yaml
kubectl get pods
kubectl get deployment
```

# 08-kubernetes(rollback)
```bash
kubectl rollout history deployment/currencyservice
kubectl rollout undo deployment/currencyservice
kubectl rollout history deployment/currencyservice
```
