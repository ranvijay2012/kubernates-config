# kubernates-config
Describing kubernates configuration

#kubernates basic command

#Start the Minikube cluster
minikube start


#To verify `minikube` for local and your cluster setup with `kubectl`, run −
minikube status
kubectl cluster-info

#Checking Cluster Status
kubectl cluster-info

#Checking Node Status
kubectl get nodes

#Applying Configurations
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

V#erifying Deployment
kubectl get pods
kubectl get services

#Accessing the Application
minikube service <spring-name>



Option 1 — Simple Project (Good for learning)
my-app-repo/
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── Dockerfile
├── src/
└── README.md

👉 How you run
kubectl apply -f k8s/


✔ Easy
✔ Good for small apps
❌ Not ideal for multi-env

🚀 Option 2 — Environment-Based (Production Recommended)
my-app-repo/
│
├── k8s/
│   ├── dev/
│   │   ├── deployment.yaml
│   │   └── service.yaml
│   │
│   ├── qa/
│   │   ├── deployment.yaml
│   │   └── service.yaml
│   │
│   └── prod/
│       ├── deployment.yaml
│       └── service.yaml
│
├── Dockerfile
└── src/

👉 Apply per environment
kubectl apply -f k8s/dev/
kubectl apply -f k8s/prod/


✔ Clean
✔ Scalable
✔ Used in companies

#ArgoCD DevOps configuration
Step 1 — Install Argo CD (if not installed)

kubectl create namespace argocd
kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

Check:
kubectl get pods -n argocd

🔑 Step 2 — Login to Argo CD

Port-forward: kubectl port-forward svc/argocd-server -n argocd 8080:443

Open: https://localhost:8080

Default username: admin

Get password from window command: 
[System.Text.Encoding]::UTF8.GetString(
[System.Convert]::FromBase64String(
(kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}")
)
)

Password: cqIOlMlWDXY2gXoR

