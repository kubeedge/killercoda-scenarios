## Create the CC2650 SensorTag device model and device instance.

```
cd $GOPATH/src/github.com/kubeedge/examples/bluetooth-CC2650-demo/crds
kubectl apply -f CC2650-device-model.yaml
sed -i "s#edge-node#<your-edge-node-name>#g" CC2650-device-instance.yaml
kubectl apply -f CC2650-device-instance.yaml
```
