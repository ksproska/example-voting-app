start-all:
	kubectl create -f redis-pod.yml
	kubectl create -f redis-service.yml
	kubectl create -f postgres-pod.yml
	kubectl create -f postgres-service.yml
	kubectl create -f result-app-pod.yml
	kubectl create -f result-app-service.yml
	kubectl create -f voting-app-pod.yml
	kubectl create -f voting-app-service.yml
	kubectl create -f worker-pod.yml

status:
	kubectl get all -o wide

show-UI-urls:
	minikube service result-service --url
	minikube service voting-service --url

delete-all:
	kubectl delete -f redis-service.yml
	kubectl delete -f redis-pod.yml
	kubectl delete -f postgres-service.yml
	kubectl delete -f postgres-pod.yml
	kubectl delete -f result-app-service.yml
	kubectl delete -f result-app-pod.yml
	kubectl delete -f voting-app-service.yml
	kubectl delete -f voting-app-pod.yml
	kubectl delete -f worker-pod.yml
