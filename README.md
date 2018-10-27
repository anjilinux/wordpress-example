# Kubernetes Wordpress example

This repository is a minimal example of getting started with a wordpress latest app on kubernetes. I will be putting up a blog post soon, but for now, I am expirementing with kubernetes and got success using these.

## How to run

1. Install [Kubernetes](https://kubernetes.io/docs/setup/)

2. Create Deployment

- `cd` into directory where you have cloned this repo.

- Create a deployment
```sh
/kubernetes-wordpress-example$ kubectl create -f resources/wp-deployment.yaml
```

- Check if deployment is running
```sh
/kubernetes-wordpress-example$ kubectl get deployments
```

You should be able to see `wp-deployment` in the list

3. Create Service

- Create a new service by running

```sh
/kubernetes-wordpress-example$ kubectl create -f resources/wp-service.yaml
```

You should be able to see `wp-app-lb` in the list


## Accessing wordpress

Once you have setup everything, you should be able to access it via the `url` of service. To obtain your service url, issue following command:

```sh
minikube service --url wp-app-lb
```

Open the link and you will be able to see wordpress installation page
