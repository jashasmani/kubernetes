# kubernetes


minikube start

 docker build -t jashasmani/html . 
 docker run -d -p 8081:80 jashasmani/html   
 docker login
 docker push jashasmani/html

 how to run docker image as code in minikube using  
 imperitve ----
 declaritve

 kubectl run html-pod --image=jashasmani/html
 kubectl get pods

 kubectl expose pod html-pod --type=NodePort --port=80 --name=html-service

 kubectl get svc

 minikube ip
