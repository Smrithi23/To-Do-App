# To-Do-App
This is a project that explores using Kubernetes and Docker for containerizing and deploying an application as part of the COMS 6998 Cloud Computing and Big Data course assignement.

## Aim of the Project
1. Containerizing the To-Do Application using Docker and push the image to Docker Hub.
2. Deploy the container on a local Kubernetes cluster using Minikube
3. Explore various Kubernetes features such as a replication controller, health monitoring, rolling updates, and alerting.
4. Use Prometheus and Alert Manager to send health alerts on Slack.

## Setup Instructions

1. Install Docker and Kubernetes

2. Create Docker Image for the Todo Flask Application
```bash
docker build -t <image_name>
```

3. View Docker image created
```bash
docker images
```

3. Push image to DockerHub
```bash
docker push <image_name>
```

4. Start Minikube
```bash
minikube start
```

5. Create todo flask app service on kubernetes
```bash
cd flask-app
kubectl apply -f kube
kubectl get service
minikube service <service_name> --url
```

6. Create prometheus service
```bash
cd ../prometheus
kubectl apply -f .
kubectl get service
minikube service <service_name> --url
```

7. Create alertmanager service
```bash
cd ../alertmanager
kubectl apply -f .
kubectl get service
minikube service <service_name> --url
```

8. Create kube-state-metrics service
```bash
cd ../kube-state-metrics
kubectl apply -f .
kubectl get service
minikube service <service_name> --url
```

## References
1. https://devopscube.com/setup-prometheus-monitoring-on-kubernetes/
2. https://grafana.com/blog/2020/02/25/step-by-step-guide-to-setting-up-prometheus-alertmanager-with-slack-pagerduty-and-gmail/