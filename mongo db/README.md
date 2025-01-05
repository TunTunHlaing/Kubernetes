
This repository provides YAML files and instructions to deploy MongoDB and Mongo-Express on a Kubernetes cluster using Minikube.

---

## Prerequisites

Before starting, ensure the following:

- **Minikube** is installed and running on your machine. Refer to the [Minikube installation guide](https://minikube.sigs.k8s.io/docs/start/) if needed.
- **kubectl** is installed and configured to communicate with your Minikube cluster.

---

## Deployment Steps

### <h2>1. Create a Secret</h2>

A Kubernetes Secret is used to securely store sensitive information like MongoDB credentials. Use the `mongo-secret.yml` file to create the required secret.

Run the following command:

```bash
kubectl apply -f mongo-secret.yml

### <h2>2. Create a ConfigMap</h2>

A Kubernetes configmap is used to store share env variables  like MongoDB server url. Use the `mongo-configmap.yml` file to create the required variables.

Run the following command:

```bash
kubectl apply -f mongo-configmap.yml


### <h2>3. Create a deployment for mongodb and mongo-express</h2>

And then create deployment 

Run the following command:

```bash
kubectl apply -f mongo.yml

```bash
kubectl apply -f mongo.-express.yml

And get the service details to find the NodePort by following command

minikube service {service name}

```bash
minikube service mongo-express-service

Finally you can test with the output url from above command 