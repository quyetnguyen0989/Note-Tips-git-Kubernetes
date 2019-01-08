# Command useful docker

## Auth registry gcr 
```
docker login -u _json_key -p "$(cat login.json)" https://asia.gcr.io/
```
# Push docker to repo in docker server of google
```
docker tag grafana/grafaba:5.4.2 gcr.io/[name of project]/grafana
docker push gcr.io/[name of project]/grafana
```
