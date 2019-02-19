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
