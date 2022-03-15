# Kubernetes Demo Project
Inspired From - in28min

# Kubernetes Features
- Declarative
- Auto/Easy Scaling
- Load Balancing
- Self Healing
- Zero Down Time deployments
- Manage 100's of Instances , 1000's or Microservices

## Steps to Deploy to Kubernetes
** Step 1: Build Image using Spring Boot Plugin

** Step 2: Push Docker Image to Docker Hub.

** Step 3: Connect with Gcloud, excute below Commands,
    kubectl version

** Step 4: Setup Deployment for Currency Exchange Service,
    kubectl create deployment currency-exchange --image=surajsharma286/msvc-currency-exchange-service:0.0.1-SNAPSHOT

** Step 5: Expose Deployment
    kubectl expose deployment currency-exchange --type=LoadBalancer --port=8000

** Step 7: Test Endpoint - http://<Load Balancer IP>:8000/currency-exchange/from/USD/to/INR

** Step 8: Setup Deployment for Currency Conversion Service,
    kubectl create deployment currency-conversion --image=surajsharma286/msvc-currency-conversion-service:0.0.1-SNAPSHOT

** Step 9:  Expose Deployment
    kubectl expose deployment currency-conversion --type=LoadBalancer --port=8100

** Step 10: Test Endpoint - http://<Load Balancer IP>:8100/currency-conversion/from/USD/to/INR/quantity/10

** Step 11:
    kubectl autoscale deployment currency-exchange --min=1 --max=3 --cpu-percent=2