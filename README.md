# Udagram Microservices

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The goals of this project:
 - Refactor monolith application to microservice.
 - Build CI pipeline for each microservice using Docker and Travic CI
 - Build CD pipeline for each microservice using AWS EKS.

Monolith vs Microservice architecture of the app:
- The monolith app consists of two parts:
  1. Frontend - Angular web application built with Ionic Framework
  2. Backend RESTful API - Node-Express application

- After refactoring to microservices, the app consists of four parts:
  1. Frontend service - Angular web application built with Ionic Framework
  2. Udagram feed api - node-express API for feed functionality of the app 
  3. Udagram user api - node-express API for user functionality of the app 
  2. Reverse proxy - to forward requests to appropriate service either feed service or user service
  ![structue of microservice app](./screenshots/microservice_app_structure.png)

## Tech Stack
 - Nodejs
 - Docker
 - Travis CI
 - Kubernets
 - AWS EKS
 - AWS S3
 - AWS RDS

## CI/CD Infrastructure
### DockerHub Repositories
The DockerHub repositories of the microservices can be found in the following link:
- https://hub.docker.com/repository/docker/mahmoudsharshar/udagram-reverseproxy
- https://hub.docker.com/repository/docker/mahmoudsharshar/udagram-frontend
- https://hub.docker.com/repository/docker/mahmoudsharshar/udagram-api-user
- https://hub.docker.com/repository/docker/mahmoudsharshar/udagram-api-feed
![DockerHub Repositories](./screenshots/docker_hub_registers.PNG)

### Travis CI Build
we used travis CI to track changes on github repo then build new images and push them to docker hub repositories.
The configuration of Travis CI can be found in .travis.yaml file
![Travis CI Build](./screenshots/travis_ci_build.PNG)
![Travis CI Build](./screenshots/travis_ci_build_history.PNG)

### Conitnuous Integration
[Useful Guide](https://blog.juadel.com/2020/05/15/create-a-kubernetes-cluster-in-amazon-eks-using-a-reverse-proxy/)

- `kubectl get nodes`

![kubectl get nodes](./screenshots/kubectl_nodes.PNG)

- `kubectl get pods`

![kubectl get pods](./screenshots/kubectl_pods.PNG)

- `kubectl describe services`
![screenshot 1](./screenshots/kubectle_sevices_1.PNG)
![screenshot 2](./screenshots/kubectle_sevices_3.PNG)
![screenshot 3](./screenshots/kubectle_sevices_3.PNG)

- `kubectl describe hpa`
![kubectl describe hpa](./screenshots/kubectl_hpa.PNG)

- `kubectl logs <your pod name>`
   - Feed service logs
   ![feed pod](./screenshots/feed_service_logs.PNG)
   - User service logs
   ![user pod](./screenshots/user_pod_logs.PNG)
   - Reverse proxy service logs
   ![reverseproxy](./screenshots/reverseproxy_pod_logs.PNG)
   - Frontend service logs
   ![Frontend logs](./screenshots/frontend_pod_logs.PNG)
