# Gcloud command
## Check project:
```
gcloud config set-value project
gcloud info
```
## Copy use gcloud:
```
gcloud beta compute scp --recurse [file] [name vm]:[desnitaion] --internal-ip | if it internal-ip
```

## Example:
```
gcloud compute scp --recurse [instnace-name]:/home/user/montior /Users/quyet.nguyen/Downloads
```

## Create Database:
```
gcloud sql instances create test-master --tier=db-f1-micro --region=asia-southeast1
```
## Delete Database:
```
gcloud sql instances delete test-maser
```
## Gcloud replica:
```
```
# Node-taints
```
https://cloud.google.com/kubernetes-engine/docs/how-to/node-taints
```
# Create node pool with autosclaing , preemptible

```
gcloud container node-pools create  pool-3 \
--cluster=default \
--machine-type=n1-standard-2 \
--num-nodes=2 \
--service-account=k8s-cluster-manager@[name service]-staging.iam.gserviceaccount.com \
--enable-autoupgrade \
--enable-autoscaling \
--max-nodes=6 \
--min-nodes=2 \
--preemptible \
--region=asia-southeast1-a
```
# Create cluster with Mlts 
```
gcloud beta container clusters create \
istio-addon-cluster \
--addons=Istio --istio-config=auth=MTLS_PERMISSIVE \
--cluster-version=latest \
--num-nodes=2 \
```
```
gcloud container node-pools create pool-2 \
--cluster=default \
--machine-type=n1-standard-1 \
--num-nodes=1 \
--k8s-cluster@kazan-trading-236803.iam.gserviceaccount.com \
--addons=Istio --istio-config=auth=MTLS_PERMISSIVE \
--cluster-version=latest \
--preemptible \
--region=asia-southeast1-a
```
