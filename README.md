# springboot-helloworld-k8s-manifest

This project contains K8s manifest yaml files to deploy springboot-helloworld to Kubernetes. These files was applied to minikube as an example.
The springboot-helloworld image is found in docker hub https://hub.docker.com/r/foconer/springboot-helloworld. 

This was tested in MacOS Sequoia 15, Docker Desktop, minikube v1.38.0

Prerequisite (local deployment)

* Install Docker Desktop (29.1.5+) include the kubectl CLI
* Install minikube

Deployment Instruction
* Start docker and minikube, check with commands
  - docker container ls (check to see that minikube container is running)
  - kubectl get nodes (check that a nodes exists)
* Clone this repository
* Go to Terminal and run the following commands
  - kubectl apply -f deployment.yaml
  - kubectl apply -f service.yaml
* Check that pods and a service are created
  - kubectl get pods
  - kubectl get svc
* If using MacOS, a minikube tunnel is need to access the springboot-helloworld instance
  - minikube service springboot-service
  - Use the tunnel URL to access the application, generated URL example http://127.0.0.1:52883)
