# Screenshots
To help review your infrastructure, please include the following screenshots in this directory::

## Deployment Pipeline
* DockerHub showing containers that you have pushed
![DockerHub Repositories](./docker_hub_registers.png)
* GitHub repository’s settings showing your Travis webhook (can be found in Settings - Webhook)
* Travis CI showing a successful build and deploy job
![Travis CI Build](./travis_ci_build.png)
![Travis CI Build](./travis_ci_build_history.png)

## Kubernetes
* To verify Kubernetes pods are deployed properly
```bash
kubectl get pods
```
![kubectl get pods](./kubectl_pods.png)

* To verify Kubernetes services are properly set up
```bash
kubectl describe services
```
![screenshot 1](./kubectle_sevices_1.png)
![screenshot 2](./kubectle_sevices_3.png)
![screenshot 3](./kubectle_sevices_3.png)
* To verify that you have horizontal scaling set against CPU usage
```bash
kubectl describe hpa
```
![kubectl describe hpa](./kubectl_hpa.png)

* To verify that you have set up logging with a backend application
```bash
kubectl logs {pod_name}
```
- Feed service logs
![feed pod](./feed_service_logs.png)
- User service logs
![user pod](./user_pod_logs.png)
- Reverse proxy service logs
![reverseproxy](./reverseproxy_pod_logs.png)
- Frontend service logs
![Frontend logs](./frontend_pod_logs.png)
