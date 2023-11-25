### Run KubeEdge WeChat App

The KubeEdge WeChat App runs in a VM on cloud and serve for WeChat.
It can be deployed using a Kubernetes deployment yaml.

```
cd $GOPATH/src/github.com/kubeedge/examples/wechat-demo/kubeedge-wechat-app/deployments/
kubectl create -f kubeedge-wechat-app.yaml
```
