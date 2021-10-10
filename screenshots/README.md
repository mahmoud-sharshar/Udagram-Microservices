# Screenshots
To help review your infrastructure, please include the following screenshots in this directory::

## Deployment Pipeline
* DockerHub showing containers that you have pushed
![DockerHub Repositories](./docker_hub_registers.PNG)
* GitHub repository’s settings showing your Travis webhook (can be found in Settings - Webhook)
* Travis CI showing a successful build and deploy job
![Travis CI Build](./travis_ci_build.PNG)
![Travis CI Build](./travis_ci_build_history.PNG)

## Kubernetes
* To verify Kubernetes pods are deployed properly
```bash
kubectl get pods
```
![kubectl get pods](./kubectl_pods.PNG)

* To verify Kubernetes services are properly set up
```bash
kubectl describe services
```
![screenshot 1](./kubectle_sevices_1.PNG)
![screenshot 2](./kubectle_sevices_3.PNG)
![screenshot 3](./kubectle_sevices_3.PNG)
* To verify that you have horizontal scaling set against CPU usage
```bash
kubectl describe hpa
```
![kubectl describe hpa](./kubectl_hpa.PNG)

* To verify that you have set up logging with a backend application
```bash
kubectl logs {pod_name}
```
- Feed service logs
![feed pod](./feed_service_logs.PNG)
- User service logs

![user pod](./user_pod_logs.PNG)
- Reverse proxy service logs

![reverseproxy](./reverseproxy_pod_logs.PNG)
- Frontend service logs

![Frontend logs](./frontend_pod_logs.PNG)
