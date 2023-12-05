## Deploy the light mapper.

```console
cd $GOPATH/src/github.com/kubeedge/examples/led-raspberrypi/
```

Please enter the following details in the deployment.yaml :-
1. Replace <edge_node_name> with the name of your edge node at spec.template.spec.voluems.configMap.name
2. Replace <your_dockerhub_username> with your dockerhub username at spec.template.spec.containers.image

```
kubectl create -f deployment.yaml
```



Change the device Twin attribute (expected value) "power-state" of the device to "ON" to turn on the light, and "OFF" to turn off the light using the device CRDs. The mapper will control the LED to match the state mentioned in the cloud and also report back the actual state of the light to the cloud after updating.

