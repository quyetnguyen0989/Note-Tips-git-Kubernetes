# Command useful docker

## Auth registry gcr 
```
docker login -u _json_key -p "$(cat login.json)" https://asia.gcr.io/
```
##Push docker to repo in docker server of google https://cloud.google.com/container-registry/docs/pushing-and-pulling
```
gcloud auth configure-docker
docker tag grafana/grafaba:5.4.2 gcr.io/[name of project]/grafana
docker push gcr.io/[name of project]/grafana
```
