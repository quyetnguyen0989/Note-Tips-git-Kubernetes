# Tips-Kubectl
## Check project:
```
gcloud config set-value project
gcloud info
```
## Copy use gcloud:
```
gcloud beta compute scp --recurse [file] [name vm]:[desnitaion] --internal-ip | if it internal-ip
```
## basic
```
kubectl get pod ..
kubectl get pod [namepod] --output=yml
```
## Create a Cluter kubectl:
```
gcloud container cluster create quyet -- zone asia-southeast1-a
gcloud container clusters get-credentials quyet --zone=asia-southeast1-a
```
## Deploy first application:
```
kubectl apply -f./deployment.yaml
kubect expose deployment tomcat-deployment --type=NodePort
kubectl get pods
```
## Kubectl create deployment
```
kubectl create deployment ubuntu --image=nginx
```
## Delete application:
```
kubectl delete -f ./deployment.yaml
```
## Kubectl create scale:
```
kubectl scale --replicas=4 deployment/tomcat-deployment 
 
kubectl expose deployment tomcat-deployment --type=NodePort
kubectl expose deployment tomcat-deployment --type=LoadBalancer --port=8080 --target-port=8080 --name tomcat-load-balancer
 
kubectl describe services tomcat-load-balancer
```
## Roullout and email check history change
```
kubectl rollout status deployment tomcat-deployment
kubectl set image deployment/tomcat-deployment tomcat=tomcat:9.0.1
kubectl rollout status deployment tomcat-deployment
kubectl rollout history deployment tomcat-deployment
kubectl rollout history deployment/tomcat-deployment --revision=2
kubectl rollout undo deployment [name deployment] --to-revision=2
```
## Label and selection nodes
```
kubectl get node
kubectl label node gke-quyet-default-pool-799a436e-b4p7 use storageType=ssd
kubectl describe node gke-quyet-default-pool-799a436e-g7rl
```

## Kubectl get secret
```
kubectl get secret
kubectl get secrets [name of sceret] -o yaml
echo -n [password] | base64 -d
```

## Kubectl describe 
```
kubectl describe service [name services]
```

## Fixed error can't create pod
```
kubectl create serviceaccount --namespace kube-system tiller
kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
kubectl patch deploy --namespace kube-system tiller-deploy -p '{"spec":{"template":{"spec":{"serviceAccount":"tiller"}}}}'      
helm init --service-account tiller --upgrade
```
## Show resource nodes
```
kubectl get nodes --no-headers | awk '{print $1}' | xargs -I {} sh -c 'echo {}; kubectl describe node {} | grep Allocated -A 5 | grep -ve Event -ve Allocated -ve percent -ve -- ; echo'
```
```
kubectl top pod --all-namespaces
```
# Limittranger, so that limit resource of node if use default
```
kubectl describe limitranges
kubectl get limitranges -o yaml
kubectl edit limitranges
```

# Limittranger, so that limit resource of node if use default
```
kubectl describe limitranges
kubectl get limitranges -o yaml
kubectl edit limitranges
```
# Config vertical pod autoscaling 
https://cloud.google.com/kubernetes-engine/docs/how-to/vertical-pod-autoscaling

```
cloud beta container clusters update default --enable-vertical-pod-autoscaling
```
# Delete muti pod
```
k get cronjobs | grep finportal-backend | awk '{ print $1 }' | xargs -n 1 kubectl delete cronjob

kubectl get job | awk '{print $1}' | xargs kubectl delete job

kubectl get job | grep cluster | awk '{print $1}' | xargs kubectl delete job
```

# Stern get log service of
```
stern [service-name]
stern [service-name] | grep abc
```

##
```
k get svc --all-namespaces
```
## delete pods
```
for i in $(k get pods |grep be-dp-calc |awk '{print $1}');do echo $i;kubectl delete pods $i;done
```
## Get service account of node and cluster
```
gcloud container clusters describe default --zone asia-southeast1-a |grep serviceAccount

```
## Restart deployment
```
kubectl rollout restart deployment [deployment]
```
