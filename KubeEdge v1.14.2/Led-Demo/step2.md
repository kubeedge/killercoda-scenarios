Create the LED device model and device instance.

```
cd $GOPATH/src/github.com/kubeedge/examples/led-raspberrypi/crds
```
```
kubectl apply -f led-light-device-model.yaml
```
```
kubectl apply -f led-light-device-instance.yaml
```
Note: You need to modify led-light-device-instance.yaml: replace string litearl 'edge-node1' with your edge node name at spec.nodeSelector.nodeSelectorTerms.matchExpressions.values
<br>
Note: You can change the CRDs to match your requirement


 ### Update the name of the device (device instance name) created using the device CRD in the previous step along with the MQTT URL using which edge_core is running in the configuration file present at
 
 ```
 $GOPATH/src/github.com/kubeedge/examples/led-raspberrypi/configuration/config.yaml
 ```