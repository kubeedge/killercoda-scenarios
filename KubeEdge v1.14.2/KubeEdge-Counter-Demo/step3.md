### Run KubeEdge Pi Counter App

The KubeEdge Counter App run in raspi.

```
cd $GOPATH/src/github.com/kubeedge/examples/kubeedge-counter-demo/counter-mapper
make
make docker
```
```
cd $GOPATH/src/github.com/kubeedge/examples/kubeedge-counter-demo/crds
kubectl create -f kubeedge-pi-counter-app.yaml
```

The App will subscribe to the `$hw/events/device/counter/twin/update/document` topic, and when it receives the expected control command on the topic, it will turn on/off the counter, also it will fresh counter value and publish value to `$hw/events/device/counter/twin/update` topic, then the latest counter status will be sychronized between edge and cloud.

At last, user can get the counter status at cloud side.
