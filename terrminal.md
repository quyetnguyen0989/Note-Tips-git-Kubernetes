# Install fish
 brew install fish <br />
 curl -L https://get.oh-my.fish | fish <br />
## fish tip
 fish_config <br />
 ~/.config/fish/conf.d/google.fish <br />
##
Bash , can add ~/.bashrc , or ~/.zshrc
```
function swe() {
    case $1 in
    develop)
        gcloud config set project [name of project]
        gcloud container clusters get-credentials bu1-k8s-dev --zone=asia-southeast1-a
        ;;
    stage)
        gcloud config set project [name of project]
        gcloud container clusters get-credentials default --zone=asia-southeast1-a
        ;;
    docker)
               gcloud config set project [name of project]
        ;;
    production)
          gcloud config set project [name of project]
          gcloud container clusters get-credentials default --zone=asia-southeast1-a
        ;;
    practice)
                 gcloud config set project [name of project]
                 gcloud container clusters get-credentials quyet --zone=asia-southeast1-a
               ;;

    azui)
                 gcloud config set project [name of project]
                 gcloud container clusters get-credentials default --zone=asia-southeast1-a
               ;;
    esac;
}
```
