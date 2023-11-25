### create crds at cloud node:

```
cd crd
kubectl apply -f model.yaml
```
replace "<your edge node name>" with your edge node name

```
sed -i 's#raspberrypi#<your edge node name>#' instance.yaml
kubectl apply -f instance.yaml
```