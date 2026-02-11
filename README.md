# springboot-helloworld-k8s-manifest

This project includes Kubernetes manifest YAML files for deploying springboot-helloworld to Kubernetes. The manifests were tested using Minikube as an example environment.
The Docker image springboot-helloworld is hosted on Docker Hub: https://hub.docker.com/r/foconer/springboot-helloworld

This project was tested on macOS Sequoia 15 using Docker Desktop and Minikube v1.38.0

Prerequisite (local deployment)

* Install Docker Desktop (29.1.5+) include the kubectl CLI
* Install minikube

Deployment Instruction
* Start Docker and Minikube, then verify using the following commands
  - docker container ls (check to see that minikube container is running)
  - kubectl get nodes (check that a nodes exists)
* Clone this repository
* Open a terminal and run the following commands
  - kubectl apply -f deployment.yaml
  - kubectl apply -f service.yaml
* Check that the pods and the service are successfully created
  - kubectl get pods
  - kubectl get svc
* On macOS, running minikube tunnel is required to access the springboot-app service
  - minikube service springboot-service
  - Use the tunnel URL to access the application, generated URL example http://127.0.0.1:52883)
