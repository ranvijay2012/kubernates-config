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
