## clone the demo code

```
git clone https://github.com/kubeedge/examples.git
```

```
cd $GOPATH/src/github.com/kubeedge/examples/kubeedge-counter-demo
```
<br>
replace "<your edge node name>" with your edge node name
<br>

```
sed -i "s#edge-node#<your edge node name>#" crds/kubeedge-counter-instance.yaml
```

```
kubectl create -f crds/kubeedge-counter-model.yaml
kubectl create -f crds/kubeedge-counter-instance.yaml
```