# Udagram Image Filtering Microservices

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. [The Simple Frontend](/udacity-c3-frontend)
A basic Ionic client web application which consumes the RestAPI Backend. 
2. [The RestAPI Feed Backend](/udacity-c3-restapi-feed), a Node-Express feed microservice.
3. [The RestAPI User Backend](/udacity-c3-restapi-user), a Node-Express user microservice.
4. [Deployment](/udacity-c3-deployment), a docker configuration and k8s configurations

## Getting Setup

### Prerequisite - Environment Variables:

```bash
export POSTGRESS_USERNAME=myusername;
export POSTGRESS_PASSWORD=mypassword;
export POSTGRESS_DB=postgres;
export POSTGRESS_HOST=udagramdemo.abc4def.us-east-2.rds.amazonaws.com;
export AWS_REGION=us-east-2;
export AWS_PROFILE=default;
export AWS_BUCKET=udagramdemo;
export JWT_SECRET=helloworld;
```

### Run the project using docker public images:
```bash
docker-compose -f docker-compose-build.yaml build --parallel
docker-compose up
```

### Go to the browser and run “http://localhost:8100/” to see our Udagram application up and running with two funcaitonalities: feed and user service. “Feed” service will allow the user to upload images and “user” service will allow a user to log-in or log-out from the system.

### Stop the project
```bash
docker-compose stop
docker-compose down
```

### Docker images are available at:
#### https://hub.docker.com/u/ivanrylov

### Deployment

## Deployment configuration located at k8s](/udacity-c3-deployment/k8s)

## In order to deploy project to the cloud use kubectl (https://github.com/kubermatic/kubeone)
```bash
kubectl apply -f backend-feed-deployment.yaml 

kubectl apply -f backend-user-deployment.yaml 

kubectl apply -f frontend-deployment.yaml 

kubectl apply -f reverseproxy-deployment.yaml

kubectl apply -f pod-example/pod.yaml
```

