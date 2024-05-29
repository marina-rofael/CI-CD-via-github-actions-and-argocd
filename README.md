- install Argocd on your cluster
- create namespace
#kubectl create ns argocd
- install argocd
#kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.5.8/manifests/install.yaml
- check the installation
#kubectl get all -n argocd
- expose the argocd service 
#kubectl port-forward svc/argocd-server -n argocd 8080:443
- get the password of the admin user
#kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
