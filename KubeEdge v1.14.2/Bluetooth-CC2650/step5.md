### Deploy the mapper by following the steps given below.

```
cd $GOPATH/src/github.com/kubeedge/kubeedge/mappers/bluetooth_mapper
```
#### Please enter the following details in the deployment.yaml :-
1. Replace <edge_node_name> with the name of your edge node at spec.template.spec.voluems.configMap.name <br>
2. Replace <your_dockerhub_username> with your dockerhub username at spec.template.spec.containers.image <br>

```
kubectl create -f deployment.yaml
```