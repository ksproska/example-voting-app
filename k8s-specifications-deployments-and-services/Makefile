start-all:
	kubectl create -f redis-deploy.yml
	kubectl create -f redis-service.yml
	kubectl create -f postgres-deploy.yml
	kubectl create -f postgres-service.yml
	kubectl create -f result-app-deploy.yml
	kubectl create -f result-app-service.yml
	kubectl create -f voting-app-deploy.yml
	kubectl create -f voting-app-service.yml
	kubectl create -f worker-deploy.yml

status:
	kubectl get all -o wide

show-UI-urls:
	minikube service result-service --url
	minikube service voting-service --url

delete-all:
	kubectl delete -f redis-service.yml
	kubectl delete -f redis-deploy.yml
	kubectl delete -f postgres-service.yml
	kubectl delete -f postgres-deploy.yml
	kubectl delete -f result-app-service.yml
	kubectl delete -f result-app-deploy.yml
	kubectl delete -f voting-app-service.yml
	kubectl delete -f voting-app-deploy.yml
	kubectl delete -f worker-deploy.yml
