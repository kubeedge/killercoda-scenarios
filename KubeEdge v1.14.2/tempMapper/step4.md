### Deploy the temperature mapper.

```
cd $GOPATH/src/github.com/kubeedge/examples/temperature-demo/
```

Please enter the following details in the deployment.yaml :-
 1. Replace "edge-node" with the name of your edge node at spec.template.spec.nodeSelector.name
 2. Replace "kubeedge/temperature-mapper-demo:arm32" with your own image at spec.template.spec.containers.image

```
 kubectl create -f deployment.yaml
```