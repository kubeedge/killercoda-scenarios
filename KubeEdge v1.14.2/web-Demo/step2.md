### Run KubeEdge Web App

The KubeEdge Web App runs in a VM on cloud.
It can be deployed using a Kubernetes deployment yaml.

```
 cd $GOPATH/src/github.com/kubeedge/examples/web-demo/kubeedge-web-app/deployments/
 kubectl create -f kubeedge-web-app.yaml
```