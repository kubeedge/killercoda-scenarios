### Create the temperature device model and device instance.

```
cd $GOPATH/src/github.com/kubeedge/examples/temperature-demo/crds
```

```
kubectl apply -f devicemodel.yaml
```

```
sed -i "s#edge-node#<your-edge-node-name>#g" instance.yaml
```

```
kubectl apply -f device.yaml
```