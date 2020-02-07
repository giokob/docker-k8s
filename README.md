minikube start
eval $(minikube docker-env)
docker image build -f Dockerfile-api -t api .
docker image build -f Dockerfile-web -t web .

kubectl apply -f deploy/
minikube service web

kubectl delete all --all

----
kustomize