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
