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
