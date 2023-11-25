## Steps to run the demo

### Clone demo code

```
 git clone https://github.com/kubeedge/examples
```

### Create the device model and device instance for the speaker

With the Device CRD APIs now installed in the cluster,
we create the device model and instance for the speaker using the yaml files.

```
 cd $GOPATH/src/github.com/kubeedge/examples/web-demo/kubeedge-web-app/deployments/
```

```
 kubectl create -f kubeedge-speaker-model.yaml
 kubectl create -f kubeedge-speaker-instance.yaml
```