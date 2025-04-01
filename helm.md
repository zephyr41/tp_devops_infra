# Commandes de déploiement Kubernetes
Initialisation et application Terraform

terraform init


terraform apply

az aks get-credentials --resource-group plop --name yes-default

kubectl get nodes
Création du Chart Helm et préparation de l'image Docker


helm create mon-app

docker build -t mon-app .


docker login


docker tag mon-app:latest z3ph7r/mon-app:latest


docker push z3ph7r/mon-app:latest
Ingress Controller NGINX


helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx


helm install nginx-ingress ingress-nginx/ingress-nginx --create-namespace --namespace ingress-nginx


kubectl get svc -n ingress-nginx


helm install nginx-ingress ingress-nginx/ingress-nginx --version 4.10.0


kubectl get svc -n ingress-nginx


helm uninstall nginx-ingress


helm install nginx-ingress ingress-nginx/ingress-nginx --version 4.10.0 --create-namespace --namespace ingress-nginx


kubectl get svc -n ingress-nginx
Installation de Kubecost


helm repo add kubecost https://kubecost.github.io/cost-analyzer/


helm repo update


kubectl create namespace kubecost


helm install kubecost kubecost/cost-analyzer --namespace kubecost


kubectl get pods -n kubecost


kubectl get svc -n kubecost
Déploiement de l'application


helm upgrade --install mon-app ./mon-app


kubectl get ingress


curl http://mon-app.local
