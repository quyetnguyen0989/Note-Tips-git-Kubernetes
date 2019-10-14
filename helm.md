# Command helm
## Helm status
```
helm status [name of service]
helm history [name of service]
helm rollback [name of service] [number want to rollback]
```


```
vi sts.yaml
cd pmm-server/
helm install --name pmm-02 --set platform=kubernetes pmm-server/
helm install -n pmm02 .
helm del --purge pmm-02
k logs -f pmm-02-0
k describe po pmm-02-0
kubectl logs -f pmm-02-0
kdp pmm-02-0
helm ls pmm-02
cd _template/
cat sts.yaml
cat templates/
vim values.yaml
vim Chart.yaml
helm install --name pmm1 --set platform=kubernetes pmm-server/
```
# deploy phpmyadmin with heml
```
helm install -name phpmyadmin --set ingress.host=[domain name],ingress.enable=true stable/phpmyadmin
```
