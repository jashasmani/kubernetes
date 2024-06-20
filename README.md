# README

## Description

**Imperative**

```bash
# Create a Pod using kubectl run
kubectl run html-pod --image=jashasmani/html

# Expose the Pod as a Service
kubectl expose pod html-pod --type=NodePort --port=80 --name=html-service

# Get the Service's IP address
kubectl get svc html-service -o jsonpath='{.spec.clusterIP}'
```

**Declarative**

Create a YAML file named `html-deployment.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: html-deployment
spec:
  selector:
    matchLabels:
      app: html
  template:
    metadata:
      labels:
        app: html
    spec:
      containers:
      - name: html
        image: jashasmani/html
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: html-service
spec:
  selector:
    app: html
  type: NodePort
  ports:
  - port: 80
    targetPort: 80
```

Apply the YAML file to create the Deployment and Service:

```bash
kubectl apply -f html-deployment.yaml
```

Get the Service's IP address:

```bash
kubectl get svc html-service -o jsonpath='{.spec.clusterIP}'
```

**Using Minikube**

To access the HTML application running in Minikube, retrieve the Minikube IP address:











kubernetes
minikube start

docker build -t jashasmani/html . docker run -d -p 8081:80 jashasmani/html
docker login docker push jashasmani/html

how to run docker image as code in minikube using
imperitve ---- declaritve

kubectl run html-pod --image=jashasmani/html kubectl get pods

kubectl expose pod html-pod --type=NodePort --port=80 --name=html-service

kubectl get svc

minikube ip

```bash
minikube ip
```

Navigate to the IP address followed by the NodePort assigned to the HTML Service (e.g., `http://<minikube-ip>:30000`).
