## Ssh Tunel
```
gcloud compute ssh be-jump --zone asia-southeast1-a -- -L 3333:10.76.64.3:3306
```
## run script bash from git hub
bash <(curl -s https://raw.githubusercontent.com/quyetnguyen0989/sell-script-all/master/install-docker-docker-compose.sh)
