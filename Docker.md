# Command useful docker

## Auth registry gcr 
```
docker login -u _json_key -p "$(cat login.json)" https://asia.gcr.io/
```
## [Push docker to repo in docker server of google] https://cloud.google.com/container-registry/docs/pushing-and-pulling
```
gcloud auth configure-docker
docker tag grafana/grafaba:5.4.2 gcr.io/[name of project]/grafana
docker push gcr.io/[name of project]/grafana
```

## Example push docker to private registry

```
1, docker push asia.gcr.io/docker-quyet/app1:app1
2, docker tag asia.gcr.io/docker-quyet/app1:app1 asia.gcr.io/docker-quyet/app1:app1
3, docker build -t asia.gcr.io/docker-quyet/app1:app1 .

```
