## Ssh Tunel
```
gcloud compute ssh be-jump --zone asia-southeast1-a -- -L 3333:10.76.64.3:3306
gcloud compute ssh be-jump --zone asia-southeast1-a -- -L 6379:[ip redis]:6379
```
## run script bash from git hub
bash <(curl -s https://raw.githubusercontent.com/quyetnguyen0989/sell-script-all/master/install-docker-docker-compose.sh)

## Redash
https://redash.io/help/open-source/admin-guide/google-developer-account-setup

## Quit telnet
```
^]   ( ctrl + ] )
close
```
## Filter

```
[a-z\._]+@be.xyz
\s+[0-9]+,1:\s+
"quyet.nguyen0989@gmal.com",*\n 
```
## Upgrader terraform in macos
mv terraform /usr/local/bin/terraform

## Base 64 decode and and code
```
echo 'ditcu' | base64
echo 'ZGl0Y3UK' | base64 -D
echo -n "B2EG3R4OU56P1" | base64 | for base 64 not 
```
