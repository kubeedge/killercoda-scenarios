### Run KubeEdge Web App

The KubeEdge Web App runs in a VM on cloud.

```
cd $GOPATH/src/github.com/kubeedge/examples/kubeedge-counter-demo/web-controller-app
make
make docker
```

```
cd $GOPATH/src/github.com/kubeedge/examples/kubeedge-counter-demo/crds
kubectl create -f kubeedge-web-controller-app.yaml
```

**Note: instance must be created after model and deleted before model.**