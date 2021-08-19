# simple-vuejs-helloworld

## Purpose

This project is for learning purposes. It was created to understand how vuejs works in a kubernetes environment.

## Description

A simple vuejs application that is capable of reading configuration at runtime from a configmap.

## How to use

### Build docker image in minikube context

```console
eval $(minikube docker-env)
docker build --rm -t vuejs-app:0.0.2 .
```

### Test image in minikube

```console
eval $(minikube docker-env)
kubectl apply -f minikube.yaml
kubectl port-forward svc/vuejs 8080:80
```

### Change config

```console
kubectl edit cm fe-config
# Now change the value of VUE_APP_ENV_envName "minikube-dev" to whatever value you want
```
