# k8s-app
Setup Kubernetes Cluster

Install Minikube

	brew update
	brew install hyperkit
	brew install minikube (also install kubectl & docker runtime)

Create & start Cluster

	minikube start -driver=hyperkit
	minikube start -driver=docker
    * In case of errors delete below folders
        C:\ProgramData\DockerDesktop\pki
        C:\Users\vsharm86\AppData\Local\Docker\pki

Get status of nodes

	kubectl get node
	kubectl get nodes
	
Get status of Minikube cluster components

	minikube status
	
Kubernetes Version

	kubectl version
	
Get Kubernetes data

	kubectl get all
	kubectl get pod
	kubectl get secret
	kubectl get configmap
	kubectl get service
	kubectl get deployment
	kubectl get replicaset
	
	kubectl get pod --watch
	kubectl get pod -n explore-the-web
	
	kubectl describe deployment webapp-deployment
	kubectl describe pod mongo-deployment-7875498c-k26mw
	
	kubectl apply -f mongo-config.yaml
	kubectl apply -f mongo-config.yaml --namespace=explore-the-web
	
	kubectl logs mongo-deployment-7875498c-k26mw
	kubectl logs mongo-deployment-6884bb855-hbpxk -f
	
	minikube ip
	kubectl get node -o wide
	kubectl get deployment webapp-deployment -o yaml
	
	kubectl edit deployment nginx-depl
	kubectl delete deployment mongo-deployment
	
	kubectl exec -it webapp-deployment-dcffd6bcc-sdkd9 -- //bin//sh
	
	echo -n 'testing' | base64
	echo -n 'c3RzE2' | base64 --decode
	
Port Forwarding / Tunneling

	minikube service webapp-service
	

	kubectl cluster-info
	
	kubectl create namespace explore-the-web
	
Ingress Controller

	minikube addons enable ingress
	kubectl get ingress -n kubernetes-dashboard
	
	kubectl describe ingress dashboard-ingress -n kubernetes-dashboard
    * wait for address to allocate, then map that ip address to ingress domain url in hosts file