# Deploy Apps on edge nodes

This step helps to try out a sample application deployment.

Go to this path to see a sample deployment file.

`cd $GOPATH/src/github.com/kubeedge/kubeedge/build`{{execute HOST2}}

`ls`{{execute HOST2}}

Add a Node Selector in this deployment yaml if the application is to be scheduled on a particular edge node. If not ignore this step and apply the deployment.

```sh
kubectl apply -f deployment.yaml -s cloudhuburl:8080
```
Replace cloud hub url with ip of machine where cloud is running.

Any desired application can be deployed to the created edge nodes.

Use below command to check if the application is successfully deployed and running.

`kubectl get pods`{{execute}}

Execute above command until the application status is "Running".
